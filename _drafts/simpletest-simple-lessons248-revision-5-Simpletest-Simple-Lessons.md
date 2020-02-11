---
id: 702
title: Simpletest, Simple Lessons
date: 2009-02-24T01:25:52+00:00
author: mcgrue
excerpt: 'Learn these lessons, fair reader, so that you may not stub thy code-toe upon SimpleTest! '
layout: revision
guid: http://www.egometry.com/gruedorf/248-revision-5/
permalink: /gruedorf/248-revision-5/
---
At <a href="http://imvu.com/" target=_blank>IMVU</a>, we use a suite of testrunners and enhancements that sit on top of a core of <a href="http://simpletest.org/" target=_blank>Simpletest</a>. It&#8217;s a pretty sweet suite, filled with all sorts of fancy doodads, gewgaws, and the most lovely selenium fixture you ever did see. Convenience pours out of it&#8217;s every pore, as put there by scores of engineers over literally pairs of years.

However, we haven&#8217;t spent the time yet to pretty the ol&#8217; girl up for public consumption (which we _totally_ should), so I decided to just use the basic core of SimpleTest while developing (as a personal project) the third iteration of the <a href="http://beta.verge-rpg.com" target=_blank>verge 2d game engine&#8217;s website</a> (wip). 

I didn&#8217;t know what I got myself into. 

Here&#8217;s some hard-earned knowledge I wrestled from the core of this beasty. These simple statements represent hours of shouting, grunting, and crying defiantly into the rain-filled sky daring a cruel god to strike me down.

## SimpleTest Lessons

<span style="font-size: 250%">1.</span> <span style="font-family: monospace;">assertFieldById()</span> and <span style="font-family: monospace;">assertFieldByName()</span> do not work on html input elements which are improperly placed outside of <span style="font-family: monospace;"><form></span> tags.

<span style="font-size: 250%">2.</span> There do not appear to be out-of-the-box accessors for field values. I had to code up my own <span style="font-family: monospace;">getFieldById()</span>.

<span style="font-size: 250%">3.</span> If an element has an id, but not a name, it&#8217;s value will be inaccessible.

<i style="color: silver;">This list is not exhaustive</i>

Learn these lessons, fair reader, so that you may not stub thy code-toe upon SimpleTest! And one day maybe we&#8217;ll get around to releasing IMVU&#8217;s Sweet Suite of Not-So-Simpletest. 

<div style="font-size: 80%; color: silver;">
  Apologies for a lack of bloodposting for the past few days. I was deathly ill and moving to San Francisco with <a href="http://timothyfitz.wordpress.com/" target=_blank>some guy</a> all at once.
</div>