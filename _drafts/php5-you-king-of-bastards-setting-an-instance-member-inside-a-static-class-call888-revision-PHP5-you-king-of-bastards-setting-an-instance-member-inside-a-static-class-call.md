---
id: 889
title: PHP5, you king of bastards (setting an instance member inside a static class call)
date: 2009-07-08T05:48:10+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/888-revision/
permalink: /gruedorf/888-revision/
---
If I&#8217;m in an instanced class, and I call another class&#8217;s method statically inside of a method in the first class, and that static method should happen to _(erroneously)_ have $this->whatever inside of it&#8230;

&#8230;it sets $whatever on my outer instanced class.

Here&#8217;s some illustrative code:

<pre style="padding: 8px; background-color: rgb(221, 221, 221);" >&lt;?
&nbsp;&nbsp;&nbsp;&nbsp;class&nbsp;Inner_Static&nbsp;{
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;function&nbsp;burrito()&nbsp;{
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$this-&gt;_member&nbsp;=&nbsp;‘A&nbsp;keyboard.&nbsp;How&nbsp;quaint.’;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}
&nbsp;&nbsp;&nbsp;&nbsp;}

&nbsp;&nbsp;&nbsp;&nbsp;class&nbsp;Outer_Instance&nbsp;{
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;function&nbsp;taco()&nbsp;{
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Inner_Static::burrito();
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}
&nbsp;&nbsp;&nbsp;&nbsp;}

&nbsp;&nbsp;&nbsp;&nbsp;$my_guy&nbsp;=&nbsp;new&nbsp;Outer_Instance();
&nbsp;&nbsp;&nbsp;&nbsp;$my_guy-&gt;taco();

&nbsp;&nbsp;&nbsp;&nbsp;print&nbsp;‘$my_guy-&gt;_member:&nbsp;‘&nbsp;.&nbsp;$my_guy-&gt;_member;&nbsp;
</pre>

This boggles my mind a bit. Tracking it down cost me a bit of time. Is there actually a sane use for this little tidbit, or am I justified in thinking that a good language would warn you that