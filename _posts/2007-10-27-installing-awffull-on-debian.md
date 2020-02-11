---
id: 8
title: Installing awffull on debian
date: 2007-10-27T23:36:23+00:00
author: mcgrue
layout: post
permalink: /tech/installing-awffull-on-debian/
categories:
  - Technology
tags:
  - apache
  - awffull
  - debian
---
## Installing awffull on debian

I wanted the sexy newer beta version of <a href=http://www.stedee.id.au/awffull>awffull</a> (because <a href=http://www.mrunix.net/webalizer/>webalizer</a> is&#8230; awful&#8230; and <a href=http://en.wikipedia.org/wiki/Webalizer#Criticism>hasn&#8217;t been updated since 2002 and keeps spiders in your stats</a> and stuff).

Unfortunatly, this meant I had to not use apt-get for the first time in months.

Here&#8217;s a redux of what a debian user needs to do to get Awffull running local (assuming you have superuser privileges):

<pre><span style="color: #AAAAAA;">#
# grab the recent build, at the time of this writing: 3.8.1 b3
#</span>
wget &lt;a href=http://www.stedee.id.au/files/awffull-3.8.1-beta3.tar.gz>http://www.stedee.id.au/files/awffull-3.8.1-beta3.tar.gz&lt;/a>

<span style="color: #AAAAAA;">#
# untar it and gunzip it</span>
#&lt;/span>
tar -xvvzf awffull-3.8.1-beta3.tar.gz

<span style="color: #AAAAAA;">#
# climb into the newly minted directory (for you neophytes out there,
# it'll be different if the version/filename is different)
#</span>
cd awffull-3.8.1-beta3

<span style="color: #AAAAAA;">#
# Now you need to make sure you have the libpng libraries installed.
# So as superuser we'll grab ALL of the libpng libraries...
#</span>
sudo apt-get install libpng*

<span style="color: #AAAAAA;">#
# now the GD Lib... which had a somewhat esoteric name for apt-get.
# I found this by running a &lt;a href=http://www.google.com/search?client=opera&#038;rls=en&#038;q=debian+site:http://www.libgd.org&#038;sourceid=opera&#038;ie=utf-8&#038;oe=utf-8>debian site:http://www.libgd.org&lt;/a> google.
#</span>
apt-get install libgd2-dev

<span style="color: #AAAAAA;">#
# Next was the perl compatible regular expressions library.
# The google for this one was &lt;a href=http://www.google.com/search?hl=en&#038;client=opera&#038;rls=en&#038;hs=uLz&#038;q=apt-get+%22Perl+Compatible+Regular+Expressions%22&#038;btnG=Search>apt-get "Perl Compatible Regular Expressions"&lt;/a>
#</span>
apt-get install libpcre3-dev

<span style="color: #AAAAAA;">#
# You may need to also install zlib.  I didn't, as it's a very common library... but
# if you do, you can get it with this command
#</span>
apt-get install zlib*

<span style="color: #AAAAAA;">#
# Now we're in the home stretch.  Run these commands, and you should be golden.
#</span>

./configure

make

make install

</pre>

And if all went well, you&#8217;ve compiled a delicious build of awffull. The binary will be sitting in the src directory, (in this case ~/awffull-3.8.1-beta3/src ) and should&#8217;ve been already copied to it&#8217;s new home at /usr/local/bin/awffull.

You can make a symbolic link to /usr/bin/awffull from /usr/local/bin/awffull if you want.