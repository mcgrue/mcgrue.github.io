---
id: 628
title: 'IMVU is 3d avatar chat; it&#8217;s also a pride-inducing piece of software engineering.'
date: 2009-02-14T09:37:29+00:00
author: mcgrue
excerpt: 'Guy whose "About me" page says "I currently work full time on my blog" mocked the place I work for not being a cure for cancer. '
layout: revision
guid: http://www.egometry.com/gruedorf/624-revision-3/
permalink: /gruedorf/624-revision-3/
---
### Twitter conversing

<div style="padding: 20px; background-color: silver;">
  <b><a href="http://twitter.com/codinghorror">codinghorror</a></b>: If I worked on &#8220;IMVU: 3D Avatar Chat Instant Messenger & Dress Up Game&#8221;, I&#8217;d be too embarrassed to blog about it, frankly.</p> 
  
  <p>
    <b><a href="http://twitter.com/codinghorror">codinghorror</a></b>: He&#8217;s like &#8220;our deployment is sweet!&#8221; I&#8217;m like &#8220;dude, you&#8217;re deploying a 3d chat game for tweens.&#8221; Congratulations, I guess http://is.gd/j4Bh
  </p>
  
  <p>
    <b><a href="http://twitter.com/antumbral">antumbral</a></b>: @codinghorror Feel free to ignore the lessons learned by industry leaders like Nexon just because their customers are younger than you.
  </p>
  
  <p>
    <b><a href="http://twitter.com/codinghorror">codinghorror</a></b>: @antumbral well, let&#8217;s just say 3d chat avatar dress-up software was not the cure for cancer I had hoped it would be.
  </p>
  
  <p>
    <b><a href="http://twitter.com/Prestemon">Prestemon</a></b>: Guy whose &#8220;About me&#8221; page says &#8220;I currently work full time on my blog&#8221; mocked the place I work for not being a cure for cancer. Speechless. </div> 
    
    <div style="font-size: 75%; color: #ccc; line-height: 115%">
      References: <a style="color: #ccc;" href="http://twitter.com/codinghorror/status/1208276353">http://twitter.com/codinghorror/status/1208276353</a> <a  style="color: #ccc;"  href="http://twitter.com/codinghorror/status/1208287780">http://twitter.com/codinghorror/status/1208287780</a> <a  style="color: #ccc;"  href="http://twitter.com/antumbral/status/1208568194">http://twitter.com/antumbral/status/1208568194</a> <a  style="color: #ccc;"  href="http://twitter.com/codinghorror/status/1208675606">http://twitter.com/codinghorror/status/1208675606</a> <a  style="color: #ccc;"  href="http://twitter.com/Prestemon/status/1209022504">http://twitter.com/Prestemon/status/1209022504</a>
    </div>
    
    <h3>
      What, really?
    </h3>
    
    <div style="float: right; margin-left: 20px; margin-bottom: 20px; text-align: center">
      <a href="http://www.egometry.com/i/2009/02/jeffatwood.jpg"><img src="http://www.egometry.com/i/2009/02/jeffatwood.jpg" alt="" title="jeffatwood" width="225" height="135" class="alignnone size-medium wp-image-625" /></a><br /> Jeff Atwood/<a href=http://codinghorror.com>Coding Horror</a>
    </div>
    
    <p>
      What Jeff Atwood is missing the complete point of (in the second tweet) is that the deployment system <em>is</em> sweet, and a successful &#8220;3d chat game&#8221; requires some amazing pieces of engineering required to pull it off. We have a 3d desktop application, a chat service, a giant catalog, a very high-traffic site, and an always-increasing number of persistent users.
    </p>
    
    <h3>
      Shame?
    </h3>
    
    <p>
      The number of interesting things to do at IMVU as an engineer is endless: Do you want to work in C++ today and play with the deep guts of 3d implementation and optimization? Would you like to work in python and use a <a href="http://sourceforge.net/project/showfiles.php?group_id=209568">really cool task system</a>? How about some Flash that&#8217;ll be used daily by a horde of customers, or the <a href="http://code.google.com/p/imvu-flash">infrastructure to allow those customers to make (and sell) their own flash for other customers to use in the product</a>? Interested in scalability problems and other large-scale optimizations or the infrastructure and <a href="http://www.imvu.com/blogs/index.php?blog=12&title=using_master_master_replication_for_back&more=1&c=1&tb=1&pb=1">strategies needed to allow for making changes to a truly titanic amount of data</a>? Or maybe just work on new and better things that will make customers, <em>real people</em>, happy?
    </p>
    
    <p>
      Want to be in a functional business environment yet, as a team of engineers, <a href="http://timothyfitz.wordpress.com/2009/02/10/continuous-deployment-at-imvu-doing-the-impossible-fifty-times-a-day/">ship code fifty times a day to a live and heavily used service</a>?
    </p>
    
    <p>
      We do these things every day. It&#8217;s engineering candyland.
    </p>
    
    <p>
      I work at IMVU, and I&#8217;m damned proud of it mister Atwood. If you&#8217;d like
    </p>