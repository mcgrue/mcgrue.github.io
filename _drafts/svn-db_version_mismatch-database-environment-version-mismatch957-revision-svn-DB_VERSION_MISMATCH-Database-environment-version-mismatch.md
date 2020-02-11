---
id: 961
title: 'svn: DB_VERSION_MISMATCH: Database environment version mismatch'
date: 2010-08-14T15:57:30+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/957-revision/
permalink: /gruedorf/957-revision/
---
## &#8230;or Part 2 of <a href=http://www.egometry.com/tech/could-not-open-the-requested-svn-filesystem/ target=_blank>&#8220;Could not open the requested SVN filesystem&#8221;

Two years ago I ran into a problem with my SVN filesystem and got &#8220;Could not open the requested SVN filesystem&#8221; as the front-end error.

This appears to be an annoying catch-all error for &#8220;shit is broken with your SVN, dawg.&#8221;

Last time, it was because I had SVNPath defined in my apache&#8217;s httpd.conf file instead of SVNParentPath (when I had many repos in the same root directory.) This time I did not have that problem, but I did have _the same error message_.

That is annoying.

After several dead-ends, the vital kernel of information came from <a href=http://mrooney.blogspot.com target=_blank>Mr. Mike Rooney&#8217;s</a> suggestion to go to the host server itself and run:

<pre>sudo svn ls file:///path/to/local/repo
</pre></p> 

The two important parts here are that I&#8217;m trying to access the bjorked repo from the local filesystem, so the webdav layer isn&#8217;t being retarded at me and giving me the same enigmatic error message. The second important part here is that I&#8217;m running sudo to get past possible permission problems.

That command produced the following output:

<pre>$ sudo svn ls file:///path/to/local/repo/
svn: Unable to open an ra_local session to URL
svn: Unable to open repository 'file:///path/to/local/repo/'
svn: Berkeley DB error for filesystem '/path/to/local/repo/db' while opening environment:

svn: DB_VERSION_MISMATCH: Database environment version mismatch
svn: bdb: Program version 4.6 doesn't match environment version 4.4
</pre></p> 

At this point, I used the tried and true google-the-unique-error-message technique. After googling &#8220;svn: DB\_VERSION\_MISMATCH: Database environment version mismatch&#8221; (including the quotation marks for an exact search), I found <a href="http://www.hermann-uwe.de/taxonomy/term/50" target=_blank>this blog post</a> that solved my problem.

Here&#8217;s the punchline:

<pre></pre></p> 

At