---
layout: post
title: "VPSLand Staff: illiterate, incompetent or just don't care?"
Slug: vpsland-staff-illiterate-incompetent-or-just-dont-care
date: 2009-10-28 06:44:22
categories: [Customer Service,Hosting,Uncategorized,Work Life]
---
I've been a customer of VPSLand's for some years in one form or another. A friend recommended them when the Melbourne PHP Users Group was looking for a new server, he'd been with them for a while. I decided to get one for MooBox too.

Time passed, servers churned, and for the most I was happy. Then MooBox's VPS dropped off the face of the ether. An email to support had the issue resolved in slightly more time that I'd hoped and all was well. Apparently the host server my VPS was on had issues and I was migrated. A year later, the same happened again, same reason.

#### The Last Straw

A short while ago, this server then stopped being able to communicate externally. Web sites were being served, but our spam detection system died (it needs to be able to talk to external servers) which meant our clients on that server couldn't receive email. I emailed VPSLand support for assistance. 4 hours later I was told the issue had been escalated to senior admins. When I asked their sales staff how long I'd have to wait for a response on a ticket I was told an hour or two. 8 hours later I'd still heard nothing, so I asked for an update. No response. I asked again 32 hours after the original request for support, shortly after which I noticed the server was completely inaccessible. No web sites, no SSH, no email. It had been 5 days since email had stopped coming in and now I couldn't access the server at all. I requested a reboot.

Now historically when I've asked for reboots of servers from VPSLand it'll happen within an hour. For now, let's not get in to why I've had to request VPSLand for so many reboots when none of my other servers require this.

It took them 7 hours to tell me they'd escalated to a senior admin. For a reboot? And it took that admin 1.5 hours to get around to performing the reboot!

After some time spent looking through logs to determine the source of the cause, it became apparent, as was my original observation, that the server hadn't changed but that some upstream data provider or connectivity/routing point had failed. I resolved to migrate all my clients to a different server with another provider and to cancel this VPS.

In the meanwhile, I've also been migrating services from the Melbourne PHP Users Group's VPSLand VPS to a new server that a friend and I have set up for the Open Source Developers' Club, of which phpMelb is now a significant interest group. So phpMelb gets free hosting, no need for the VPS. Note that I've never had the level of issues with the VPSLand VPS that MooBox had with the one phpMelb had, but we were migrating anyway.

Having migrated everything, I sent a request to VPSLand asking them not to renew the VPS for phpMelb:

> Please do not renew this VPS. We are in the process of migrating this to another server and will not require this VPS after the renewal date of the 2nd November.

And with that, I breathed a sigh of relief that I wouldn't have to deal with VPSLand any more.
#### Cancelling a non-existent server

Imagine my utter surprise when VPSLand sent this in response to the phpMelb VPS discontinuation request:

>Hello Ben, Thank you for contacting VPSland.
> 
> We have checked your account and have found that your subscription has been deleted due to non-payment.
> 
> The grace period of your subscription has expired on <07-May-2009>. The grace period is a period of time that starts after a service subscription expires. You are then granted a grace period to prolong your subscription. As the grace period has already expired, you cannot prolong your subscription.
> 
> Now you will have to place a new order. Once your new order is processed, you will be allotted a blank VPS with new IP address.
> 
> Please let me know if there is anything else I can help you with.
> 
> Regards
> 
> Nick

So this server, that I've not had any major issue with, and have recently migrated web sites and email accounts from, has actually not been active for some time. This is rather confusing to me, especially given I have a connection to the server open at the time. Well Nick, seems someone can't read. So I clarify:

>

>We have checked your account and have found that your

>subscription has been deleted due to non-payment. So are you saying that I shouldn't be able to ping or SSH in to this server?
> 
> $ ssh ben@64.22.91.206 Linux phpmelb.org 2.6.16.33-vpsX #2 SMP Tue Jan 23 22:53:20 EST 2007 i686
> 
> The programs included with the Ubuntu system are free software; the exact distribution terms for each program are described in the individual files in /usr/share/doc/\*/copyright.
> 
> Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by applicable law. Last login: Fri Oct 23 03:10:11 2009 from 115.69.161.104
> 
> \> The grace period of your subscription has expired on

><07-May-2009> ... as the grace period has

>already expired, you cannot prolong your subscription.
> 
> I'm not asking to prolong my subscription. Any way, if this VPS has passed its grace period, why can I still connect to it?
> 
> \> Now you will have to place a new order. Once your new order is

>processed, you will be allotted a blank VPS with new

>IP address.
> 
> Did you read that I wanted to not renew this VPS? Why would I create a new account and get a new VPS?
> 
> \> Please let me know if there is anything else I can help you with.
> 
> There's nothing else, but you haven't addressed my initial request. I would like you to not renew the VPS with IP 64.22.91.206.
> 
> Cheers Ben

I thought that would drive the message home, but unfortunately I seem to be dealing with not one, but two people at VPSLand who are either illiterate, untrained or just don't care.

>Hello, We have checked your account and have found that your subscription has been deleted due to non-payment. It is not possible to reactivate the deleted VPS. To be having a VPS I would request you to please place a new order with correct and complete contact information on our online order form. Then please update our billing team soon as you place a new order, so that we can expedite the order.
> 
> Please let me know if there is anything else I can help you with.
> 
> Regards
> 
> Chris

I wondered if I could make this any clearer and chose my words wisely.

>I AM NOT MAKING AN ORDER! MY ACCOUNT IS STILL ACTIVE
> 
> I DO NOT WANT TO RENEW
> 
> Please note that any attempt to take payment for the VPS which is still active will result in legal proceedings.
> 
> \> Please let me know if there is anything else I can help you with.
> 
> Yes - please read my request.

Moments before publishing this post, I notice the most recent reply cannot get through. My mail logs show it left my server and was delivered to mx1.exchangesync.com ("a VPSLand company"). Perhaps in some moment of karmic correction, their mail server cannot accept emails because they're having the some strange connectivity issues. Do you work for VPSLand? Do you have a phone number for them? I'd love to chat to someone there. There's no number on your site anywhere - do you not like taking calls? I wouldn't actually mind if you could act on emails in a timely and accurate manner.

#### Update: 9th November

The server was due for renewal 5 days ago, and the on-line billing system shows a new invoice has been raised against it. Rather worryingly, their billing site's SSL certificate reports itself as having expired on 24/05/09. Strangely this wasn't the case a few weeks ago.

Now it's fair to assume their billing system has automatically generated this invoice, but I'm still confused that the account hasn't been cancelled. My latest missive to them:

> I notice that invoice 39550 has been raised for this VPS. You state the VPS doesn't exist (which is not the case - I can still connect to it), so why are you invoicing me for it?
> 
> I have asked you repeatedly to cancel this VPS, so why are you invoicing me for it?
> 
> Do not attempt to charge any amounts to my credit card for this VPS. I do not want to keep it.

Taking bets now on: 1. number of hours to first response
2. receiving an email telling me the VPS doesn't exist and that I'll have to order a new one through sales
3. being charged for the renewal

Ooh - mini addendum: I have two automated emails from thir billing system, one on the 2nd, one at 4pm today, telling me they tried to charge my card but it failed. I did update my credit card number to 4242424242424242 (a test number) which the system must have accepted. Glad I did that!
#### Update: 23rd November

They've now tried to charge this test card 4 times. For a server that I cancelled. And that they refuse to acknowledge exists!
#### Update: 28th January 2010

Yes, I'm still getting emails from them. Yes, they're still trying to charge a test credit card number. But as of a few days ago, I'll not be troubled by them again. The solution: change the account details to: [![VPSLand Account Info](/wp-content/uploads/2009/10/vpsland-account-info-300x195.jpg "VPSLand Account Info")](https://bendechrai.com/wp-content/uploads/2009/10/vpsland-account-info.jpg)(click to enlarge)
