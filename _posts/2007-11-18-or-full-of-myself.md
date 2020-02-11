---
id: 13
title: '&#8230;or full of myself!'
date: 2007-11-18T20:07:04+00:00
author: mcgrue
layout: post
permalink: /egometry/or-full-of-myself/
categories:
  - egometry
tags:
  - astrad
  - maped
---
### &#8230;or full of myself!

<div style="float: right; padding: 4px; margin: 4px;">
  <a href=/files/gruedorf_challenge/006/2007-11-18_0-ontaran_obs_full.png target=_new><img src=/files/gruedorf_challenge/006/2007-11-18_0-ontaran_obs.png alt="The Ontaran Caves, now diagonified for your sliding pleasure."></a><br /><span style="color: silver; font-size: -1;">A view of maped3 showing the obs.<br /><a href=/files/gruedorf_challenge/006/2007-11-18_0-ontaran_obs_full.png target=_new>click to biggify</a></span>
</div>

Okay, so in keeping with tradition, as soon as I make a boastful claim of future work, I of course don&#8217;t get to complete it. However, since I have many years of experience with this sort of phenomenon, I kept the boastful claim REALLY SMALL and still got work done towards it. However, you&#8217;re all going to have to make due with more map maintenence for now.

Today&#8217;s precious update is the Ontaran Mines, which is the last zone before you exit Alden Kingdom. The base of this map was first seen by the public in a bunch of public domain tilesets I released a few years ago. I was going to redo the entire cave sequence, but I decided that, although the layout was a bit flat, it was something I could work with&#8230;

### Doctor TwopointohLove

#### (or: how I learned to stop worrying and love rounded corners)

<div style="float: left; padding: 4px; margin: 4px;">
  <img src=/files/gruedorf_challenge/006/2007-11-18_1-ontaran_before_roundification.png alt="A shake for breakfast, a shake for lunch..."><br /><span style="color: silver; font-size: -1;">TEH WIRLD IZ SKWARE</span>
</div>

One of the main problems with this map&#8217;s original incarnation was it&#8217;s harsh 90-degree corners. If you open up the old version (which isn&#8217;t in the svn, and I can&#8217;t currently find in the repo (goddamnit)), you&#8217;ll notice it&#8217;s mainly just twisty 90-degree passages. Visually dull, annoying to navigate, and really kinda flat. BAD!

<div style="float: right; padding: 4px; margin: 4px;">
  <img src=/files/gruedorf_challenge/006/2007-11-18_2-ontaran_after_roundification.png alt="...and then a sensible dinner!"><br /><span style="color: silver; font-size: -1;">Enter: the Corner.</span>
</div>

The solution to this first visual issue was to use the already-existing diagonal wall pieces gratuitously. with the addition of a very small number of new transition tiles (something like 6 new tiles), I managed to soften the harsh edges, diversify the number of shapes on the screen, and overall improve the boring parts of the map a few hundred percent. Once I was done smoothing out the maze, I created a new obstruction tileset, and made everything utilize v3&#8217;s diagonal-slidey abilities (see first screenshot of the post) which is one of the stupidly fun things there is while walking around. Who knew sliding across a wall would be so fun?

This map has a lot to go before it&#8217;s done, too, but the initial changes are a good start. I hate it several orders of magnitude less already!

In other news, I&#8217;ve been using a debug version of maped3 running from Visual Studio itself, which has been fairly illuminating. I&#8217;ve fixed two bugs so far&#8230; which is about a hundred less bugs than <a href=http://thespeedbump.livejournal.com/>Andy&#8217;s</a> fixed in it lately.

### As always: the goods

In full accordance to the grutopian policy of full disclosure, today&#8217;s updates can be seen (as always) in the svn. Remember: user and password are both &#8220;anonymous&#8221;!

<a href=http://www.verge-rpg.com/svn/sots/>http://www.verge-rpg.com/svn/sots/</a> &#8211; the Astradian Repositorium!