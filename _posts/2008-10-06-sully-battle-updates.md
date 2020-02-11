---
id: 56
title: Sully Battle Updates.
date: 2008-10-06T03:52:21+00:00
author: mcgrue
layout: post
permalink: /gruedorf/sully-battle-updates/
categories:
  - Gruedorf
tags:
  - Gruedorf
  - Sully
---
### Sully Battle Updates

Too tired right now to give a full dissertation on the week&#8217;s productivity. So instead I&#8217;ll comb through the week&#8217;s Sully SVN commits and post the notable ones. Supersorry.

  * Fixed the sprite parser, removing (hopefully) all tab literals. 
      * Updated the battle hud so that the HP/MP bars worked. 
          * Fixing bugs in the battle menu and the targetting system, both conspiring to cause suck. 
              * Fixed the quantity bug, removed debugging statements. 
                  * Updated the mcgrender engine to clean up more of it&#8217;s shit. 
                      * Making it so enemies always animate on battle start. 
                          * Fixed the queueing problems. Now actions properly have charges and delays. 
                              * Sped up the bounce of the numbers 
                                  * Making it so allies always animate on battle start. </ul> </p> 
                                    So that&#8217;s that. The battle system now, for once, doesn&#8217;t feel &#8216;broken&#8217;. It feels good. Most of what&#8217;s left now is to fill it with content&#8230; which is, one assumes, the &#8220;fun&#8221; part. :)