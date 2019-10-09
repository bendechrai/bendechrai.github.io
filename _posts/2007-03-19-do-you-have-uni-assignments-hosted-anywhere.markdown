---
layout: post
title: "Do you have uni assignments hosted anywhere?"
Slug: do-you-have-uni-assignments-hosted-anywhere
date: 2007-03-19 13:51:27
tags: [Patents]
---
I went to University and studied Software Engineering. I also did Computing at high school. I've also been programming in one way or another since the age of 8. I'm not unusual.

One of the things I learned about was data storage, and how it actually works. For example, an array of data is a single data store that allows you to store multiple items. For example, you might have an array of contacts where each element of the array is an email address. The way an array works in terms of raw storage in memory is quite simple.

- A variable points to a location in memory,
- That location contains the first element followed by a pointer to another point in memory,
- That location contains the first element followed by a pointer to another point in memory,
- Etc... until the pointer to the next point in memory signifies the "end of array" marker.

This is called a linked list - because each item in the list is linked to the next. Now one day, some guy (it might have been a gal, but we'll call him Bob for now) decided he wanted a way to find the previous item in the list. Instead of starting at the start of the list again, Bob just added a second pointer to each element pointing to the previous element. And thus was born the doubly-linked list. Now imagine you want those elements sorted, but you still want to keep the "natural order". You'd need a second linked list for the sorted version. Or you can just give each element 4 pointers, 2 for the natural order (previous/next) and 2 for the sorted order (previous/next). Now you have a list with multiple pointer to other elements.

If you've ever used this type of data storage, I highly recommend you remove any proof thereof from any publicly accessible source, find the print outs and burn them, preferably after a good soaking in something flammable\*. Why?

Ming-Jen Wang of Colorado Springs has a patent on:

> A computerized list is provided with auxiliary pointers for traversing the list in different sequences. One or more auxiliary pointers enable a fast, sequential traversal of the list with a minimum of computational time. Such lists may be used in any application where lists may be reordered for various purposes. [US Patent Office](http://patft1.uspto.gov/netacgi/nph-Parser?Sect1=PTO1&Sect2=HITOFF&d=PALL&p=1&u=%2Fnetahtml%2FPTO%2Fsrchnum.htm&r=1&f=G&l=50&s1=7028023.PN.&OS=PN/7028023&RS=PN/7028023 "Patent number 7028023")

It seems that the USPTO have extremely highly qualified examiners, and Mr Wang found a way of registering [unenforceable patents](http://www.patentlegal.com/ "Cochran Freund & Young LLP") through Cochran Freund & Young LLP, the **Attorney, Agent or Firm** listed against this patent. \* This is a joke. If you burn (or kill) yourself (or someone/thing else) or destroy anything or indeed cause anything at all to happen by following my obviously ridiculous suggestion then [you probably deserve what you get](http://darwinawards.com/).

Thanks to [Uber Monkey](http://ubermonkey.wordpress.com/ "Uber Monkey") for giving me the tip on this story.
