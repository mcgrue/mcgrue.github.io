---
id: 1028
title: Request exceeded the limit of 10 internal redirects due to probable configuration error.
date: 2010-12-14T21:28:50+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/1024-autosave/
permalink: /gruedorf/1024-autosave/
---
In my experience, if you get the old apache default error page of 

`<br />
Internal Server Error<br />
The server encountered an internal error or misconfiguration and was unable to complete your request.<br />
` 

It tends to be a misconfigured .htaccess file somewhere.

<a href=http://www.johnweng.com>www.johnweng.com</a> was down today with that error message. JohnWeng.com is a website I host for Ustor which contains, among other things, the [gruedorf competition homepage](http://johnweng.com/gruedorf/). 

So the first thing I do is to shell into the server and change into the webroot directory for johnweng.com. 

But there was no htaccess file.

The next most common problem I find is unix permissions-based, although you don&#8217;t tend to get 500&#8217;s in that instance. Regardless, I started asserting that ustor owned everything, www-data was the group on everything, and the proper chmod was in place.

Still nothing. Still the same error.

The next thing I do is verify that the name &#8220;johnweng.com&#8221; was actually resolving to my server. It always helps to verify that you&#8217;re looking at the right level of the problem. One traceroute later and I&#8217;ve confirmed that DNS is working as expected: the name was going to the numerical IP of the host box.

So this got curious. And increasingly frustrating.

My next step was to go to my apache log file, like the 500 error page helpfully suggested. Whenever I hit it, I&#8217;d get a the following error:

`<br />
Request exceeded the limit of 10 internal redirects due to probable configuration error. Use 'LimitInternalRecursion' to increase the limit if necessary. Use 'LogLevel debug' to get a backtrace.<br />
` 

Which reinforced the initial &#8220;it has to be an .htaccess file, damnit!&#8221; reaction. Those wily mofos are always redirectin&#8217; shit. But where could it be?

The answer is, of course, up a directory. 

htaccess files can, with the proper apache server settings, listen to its parent folder&#8217;s .htaccess file if one isn&#8217;t present in the current directory. And so on, and so on. I didn&#8217;t think to look in the shared directory that all my hosted sites sit in because it&#8217;s not a webroot itself, and why would there be an htaccess file there anyway?

It turns out I accidentally checked out a copy of vrpg&#8217;s svn to that shared root directory two nights prior during some late-night hackery. This caused vrpg&#8217;s htaccess file to be one file up from where johnweng.com&#8217;s webroot was. And apparently even though johnweng.com was &#8220;the top&#8221; directory in its structure, apache still looked to its parent directory and found a htaccess file to access the rules from.

Lesson learned: apache doesn&#8217;t care about its own webroots. It just cares about folders.

As a side note, I didn&#8217;t notice that this mis-checkout happened until johnweng.com was noticed to be down because every other site I deal with has its own htaccess file in its own webroot, defining exactly the rules that vrpg&#8217;s misplaced htaccess file was. So each of those child directories was overriding the rogue parent file, and so was acting as expected.

Yay systems administration!