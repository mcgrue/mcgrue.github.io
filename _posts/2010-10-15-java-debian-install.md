---
id: 970
title: Java Debian Install
date: 2010-10-15T17:45:21+00:00
author: mcgrue
excerpt: All you need to do to install java on debian is "sudo apt-get install sun-java6-jdk".
layout: post
guid: http://www.egometry.com/?p=970
permalink: /tech/java-debian-install/
ratings_users:
  - "0"
ratings_score:
  - "0"
ratings_average:
  - "0"
categories:
  - administration
  - Technology
---
For my internet-using administrative brethren: this is all you need to do on a modern debian box for a modern java install:

<pre>sudo apt-get install sun-java6-jdk</pre>

The internet is filled with false paths involving 

<pre>sudo apt-get -u install java-package</pre>

and 

<pre>fakeroot</pre>

and 

<pre>make-jpkg</pre>

.

None of that is necessary anymore.