---
id: 54
title: Smash and Edit
date: 2008-09-21T05:46:31+00:00
author: mcgrue
layout: post
permalink: /gruedorf/smash-and-edit/
categories:
  - Gruedorf
tags:
  - maped
  - verge3
---
### Smash and Edit

<div style="float: right; padding: 4px; margin: 4px;">
  <a href="http://www.egometry.com/files/gruedorf_challenge/046/2008_09_21_crash_handler_demo_big.png"><br /> <img src="http://www.egometry.com/files/gruedorf_challenge/046/2008_09_21_crash_handler_demo_thumb.png" /></a></p> 
  
  <div align="center">
    <span style="color: silver; font-size: -1;"><br /> <br />Pushing things around<br /> is fun!<br /><span style="color: silver; font-size: -2;">(click image to biggify)</span></span>
  </div>
</div>

This week&#8217;s gruedorf challenge is a day late but at least 19.95 over. First up is a prototype of the reason I put in the entity collision event: A block-pushing demonstration! While it&#8217;s not quite &#8220;there&#8221;, I&#8217;m amused by the demo. I expected to have to do a little more work to get non-player entities to interact with each other, but the way I coded it up worked right on the first attempt!

Unfortunately the handling acts in peculiar ways, mainly due to the fact that I&#8217;m using <span style="font-family: Courier; background-color: #AAA;">playerstep = 16;</span> to fake tile-based movement. I initially thought that playerstep would effect all entities, but ha&#8230; look at the name again, sucker! I&#8217;m tiring of how verge always handles player-entities as a super-special case from regular entities. They should all be one and the same but for where their marching orders are coming from, maaan.

There will be more developments on this front in the near future. Don&#8217;t worry, Glambo. Your [two cents](http://www.verge-rpg.com/boards/display_thread.php?next=1&id=132162) have not fallen on deaf piggy banks.

### Old dog, new code.

<div style="float: left; padding: 4px; margin: 4px;">
  <a href="http://www.egometry.com/files/gruedorf_challenge/046/2008_09_21__IN_V3_MAPED_big.png"><img src="http://www.egometry.com/files/gruedorf_challenge/046/2008_09_21__IN_V3_MAPED_thumb.png" /></a></p> 
  
  <div align="center">
    <span style="color: silver; font-size: -1;"><br /> <br />I&#8217;ve invented maped1!<br /><span style="color: silver; font-size: -2;">(click image to embiggen)</span></span>
  </div>
</div>

Today&#8217;s second verge-based miracle is Maped 1. In verge 3. In VC. Well, not quite fully functional seeing as it can&#8217;t load or save maps, and not really maped1 since its tiles are 32&#215;32 and based off of pngs in the ./tile/ directory instead of a real vsp, but&#8230; SHUT UP OKAY.

This project came about from a long-standing desire for a mapeditor in-code in vc, a desire to find a use for overkill&#8217;s widget library, and a need for a map editor for my iPhone games projects. I don&#8217;t have much intent to build this past my needs there, but I have been building it fairly generically, so it could be updated for 16&#215;16 tiles easily&#8230; so if anyone wants to come along and write v3 loaders and savers in vc, well, hell, we could surely use&#8217;m ;)

### [Download the Block Pushing Demo here](http://www.egometry.com/files/gruedorf_challenge/046/2008_09_21_crash_handler_demo.rar).

### [Download the Map Editing Demo here](http://www.egometry.com/files/gruedorf_challenge/046/2008_09_21__IN_V3_MAPED.rar).

As far as the mapediting goes, select &#8220;New Map&#8221;, enter a garbage string as the name, and two positive ints between 1 and 100 for the size. When in the map editing mode, &#8216;A&#8217; and &#8216;Z&#8217; scroll the left click button&#8217;s selected tile up and down, and &#8216;S&#8217; and &#8216;X&#8217; scroll the right click button&#8217;s selected tile up and down. Clicking left or right on a tile will paint, and holding &#8216;CTRL&#8217; while left or right clicking will &#8216;eyedropper&#8217; the tile you click on into the button&#8217;s slot you clicked with.