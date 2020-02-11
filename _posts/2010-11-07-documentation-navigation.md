---
id: 986
title: Documentation Navigation
date: 2010-11-07T00:40:08+00:00
author: mcgrue
excerpt: foreach( $uncles as $creepy )
layout: post
guid: http://www.egometry.com/?p=986
permalink: /gruedorf/documentation-navigation/
categories:
  - Gruedorf
---
Greetings from the first bay-area mini game-jam, live from [Daniel X. Moore](http://strd6.com/)&#8216;s Palace of Wonders!<div align=center><img src=http://www.egometry.com/i/2010/11/2010-11-07.png alt="" />

  
<a href=http://beta.verge-rpg.com/docs/the-verge-3-manual/general-utility-functions>http://beta.verge-rpg.com/docs/the-verge-3-manual/general-utility-functions</a> </div> 

Today I got the documentation prev/next feature into the codebase. The controller code is a bit on the janky/spaghettiey/incredibly-high-cyclomatic-complexity side, but I&#8217;ve got all of the edges covered and you can walk through the entire documentation system with just the links at the top.

on the up-side, I now have a line of code that reads:

<pre>foreach( $uncles as $creepy ) {
</pre>

&#8230;so that&#8217;s awesome. 

Now I have nothign left to do on the documentation system except the editing/reverting parts. Oh joy.

Committed revision 455, Riding high on the gruedorf leaderboard. Take that, Kildorf.