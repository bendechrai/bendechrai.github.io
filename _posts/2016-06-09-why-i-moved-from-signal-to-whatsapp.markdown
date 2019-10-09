---
layout: post
title: "Why I Moved from Signal to WhatsApp"
Slug: why-i-moved-from-signal-to-whatsapp
date: 2016-06-09 06:58:28
tags: [Freedom,Open Source,Opinion,Privacy,Security]
---
Signal, created by [Whisper Systems](https://whispersystems.org/), allows you to send secure, encrypted messages to other Signal users, both text and voice.

It's probably one of the major contributors to making secure, encrypted, safe communication accessible to all. I recommend it to anyone, if you're not already encrypting your communications.

That said, I've recently dropped it in favour of [WhatsApp](https://www.whatsapp.com). I know, it's not open source, and for an open source advocate, this might seem a bit strange. I'd like to explain, and hopefully get your thoughts on the pros and cons.

### Open Source Rules. Especially for Encryption!

Open Source is the only way that encryption can truly work. If anyone has the ability to audit the code, everyone can infer greater assurance of its security. Closed source, proprietary software could have secret back-doors that will never see the light of day. _(Sure, open source can, and has been found to have back-doors, and there's no guarantee that someone will find them, but in closed source code, it's nigh-on impossible.)_

Open Source also provides you the ability to run the code yourself, in a way that gives you more comfort, convenience, and confidence. You can make changes to make it work better for you.

_(Sure, not all of us are developers, but open source allows you to get a developer to make these changes for you. It gives you control.)_

![F-Droid Logo](https://bendechrai.com/wp-content/uploads/2016/06/fdroidnewheader-300x79.png)Open Source allows you to install software in a way that's right for you. Google Play? Sure, there it is. Don't want to connect to Google's proprietary systems? Why not use alternative app stores like [F-Droid](https://f-droid.org/)?

### Open Source Contradictions

I first became wary of Whisper Systems when they <del>demanded</del> requested that F-Droid remove Signal (then TextSecure) from their repository. The software they had released under an open source licence was being made inaccessible to anyone not using Google Play.

>[![](https://bendechrai.com/wp-content/uploads/2016/06/Selection_999302-150x150.png)](https://bendechrai.com/wp-content/uploads/2016/06/Selection_999302.png)However, the author ... asked for the application to be removed from our repository as he wants to distribute it via Google Play only. – [F-Droid posts, "Security Notice – TextSecure"](https://f-droid.org/posts/security-notice-textsecure/)

More recently, I have learned that they're creating a locked-in infrastructure for those who wish to use the software. You see, it's possible for you to run your own Signal server, and the software is designed to work in a distributed manner, so that all Signal servers can work with each other. This allows your messages to get to the recipient, no matter which server they use.

Whisper Systems have no intention to ever allow your server to connect with theirs, and given theirs is the de-facto server that all people use, that's effectively creating lock-in. They are removing one of the freedoms that Open Source offers.

The reason they give for this? They cannot be sure that the software you're running is up-to-date. They don't control the full infrastructure, so can't trust it.

I sympathise with this, I do. Software development is hard. Distributed systems are harder. Distributed systems that are controlled by different people can be a real headache. And when security and encryption are added to the mix, it requires a good strategy to make it work, but it can be done.

### "That's all very well, Ben, but I don't want to run my own server."

True. For most people that's true. Most people don't want to run their own email servers either, but can you imagine if Google turned round and decided to only route emails to and from other Gmail users? There are many reasons that someone might want to run their own server though, and it seems disingenuous to create software that's capable of being distributed and open, and then locking that option out at a policy level.

### "What are some examples of why someone would want to run their own server?"

Great question. I'm glad you asked! Whisper Systems made a decision some time ago to use Google Cloud Messaging for communication between their servers and the app running on your phone. This necessitates the use of Google's proprietary platform.

If you didn't want to have to connect to Google simply to send and receive text messages and phone calls, you could use a version of Signal server that uses a different messaging protocol.

If you worked for an organisation with highly compartmentalised communications protocols (defense, intelligence, security, law), you might want to run your own Signal server for all your staff, and have a gateway that only allows messages to and from external Signal users under certain circumstances.

What if you simply wanted to run your own server. There are plenty of people running their own email servers, web servers, file servers. They could use Gmail, AWS, Dropbox.

### How does WhatsApp compare to Signal?

They both encrypt traffic end-to-end. That is, it's encrypted on your device, and decrypted on the recipient's. No one in between, not even Signal or WhatsApp, can read it. We can't read the WhatsApp code, though, to make sure that it doesn't do anything it's not supposed to.

They both control the full server infrastructure for all users, you're locked in to their infrastructure.

However, WhatsApp works without connecting your Android device to Google. You can download the app from their website directly, and communicate with others without Google Cloud Messaging.

### So, which should I use?

The decision for me to move from Signal is two-fold. Firstly, I don't want my phone connected to Google's infrastructure, so I can't install Signal, nor communicate with others. Secondly, the open source advocate in me dislikes the way they have interacted with the open source community. WhatsApp, on the other hand, is closed source, and has never pretended to be otherwise. While I cannot verify the security of the communications, my research in to the app before I started using it a week ago gave me a degree of blind comfort.

I also hope like hell, because it's so popular, that there are [people trying to break it](https://www.praetorian.com/blog/whats-up-with-whatsapps-security-facebook-ssl-vulnerabilities) and alerting the developers to the issue. Is seems that, once aware of an issue, they're quick to fix things.

Ideally, I'd like an open source option that doesn't impinge on users' freedoms through policy or otherwise. I'd like an option that doesn't require me to opt-in to a proprietary framework for it to operate. And I'd like my non-technical family and friends to be able to set it up easily. At the moment, I don't believe anything exists that meets these ideals.

So, while Signal is more accountably secure (you can read the source code), WhatsApp doesn't make you dependent on third-party infrastructure, and is actually available to all users.

What do you think?

- - - - - -

**Update, 18th August:** Added quote and reference to the request for removal of TextSecure from F-Droid's, in order to address a [request from Moxie to quote the source](https://twitter.com/moxie/status/766142286619025409).

- - - - - -

**Update, 18th August****:** Clarified the ideals of the system I'd like, to be easy to use by non-technical users.

- - - - - -

**Update, 19th August:** Moxie disagrees that a demand was made, so I've downgraded the wording to a request.
