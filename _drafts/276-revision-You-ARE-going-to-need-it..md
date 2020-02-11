---
id: 277
title: You ARE going to need it.
date: 2008-12-11T01:53:52+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/276-revision/
permalink: /gruedorf/276-revision/
---
I&#8217;ve written so many tests around this feature&#8230; surely I can let this one, tiny clause slip?

## Test coverage is good.  And you _are_ going to need it.

Sure, the way the program&#8217;s currently structured makes covering this seam a pain.  Why not let it slip, you ask?  Why restructure everything just to prove that this thing that never, ever could possibly fail is covered?

Because it will.  Oh dear god, it will.  Like love, failure will find a way.

Let&#8217;s put aside the fact that if you have critical behavior that&#8217;s hard to test, you probably are _doing it wrong*_._ _Eventually, one day, Someone will come along and make a change.  And that Someone will change your code.  Since it&#8217;s got test coverage around it&#8217;s functionality, they&#8217;ll feel all safe and snug in their little blanket and mung your code (for better or for worse) and then, when all your old tests pass they will pat themselves on the back and breathe easy. 

They will probably go get a beer and tell their buddies about the terrible code they just had to refactor.

And _they&#8217;ll be right__!_  Your code was terrible!  Because you left this untested, critical seam in a field of other tests, and it is now red.  Your negligence has caused the worst kind of red, too: the red that isn&#8217;t there blocking anyone.  It is invisible.  You&#8217;ve made an _infra_-red test.

## You are going to need it.

 

* by the way, you shouldn&#8217;t put this aside.  If you can&#8217;t test something easily, _you are doing it wrong_.