---
layout: post
title: "Free SSL Certificates!"
Slug: free-ssl-certificates
date: 2006-03-28 01:57:35
categories: [Hosting,Uncategorized,Work Life]
---
A friend asked me today where he can get free SSL certs, as he'd heard me mention this before. [CAcert](http://cacert.org/) offer this service, but before you get all security conscious:

- The use a web-of-trust system of assurance to make sure people are who they say they are
- You need to be assured by at least 2 highly trusted assureres to create a server certificate
- They [protect their root certificate](http://www.cacert.org/help.php?id=7) (in my opinion) very well

That's just a short list of why they are trust-worthy. Check out their site, [help page](http://www.cacert.org/help.php) and [wiki](http://wiki.cacert.org/) for more info.

And don't forget to [install their root certificate](http://www.cacert.org/index.php?id=3) in your browsers and mail clients. And when I say browsers and mail clients, read also: instant messaging applications, operating systems, in fact anything that might use SSL.

Finally, why not support the inclusion of their root certificate by default?

These do:

- FreeBSD
- Nokia 770
- Knoppix
- Debian
- Gentoo
- MirBSD
- CentOS
- Wildfire

These will soon:

- Grml 0.5
- Mozilla
- Fedora

Your app not listed? Ask the developers to include it!
