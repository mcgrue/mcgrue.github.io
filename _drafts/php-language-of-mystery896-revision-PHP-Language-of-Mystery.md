---
id: 897
title: PHP, Language of Mystery
date: 2009-07-21T09:07:27+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/896-revision/
permalink: /gruedorf/896-revision/
---
PHP seems so arbitrary sometimes.

<pre style="background-color: #ccc; font-family: monospace; padding: 10px;">function test_nine() {
	$$"9" = 22;
}

</pre>

fails to parse.  
(which is good, I suppose)

This passes:

<pre style="background-color: #ccc; font-family: monospace; padding: 10px;">function test_nine() {
	$n = 9;
	$$n = 22;
	$this->assertEqual($$n, 22);
}

</pre>

-Andy Friesen, of <a href=http://giant-communist-robots.com/>giant-communist-robots.com</a> and IMVU tech lead.