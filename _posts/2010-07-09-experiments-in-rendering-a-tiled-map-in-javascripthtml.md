---
id: 936
title: 'Experiments in rendering a Tiled Map in javascript/html&#8230;'
date: 2010-07-09T01:53:38+00:00
author: mcgrue
layout: post
guid: http://www.egometry.com/?p=936
permalink: /gruedorf/experiments-in-rendering-a-tiled-map-in-javascripthtml/
ratings_users:
  - "0"
ratings_score:
  - "0"
ratings_average:
  - "0"
categories:
  - Games
  - Gruedorf
  - Technology
tags:
  - Games
  - javascript
---
<div style="float: right; padding: 4px; margin: 4px;">
  <p>
    <a title="Sophia Game mk1." rel="lightbox[pics936]" href="http://www.egometry.com/i/2010/07/SophiaGame.png"><img class="attachment wp-att-937 alignleft" src="http://www.egometry.com/i/2010/07/SophiaGame.thumbnail.png" alt="Sophia Game mk1." width="192" height="200" /></a>
  </p>
  
  <p>
    <span style="color: silver; font-size: -1;"><br /> <br />Sophia&#8217;s first tiles!<br />Embrace the pixels!</span></div> 
    
    <p>
      Sophia has been chomping at the bit to make more games. Since it&#8217;s been going on <a href="http://www.egometry.com/gruedorf/the-magical-meaning-of-m/">two years since I last flexed my gamemaking muscles fully</a>, and since I rather adore Sophia, I&#8217;ve been chasing this rainbow.
    </p>
    
    <p>
      I&#8217;ve been ever more intrigued by the idea of a pure html/javascript game engine of late, and have started taking existing, established tools (like mapeditor.org&#8217;s tiled) and putting them into the browser.
    </p>
    
    <p>
      <a href="http://www.egometry.com/files/gruedorf_challenge/070/" target=_new>Here&#8217;s the result: (currently firefox-only)</a>. To fully get the pleasure, inspect elements on this example in firebug.
    </p>
    
    <p>
      The idea is simple: html/js has affordances baked-in to parse xml documents. This can handle traditional map data. css sprite-sheet techniques have been used for years now, which directly mimic old tilset/vsp-style assets. Combine the two&#8230; and you have a effen map. Throw in browser optimizations for visible/hidden elements, and we should have a relatively cheap rendering method.
    </p>
    
    <p>
      The above test is fairly simple: one 30&#215;30 map, one layer. It loads instantaneously fast. It&#8217;s tiles are a single gif sized 304&#215;144. Fairly economical. I decided to shove each of these boys into a div for now and use the background-image css spriting technique to get a &#8220;purist&#8221; tiling implementation going.
    </p>
    
    <p>
      I opted against using canvas for now because I wanted to see how far I could get without it. So far so good, but I&#8217;ve not yet really stressed the system. The next jump will be to take some of my epic 6-layer maps from SotS, translate them into xml, and see how they fair in the browser.
    </p>
    
    <p>
      Of the code I wrote, I suppose the &#8220;sauce&#8221; was a fairly common offset calculation. Although this sort of endeavor may not be so common in the modern age, it&#8217;s pretty commonplace to those of us who labored in 320&#215;240 back in DOS. Get off my lawn.
    </p>
    
    <pre>
var tileset = {
    tileWidth: 16,
    tileHeight: 16,
    setWidth: 304,
    setHeight: 144,
    
    getCoordsfromIdx : function( idx ) {
        var idx = parseInt(idx);
        idx--; //tmx is 1-based, not 0-based.  We need to sub 1 to get to a proper mapping.
        //idx--;
        
        var perRow = this.setWidth / this.tileWidth;
        
        var x = idx % perRow;
        var y = (idx / perRow);

        return [ 
            -(parseInt(x)*parseInt(this.tileWidth)),
            -(parseInt(y)*parseInt(this.tileHeight))
        ];        
    }
}
</pre>
    
    <p>
      This is converting a single tile index into two coordinates for the renderer to consume. For instance, if you want tile 2, it takes a &#8216;2&#8217; at the top, does some maths, and tells you that tile 2&#8217;s offset is 16 pixels in from the top-left corner, and 0 pixels down (ie, on the top row). Some strange quirks of this code: I had to decrement the idx, because Tiled&#8217;s xml format is 1-based, not 0 (ie, the first tile, the one at (0,0), is index 1, not index 0); and I negate the two numbers I return because the consumer of these coordinates is a css background-position style, and that&#8217;s how they work.
    </p>
    
    <p>
      Also of note was a small hiccup when I uploaded this to my server. My sandbox had no trouble serving a .tmx file as Content-Type: text/xml, but my big-boy server threw a conniption about it. I didn&#8217;t realize that was a problem until I threw some debugger statements into the code that &#8220;should&#8217;ve just worked&#8221; and found that all of the proper stuff was in the responseText attribute, but responseXML was null. So I renamed the mapfile to .xml on the server and everything worked fine.
    </p>
    
    <p>
      I guess next step, before trying to stress the system with a super macho map, is to figure out why this isn&#8217;t working in Safari/Chrome/IE/Opera/Whatever&#8230;
    </p>