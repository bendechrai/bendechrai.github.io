---
layout: post
title: "Powerful Cross Site Scripting Scanning Tool"
Slug: powerful-cross-site-scripting-scanning-tool
date: 2007-12-01 00:37:36
tags: [Conference,Open Source,Security]
---
![scanEE](https://bendechrai.com/wp-content/uploads/2007/12/scanee-copy.png "scanEE")Web developers today are increasingly aware of the number of ways that attackers can abuse their site. Not only do we have to worry about someone stealing data directly through our site or from our database, cross site scripting (XSS) attacks provide a mechanism for someone to run arbitrary code on another web site. During his [OSDC](http://osdc.com.au/ "Open Source Developers' Conference web site") 2007 keynote, [Rasmus Lerdorf](http://lerdorf.com/ "Rasmus's web site") mentioned the scanmus, a cross site scripting scanning tool he'd written. It looks at a page's source code and identifies potential entry points. In the case where it finds a form, it will submit data in a way to detect a number of XSS vulnerabilities, and report those to the user. Unfortunately, while he plans to make this available to the community, this won't happen just yet.

[Ben Cornwell](http://bencornwell.com/ "Ben Cornwell's web site") and I got to chatting during the break and when I suggested we write our own, he didn't hesitate. I don't think he quite realised at the time that there wouldn't be any PHP work involved though.

You see, there's this tradition at conferences (at least the ones that I've attended), that when a discussion or talk at the conference gives you an idea for a product, script or technology, you start on it right away and present it at a lightening talk during the same conference. So we couldn't just have some lame PHP script parse the resultant HTML and spew it to the browser. That would be too easy. That would be just what they'd be expecting us to do! And you know you can't take over the world by being predictable.

So we wrote it in HTML and JavaScript. Even the logo! It's one HTML file.

Now this will work perfectly if the HTML script is placed in the document root of the site you want to test. If you want to test remote web sites though, as we did during the lightening talk, you'll have an issue with cross domain xmlhttprequests. So for the demo we had a simple proxy helper that would load the remote site. The JavaScript class could then load the remote site's contents through a local call.

So without further ado, you might all be wondering where you can download this awesome tool. Well, it's still extremely pre-alpha. It itself has XSS vulnerabilities! It needs to be worked on. But you can still grab the [HTML](https://secure.benshosting.com/svn/projects/scanee/trunk/index.html "scanEE HTML file") and [PHP](https://secure.benshosting.com/svn/projects/scanee/trunk/get.php "scanEE PHP file") files if you like.

I've already had a fair amount of interest from people who want to help, so if you'd like commit privileges, [please let me know](https://bendechrai.com/contact/ "Contact me"). You can check out the [trunk](https://secure.benshosting.com/svn/projects/scanee/trunk/ "scanEE subversion trunk") in the meanwhile.
