---
id: 1082
title: Tuning Canvas Javascript in Firefox 4
date: 2011-01-11T02:46:10+00:00
author: mcgrue
layout: post
guid: http://www.egometry.com/?p=1082
permalink: /gruedorf/tuning-canvas-javascript-in-firefox-4/
categories:
  - Gruedorf
tags:
  - javascript canvas
---
My friend [Kevin](http://www.luminance.org/inferusgame) took an interest in why [SpriteRight](http://spriteright.com) was performing so poorly in Firefox 4, since it has hardware acceleration. 

So after cracking open his profile and bothering the firefox developers themselves a bit (Kevin takes his debugging seriously) he found that my tilesheet was stupidly formed: it was over 20,000 pixels long and so was much, much larger than a texture can be on a modern video card. This was forcing the renderer to always be in software rendering mode.

When I was dumping the data out of verge, this was not something I was thinking about.

So, at his suggestion, I made the tileset filmstrip into a more traditional atlas-style spritesheet, and after a few nips and tucks in the engine, rendering speed went from less than 10 FPS to over 70 fps on firefox 4! Yay!

(Firefox 3 gained nothing. Boo.)

Anyways, that was all well and good, until Kevin tried toggling the obstruction layer&#8217;s visibility. At which point FF4 dropped back to 10fps. This made no sense to me, because the marginal cost of rendering that layer would&#8217;ve been another 33% (it basically just added another layer to the renderer).

The trick was the obs layer rendered using the &#8216;lighter&#8217; compositeOperation, which was causing the dramatic slowdown, even on accelerated cards. I&#8217;ve opted to turn that off for now.

Thanks for the help, Kevin!