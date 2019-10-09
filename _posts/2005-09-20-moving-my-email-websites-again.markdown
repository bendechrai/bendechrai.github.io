---
layout: post
title: " Moving my email & websites again!"
Slug: moving-my-email-websites-again
date: 2005-09-20 01:14:04
tags: [Hosting,Random,Uncategorized]
---
It seems this is becoming a bit of a hobby of mine. No sooner has my email account settled, and along I come and decide to move it all to another place...

Now this whole process is getting a little bit easier. You see, all my wife's and my email sits on an internal mail server. This allows me to get to that all important email from my god-daughter's sister's nanny's post man from 3 years ago that I thought I'd lost - even when the ADSL line goes down. It also means that I don't have 100Mb of mail to transfer every time I move email host - it's all on the internal server.

Down side is I'm on a dynamic IP, and while this doesn't present a problem for hosting web sites (use [dyndns.org](http://dyndns.org/) and create a CNAME record to that address for any other domain, for example) MX records don't like pointing to CNAME records. In layman's terms, you can't direct email to a dynamic IP - easily.

So I host my email on an external server, and poll it regularly. Personally I go for once a minute. Every minute, my internal mail server check the external "official" mail server if there's any new email, and if so, sucks it down.

Now that's all grand, and I can get to my mail internally, but now I can't get to it from anywhere else. Or can I? I've simply routed port 943 (IMAP over SSL) from the router to this machine, so I can connect from anywhere (net-enabled) in the world. Just need an IMAP client. And if all else fails, I can even use [web2mail.com](http://www.mail2web.com/).

So there we have it. Easily movable email, and yet it's always in the same place. Now I just have to perfect that backup system and ... oh yeah - reason for post: I'm moving my email to another server, so bear with me if it goes down temporarily...

Now as for my web site - well you now know that this exists. I'm still planning on moving my photo albums back internally and will let you all know when it's moved.

Time for bed.

Benji
