---
id: 971
title: Java Debian Install
date: 2010-10-15T14:50:22+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/970-revision/
permalink: /gruedorf/970-revision/
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