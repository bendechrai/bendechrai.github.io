---
layout: post
title: "Banks going Biometric"
Slug: banks-going-biometric
date: 2012-10-05 13:57:56
tags: [Data Sovereignty,Personal,Privacy,Security,Uncategorized]
---
Identity is usually verified by checking one or more of three pieces of information:

- something you know,
- something you have,
- something you are.

To access Facebook or Twitter, you need you password (something you know). To get money out of a cash machine you need your bank card (something you have) and a PIN (something you know). To get through passport control, you need your passport (something you have) and your face (something you are). Most high security systems use three factor authentication, meaning you need to provide one of each three information types, and banks are looking to follow suit. In fact, they've been looking in to this for years:

- [NAB launches voice biometrics to improve security and customer experience](https://www.nab.com.au/wps/wcm/connect/nab/nab/home/About_Us/8/5/14/16/) - Australia, 2009
- [Biometrics becoming the norm for Aussie banking](http://www.itnews.com.au/News/161731,biometrics-becoming-the-norm-for-aussie-banking.aspx) - Australia, November 2009
- [Automatic teller machines will identify users by their palm prints](http://tenbreakfast.com.au/japan-s-biometric-banking-boom.htm) - Japan, April 2012
- [An eye for a buy: bank looks to retina and fingerprint technology](http://www.watoday.com.au/it-pro/business-it/an-eye-for-a-buy-bank-looks-to-retina-and-fingerprint-technology-20121004-2729v.html) - Australia, October 2012

I haven't looked for any articles for 2010 or 2011, but the initial search engine results indicate, correctly or not, that most of the investigation happened three years ago and banks are starting to implement now. For some time now, banks have moved on to two-factor authentication for online banking; your username and password (things you know) and a number generating key fob (something you have).

With the desire to increase security and reduce identity theft and related fraud, banks are, quite rightly, implementing the third factor - something you are - by scanning your thumb, palm or eye at the ATM.

## Securing You

As you might know, I'm a staunch advocate of owning your own data, and I wonder how banks will be storing the biometric data about me. Now, I _presume_ that banks will record my retina scan or thumb print on central bank computers for verification, and if that's the case, I have major issues. You see, my biometric data is me, it's a recipe for who I am. My password, PIN, ATM card and passport are all bits of information that I know or I have. I can change them. I can change my password and PIN. I can get a new ATM card and passport.

I can't change my thumb print or retina scan, short of applying sandpaper, which would be uncomfortable in the first instance and life changing in the second.

I've been thinking about the technical feasibility of this tonight. The banks will likely say that they need to store your biometric data so they can trust the data hasn't been tampered with. Storing biometric data on your ATM or a separate card, means that data could be changed.

Well, the good news is there are existing technologies that make this fairly trivial.

As a minor segue, I was looking at the [GPG/OpenPGP cards](http://www.gnupg.org/howtos/card-howto/en/smartcard-howto.html) today. They allow you to store your GnuPG keys (keys used for secure encryption) on portable storage cards. They cost about $15 each; about the same price as one of those number generating key fobs.

Now, let's take one of those cards, and instead of storing your encryption keys on them, you store your biometric data on them. I might write an article on encryption one day, but for now if you want to know, view this video of [how public private key encryption works](https://www.youtube.com/watch?v=3QnD2c4Xovk). The first half is a great visualisation for non-technical folk.

So, if I go in to my bank and get one of these cards, they can then photograph me and take my fingerprint and digitise the data. They then sign this data with their public key, and encrypt it with mine. Now, I'm the only person who can unlock this data, but they can verify that they've signed the data.

Note, ANZ currently store my PIN only on my ATM card, so this trust mechanism is already a solved problem for them.

Next time I want to get cash out, I put my new card in the machine (something I have). The ATM verifies the data is signed by the bank's key in order to continue. If all's well, I enter my PIN (something I know) which is verified as usual. I'm then asked for my passphrase to decrypt my biometric data, which is decrypted in to an encrypted memory location. Once the data is decrypted and verified, I'm asked to provide my thumb/palm/eye (something I am) and the scanned biometric data is matched to the decrypted data.

As soon as all tests have been made, the encrypted memory location is destroyed, regardless of the outcome of the checks. If all checks pass, I'm granted access to the ATM's authenticated functions (withdraw cash, etc).

Now, I'm wondering whether the PIN and decrypt passphrase could be merged in to one; after all, if I know the passphrase to decrypt the biometric data then you don't really need to check my PIN.

So, there we have it. Three-factor authentication with biometric data stored on a single secure storage device (ATM card) without having your data stored on the bank's central servers. Now all we need to do is trust they don't keep copies, do destroy biometric data stored in ATMs as soon as they're no longer needed and don't provide back doors to law enforcement agencies.

## Health and Safety

Research in to ["Laser Safety Analysis of a Retinal Scanning Display System" from the University of Washington](http://www.hitl.washington.edu/publications/r-97-31/) suggests that there's a chance of danger, and that its use hasn't been found to be categorically safe concerns me. How do you feel about banks using "something you are" to authenticate your access?
