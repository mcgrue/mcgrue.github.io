---
id: 972
title: How to make wordpress autoupdate work on a debian server
date: 2010-10-17T13:05:17+00:00
author: mcgrue
layout: post
guid: http://www.egometry.com/?p=972
permalink: /tech/how-to-make-wordpress-autoupdate-work-on-a-debian-server/
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
In case you&#8217;re seeing a call to action to enter FTP credentials when you attempt to auto-update your wordpress, you just need to log into your server, cd into the blog&#8217;s webroot directory, and do this:

<pre>sudo chown -R www-data .</pre>

(replace www-data with whomever your apache user is if it&#8217;s not www-data.)

Yeah, that&#8217;s it.