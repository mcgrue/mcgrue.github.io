---
id: 75
title: 'Gruedorf: If you should strike me down&#8230;'
date: 2008-10-20T00:07:23+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/?p=75
permalink: /gruedorf/52-revision/
---
### Gruedorf: If you should strike me down&#8230;

<div style="float: right; padding: 4px; margin: 4px;">
  <img src="http://www.egometry.com/files/gruedorf_challenge/044/gruedorf-2008-09-04_dont_make_me_hit_you.png" /></p> 
  
  <div align="center">
    <span style="color: silver; font-size: -1;"><br /> <br />don&#8217;t eat the yellow tile.</div> </div> 
    
    <p>
      So, I just added a global entity colission trigger to verge 3. If you set the global string trigger.onEntityCollide equal to a vc function, whenever an entity runs into an obstruction that function will be called.
    </p>
    
    <p>
      It sets the following variables:
    </p>
    
    <li>
      event.tx and event.ty are the tile coodinates hit. <li>
        event.entity is the entity who did the hitting. <li>
          event.zone is the zone of the tile being struck, as long as it was a tile obstruction being hit. Otherwise, -1. <li>
            event.entity_hit is entity index of the entity being hit, as long as it was an entity-on-entity collision. Otherwise, -1. </p> <p>
              This facilitates pushing entities around, and zelda-like tool use, and entities reacting to their environment in general. Basically everything that people generally hijack verge&#8217;s native movement system for. So, yeah.
            </p>
            
            <p>
              This feature is as of r244 of <a href=http://www.verge-rpg.com/svn/verge3/>http://www.verge-rpg.com/svn/verge3/</a>. I haven&#8217;t fully announced it yet as I&#8217;m sure there are bugs and &#8220;bugs&#8221; in here (for instance, NPCs don&#8217;t collide with the player yet because that was apparently never permitted in the first place?). However, I really would like some feedback since this is a feature that lets everyone stop hijacking control from verge and gives the power back to the people. Or stuff.
            </p>
            
            <p>
              <a href="http://www.egometry.com/files/gruedorf_challenge/044/crash_handler_demo.rar">Download the demo here!</a>
            </p>