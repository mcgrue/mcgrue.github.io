---
id: 84
title: '&#8220;Could not open the requested SVN filesystem&#8221;'
date: 2008-10-20T00:13:10+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/?p=84
permalink: /gruedorf/10-revision/
---
### &#8220;Could not open the requested SVN filesystem&#8221;

Sometimes problems happen.

Sometimes problems happen when you install svn with apache 2 and dav.

Sometimes after installing all the binaries and editing your apache configuration file (and, naturally, restart apache), you get the following error:

<pre>svn: Could not open the requested SVN filesystem</pre>

Sometimes this happens.

_Usually_ it means &#8220;lol, you need to chown/chgrp the repos to your apache&#8217;s user&#8221;. Usually. And because this is the usual case, that&#8217;s what all the googles I check suggested.

However, it bears mention that I&#8217;m, in fact, somewhat experienced at this point in Linux administration. I chown. That&#8217;s not even a pun.

The rub is that&#8217;s a catch-all for any read problems. The error in my case was &#8220;lol, you&#8217;re pointing to the wrong directory with the wrong directive, noob.&#8221;

To wit, I was using (in my apache configuration file):

<pre><span style="color: #AAAAAA;">&lt;Location /svn>
        DAV svn</span>
        SVNPath /repos/svn
<span style="color: #AAAAAA;">#...
&lt;/Location></span></pre>

&#8230;when I actually wanted&#8230;

<pre><span style="color: #AAAAAA;">&lt;Location /svn>
        DAV svn</span>
        SVNParentPath /repos/svn
<span style="color: #AAAAAA;">#...
&lt;/Location></span></pre>

I wanted **SVNParentPath** because it was a directory containing many repositories, instead of a single repository. How simple. Yet, while doing 2 am hungover-style administration, somewhat frustrating.

### An aside about Linux paths and URLs

This conf snip is a good example of something I find <s>frustrating</s> <s>annoying</s> understandable-but-sometimes-confusing. Unix filesystem paths, like http urls, use the forward-slash (/) instead of the backslash (). This conflation of slashing makes them look like each other in configuration files. This mainly becomes an issue for neophytes tinkering with apache for the first (and perhaps subsequent) times.

For example, in the above conf-snippets, the **/svn** refers to <a href=http://www.verge-rpg.com/svn>http://www.verge-rpg.com/svn</a>, a Location defined in apache saying &#8220;hey, I exist to teh internots!&#8221;

Meanwhile, **/repos/svn** refers to a folder on the server&#8217;s filesystem. It can be easy to think, in this context, that something might be at http://www.verge-rpg.com/repos/svn on the internet.

Anyone with any small grasp of the nature of what&#8217;s going on in this task will be able to separate the two mentally, since here&#8217;s we&#8217;re trying to make a bridge between clients via the internet and the svn repo files on the server, but the slashy-syntax can lead to confusion. I know back when I was a young adminling unwrapping his first local development install of apache this stuff caused no end of heartache and strife.

Anyway, I&#8217;m not saying MS-style backward-slashes are better. In fact, they have their own brand of obnoxiousness in the form of unintended escape sequences. But in this instance, backslashes would highlight the difference between a webpath and a filepath.

This digression is what happens when someone likes aphorisms _and_ being long-winded.