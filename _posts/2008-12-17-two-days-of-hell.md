---
id: 321
title: Two Days of Hell
date: 2008-12-17T02:57:16+00:00
author: mcgrue
excerpt: Hell truly is revisiting old, crufty code made by yourself.
layout: post
guid: http://www.egometry.com/?p=321
permalink: /gruedorf/two-days-of-hell/
categories:
  - Gruedorf
tags:
  - hell
  - mysql
  - php
  - refactoring
---
<div style="float: right; margin-left: 20px;">
  <figure id="attachment_322" style="width: 267px" class="wp-caption alignnone"><a href="http://www.egometry.com/wp-content/uploads/2008/12/screenshot.png"><img class="size-medium wp-image-322" title="screenshot" src="http://www.egometry.com/wp-content/uploads/2008/12/screenshot.png" alt="A screenshot of code for Syn" width="267" height="145" /></a><figcaption class="wp-caption-text">A screenshot of code for Syn</figcaption></figure>
</div>

As a brief gruedorf update, I&#8217;ve completed moving the old site&#8217;s code from mysql\_fetch\_row() to mysql\_fetch\_assoc() on all queries with tablename.* on their select clause.

I can now move forward with the beta site&#8217;s schema changes unimpeded.  

> Hell truly is revisiting old, crufty code made by yourself.

As an unintentional side effect, several old bugs have cleared up.  Apparently in the past I added fields and some time later noticed bugs and never correlated the two events happening.  

Hell truly is revisiting old, crufty code made by yourself.

I added a screenshot of the last two days of gruedorf progress for Syn, who apparently likes screenshots.