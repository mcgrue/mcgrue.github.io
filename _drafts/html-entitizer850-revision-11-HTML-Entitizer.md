---
id: 1113
title: HTML Entitizer
date: 2009-07-01T02:50:58+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/850-revision-11/
permalink: /gruedorf/850-revision-11/
---
# Escape html

This is a simple script to give the escaped codes for some html. Useful for making foreign languages play nice with html, regardless of how the server handles string encoding.

<?

if( isset($_POST['escape_me']) ) {
echo( '

<h2>Your escaped html</h2> 

<div style="background-color: #ddd; padding: 8px;">
  &#8216; );<br /> echo(str_replace(&#8216;&&#8217;, &#8216;&&#8217;,htmlentities(stripslashes($_POST[&#8216;escape_me&#8217;]),ENT_NOQUOTES,&#8217;UTF-8&#8242;)));<br /> echo( &#8216;
</div>

&#8216; );  
}

?>