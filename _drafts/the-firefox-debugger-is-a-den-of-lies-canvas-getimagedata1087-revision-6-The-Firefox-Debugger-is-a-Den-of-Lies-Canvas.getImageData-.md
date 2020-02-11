---
id: 1095
title: The Firefox Debugger is a Den of Lies ( Canvas.getImageData )
date: 2011-01-12T17:26:31+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/1087-revision-6/
permalink: /gruedorf/1087-revision-6/
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

&#8230;but when I was testing it, `res` there was very much an empty object. Then started the gnashing of teeth and recoding and the step-by-step debugging.

After I threw in the Towel of Pride, <a href=http://strd6.com/>Daniel</a> provided a sanity check and found that `res` did indeed hold the specific object I was looking for.

<a href="http://www.egometry.com/i/2011/01/canvas-getpixels.png" target=_blank><img src="http://www.egometry.com/i/2011/01/canvas-getpixels.png" alt="" title="canvas-getpixels" width="518" height="70" class="aligncenter size-full wp-image-1090" srcset="https://www.egometry.com/i/2011/01/canvas-getpixels.png 1036w, https://www.egometry.com/i/2011/01/canvas-getpixels-300x40.png 300w, https://www.egometry.com/i/2011/01/canvas-getpixels-1024x139.png 1024w" sizes="(max-width: 518px) 85vw, 518px" /></a>

So what gives? 

Apparently, javascript ImageData objects have a defined toString() returning &#8220;Object { }&#8221;. 

I find toString overloads of this type to be a terrible throwback to the dark ages of javascript. I should&#8217;ve realized that what it said wasn&#8217;t actually an empty object (which would&#8217;ve been represented as just &#8220;{}&#8221;) but in fact was a much more insidious manifestation of the old &#8220;[object Object]&#8221; which plagued javascript alert() messages for years.

Please, developers, if you make a toString() overload for your javascript objects, make them read like they contain data. :(