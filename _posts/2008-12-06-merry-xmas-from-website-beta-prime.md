---
id: 269
title: 'merry xmas, from website beta prime&#8230;'
date: 2008-12-06T17:28:24+00:00
author: mcgrue
layout: post
guid: http://www.egometry.com/?p=269
permalink: /gruedorf/merry-xmas-from-website-beta-prime/
categories:
  - Gruedorf
tags:
  - simpletest
  - verge-rpg
---
This last week has been light on the gruedorfing and more heavy on the drinking.  Oh, when will I learn?

Several hours of work, however, were invested into investigating why I couldn&#8217;t get variables from simpletest by id.  To make a long story short, form element values in simpletest won&#8217;t be accessible if the element you want is in a malformed <form>.  In this case, there was no form tag at all, and so I was SOL until I tried actually making my html valid.

Feh.  _Valid_ HTML.

Anyways, now the insidious bastard that was test\_admins\_can\_edit\_anything() passes.  Revisions 161 and 162 of the beta vrpg codebase happened this week.  I believe this is the last of my major infrastructure blocks, now, so the rest of the forums tests should go much quicker next time I sit down and tackle fleshing out the functionality.