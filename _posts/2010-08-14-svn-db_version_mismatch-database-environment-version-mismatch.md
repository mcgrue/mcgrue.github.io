---
id: 957
title: 'svn: DB_VERSION_MISMATCH: Database environment version mismatch'
date: 2010-08-14T21:57:34+00:00
author: mcgrue
excerpt: "Of course, this was about 10 hours after where I expected to grab my old repo's contents..."
layout: post
guid: http://www.egometry.com/?p=957
permalink: /gruedorf/svn-db_version_mismatch-database-environment-version-mismatch/
ratings_users:
  - "1"
ratings_score:
  - "1"
ratings_average:
  - "1"
categories:
  - Gruedorf
  - Technology
---
## &#8230;or Part 2 of <a href=http://www.egometry.com/tech/could-not-open-the-requested-svn-filesystem/ target=_blank>&#8220;Could not open the requested SVN filesystem&#8221;</a>

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

<pre>$ cd /path/to/myrepo/db
$ db4.4_checkpoint -1
$ db4.4_recover
$ db4.4_archive
$ svnlook youngest ..
$ db4.6_archive -d
</pre></p> 

## BUT&#8230;

The double-punchline that screwed me for a while was the fact that the berekley db utils for 4.4 were unavailable via apt-get in modern times. Thankfully, long-time <a href=http://surreality.us target=_blank>systems-administration bad-ass Ted Reed</a> was here to suggest the following set of commands: 

<pre>$ wget http://mirrors.kernel.org/ubuntu/pool/universe/d/db4.4/libdb4.4_4.4.20-12_i386.deb
$ wget http://mirrors.kernel.org/ubuntu/pool/universe/d/db4.4/db4.4-util_4.4.20-12_i386.deb
$ dpkg -i libdb4.4_4.4.20-12_i386.deb
$ dpkg -i db4.4-util_4.4.20-12_i386.deb
</pre>

All of these commands (run as root or through sudo) grab the neccesary files from arcane places and got them installed. After that, the previous blog post&#8217;s wisdom could be applied. From there, I was a chmod, a chgrp, and a chown away from actually being able to access my old repository again. 

Of course, this was about 10 hours after where I expected to grab my old repo&#8217;s contents&#8230;