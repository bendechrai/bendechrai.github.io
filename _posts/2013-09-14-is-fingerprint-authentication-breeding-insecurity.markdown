---
layout: post
title: "Is Fingerprint Authentication Breeding Insecurity?"
Slug: is-fingerprint-authentication-breeding-insecurity
date: 2013-09-14 03:54:47
tags: [Data Sovereignty,Privacy,Security,Technology]
---
![iphone5s](https://bendechrai.com/wp-content/uploads/2013/09/iphone5s.png)The latest iPhones have just been released, and the latest feature, available in the iPhone5S, is the fingerprint scanner. This funky bit of technology allows you to program your fingerprint in to the phone, and then unlock it with a touch. No more remembering security codes. Apple say the fingerprint will be securely stored on the phone, but I'm not sure as yet whether a they store enough data to simply verify your fingerprint later, or enough to reproduce your fingerprint. They do, however, add that it will only be stored on the phone, not sent to Apple or stored in "the cloud".

So, should you be concerned about the security implications of giving your fingerprint to your phone?

You guessed it; I say yes. I'd be very concerned. Let me give a few reasons.

## What is trust?

In order to have trust in any system, you must trust all components. Let's discuss some systems that you might trust now:
## Storing passwords on sticky notes

Some security experts say this is a great way to ensure your passwords are safe. Here are the components of the system: - Neither the manufacturer of the pen, nor that of the paper, are able to see your password;
- You need physical access to them to use them, so the number of people who will ever see these notes is relatively small (about 3 people in your home, 20 people in your office) compared with the online world;
- Of the people who can access the passwords, a significantly lower percentage will have malicious intent towards you (i.e. you inherit your trust of the people to augment the trust of the system); and
- It is relatively hard to duplicate, having to manually copy and "paste" or photocopy the paper.

The passwords are insecure in cryptographic terms, but the risk of this is mitigated by the low risk of access to them by an unauthorised party. Note, you could use some form of manual encryption or encoding when you write them down to reduce this risk even further. _Who you have to trust:_ people with physical access to your sticky notes.

## Storing the passwords in a text file on your computer

Let's build on the assumptions of the previous example. - Passwords just became easier to duplicate - the file could be copied on to a USB stick, emailed to someone, or copied and pasted in to a web form;
- Anyone with access to your computer can see the files - this could be family/office members, and also anyone who has remote access through official means such as company IT staff maintenance access, or nefarious means such as trojans applications; and
- Anyone with access to any backups that might be made of your computer can see previous versions of the file.

The reason you might still choose to store your passwords in a text file is that it becomes easier to copy and paste the passwords in to applications and web page login forms. _Who you have to trust:_ people with physical access to your computer; people with remote access to your computer; people with the rights to install other software on your computer; and people who write security software to stop trojan applications getting on to your computer.

Wow - that jumped up quickly!

## Storing the password in a text file on a shared drive or cloud synchronised folder

By synchronising your file of passwords with other machines, you get the benefit of having new and changed passwords replicate to other computers you might use, or might share with others. This use case also includes the use of tools like Google Docs and Wikis for sharing this information between multiple computers. _Who you have to trust:_ people with physical access to your computer; people with remote access to your computer; people with the rights to install other software on your computer; people who write security software to stop trojan applications getting on to your computer; people who manage the web servers or file servers of the remote storage systems; people who manage the security of the remote storage systems to stop attackers getting in to their systems; and the security policies of the company that run the remote storage systems that ensure that only those employees who should have access, do.

Jeebers!

Just as an aside, I just read an article entitled [Dropbox…opening my docs?](http://www.wncinfosec.com/dropbox-opening-my-docs/), which shows that certain files are opened after being uploaded to Dropbox. The reason is currently unknown, but the fact that they can, and do, should be a great concern.

## So what about the iPhone5S?

Now that we've covered a few examples of the chain of trust that must be maintained in order to ensure the privacy and security of your passwords, let's look at the iPhone5S's fingerprint scanning technology. When you program your fingerprint in to the phone, the sensor detects your fingerprint; and software on the phone analyses the print and stores it locally on the phone. While Apple confirm they encrypt the data on the phone, there's not information on how much of the fingerprint data they retain. Remember, also, that anything that's been encrypted by the phone can also be decrypted by the phone.

## Why shouldn't the iPhone store the whole fingerprint?

Consider this analogy; when you sign up for a new phone plan, you need to provide enough information to prove who you are; perhaps your drivers license number and date of birth. Next time you call, they'll ask you for one of those to confirm your identity with enough certainty for their purposes. Imagine if you needed to provide your phone company a DNA sample - they could then ask you for another DNA sample next time you call (just pretend phones have built-in DNA samplers now too) to verify who you are. They could, conceivably, also clone you.

In the same way, the phone doesn't need to remember your whole fingerprint in fine detail; only enough information to confirm it's the same one next time it scans your finger.

## Who can access the fingerprint?

iPhone app developers won't have access to this information, according to reports. In theory, only the core phone software can access it. For now.

The issue is that it's all software based, so whatever is currently the case, changes can be made remotely simply by Apple pushing through an over-the-air live update of your software. The software could be changed to ensure full print detail is captured, stored, and sent to a remote server, all without your consent or knowledge.

So, now let's look at a list of people or organisations involved in the chain of trust for the iPhone's fingerprint authentication to be trustworthy:

- people with physical access to your phone - it won't be long before someone works out how to get the data off the phone, and not much longer for it to be decoded;
- the developers at Apple who write the security software for the phone to stop others breaking in remotely;
- the developers at Apple now to add backdoors to this functionality;
- the lawyers at Apple who determine how to respond to security agency requests; and
- security agencies, such as the NSA, GCHQ, ASIO, etc, who may compel Apple to push over-the-air updates in order to alter the fingerprint software.

Look, it's true, the likelihood of **you** being the target of this is slim, but consider this. Is it easier for Apple to help the NSA track someone down by fingerprint by pushing a single update to all phones, or just selected phones? Is it easier for Apple to send a software update that looks for a particular fingerprint match to the phone, or just collect all fingerprints centrally and process them there? You might not be the target, but we'd all be collateral damage. So, if your phone is ever updated to send full details to a remote location, you will then also have to trust the hosting provider of that data to ensure no unauthorised people can now access this treasure trove of fingerprint data. This information could be very valuable, and being in one place will make it a target greater than any individual phone.

Remember also that security folk need to stop every single attack, attackers only need to succeed once.

## But the government already has my fingerprint

Have you ever gone through border control and had your fingerprint scanned? Sure, various governments may have your fingerprint already, and here's what they know about that fingerprint: - it belongs to you;
- you have a password from country X with passport number Y; and
- you have arrived and departed the country on known dates.

If you have more interaction with that government, for instance if it's your own government, they might also have information such as your employer's details, your income, social security details, home address, credit file. That's a lot of inforamtion they can collate and associate with a fingerprint, and I've only just scratched the surface. If your phone also has your fingerprint, then not only is your phone is associated with all that information, everything on the phone is now indesputably yours, and can add to the growing mound of data that can be used to profile you further. It's how this authentication mechanism links the data to your personal identity that's of concern.

Oh, and why would you use a "password" to unlock your phone that someone else knows? If others have your fingerprint already, isn't that a really bad thing to use to authenticate yourself?

## How secure are fingerprints?

This, for me, is the crux of it. Good password management states you are better protected if you have a complex password that no-one knows, and use a different password for every system. Fingerprints are complex passwords that some people already know, and never changes. This means, if someone discovers or appropriates your fingerprint once, they can then access any system you already use your fingerprint with. Even if you discover your fingerprint has been compromised, you can't change it, like you would a password. Fingerprint authentication isn't new; some laptops have had them for years, but the fact that Apple are bringing fingerprint technology to the masses is a little concerning. Given the security issues of using fingerprints instead of passwords, and the privacy concerns of storing your fingerprint on a device you probably can't fully trust, that Apple are making the technology so available without adequate and transparent education of the implications may backfire on the security industry at large.

You see, that hardest aspect of security to control is the user. This is why some systems check your password for complexity. If you suddenly start trusting fingerprints as the best new thing in security, and don't think twice about giving it away, society may become less secure as a consequence. Not only are we assuming fingerprints are by themselves, a good security measure, we're also giving it to everyone, reducing its secrecy.

## Multi Factor Authentication

The hot topic in security for many: two-factor authentication. These systems require two forms of authentication to let you in. Generally, there are three ways to identify someone: 1. Something you know (a password, PIN, or pass phrase)
2. Something you have (a keyring, or swipe card)
3. Something you are (biometric data such as your thumbprint, or retina scan)

Banks give you a keyring and you enter a number plus your password. Giigle sends you an SMS to complete the log in mechanism. These are both examples of something you know, and something you have. Smart phones can also act as a something-you-have through the use of authenticator apps used for logging in to Dropbox, Google, and even some banks. There has been [discussion about how the iPhone5S could now be used for high security authentication](http://www.macworld.com/article/2048514/the-iphone-5s-fingerprint-reader-what-you-need-to-know.html); two-factor authentication in one, as you'd have to unlock your iPhone with your fingerprint before you can run the app. There's a theoretical problem with this suggestion though. If someone else has your phone, and they get past the fingerprint scanner, the authenticator app provides no additional protection, so it's no better than single-factor.

## Convenience

And here it is; the selling point. Many people don't bother with swipe codes, PINs or pass phrases to unlock their phones. Fingerprint authentication will be better than no passcode at all, no? And it so much easier to use, so you might as well, no? Let me be blunt on my thoughts on this point. By all means, choose convenience over security and privacy, that's your choice, and it may well be right for you. Consider, though, that once you share any data with any device, system, organisation or person, your trust in the privacy of that data diminishes irrevocably; you can never take that action back.
