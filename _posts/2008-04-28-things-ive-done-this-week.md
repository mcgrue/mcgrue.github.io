---
id: 35
title: 'Things I&#8217;ve done this week'
date: 2008-04-28T02:18:19+00:00
author: mcgrue
layout: post
permalink: /gruedorf/things-ive-done-this-week/
categories:
  - Gruedorf
tags:
  - Sully
  - verge3
---
### Things I&#8217;ve done this week

I added 4 new ways for fucntions to be called in verge3: trigger.onStep, trigger.afterStep, trigger.beforeEntityScript, and trigger.afterEntityScript. They are neat, and explained in detail in a <a href=http://www.verge-rpg.com/boards/display_thread.php?id=132010>news post</a> and a <a href=http://www.verge-rpg.com/docs/view.php?libid=1&section=368>new docs page</a>.

Updated Sully using trigger.onStep so in battle zones every step you take decrements the counter until the next battle. When it hits 0, you enter the battle system, and when you exit the battle system the counter is replenished beginning the cycle anew.

I also bound trigger.beforeEntityScript to EntStart() and trigger.afterEntityScript to EntFinish(), and removed every single reference to these functions in map vc. Previously, to make things all kosher, these functions needed to be in every entity&#8217;s function at the top and bottom. So annoying.

Then I fixed up Sully so you could get through a lot more of the game linearly again. Yay! You can presently get up to getting sara to the room with the thermal activators in the chests.

I also have fixed two of the major battle system bugs: the original field music now resumes after a battle, and the renderstack seems to work right after any number of battles (whereas before it would slowly corrupt.)

### Pretty awesome, eh?

You can get the updated Sully <a href=http://www.verge-rpg.com/svn/sully/>in the SVN</a>. Anonymous/Anonymous