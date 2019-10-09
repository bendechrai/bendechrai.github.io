---
layout: post
title: "PHP Usage Stats"
Slug: php-usage-stats
date: 2006-03-13 22:50:42
tags: [Hosting,Open Source,Random,Uncategorized,Work Life]
---
I was challenged to justify my position this morning, that PHP is a popular programming language.

Unfortunately, I didn't have figures in my head, and the other person told me that Sourceforge had 12,000 Java projects, and only 2,000 PHP projects.

This post is my attempt to pull together a whole load of stats on various programming languages.

My first jump from [google's search results](http://www.google.com/search?q=php+usage+stats) was to [TIOBE Programming Community Index](http://www.tiobe.com/tpci.htm), which lists programming languages based on the availability of skilled engineers, courses and third party vendors - a good indicator of the way the market is going.

TOIBE, as of today, report:

<table><tr><th>Position  
Mar 2006</th><th>Position  
Mar 2005</th><th>Delta  
in Position</th><th>Programming Language</th><th>Ratings  
Mar 2006</th><th>Delta  
Mar 2005</th><th>Status</th></tr><tr height="25"><td>1</td><td>2</td><td align="center">Up</td><td>Java</td><td align="center">21.889%</td><td align="center">+3.01%</td><td align="center">A</td></tr><tr height="25"><td>2</td><td>1</td><td align="center">Down</td><td>C</td><td align="center">17.794%</td><td align="center">-1.67%</td><td align="center">A</td></tr><tr height="25"><td>3</td><td>3</td><td align="center">Same</td><td>C++</td><td align="center">11.159%</td><td align="center">-0.47%</td><td align="center">A</td></tr><tr height="25"><td>4</td><td>4</td><td align="center">Same</td><td>PHP</td><td align="center">9.948%</td><td align="center">+0.53%</td><td align="center">A</td></tr><tr height="25"><td>5</td><td>6</td><td align="center">Up</td><td>Basic</td><td align="center">9.892%</td><td align="center">+2.99%</td><td align="center">A</td></tr><tr height="25"><td>6</td><td>5</td><td align="center">Down</td><td>Perl</td><td align="center">6.421%</td><td align="center">-2.73%</td><td align="center">A</td></tr><tr height="25"><td>7</td><td>7</td><td align="center">Same</td><td>C#</td><td align="center">3.146%</td><td align="center">+0.61%</td><td align="center">A</td></tr><tr height="25"><td>8</td><td>8</td><td align="center">Same</td><td>Python</td><td align="center">3.093%</td><td align="center">+0.66%</td><td align="center">A</td></tr><tr height="25"><td>9</td><td>9</td><td align="center">Same</td><td>Delphi/Kylix</td><td align="center">1.843%</td><td align="center">-0.29%</td><td align="center">A</td></tr><tr height="25"><td>10</td><td>11</td><td align="center">Up</td><td>JavaScript</td><td align="center">1.733%</td><td align="center">+0.08%</td><td align="center">A</td></tr><tr height="25"><td>11</td><td>12</td><td align="center">Up</td><td>SAS</td><td align="center">1.337%</td><td align="center">+0.07%</td><td align="center">A</td></tr><tr height="25"><td>12</td><td>10</td><td align="center">Down 2</td><td>PL/SQL</td><td align="center">0.990%</td><td align="center">-0.68%</td><td align="center">A</td></tr></table>It looks, according to these results, that PHP will soon take 3rd place from C++ in the "market demand" arena, while Java and C battle out for first, with twice the demand each.

While [PHP's own stats](http://www.php.net/usage.php) show a steady increase in the usage of PHP, it's not obvious whether the graph indicates the number of installations of PHP, or actual usage. It might be argued that the two are approximately equal, as a shared hosting provider might install PHP once for all users of a single IP address, and many users would use PHP. This might balance out the dedicated servers that have PHP installed but run no applications that use PHP. In following their link to the [NetStats Survey](http://news.netcraft.com/archives/web_server_survey.html), from where these resutls are apparently taken, I was unable to find any information relating to PHP usage anywhere on the site.

Just for a bit of fun (and yes, this only counts web based language usage, sort of) I asked google how many php, asp, aspx and jsp pages it had in its index:

php: 1,360,000 asp: 277,000 jsp: 25,000 aspx: 13,500

Note: those numbers probably mean nothing! There may be 42,309,194 asp pages hidden from search engines. Developers might be naming their jsp files .php to confuse attackers.

Do you have any other stats sources?
