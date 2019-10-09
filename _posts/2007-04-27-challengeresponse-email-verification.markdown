---
layout: post
title: "Challenge/Response Email Verification"
Slug: challengeresponse-email-verification
date: 2007-04-27 03:22:46
tags: [Hosting,Security,Uncategorized,Work Life]
---
Challenge/Response email verification (CREV) is a mechanism for reducing the amount of spam you get. It works like this:

- **Alice sends** Bob an email,
- Bob uses a CREV system, and this is the first email he's received from Alice,
- The CREV system holds the email and sends an email to Alice asking her to reply or follow a link to verify she is a real person before the email can be released and sent to Bob,
- **Alice replies or follows the link**,
- The CREV system adds Alice to a white-list (so she won't be asked to verify herself again) and releases the email for delivery to Bob,
- Bob receives the email.

Compare this with normal email systems: - **Alice sends** Bob an email,
- Bob receives the email.

Looking at it this way, you might think "Cool! So much less spam! And Alice only has one extra step to allow her email to get trough". Well, consider my way:

- **Alice sends** Bob an email,
- Bob's mail server noticed this is the first email he's received from Alice,
- Bob's mail server tells Alice's mail server it's currently busy, and could the email be sent again in 5 minutes (this is referred to as grey-listing),
- Alice's mail server holds onto the email and resends 5 minutes later,
- Bob's mail server accepts her email on the second attempt - any subsequent emails from Alice to Bob will be immediately accepted in future,
- Bob receives the email.

This method doesn't require any extra work on Alice's behalf, and when implemented in conjunction with other anti-spam mechanisms (such as checking sending mail servers against black lists, which I didn't include in my flow because this can also be used with CREV systems) cuts down spam enormously. For example, I got 1 spam email yesterday. You might argue that CREV systems would cut that down to zero spam, but this is not the case. CREV will only allow emails to a user from a given email address. If you receive a spam that appears to come from a white-listed address, it will still get through. This is more likely than you might expect, as many spam and virus-laden emails are sent through spyware applications that email users in the infected person's address book, which means they come from someone you know. Neither grey-listing nor CREV systems will stop this type of spam.

So what's wrong with CREV systems? In my opinion, it's a poor implementation due to the challenge/response requirement that the sender must take action to ensure the email gets through. Imagine a scenario: you're at the airport, your flight is about to leave. You have to email a document to a client that you haven't emailed before, and they require it by close of business that day. You hit send, you shut down your laptop and board for a 16 hours flight, only to get to the end and find the challenge response email. Your email has not been delivered, and the client will not get the document they required until the next business day.

With my implementation, you hit send, you shut down your laptop and board the plane. Your email reaches their server, and they pretend to be busy. Your email is resent automatically by your mail server 5 minutes later. The client gets the document 5 minutes after you sent it. All's well.

**Update**

I thought I should explain more about why grey-listing works. In the example above, Bob's mail server correctly retries to send the email to Alice after the 5 minute period. If Sam the spammer sends Bob (or Alice) an email, his mail server will likely ignore the request to resend in 5 minutes. All Sam wants to do is pump out as many emails as possible before his mail server is black-listed. As the email is never resent, it never gets delivered.

And purely for interests sake, here are some other checks my mail servers perform after the grey-listing process before allowing email through:

- Check the remote mail server communicates using the correct protocol,
- Check the remote mail server is not black-listed,
- Check the email address of the sender is valid,
- This checks that the sender's mail server will accept email to this address, not just that the address is correctly formed
- Check the sender's computer or gateway is not black-listed
- Check email isn't identified as spam using a bayesian spam filter

If these checks pass, the email gets delivered.
