---
layout: post
title: "Secure Instant Messenger from the ground up"
Slug: secure-instant-messenger-from-the-ground-up
date: 2006-07-06 01:14:16
tags: [Open Source,Security]
---
> CSpace provides a platform for secure, decentralized, user-to-user communication over the internet.

Users are simply identified by their 2048-bit RSA keys. Peer-to-peer means you send messages directly to the recipient, not via a central server. Messages are encrypted at your end and decrypted at their end - they are never handled in plain text anywhere else. Compare this with traditional instant messenger clients that use a central server to relay messages.

I wonder if this is any more secure than using PSI's ability to use PGP keys for encrypting messages. Although it sends messages via a central server, the message is still encrypted with your public key, sent via the central server (still encrypted) and delivered to the recipient, who then decrypts it with their public key. Unless PSI covertly encrypts the message with an additional public key so someone else can decrypt it, I don't see how this is any less secure than CSpace's peer-to-peer model.

[CSpace](http://cspace.in/) via [Digg](http://digg.com/software/World_s_Most_Secure_Instant_Messenger_is_here_%21%21)
