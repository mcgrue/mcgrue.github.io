---
id: 700
title: Simpletest, Simple Lessons
date: 2009-02-24T01:20:00+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/248-revision-3/
permalink: /gruedorf/248-revision-3/
---
At <a href="http://imvu.com/" target=_blank>IMVU, we use a suite of testrunners that sit on top of a core of <a href="http://simpletest.org/" target=_blank>Simpletest</a>. It&#8217;s a pretty sweet suite, filled with all sorts of fancy doodads, gewgaws, and the most lovely selenium fixture you ever did see.

However, we haven&#8217;t spent the time yet to pretty the ol&#8217; girl up for public consumption (which we _totally_ should), so on a fool&#8217;s errand I decided to just use the basic core of SimpleTest while developing the third iteration of the <a href="http://beta.verge-rpg.com" target=_blank>verge 2d game engine&#8217;s website</a> (wip). 

I didn&#8217;t know what I got myself into. 

Here&#8217;s some hard-earned knowledge I wrestled from the core of this beasty. These simple statements represent hours of shouting, grunting, and crying defiantly into the rain-filled sky daring a cruel god to strike me down.

## SimpleTest Lessons

<span style="font-size: 250%">1.</span> assertFieldById() and assertFieldByName() do not work on html input elements which are improperly placed outside of <form> tags.

<span style="font-size: 250%">2.</span> There do not appear to be out-of-the-box accessors for field values. I had to code up my own getFieldById().

<span style="font-size: 250%">3.</span> If an element has an id, but not a name, it&#8217;s value will be inaccessible.

Learn these lessons, fair reader, so that you may not stub thy code-toe upon SimpleTest! And one day maybe we&#8217;ll get around to releasing IMVU&#8217;s Sweet Suite of Not-So-Simpletest. 

<div style="font-size: 80%; color: silver;">
  Apologies for a lack of bloodposting for the past few days. I was deathly ill and moving to San Francisco with <a href="http://timothyfitz.wordpress.com/" target=_blank>some guy</a> all at once.
</div>