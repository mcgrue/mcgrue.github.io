---
id: 182
title: Anti-ninja Parade
date: 2008-10-20T00:25:30+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/24-revision-3/
permalink: /gruedorf/24-revision-3/
---
### Anti-ninja Parade.

<div style="float: right; padding: 4px; margin: 4px;">
  <p>
    <img src=/files/gruedorf_challenge/017/2008-02-04_0-its_walky!.png ><br /> <span style="color: silver; font-size: -1;"><br /> <br />Dance, varmints!</span></div> 
    
    <p>
      I finished up Erikk, basing his cape&#8217;s folding animation on the up-walk on the FF6-style cape-crinkling. Hey, capes are hard and ff6 did a good job with it. I HAVE NO REGRETS!
    </p>
    
    <p>
      After a bit of spriting it was time to prepare the makefiles.
    </p>
    
    <h3>
      Some lessons re-learned
    </h3>
    
    <p>
      The first thing I re-discovered was that v3&#8217;s character makefile format is extra-picky. For instance,
    </p>
    
    <pre style="background-color: #dddddd;">
	d_walk F0 W25 F1 W25 F0 W25 F2 W25
</pre>
    
    <p>
      Is invalid! Yeah, in fact you need to do this:
    </p>
    
    <pre style="background-color: #dddddd;">
	d_walk F0W25F1W25F0W25F2W25
</pre>
    
    <p>
      And don&#8217;t you dare think about leaving some trailing whitespace at the end of the string, and you&#8217;d better add an extra newline after the last line of the file, too, boy.
    </p>
    
    <p>
      After re-learning that little particuliarity, I noticed that the W33&#8217;s I&#8217;d been doing in <s>rhubarb</s> roobarb to test looked terrible in-engine, so I went from 1/3rd of a second delay between frames to 1/4th of a second (W25). That helped, but I noticed it looked like you were sliding around at the start of your walk from a standstill. So to solve this I changed the first frame of the animation to not be the same as the standing still frame. To wit:
    </p>
    
    <pre style="background-color: #dddddd;">

	<span style="background-color: #AAAAAA;"># This is the idle "standing" frame.</span>
	d_idle 0

	<span style="background-color: #AAAAAA;"># (expanded improperly, so it is easier to read)</span>
	d_walk F1 W25 F0 W25 F2 W25 F0 W25 

	<span style="background-color: #AAAAAA;"># see, instead of starting on frame 0 on the down-walk, I start on frame 1, </span>
	<span style="background-color: #AAAAAA;"># so you instantly animate from the frame you saw on the standing-frame. </span>

</pre>
    
    <p>
      Hopefully that was clear.
    </p>
    
    <h3>
      Still going.
    </h3>
    
    <div style="float: left; padding: 4px; margin: 4px;">
      <p>
        <img src=/files/gruedorf_challenge/017/2008-02-04_1-looking_at_stuff.png ><br /> <span style="color: silver; font-size: -1;"><br /> <br />Science!</span></div> 
        
        <p>
          So, seventeenth update and still going strong. I recommend grabbing an update from the repo and running it for yourself, so you can see the kids all animating live in scene. I added them all to the party so you could see the glorious man-train in action.<br /> As always, <a href=http://www.verge-rpg.com/svn/sots/>http://www.verge-rpg.com/svn/sots/</a> is where you get the goods. Anonymous/Anonymous for user/password.
        </p>
        
        <p>
          In other news&#8230; Christ, I <i>still</i> don&#8217;t have internet at home. Heads will fucking roll. I mean, really now. It&#8217;s been like a month at this place. What kind of sham game are AT&T and Speakeasy running here. Kael and I both have wasted time waiting and on the phone trying to sort this out.
        </p>
        
        <p>
          <i>Goddamn.</i>
        </p>
        
        <p>
          <i>&#8230;It&#8217;s late. >_></i>
        </p>