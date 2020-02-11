---
id: 857
title: HTML Entitizer
date: 2009-06-29T09:16:31+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/850-revision-5/
permalink: /gruedorf/850-revision-5/
---
# Escape html

This is a simple script to give the escaped codes for some html. Useful for making foreign languages play nice with html, regardless of how the server handles string encoding.

<?

if( isset($_POST['escape_me']) ) {
echo( '

<h2>Your escaped html</h2> 

<div style="background-color: #ddd;">
  &#8216; );<br /> echo( htmlentities( $_POST[&#8216;escape_me&#8217;],ENT_NOQUOTES ) );<br /> echo( &#8216;
</div>

&#8216; );  
}

?>