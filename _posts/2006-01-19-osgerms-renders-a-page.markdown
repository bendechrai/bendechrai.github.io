---
layout: post
title: "OSGERMS renders a page"
Slug: osgerms-renders-a-page
date: 2006-01-19 07:29:21
tags: [Open Source]
---
I'm very excited today. I just got OSGERMS to a point where a default install renders a page! Woohoo.

Okay, so it only says "Hello", but it's a start. The system is separated into a share and docroot directory, where the docroot contains a symlink to the index.php in the share directory, and deployment specific files (currently only the template files).

The share directory contains the meat of the system, all completely OO (except for an error handler, convenient p() function for printing debug info and the \_\_autoload function).

Anyway, it's after 6 o'clock, and I've been fighting to get this done by the end of today. It's all [checked in](http://osgerms.tigris.org/source/browse/osgerms/trunk/) if you're interested in looking at it...

I'm off to the [Melbourne PHP User Group](http://phpmelb.org/) committee meeting now. I'll write more on this soon. Even if you're not that interested :-)
