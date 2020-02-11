---
id: 1069
title: '&#8220;Package lua5.1 was not found in the pkg-config search path&#8221; on OSX'
date: 2010-12-29T00:10:49+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/1039-revision-2/
permalink: /gruedorf/1039-revision-2/
---
So I was trying to install [Lua-GD](http://lua-gd.luaforge.net/) on my macbook pro, but there was no OSX binary.

I figure, eh, I can build a package. So then I download the source and do the make dance. After a bit I get to:

<pre>Package lua5.1 was not found in the pkg-config search path.
Perhaps you should add the directory containing `lua5.1.pc'
to the PKG_CONFIG_PATH environment variable
No package 'lua5.1' found
</pre>

And that&#8217;s where I got stuck after several googles. The internets were unkind to this problem.

So I stepped away for a bit, and when I got back to the computer I decided I was probably approaching this from the wrong angle. At which point I [did a search on macports](http://www.macports.org/ports.php?by=name&substr=lua) and found [lua-lua-gd](http://trac.macports.org/browser/trunk/dports/devel/lua-lua-gd/Portfile).

Ratholes aren&#8217;t fun. Sometimes it&#8217;s best to take a step back instead of pounding a round peg into a square hole.