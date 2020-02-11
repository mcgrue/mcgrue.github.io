---
id: 241
title: Roughing up the clam
date: 2008-11-27T12:26:51+00:00
author: mcgrue
layout: post
guid: http://www.egometry.com/?p=241
permalink: /gruedorf/roughing-up-the-clam/
categories:
  - Gruedorf
---
This week&#8217;s changes are all to Sully. There was a lot of refactoring (mainly of the mundane folder-moving variety), where I killed the redundant ./res/battle/ dirtree and moved it&#8217;s inhabitants all into various folders under ./res/image/battle/. This was mainly to make Gayo and I a small amount saner. 

Also tracked down and fixed were various issues around the textbox. An issue had arisen where you&#8217;d constantly reactivate a textbox event that was triggered by adjacent activation with the same keypress you&#8217;d hit to leave the textbox. That was solved with an Unpress(); at the bottom of the inner textbox-handling function.

Another major error was tracked down and solved where, in the jujube sign-blowy-up scene, the game would refuse to move past a certain textbox. The problem was that I switched the HookRetrace function to do some animation there, and the new retrace function (VictoryDance()) didn&#8217;t call the old on inside of it (V1RPG\_RenderFunc()), and V1RPG\_RenderFunc() is responsible for updating the state of keypresses. So the textbox right after the switch to HookRetrace(&#8220;VictoryDance&#8221;); had no way of exiting out.

Fun times.

Next up is a sully battle system bug that&#8217;s been bugging (ha, groan, etc) me for a while, where any PC battle actor other than Darin/Crystal sorta&#8230; blows up. This looks mainly to be a case of bad indexing in places to track down, because everything works right when slot indexes 0 and 1 are filled with cast indexes 0 and 1, but go to shit when slot index 0 contains cast index 3, for example.