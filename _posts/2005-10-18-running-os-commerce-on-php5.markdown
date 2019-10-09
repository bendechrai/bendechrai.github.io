---
layout: post
title: " Running OS Commerce on PHP5"
Slug: running-os-commerce-on-php5
date: 2005-10-18 01:32:27
tags: [Open Source,Work Life]
---
Day two at the new job. My first tasks involve making some customisations to an OS Commerce installation and, as ever, I hate to work on live servers. I just spent an hour or so downloading the live application, but of course I've installed [Dexter's PHP5.1](http://people.debian.org/%7Edexter/dists/php5.1/) with MySQL4.1 and Apache2. OS Commerce is written for PHP4.

The home page loaded fine, but heading to the admin page, I get "Fatal error: Cannot re-assign $this in .../admin/includes/classes/upload.php on line 31". I figured that I'd document the changes required to get this running on PHP5 so that I can refer to it again later, and maybe help a few others out.

### Fixing the $this re-assignment

First job is to get rid of that error. Looking at line 31 in /admin/includes/classes/upload.php I see:

```
// self destruct
$this = null;
```

For now, I'm just going to comment this out and see if there are any undesirable consequences as I test the system. Bingo - admin system works now.

Well I never - it works. Hardly seems worth posting this. In order to make this post a little more useful, I tried to see if anyone else has done this and found [a thread on webmasterworld](http://www.webmasterworld.com/forum22/4020.htm). This person seems to have found problems with the navigation object, but I can't reproduce that. No errors here. [Another thread covering this issue](http://forums.redfoxhosting.com/showthread.php?s=bf7b1ea22a81ca5cd8933f44f2535b7e&t=178) might also be useful to you.

### \[Update: 19 Oct @ 15:20\]

It seems there is something else. When using the admin area, trying to add tax zones, I got an SQL error: "You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '-20, 20' at line 1".

Seems the paging code doesn't work well in PHP5, and [a thread on the oscommerce forum](http://forums.oscommerce.com/index.php?showtopic=149752) gives one solution: if the offset goes below zero, set it to zero. So on line 38 of admin/includes/classes/split\_page\_results.php and line 66 of includes/classes/split\_page\_results.php, add:

`if ($offset < 0) $offset=0;`

As is the poster of this tip, I'm unsure how this will cope with pages 2 and later when paging. I'll update this if I find another problem.
