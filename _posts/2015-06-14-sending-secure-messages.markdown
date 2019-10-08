---
layout: post
title: "Sending Secure Messages"
Slug: sending-secure-messages
date: 2015-06-14 01:41:34
categories: [Uncategorized]
---
For some time, I've had a system that allows people to send encrypted messages via a web browser. It's a slightly modified ZeroBin installation, which is a proven and independently audited, open source platform. Here's a quick primer on how to use it.

Head to https://paste.priva.si/. For security reasons, I recommend you type that address, including the https part, manually, and completely. If you don't, there is a small chance that you will end up on a different server without knowing it.

Once there, you'll see the following:

[![ZeroBin entry screen](https://bendechrai.com/wp-content/uploads/2015/06/Selection_357-1024x286.png)](https://bendechrai.com/wp-content/uploads/2015/06/Selection_357.png)

By default, messages are set to "Burn after reading". This feature means that, once read, the message can never be read again. This is a great way of ensuring that only the intended recipient gets the message. See my notes on this below though.

Paste your message in to the large text area, and click the **Send** button. You'll see a popup that looks like this:

[![ZeroBin URL result](https://bendechrai.com/wp-content/uploads/2015/06/Selection_358.png)](https://bendechrai.com/wp-content/uploads/2015/06/Selection_358.png)

Copy this URL, and send it to the intended recipient of the message. They will then load the URL up in their browser:

[![ZeroBin URL load](https://bendechrai.com/wp-content/uploads/2015/06/Selection_359.png)](https://bendechrai.com/wp-content/uploads/2015/06/Selection_359.png)

And be able to read the message:

[![ZeroBin read message](https://bendechrai.com/wp-content/uploads/2015/06/Selection_360-1024x269.png)](https://bendechrai.com/wp-content/uploads/2015/06/Selection_360.png)

## Notes on Burn After Reading

Burn after reading mode is great. Once the intended recipient has read the message, the server deletes the encrypted version, so no-one else can read it. This also has the advantage that it alerts the intended recipient if it's been read before they got to it, by way of telling them the message can't be found. This allows them to let you know, and you can reset any passwords or take other appropriate action in light of the fact that an unauthorised person has your data.

[![ZeroBin message not found](https://bendechrai.com/wp-content/uploads/2015/06/Selection_361.png)](https://bendechrai.com/wp-content/uploads/2015/06/Selection_361.png)

## Burn After Reading Problems

Depending on how you're sending the link to the encrypted message, Burn After Reading might be initiated by an automated system. Email anti-virus, Google Mail's content analysis, even previews in something like Facebook's private messaging, could cause the content to be marked as read. If this happens, there are two options. The easiest is to disable Burn After Reading, at the risk of losing the security benefit this offers. The second is to change the link before sending it.

For example, if your encrypted content link is:

`<pre class="lang:default decode:true">https://paste.priva.si/?bb36dccaea3ffe1d#h2INriTK5aYnHYJooDe4NDPI3Yp/f7bc5ylBgdTNnoE=`you could instead send `<pre class="lang:default decode:true">https://paste.pri[REMOVE]va.si/?bb36dccaea3ffe1d#h2INriTK5aYnHYJooDe4NDPI3Yp/f7bc5ylBgdTNnoE=`and advise the recipient to remove the \[REMOVE\] portion. This would invalidate the URL while being sent, and stop automated systems from loading it.
## Possible Interception

It's possible for someone to intercept the link as you send it to the intended recipient. If this happens, they have all the information needed to read the message. If it's imperative that no-one else ever reads this message, then perhaps this isn't the right solution for this situation. Consider using something like [GnuPG](https://gnupg.org/) to encrypt the message. This is more complicated, but also more secure. If you need absolute assurance that the recipient is the only person to get the message, a face-to-face meeting can never be beaten.

I hope you find this service useful, and encourage you to use it for sending sensitive information, such as access details and passwords, rather than sending them insecurely. I'd love to hear your feedback and suggestions on the service.
