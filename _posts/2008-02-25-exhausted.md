---
id: 26
title: Exhausted.
date: 2008-02-25T05:57:54+00:00
author: mcgrue
layout: post
permalink: /gruedorf/exhausted/
categories:
  - Gruedorf
tags:
  - sots
  - testing
---
### Tacos

Unsettle deliberate banana-farm elitist monster bone. Disgusting foodstuff edible taco taco burrito not because good word thing.

### Er, wait.

A little discombobulated. Today&#8217;s update is a low water mark for myself consisting of a new chr which is just a recolored semi-spoiler and some scant tests for the sully system.

### svn download

Oh my goodness, <a href=http://www.verge-rpg.com/svn/sots/>http://www.verge-rpg.com/svn/sots/</a>. Whee link.

### Oh right&#8230;

Also, for those keeping score at home, I actually did make a surrogate post last week over at <a href=http://www.verge-rpg.com/boards/display_thread.php?next=1&id=131924>The verge-rpg.com forums</a>. This was because I foolishly let my dear, sweet egometry.com unregister, and I had to hastily repurchase it. While I got the domain back, the DNS was all bjorked for a bit, so I couldn&#8217;t reach this place to post.

### Last week, regurgitated.

Added vctest.vc, which introduces a vc testing suite.

Basically: you create any number of functions in the system.vc space that start with "test" and have no args and return void. In those functions you must have one or more assertTrue and/or assertFalse functions. Call runtests(), and all your tests will run. 

If anything fails, the program will exit.

Exciting, eh?