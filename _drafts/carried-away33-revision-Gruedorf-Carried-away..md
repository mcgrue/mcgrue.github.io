---
id: 132
title: 'Gruedorf: Carried away.'
date: 2008-10-20T00:30:59+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/?p=132
permalink: /gruedorf/33-revision/
---
Another postlet: Instead of composing a big old fancy blog entry, i sorta got sucked into coding of various kinds. Been at this chunk of work for almost a full workday in hours now. Some people play videogames for fun. I work on a decade-old tech demo.

First item: I added a seperate windowsize verge.cfg variable for x/y on top of the &#8220;screen size&#8221;. Say you want your game to be 320&#215;240, but want it to run in windowed mode. Every single computer that runs verge3 will have a minimum res of 800&#215;600, and even that&#8217;s small for the majority. automax makes an ugly-ass screen with lots of jaggies, and fullscreen mode isn&#8217;t guarunteed to be a square aspect ratio in this age of LCDs (320&#215;240 on a 1280&#215;1024 native res LCD looks like _ass_ in fullscreen.) So I added new variables to give you a playable window port of 640&#215;480 (or whatever you specify, really) so you can have your perfect aspect ratio and remain windowed. Whee!

Next item: I did a hella lot of scripting of the Lance stuff on Mt. Jujube. Yay for scripting!

As usual, go check it out at the <a href=http://www.verge-rpg.com/svn/sully/trunk/>svn repo</a> if you&#8217;d like. Username and password both &#8220;anonymous&#8221;, as usual.

I&#8217;m going to bed now. Some of us have to work in very, very scant hours :(