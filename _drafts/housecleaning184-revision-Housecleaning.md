---
id: 185
title: Housecleaning
date: 2008-11-18T01:13:05+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/184-revision/
permalink: /gruedorf/184-revision/
---
I did a few navel-gazey things tonight.  

## Seperation of Gruedorf and State.  Where &#8216;state&#8217; is &#8216;me&#8217;.

First off, I decoupled the gruedorf RSS feed from the main feed, so I can now make non-gruedorf posts (like this one) and they won&#8217;t show up in the gruedorf feed.  Yay!  For the interested, the competition-only feed is at  [![](http://www.egometry.com/i/icons/feed-icon.png) www.egometry.com/category/gruedorf/feed/](http://www.egometry.com/category/gruedorf/feed/).  

The &#8220;whole site&#8221; feed is at   [![](http://www.egometry.com/i/icons/feed-icon.png) www.egometry.com/category/gruedorf/feed/](http://www.egometry.com/category/gruedorf/feed/).

## Untangling the past

Next, I went through all of the dead links from the old version of the site that google still had, and I added 301 redirects to them all.  After poking at attempting mod_rewrite exclusions on the /posts/view/ directory and failing miserably, I didn&#8217;t have a good way to make a single point of access for a lookup table and a few header() statements in php.  

So instead I got the full list of urls that google was sad about via a search on <a title="Want to know what google thinks about your site?  Ask google!" href="http://www.google.com/search?hl=en&q=site:www.egometry.com/posts&start=30&sa=N" target="_blank">site:www.egometry.com/posts</a>.  Then I methodically went though each one of the cached pages, and physically created a php file at the path expected.  So if the url www.egometry.com/posts/view/21 was broken, I made a physical file that mapped directly to it (in this case /www/egometry.com/posts/view/21/index.php), and then filled it with a file with a header redirect in it. Like so:

<pre>&lt;?
Header( "HTTP/1.1 301 Moved Permanently" );
Header( 'location: http://www.egometry.com/gruedorf/a-hint-of-things-to-come/' );</pre>

This got really, really repetitive, but I powered through it.  My shell prompt was filled with this pattern, by the end:

<pre>mcgrue@quistis:/www/egometry.com/posts/view$ mkdir 11
mcgrue@quistis:/www/egometry.com/posts/view$ cd 11
mcgrue@quistis:/www/egometry.com/posts/view/11$ nano index.php
mcgrue@quistis:/www/egometry.com/posts/view/11$ cd ..
mcgrue@quistis:/www/egometry.com/posts/view$ mkdir 37
mcgrue@quistis:/www/egometry.com/posts/view$ cd 37
mcgrue@quistis:/www/egometry.com/posts/view/37$ nano index.php
mcgrue@quistis:/www/egometry.com/posts/view/37$ cd ..</pre>

&#8230;and so on.

## Why I did this insanity

The idea of having google searches for my (inconsequential) pages turning up as &#8220;page not founds&#8221; on the new site made me sad. I&#8217;d break into cold sweats at night, unable to sleep because of the thought of these poor souls wandering into my bland, unentertaining 404 page. Google analytics incoming searches would taunt me, _taunt me_!

Now, the solution I used wasn&#8217;t a very good one. If you had a large site it&#8217;d be plumb stupid. Apartmentratings.com had a large amount of 301 redirects from when the founder moved from his original url scheme to one that was more user (and search-engine) friendly, and it handled those in a much saner way (with a single point of conversion in the code and a datatable). But since I couldn&#8217;t work in a good mod-rewrite exception, it wasn&#8217;t that much work to do the 30-odd files manually.

So, at this point some of you might be wondering why I didn&#8217;t just use the 404 handling logic in wordpress, since the mod_rewrite for wp was obviously _getting_ the urls in question to redirect them to the in-framework 404 page. A simple lookup-table and redirect before the headers were sent in that tree of logic would surely be what the doctor ordered, right? 

Yeah, it would&#8217;ve. 

I didn&#8217;t realize that until three paragraphs ago.