---
id: 80
title: 'Gruedorf: The Rendtest Cometh.'
date: 2008-10-20T00:11:45+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/?p=80
permalink: /gruedorf/7-revision/
---
### Gruedorf: The Rendtest Cometh.

<div style="float: right; padding: 4px; margin: 4px;">
  <img src=/files/gruedorf_challenge/002/2007-10-21_0_science!.png alt="Castle Alden has so many bubbling flasks it could pass for Castle Aldenstein."><br /><span style="color: silver; font-size: -1;">&#8230;and technology!</span>
</div>

It&#8217;s that time again, entry 002 into the gruedorf challenge. Things have picked up in this challenge, with ragamuffin me-tooers joining left and right. Of course&#8230; none of them get top billing because they are neither &#8216;grue nor &#8216;dorf. Or using verge, for that matter. Tsk, tsk. Well&#8230; maybe we could make it the Gruedorf Code Challenge, since <a href=http://codesgame.3host.biz/wordpress/ target=_new>Code</a> totally is using verge, and he has a suitably confusing nick. I guess to disambiguate we&#8217;d then have to make it the GrueDorf-Code Code Challenge. You know. For that ironic sort of disambiguation.

But I digress.

<div style="float: left; padding: 4px; margin: 4px;">
  <img src=/files/gruedorf_challenge/002/2007-10-21_1_rendtest.png alt="Debug statements as eyecandy. Consider this the gameart equivalent of brutalism."><br /><span style="color: silver; font-size: -1;">that slime is totally from sully. Thank Overkill.</span>
</div>

My current update is a few hours of work into improving and debugging my vc-based Render Engine, lovingly known as the McGrender Engine. Currently in it&#8217;s 5th version (#4 is in the current build of Sully), it allows for custom auto-animated sprites, static images, or &#8220;roll your own&#8221; functions (ie, Callfuncs that get triggered when they&#8217;re up on the stack). All this is put into layer functionality so you can turn on/off layers as needed, and, say, render fancy effects between your background and your sprites, or just effect the PC sprite layer while not touching the enemy sprite layer. Etc.

Also in here is bubbling click items. Any image on in the McGrender system can be given clickable properties with a bubble-down effect: that is, if you had three clickable items layered on top of each other, you&#8217;d only activate the topmost visible clickable item.

The most notable virtue of the McGrender System in this demo is it&#8217;s automoving feature&#8230; which, as trivial as it is, is the reason I made mk I a few years ago. I just wanted to throw a sprite that, while animating, would move it&#8217;s location at an even rate without me having to worry about it after setting it. Unfortunately, non-linear movements presently need a custom function (whereas an OOP system could have some custom, but more reusable, implementation of the &#8220;Hey, I move in some way!&#8221; concept), but that&#8217;s fine.

Another small, but handy, feature that lets this bitch be largely hassle-free in keeping itself moving is the optional &#8220;OnStopMoving&#8221; callback function. You can see this in effect in the demo with the close-button&#8217;s movement. Everytime it stops, the rebounceX() function is called setting new destination coordinates and sending it on it&#8217;s merry way.

### Instructions for seeing this in action

Okay, if it wasn&#8217;t apparent from the screenshots, talking to any of the flasks in the first room will start you into the rendertest demo. For the interested, the pertinent code is all in ./vc/rend/ with the mcgrender.vc and sprite.vc being the &#8220;system&#8221; files, and test_render.vc being the implementation of this demo (ignore general.vc in that dir&#8230; that was me being laaaazy).

once you&#8217;re in the demo, you can click on the slime to watch a demo of the sprite-autohandler (changing from &#8220;idle&#8221; to &#8220;death&#8221;) being triggered by the clickable feature, and clicking on the floating winXP &#8220;X&#8221; will stop the render engine demo, whereupon you can talk to a flask ans start it over. Exciting!

<a href=/files/gruedorf\_challenge/002/sots\_2007-10-21_002.rar>Click here to download the second Gruedorf release of Saga of the Stars/The Astrad</a>. You&#8217;ll be glad you did&#8230; probably!

### One last thing: new music!

Zathras was inspired to make the fourth major revision to Castle Alden&#8217;s music, which is far and away the best version to date. It&#8217;s much more soothing and gentle on the ears, and has a lot more in common with both Onam&#8217;s Theme and Amin&#8217;s theme. Nice! You can also check out <a href=http://www.zath.org target=_new>Zathras/Matthew Steele&#8217;s Homepage at the newly minted zath.org</a>. Good times.