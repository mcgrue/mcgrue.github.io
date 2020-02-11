---
id: 34
title: 'Sparse post #3'
date: 2008-04-21T02:06:56+00:00
author: mcgrue
layout: post
permalink: /gruedorf/sparse-post-3/
categories:
  - Gruedorf
tags:
  - Sully
---
For the third time in a row we&#8217;ve got a very dull posting! Boo!

But that doesn&#8217;t mean I wasn&#8217;t productive! Scanning the svn logs shows an assload of work, including adding a massive amount of scripting into jujube (Lance&#8217;s mountain cutscene stuff and the seal of evil) as well as map tweaking, some cleanup to the cave, and solving one of the major issues with the battle system breakage problems. Namely, I&#8217;d recentyl changed from tabs to spaces in the files, and that inadvertantly broke a bit of the BattleMenu parsing functionality since it had tab-literals involved in the code. The solution there was to use chr(9) instead. Whee.

Anyways, That&#8217;s the score, Alan Moore. I&#8217;ll be doing more Battlesystem fixing in the next few posts. Maybe I&#8217;ll even take screenshots.

In case anyone&#8217;s interested in seeing this week&#8217;s work, my Arch-Nemesis made a <a href=http://www.verge-rpg.com/boards/display_thread.php?id=131996>vrpg post</a> highlighting it, and went through the trouble of making new mac and windows zips of Sully. It&#8217;s worth noting that Kildorf, Gayo, and Myself didn&#8217;t let a single day this week pass without SVN commits to the project. Momentum has been achieved, mofos!