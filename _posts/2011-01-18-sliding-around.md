---
id: 1089
title: Sliding around
date: 2011-01-18T04:18:11+00:00
author: mcgrue
layout: post
guid: http://www.egometry.com/?p=1089
permalink: /gruedorf/sliding-around/
categories:
  - Gruedorf
---
There was a lot of failure earlier in this gruedorf-week attempting to import verge3&#8217;s obstruction and player movement system into spriteright. That failed a lot. The transliteration of C into javascript largely was mechanical, but the truth of the matter was there was far too much for me to convert at one time before I saw a physical return,so the bugs were legion.

I was impressed how easily I could convert C into javascript, though. And I learned that javascript had bitshifting operators!

I really didn&#8217;t expect that for some reason. Most likely because ints aren&#8217;t supported natively in the language.

At any rate I threw out most of the code and started again anew, and worked towards an obstruction system that I couldn&#8217;t walk through the walls of. And I got there tonight!

Then I started implementing an obstruction system that&#8217;d let me slide around on the diagonals. And I got there tonight!

But the hack I used to get the diagonals-sliding lets you get embedded in and/or walk through walls again. So that&#8217;s got some bugfixing in it&#8217;s future. 

The important part is: it feels fun again, and I made visible progress.

I also implemented an autoexec script for maps upon load (mapinit) and shoved a few setObstructionTile calls in there to make the map easier to navigate (specifically, to make it easier to get into and out of the hut). 

So that&#8217;s neat.

[<img src="http://www.egometry.com/i/2011/01/2011-01-18-0-150x150.png" alt="" title="2011-01-18-0" width="150" height="150" class="aligncenter size-thumbnail wp-image-1097" />](http://www.egometry.com/i/2011/01/2011-01-18-0.png)

[<img src="http://www.egometry.com/i/2011/01/2011-01-18-1-150x150.png" alt="" title="2011-01-18-1" width="150" height="150" class="aligncenter size-thumbnail wp-image-1098" />](http://www.egometry.com/i/2011/01/2011-01-18-1.png)

Press &#8216;O&#8217; to see the obstructions while you play!

<a href=http://spriteright.com>Go see SpriteRight in action!</a>

<a href=https://github.com/mcgrue/js-verge>Or maybe check out it&#8217;s source at github.</a>