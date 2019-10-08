---
layout: post
title: "The Myth of the Innocuousness of Metadata"
Slug: the-myth-of-the-innocuousness-of-metadata
date: 2015-03-31 01:16:05
categories: [Data Retention,Politics,Privacy,Surveillance]
---
The Australian Attorney General's Department (AGD) have released, under the freedom of information act, a draft, redacted copy of a fact sheet that outlines the data retention bill. There are concerning issues, both in what's been written, and what's been redacted.

## Redacted?

\[caption id="attachment\_4514" align="alignright" width="213"\][![AGD Data Retention Fact Sheet](https://bendechrai.com/wp-content/uploads/2015/03/Selection_065-213x300.png)](https://bendechrai.com/wp-content/uploads/2015/03/Selection_065.png) AGD Data Retention Fact Sheet\[/caption\] Documents shared under the freedom of information act may have sensitive items redacted. Names of offenders (to protect their family), addresses of victims, classified information (for national security purposes, for example).

What on earth is so sensitive in this draft that it needed to be redacted? I can only use my imagination and opine about protection against ridicule and embarrassment, but I freely admit that my political bias may have something to do with that.

Let me put my bias aside again, and analyse the document.

## What is metadata?

The fact sheet says this:

>The Australian Government is asking industry to keep a limited set of metadata for two years, which will be defined in regulations. Metadata is information about a communication (the who, when and where) - not the content or substance (the what) of a communication. For phone calls, metadata is information like the phone numbers of the people talking to each other and how long they talked to each other - not what they said.
> 
> For internet activity, metadata is information such as an email address and when it was sent - not the subject line of an email or its contents.
> 
> We are not asking industry to retain a person's web-browsing history.

Let's deconstruct that a little:

>a limited set of metadata for two years, which will be defined in regulations

The requirement to retain data is a law, but the definition of what is to be collected is a regulation. This means the current Government, or any successive one, can change the definition of what is to be retained, without the need to take that process through parliament and the senate.

>... - not what they said. ... - not the subject line of an email or its contents.

Note here that, in defining what they're not collecting, they are allowing the reader to assume that the content is the private stuff, and the metadata is not. This is a fallacy that I'll discuss later in this article.

>We are not asking industry to retain a person's web-browsing history.

This one is dangerously inaccurate. They are monitoring the address of the web sites you're visiting, which will give them the web-browsing history. Here's the Attorney General, Senator George Brandis, explaining the difference: <iframe allowfullscreen="allowfullscreen" frameborder="0" height="390" src="https://www.youtube.com/embed/Hw1ryLGs2ws" width="640"></iframe>

## Why do they need metadata?

Here's the rationale:

>Metadata is vital to nearly every counter-terrorism, organised crime, counter-espionage and cyber-security investigation. It is used in almost every serious criminal investigation, including murder, rape and kidnapping.

They add that it can be used to prove innocence or guilt, adding emotive constructs to make this seem like more of a good idea. They go on to say:

>Changes in business practices and developments in technology mean that many telecommunications companies are not retaining some types of data or are retaining it for long enough to enable our law enforcement and security agencies to investigate and prosecute serious crimes.

Well, they're right. Metadata is invaluable. And they've been using it for decades. They've been accessing metadata to prove innocence or guilt successfully for a long, long time. No one is disputing that. They're also right that communications providers don't have all the information they might need. What this section of the fact sheet doesn't even touch on, though, is any justification for the law enforcement agencies to have unfettered access to this information, or for the extension of retention to two years. There are many thousands of people in Australia who will fall under the definition of an authorised person for the purposes of accessing this information, and they be able to do so _without a warrant or any judicial oversight_.

In all the time they've been using metadata to help solve crimes, there has been a requirement to obtain a warrant before access is granted. Not with the new laws.

### But surely these authorized people won't abuse their position

I could find half a dozen news articles with a few minutes of searching that identify abuses of power when it comes to accessing personal information. Just recently, [a Protective Services Officer shared personal information "for a laugh"](http://www.thecourier.com.au/story/2976202/pso-breached-data-security-for-a-laugh-police-documents-reveal/). It only takes a few people willing to abuse their power for it to happen, and corruption in organisations of power is, unfortunately, inevitable. Consider that these people aren't just authorised employees of a law enforcement agency. They are human beings. They could be your neighbours, friends of friends, or friends of people who don't like you very much at all. They could learn that you've recently visited a web site related to drug rehabilitation, or that you've emailed your lawyer just moments after you received a phone call fr<span class="text_exposed_show">om your ex.</span>

These people have unfettered, legal access, without a warrant, and you don't even have a right to know they know.

## Ensuring security of personal information

The fact sheet has a section entitled _**What protections are in place to ensure the security of personal information?**_ The unredacted portions tell us:

>The protection of the privacy of Australian's \[sic\] personal information is essential

Well, that's good to know. No answer there. Next paragraph:

>The Privacy Commissioner will continue to assess industry compliance with the APPs, as well as monitoring industry's non-disclosure obligations in relation to telecommunications information under the Telecommunications Act.

Note the sub-text: any potential breach can only be from industry. Law enforcement isn't even mentioned. It may be in the redacted section, of course. Time will tell.
## Metadata tells you more than content

I touched on this fallacy above; the wording of this fact sheet suggests that the content is the private stuff, and the metadata is not. Sure, it sounds unlikely, and the thought process goes something like this. You could know that I called the pizza shop yesterday, but you don't know what I ordered. You don't even know _that_ I ordered anything. I could have been asking about opening hours, employment opportunities, or complaining that my Calzone that had just been delivered didn't have the extra pepperoni I asked for.

How on earth would metadata be so important?

For a technical take on how metadata can be used to draw inferences, check out Kieran Healy's article, [Using Metadata to find Paul Revere](kieranhealy.org/blog/archives/2013/06/09/using-metadata-to-find-paul-revere/), which identifies [Paul Revere](https://en.wikipedia.org/wiki/Paul_Revere), a patriot in the American Revolution, as a "terrorist" from the perspective of British Colonists.

### On confusing metadata

The article I just linked to shows that, using only metadata, you can find out a lot about an individual. No content required. Of course, metadata itself can portray multiple possible realities. **Scenario One**

- I call them, on average, once a week, usually on a Friday;
- Yesterday, I called them a second time 35 minutes after the first call that day;
- The pizza shop has never called me;
- On almost all occasions that I've called them, my internet connection connects to BigPond Movies 35 minutes later.

This is only metadata, however, it is consistent behaviour for someone who orders a pizza, and then watches a movie. Probably innocuous. **Scenario Two**

- I call the Pizza shop irregularly;
- 60% of the calls I make are preceded with me receiving a call on my mobile phone;
- After calling the pizza shop, I usually receive an SMS from one of two numbers;
- 100% of the days that I get an SMS response, my mobile shows my location at a Mosque at 8pm that evening.

This is only metadata. No content. What do you think is going on? Any guesses? That's right; I'm a co-organiser for a Flashmob, and when I get calls from people who want to hire us, I call the main organiser; the sister of a pizza shop owner (they live above the pizza shop). Sometimes I call her just because we're friends. If it's about a gig, she then contacts the third organiser to see if we can all meet to discuss the job. One of them will let me know if we're on, and we meet at a community center meeting room that's part of the local Mosque, who have been very supportive of our entertainment group. That's exactly what you thought, right?

However, my actions include triggers that might cause an automated system to flag me as a person of interest. You can see how easy it is to create very false information about people based on purely factual information.

## Content is hard

Analysing content is hard. Semantic analysis tries to work out the context in words are written or spoken. Language is ambiguous. Mumbling, typos and abbreviations make it harder again. There are systems that will do it, but it's orders of magnitude harder than analysing metadata. When you're told:

>It's okay, we only collect metadata, the content of your communication still requires a warrant

What they're really saying is:

>Content isn't as valuable at metadata; we'll just collect the stuff that will give us a good picture of who you are, and not worry about the ambiguous stuff.

## Ambiguous?

Here's the content of an SMS. Tell me what's going on:

>Bloody hell! He's really getting my goat. Take him out, and make sure no-one sees you.

Answers in the comments. I'd love to delve in to your imagination.
## On international approaches

I recommend looking at Leanne O'Donnell's post on [how the west is backing away from data retention](http://mslods.com/2014/11/18/update-on-how-the-west-is-backing-away-from-data-retention/). Countries are abandoning data retention as ineffective, costly, and unconstitutional. Here's how the AGD communicate this trend: \[caption id="attachment\_4515" align="aligncenter" width="300"\][![How does Australia's approach to data retention align with international approaches?](https://bendechrai.com/wp-content/uploads/2015/03/Selection_061-300x156.png)](https://bendechrai.com/wp-content/uploads/2015/03/Selection_061.png) How does Australia's approach to data retention align with international approaches? (That grey box is the redaction.)\[/caption\]

## But, isn't it still worth it?

Those wishing to perform serious crimes and acts of terrorism will almost certainly be circumventing the retention of metadata. Our government has told us how to, so the information's there to use. So they'll mostly collect data from innocent citizens and minor criminals. That's not the purpose of the act. It won't make our nation more secure. That's why other countries are disbanding their data retention programs.

### Closing Opinion

Data retention will allow surveillance and detection of civil offenses. As I'll cover in another post soon, the Trans-Pacific Partnership agreement between the US, UK, Australia and many more countries, will allow, for example, American companies to use retained data for the purposes of prosecuting pirates. Sure, it's illegal to pirate, but this bill is not being sold as a massive surveillance program for the purposes of allowing international businesses to sue our residents; it's being sold as a program to increase our national security. Which it won't do. This act isn't about terrorism, terrorism is just a convenient band-wagon upon which this act was able to hook itself.

I'm ashamed of my governments redaction of non-sensitive information; for their continuing messaging that metadata is innocuous, and for creating such an oppressive mechanism of mass surveillance.
