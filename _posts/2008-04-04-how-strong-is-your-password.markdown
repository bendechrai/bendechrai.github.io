---
layout: post
title: "How strong is your password?"
Slug: how-strong-is-your-password
date: 2008-04-04 06:37:59
categories: [Security]
---
The [Password Strength Checker](http://www.passwordmeter.com/) uses a number of metrics to determine how strong a given password is, including the number of characters in total, uppercase and lower case letters, numbers and symbols. It also deducts points in the event you have numbers only, repeated characters, consecutive same-case letters, sequential letters or numbers.

Having played around with it a bit, it's great for telling if a given password is strong, but don't worry too much if it tells you its weak.

Take, for example, the password **Ad%U,1q3b**. This string was chosen because it causes the report to give exceptional ratings for all positively scoring criteria and a pass for all deductions, resulting in a password of "Very Strong" complexity with a 100% score.

Now take the password **Ad%U,1q3bbbb**. It receives a "Very Weak" complexity with a 0% score.

I'm not a statistician, but I'm pretty sure the longer password has a lower probability of being found. Am I wrong? That said, it's still a great tool, and perhaps I need to upgrade my rudimentary [in-line password strength checker](https://bendechrai.com/tools/password-analyser/)!
