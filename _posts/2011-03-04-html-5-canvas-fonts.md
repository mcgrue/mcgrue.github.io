---
id: 1128
title: HTML 5 Canvas Fonts
date: 2011-03-04T00:27:41+00:00
author: mcgrue
layout: post
guid: http://www.egometry.com/?p=1128
permalink: /gruedorf/html-5-canvas-fonts/
categories:
  - Gruedorf
---
I took a small break from the menus to work on the fonts problem. Specifically, each browser renders the fonts in canvas differently. I attempted to solve the problem by using a pixel font (I grabbed <a href=http://dsg4.com/04/extra/bitmap/>04b08Regular</a> and made it into a font kit with <a href=www.fontsquirrel.com>FontSquirrel</a>) but&#8230; apparently no dice.

It really looks like I&#8217;m going to have to do spritesheet font blitting. It&#8217;s a shame that the &#8220;HTML is awesome for UI!!!&#8221; solution doesn&#8217;t actually work for me in this case (it works when you can embed a single browser as a downloadable, not when you have to support them all ;( )

The menu work goes slowly but surely. I&#8217;m poking functions around and playing with their structure. Hopefully I stop pushing the peas around my plate sometime soon.

I met Kildorf in the flesh today. He had some excuse about a flooded house for not working on his cool mapeditor. Whatever, my Gruedorf win ratio is now 50.0%. Climbing my way back into the majority a fractional percentage point at a time.