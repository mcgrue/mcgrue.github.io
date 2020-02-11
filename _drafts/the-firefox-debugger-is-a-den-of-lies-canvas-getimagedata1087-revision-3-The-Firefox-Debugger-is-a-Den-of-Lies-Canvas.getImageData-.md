---
id: 1092
title: The Firefox Debugger is a Den of Lies ( Canvas.getImageData )
date: 2011-01-12T09:16:37+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/1087-revision-3/
permalink: /gruedorf/1087-revision-3/
---
I&#8217;ve become accustomed to my best friend in javascript development being Firebug. Even though Firefox has become a worse browsing choice than Chrome, I always develop in it because FireBug still makes me much happier than the chrome inspector.

But last night I lost an hour or so because I forgot one of the oldest rules of javascript development: _Sometimes it lies_.

I was modifying a friend&#8217;s loader to get the pixel data out of an image to accept elements that were already loaded into the DOM. This is what I had:

<pre>function getImageData(img) {
    var ctx = document.createElement('canvas').getContext('2d');
    ctx.width = img.width;
    ctx.height = img.height;
    ctx.drawImage(img,0,0);
    var res = ctx.getImageData(0, 0, img.width, img.height);
    // debugger;
    return res;
}
</pre>

&#8230;but when I was testing it, `res` there was very much an empty object.  
<a href="http://www.egometry.com/i/2011/01/canvas-getpixels.png" target=_blank><img src="http://www.egometry.com/i/2011/01/canvas-getpixels.png" alt="" title="canvas-getpixels" width="518" height="141" class="aligncenter size-full wp-image-1090" /></a>