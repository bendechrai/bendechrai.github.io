---
layout: post
title: "Never trust your users!"
Slug: never-trust-your-users
date: 2008-08-27 03:34:25
categories: [Security,Work Life]
---
Time and again I see people do stupid stuff on the web. I'm talking about the developers. There's this big fat rule in the world of web development: never trust your users to do the right thing.

This could mean asking the user if they're sure that the want to delete an appointment from their calendar, checking a provided email address is valid or prompting them to save changes before moving to another page.

These examples are quite trivial though - hopefully nothing super bad will happen if these checks aren't performed. When it comes to money, however, you really want to make sure you're double checking everything.

I had a rather interesting encounter with a stupid system that processes tons of financial transactions every day (I assume). It's an online payment system for a number of Australian services: you can pay your car registration fees, building permit fees, council rates and parking infringement fines, to name a few.

Here's the first screen:

[![](/wp-content/uploads/2008/08/page1-300x184.png "Page 1")](https://bendechrai.com/wp-content/uploads/2008/08/page1.png)

And here's the payment confirmation page:

[![](/wp-content/uploads/2008/08/page2-300x184.png "Page 2")](https://bendechrai.com/wp-content/uploads/2008/08/page2.png)

It seems that changing the contents of the price field in the first page alters the final payment amount!

Why the developers thought this was a good idea is beyond me. When dealing with money, or any information for that matter, you should always check the values match what is expected. In this situation, I expected one of two results:

1. The payment page recalculated the payment amount and charged that amount, rather than the amount sent from the browser, or
2. The payment page tells the user that the payment amount does not match the bill amount and prompts the user to start the payment process again.

**Update**: [ZenPsycho](http://bustingseams.blogspot.com/) just suggested the system might intentionally allow users to pay more or less than the required amount. This is a valid point, and perhaps some of the billing system's clients might like to offer this. I forgot to mention though that the form element for the amount included "readonly" and "disabled" attributes, so if the client chooses not to allow the user to change the values, the system really should enforce the payment amount. At the very least it should warn me that I'm about to pay less than the current amount and ask me to confirm.
