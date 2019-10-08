---
layout: post
title: " The new job"
Slug: the-new-job
date: 2005-10-18 00:56:26
categories: [Work Life]
---
My new job started yesterday and I had one helluva time getting the new IBM ThinkCentre to run Ubuntu. Well - getting it installed was easy, and as usual took less time than configuring Windows on my other machine, which was already pre-installed.

The crunch came when the installer couldn't detect the network card. Arguably the worst device not to find, because there's no net connection, and you can't apt-get or download the drivers you need. Okay, so the monitor not working would be worse, granted, but that's very unlikely to happen :-)

So after downloading the drivers, burning them onto a CD and copying them to the linux machine and realising they needed gcc-3.4 to compile, then downloading the gcc-3.4 .deb installers, burning, copying, installing, I finally got the drivers to compile and was left with a .ko file. New to compiling linux kernel objects, I followed the instructions to the letter, and successfully insmodded the object and make installed it. The device was still not recognised. I even resorted to rebooting! A linux machine! I know, but I figured it was worth a shot. Still nothing.

After 2 hours of trying, I went round the corner and bought a $15 generic 10/100 ethernet card and was up and running 5 minutes later.

Day one. Good so far!
