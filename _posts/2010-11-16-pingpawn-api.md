---
id: 997
title: PingPawn API
date: 2010-11-16T01:56:09+00:00
author: mcgrue
excerpt: 'And broken he should be, because he was a 30-minute <a href=http://inamidst.com/phenny/>phenny</a> hack until the last straw broke tonight and I tore out the old guts, built a proper json-spewing, RESTful HTTP API on the website, and made the bot consume said API.'
layout: post
guid: http://www.egometry.com/?p=997
permalink: /gruedorf/pingpawn-api/
categories:
  - Gruedorf
---
On of my side projects, a [Social Quotefile](http://pingpawn.com) named PingPawn, fuels an [irc bot](https://github.com/mcgrue/sexymans) named [sexymans](http://twitter.com/sexymans). Amoung other places, it sits in my IRC channel, #sancho (irc.lunarnet.org). The denizens of that channel liked to point out that sexymans was, quite often, broken.

And broken he should be, because he was a 30-minute <a href=http://inamidst.com/phenny/>phenny</a> hack until the last straw broke tonight and I tore out the old guts, built a proper json-spewing, RESTful HTTP API on the website, and made the bot consume said API.

I did this mainly because I wanted to, but slightly because after a few googles I couldn&#8217;t find an elegant way to write preparedStatements for mysql in python. Fuck the MySQLDB module.

Anyways, here&#8217;s the current API. (only GET requests as of this writing.)  
<a href="http://pingpawn.com/api/rand" rel=nofollow>http://pingpawn.com/api/rand</a> &#8211; Get a random quote  
<a href="http://pingpawn.com/api/rand/grue" rel=nofollow>http://pingpawn.com/api/rand/grue</a> &#8211; Get a random quote from a specific quotefile (in this case the &#8216;grue&#8217; quotefile (mine))  
<a href="http://pingpawn.com/api/search?q=ATTEMPT+to+not+be+a+chump" rel=nofollow>http://pingpawn.com/api/search?q=ATTEMPT+to+not+be+a+chump</a> &#8211; Search for quotes that match a certain phrase (a random quote from the set of all that match).  
<a href="http://pingpawn.com/api/search/grue?q=fire" rel=nofollow>http://pingpawn.com/api/search/grue?q=fire</a> &#8211; Search for quotes that match a certain phrase from a certain quotefile (a random quote from the set of all that match).  
<a href="http://pingpawn.com/api/search/grue/2?q=fire" rel=nofollow>http://pingpawn.com/api/search/grue/2?q=fire</a> &#8211; Search for quotes that match a certain phrase from a certain quotefile, deterministically (this is the second quote in this quotefile that matches, and always will be.)

So that&#8217;s that.

I also deployed a new version of VERGE-RPG.com last night, and fixed up a few of the bug reports this evening. Yay Gravitars and BBCode!

As far as [GrueDorf](http://www.johnweng.com/gruedorf/) goes, I think this is my third successive night in a row of posting and of doing far more than an hour&#8217;s worth of work. Meanwhile, my arch-nemesis Kildorf appears to have failed to do a single hour&#8217;s worth of project work all week&#8230;