---
id: 271
title: 'merry xmas, from website beta prime&#8230;'
date: 2008-12-06T17:28:13+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/269-revision-2/
permalink: /gruedorf/269-revision-2/
---
This last week has been light on the gruedorfing and more heavy on the drinking.  Oh, when will I learn?

 

Several hours of work, however, were invested into investigating why I couldn&#8217;t get variables from simpletest by id.  To make a long story short, form element values in simpletest won&#8217;t be accessible if the element you want is in a malformed <form>.  In this case, there was no form tag at all, and so I was SOL until I tried actually making my html valid.

Feh.  _Valid_ HTML.

Anyways, now the insidious bastard that was test\_admins\_can\_edit\_anything() passes.  Revisions 161 and 162 of the beta vrpg codebase happened this week.  I believe this is the last of my major infrastructure blocks, now, so the rest of the forums tests should go much quicker next time I sit down and tackle fleshing out the functionality.