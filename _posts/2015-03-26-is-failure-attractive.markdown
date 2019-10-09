---
layout: post
title: "Is Failure Attractive?"
Slug: is-failure-attractive
date: 2015-03-26 02:26:44
tags: [Uncategorized]
---
I was invited to present at the inaugural Australian PHP Conference, and offered to give a talk on writing a virus. What ensued was the most catastrophic sequence of events. Can you imagine how the audience reacted?

## Prequel

I recently reinstalled my laptop. I run a MacBook Pro, because I love the durability and quality of the hardware, with Debian GNU/Linux, because I love Debian's philosophies on open source and trust their package management and testing frameworks. As an aside, I'm loving the latest version of Debian, Jessie, which runs extremely smoothly on Apple hardware. Given the recent install, I knew I hadn't tested the laptop on projectors yet, so anticipated a need to tweak the configuration before my presentation.

## The Night Before

\[caption id="attachment\_4477" align="alignright" width="150"\][![Photo of Ben Dechrai at SydPHP talking "Patents Rock"](https://bendechrai.com/wp-content/uploads/2015/03/sydphp-patents-rock-150x150.jpg)](https://bendechrai.com/wp-content/uploads/2015/03/sydphp-patents-rock.jpg) Me, swinging on an imaginary swing at SydPHP while talking about software patents.\[/caption\] My first presentation in Sydney last week was the the Sydney PHP Users Group, where I gave my [Patents Rock](https://speakerdeck.com/bendechrai/patents-rock "Ben Dechrai's "Patents Rock" Lightning Talk on Speaker Deck") lightning talk. I arrived an hour before the event started, plugged my laptop in, and my second screen immediately appeared on the two impressively large screens, and my talk went without a hitch.

These were external monitors though, not projectors, so I was still a bit nervous about my conference presentation the next day.

## Background: DDC and EDID

What now? [Display Data Channel](https://en.wikipedia.org/wiki/Display_Data_Channel) and [Extended Display Identification Data ](https://en.wikipedia.org/wiki/Extended_display_identification_data)are, respectively, a protocol and a data structure that allow displays to tell graphics adapters what resolution they support. Unfortunately, while most panel displays support this, most projectors don't. So how is it that you can simply plug most any device in to a projector and it'll just work?

It turns out that most proprietary graphics cards drivers don't even look for the EDID information, instead referring to a lookup table that comes with the driver. They detect the make and model, look up the resolution in their internal database, and use that.

Of course, this lookup table isn't open source, so most open source drivers don't include this information. Not that they should have to assume that display manufacturers won't follow the standards defined by the [Video Electronics Standards Association](https://en.wikipedia.org/wiki/VESA).

## Conference Day One

So, it's day one. I'm the fourth presenter. Knowing full well that my experience with the panel displays the night before would likely not be repeated by the projectors at the conference venue, and not expecting the morning break to be sufficient time, I made sure I was there as soon as the room was available for me to test my laptop. Arriving shortly after 7am, I plugged the VGA cable in to the side of my machine, and... ...nothing.

## Failure #1 - No Projection

I half expected this, so proceeded to install the proprietary nvidia drivers: `<pre class="lang:sh decode:true">aptitude -r install linux-headers-$(uname -r|sed 's,[^-]*-[^-]*-,,') nvidia-kernel-dkms`After following the prompts, ensuring everything had been done before a restart, I crossed my fingers and rebooted.
## Failure #2 - No GUI

\[caption id="attachment\_4478" align="alignright" width="371"\]![Screenshot of "Oh no! Something has gone wrong."](https://bendechrai.com/wp-content/uploads/2015/03/Selection_040.png) What you see when you start Linux, and your graphics driver is having a sad.\[/caption\] It didn't take long before my heart darted at an alarming rate towards my stomach. Blood pumped faster. Adrenaline was released. Gut wrenching fear ensued.

I stopped for a minute, long enough for the colour to evaporate from my face, and to give a friend a look of sheer horror.

I tried all sorts. I even connected to my home router, mounted my backup drive on the NAS, and copied over xorg.conf files. (Note to self, it's about time I got that VPN connection working.)

```
<pre class="lang:sh decode:true">rsync -Paz home:~/mount/backup/etx/X11 ./
diff -br ./X11/ /etc/X11/

>~/etc.diff
less ./etc.diff
```

I tried disabling the nvidia drivers and get nouveau loaded again, just to regenerate the xorg.conf file with <span class="lang:default decode:true  crayon-inline">nvidia-settings</span>. Rasmus Lerdorf's keynote was now about 30 minutes away, and with it, I'd lose the ability to test my laptop on the projector. My friend suggests I use hers instead. It had HDMI, but the AV guy just managed to get HDMI working, so that could work.

## Redeploy

She's already installed [VirtualBox](https://www.virtualbox.org/), [Vagrant](https://www.vagrantup.com/) and [playitagainsam](https://github.com/rfk/playitagainsam/), and copied my presentation to her laptop. She kindly gives me root access, and I configure the demo website. I download fonts for the slide deck. I test the demo. It works. Rasmus is about to begin, I have a working machine, and I can relax. He is followed by Steve Cooper from PayPal/Braintree, talking all things Internet of Things and payments, and then we have morning tea.

I grab the loan laptop and head to the podium to check the settings.

## Failure #3 - No HDMI

There's no HDMI cable any more, so I run to the AV room at the back of the theatre and ask the guy if he can find one. He quickly notices that his relaxed demeanor isn't reciprocated when I offer, in a hurried tone, to help him do it asap. The HDMI cable is being used by the Wordpress/Automattic crew for their sponsor stall, who generously relinquish it in favour of enabling a presenter to present. We plug the cable between some converter box near the podium, and to the laptop and...

...nothing.

I try all sorts, from trying to push the cable in harder, to praying to [Cthulhu](https://en.wikipedia.org/wiki/Cthulhu).

\[caption id="attachment\_4500" align="alignleft" width="243"\]![A sketch of the fictional character Cthulhu, drawn by his creator, H. P. Lovecraft.](https://bendechrai.com/wp-content/uploads/2015/03/Cthulhu_sketch_by_Lovecraft-243x300.jpg) A sketch of the fictional character Cthulhu, drawn by his creator, H. P. Lovecraft.\[/caption\]

The AV guy tests the laptop out at the back of the hall, near the AV room, and it works! We put it down to the converter box, and consider the option of me presenting from the back of the hall. It's quite unorthodox, but possible. The conference organiser is a little concerned, but I assure him I can manage the communication of the situation, even suggesting it becomes part of the act. After all, no self respecting virus writer would do so in public. No, I'd have to go to my "cave" and write it in secret.

Resigned to this, as my only option, and having tested my remote presentation clicker worked at that distance, I head back in to the theatre. On the way in, I bump in to another friend, whom I haven't seen in months. He smiles and joyfully asks how I'm doing.

"Panicking," I respond. When he hears of my news, he offers me his laptop! At first, I dismiss the idea, as I'm on after the next speaker, before realising I have the duration of the next speaker's talk to set it up again. What could go wrong? If I fail, I can just present with other loan laptop from my "cave", right?

Jordi Boggiano, creator of [Composer](https://getcomposer.org/), apparently gave a fantastic talk, and I'm only sorry that I missed most of it. I did, however, get the latest loan laptop working with 5 minutes to spare.

## Taking the Stage

Being very careful not to dislodge the power cord, for I believe the battery was so dead that a loss of mains power would have caused a shutdown, I gently moved the laptop on to the podium and connected the video cable. _Success!_

I started presentation mode, the auditorium projector displayed my first slide, and the laptop showed the presenter view. Perfect!

Being one for expressing my gratitude, I started by first relaying the sequence of events you've just read, to the audience, and thanking my two friends and the AV guy. While receiving looks of bemusement, and snorts of amusement, I took a moment to acknowledge to myself how much had actually gone wrong. And yet, here I was, with a slide projected on the wall behind me.

I pressed the button on the remote presentation control, to move to the next slide and...

...nothing

## Failure #4 - No Remote Control

I like to move. I'm not a behind-the-podium type of presenter. I'm very much a piss-off-the-camera-operator-by-using-the-whole-stage type of presenter. I gesticulate. I jump. Some might even say prance. So being constrained to my laptop for the purposes of changing slides forces me to change mode. Lecturer style, I discuss the concepts, purpose, techniques and detection avoidance tactics of viruses. I touch on a bit of encryption theory, and get started on the live coding.

## Failure #5 - Blinkered

I can't see the projected image! When displaying slides, you have two screens; the live projection, and your laptop screen with a presenter view, including the current and next slides, and some notes. \[caption id="attachment\_4493" align="alignleft" width="300"\]![Ben presenting at PHP Australia Conference 2015](https://bendechrai.com/wp-content/uploads/2015/03/16809280611_e7191ba96f_o-300x200.jpg) Ben presenting at PHP Australia Conference 2015\[/caption\]

Having two separate screens, rather than mirroring your laptop screen to the projector, is the ideal way to present. Not so when live coding.

Craning behind me to see what I'm typing, an audience member suggests I turn the podium around. This helps somewhat with ensuring the microphone picks up my voice, but I soon realise that the black curtains hanging on either side of the wall are blocking about 40cm of the left of the projected screen. This represents the first 10 to 15 columns of text on the screen, making it near impossible to continue without occasionally moving from the podium to see what I'm up to.

There's a solution, though, that I'd planned for. You see, talking about what you're doing, while doing it, is hard. Your brain needs to concentrate on the same thing, twice, at the same time, at different speeds.

So I used [a tool that automatically types a prerecorded sequence of keyboard presses](https://github.com/rfk/playitagainsam/) in time with my keystrokes. No matter what letter I press, the right one will come out on the screen. It works 99% of the time, and has a tendency to get confused by cursor keys.

## Failure #6 - Automated Code Writing Failure

It should come as no surprise by now that the aforementioned tool failed. The automatically written code failed to run properly, and the tension in the audience could be cut with a knife. That's not to say they were impatient, quite the opposite. I could feel an energy of empathic disappointment that, despite my valiant efforts, things weren't going well for me. I'm nothing if not prepared. While creating the prerecorded typing scripts, I had, by necessity, created the desired end result files that I wanted to demonstrate. I copied these to a dot-file (hidden files in Unix like systems), and committed them to my code repository. Simply replacing the non-functioning, auto-typed code with the contents of the desired end result, not only meant the show could most definitely go on, it also solicited applause and delight in the audience.

`<pre class="lang:sh decode:true ">cp .boom.php boom.php`I quipped that I must have left Plan B behind earlier that morning, currently implemented Plan K, and still had plans up to Z still to go.
## "Live Coding" No More

So, obviously no longer live coding, I'm now highlighting the changes with my laser pointer, and describing the thought process behind those changes. The presentation was losing dynamism at every turn, but yet, the audience was still engaged. I've just shown how a script can infect other scripts with a line of text. I extend that so the script infects other scripts with itself, creating something of a chicken and egg scenario.

The next stage of the demonstration is to obfuscate the code to avoid detection by anti-virus scanners. Step 3 uses PHP's mcrypt functionality.

## Failure #7 - Call to undefined function mcrypt\_get\_iv\_size()

When you're giving live coding demos, the last thing you want to see on the screen is error output. Unless you're demoing error handling. I wasn't. When you're not expecting it, this terse, but complex text output, can stop you in your tracks: ```
<pre class="lang:default decode:true">vagrant@localhost:~/Talks/Going Viral for Fun, not Profit/demo/files/step3$ php .boom.php 
PHP Deprecated:  Comments starting with '#' are deprecated in
/etc/php5/cli/conf.d/20-mcrypt.ini on line 3 in Unknown on line 0
PHP Fatal error:  Call to undefined function mcrypt_get_iv_size() in
/home/ben/Talks/Going Viral for Fun, not Profit/demo/files/step3/.boom.php on line 47
vagrant@localhost:~/Talks/Going Viral for Fun, not Profit/demo/files/step3$
```

It turns out that I hadn't enabled the module required for encryption. In fact, it wasn't installed on the laptop. So, with the audience watching, I started installing the required software to finish the presentation. This turned in to an audience participation segment, with members suggesting the next steps to help me get back on track as quickly as possible. I love this community. Encryption working and demonstrated, whilst suitably impressing the audience with just how hard it's becoming to detect and protect against this simple virus now, I prepare for the finale.

## The Live Server Attack

\[caption id="attachment\_4497" align="alignright" width="300"\]![The photo that was the source of the virus attack during my demo at PHPOZ15.](https://bendechrai.com/wp-content/uploads/2015/03/bread-300x225.jpeg) The photo that was the source of the virus attack during my demo at PHPOZ15.\[/caption\] I've rehearsed this part a few times. I have a gallery application that implements many, many best-practice security checks to ensure images, and only images, are uploaded to a secure location that cannot be accessed directly. The gallery application includes a system that allows the gallery application to display those images to the browser, checking, again, that they are images, and that the request came from someone using the gallery application.

The attack vector is through this gallery system. The plan is to upload the virus to this gallery, and then watch as every single editable script on the server is infected with the virus. Those who were there will recognise this photo. This one isn't the one with the virus, in case you're worried.

## Failure #8 - Call to undefined function mcrypt\_get\_iv\_size()

Again? So, this time, the Apache web server isn't aware of the mcrypt module.

>Thankfully, Dave has left me with a root terminal open, with which I can now continue my journey of completely destroying his laptop! -- Ben Dechrai on reconfiguring the web server during a demonstration.

And again, audience participation leads a diversion to configure the web server. After a few minutes, it turns out that the collective knowledge in the room is at a loss, and I decide to explain the attack in conceptual form, relying on maximum use of the stage and wild gesticulation to distract from the biggest failure of the presentation. This engages the audience even further, as they start questioning the process, and we enter a group trace mode, mentally stepping through the process from file upload to payload deployment.

## Back to Safety

With the demonstration now complete, I return to the safety of the slide show presentation, which covers some other material, closing with a call to the audience to engage in some radical hackery, for the purposes of learning something new and stretching themselves mentally. For good, not profit.
## Conclusion (Too Long, Didn't Read)

This presentation has to be the most failure-ridden talks I've given. The second next pales in comparison, but they both have something in common. They are the best received presentations I've ever given. They are the talks that had the most audience engagement. They are the talks that I've had the most follow up questions about. They are the talks that I've been told have been the stand-out events of the conference.

How can this be? I had my theories, but let me share a short story with you from a friend to whom I recalled these events.

> There's this comedian who talks on presentation techniques. As he's introduced, he walks on stage, trips over, swears under his breath (with the lapel microphone on), and continues to the podium. Once there, he tells everyone he just did all that on purpose; the purpose being to make himself out to be just like everyone else in the room. He's just as fallible, successful, vulnerable, knowledgeable.

When my presentation started falling apart, I had two options. I could get frustrated and give up. I'd have been consoled by my peers, people would have commiserated and understood. I would have been feeding a mentality of victimisation. If you know me, you know that's not me. Or I could have continued, relied on backup plans, kept a clear head and soldiered through installation processes, analysed errors and fixed them. This was my choice, and I tell you what it did. It normalised failure. By being on stage, and failing, I made it okay to fail. Because it _is_ okay to fail; that's how we learn.

Further, it allowed anyone in the audience to go ahead and actually try to fail too. They didn't need to be able to write a virus first go. They didn't need to get encryption working first go. They were able to give themselves permission to just give it a shot, and if they failed, well, Ben didn't do any better, did he?

So, I suggest that failure is attractive. It attracts those that will give it a shot, and if it doesn't work out, get back up, and give it another shot. Next time you're about to show people how to do something, think about failing first.

What say you?
