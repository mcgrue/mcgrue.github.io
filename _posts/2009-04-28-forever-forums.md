---
id: 770
title: Forever Forums.
date: 2009-04-28T21:31:17+00:00
author: mcgrue
layout: post
guid: http://www.egometry.com/?p=770
permalink: /gruedorf/forever-forums/
categories:
  - Gruedorf
tags:
  - Gruedorf
  - verge-rpg
---
I foolishly regret saying the end of my work on the [beta.verge-rpg.com forums](http://beta.verge-rpg.com/forums/) was, in fact, nigh.

I am getting close to done.  It&#8217;s just that the management of forums also requires work on the teams/games sections of the website that I was hoping to put off until later.

Here&#8217;s a list of things accomplished since my last post:

  * Added [uservoice](http://uservoice.com/) to the layout of beta (and production!) for feedback.
  * Generalized forum displaying.
  * Added forum url_key setting.
  * added /forum/find (so you can find forums you&#8217;re allowed to see, and add them to your main listing)
  * added breadcrumbs to the forums.
  * created functions to list all visible forums to the current user.
  * Added SEO stuff to the template.
  * Added nofollows to links that performed actions rather than showing pages.
  * Updated to [YUI 2.7](http://developer.yahoo.com/yui/)
  * fixed an annoying bug where a forum with no messages (ie, a newly created forum) wouldn&#8217;t render at all.
  * Created a service to look up usernames that was integrated with a YUI autocomplete widget.  This&#8217;ll mainly be of use moving forward with the team creation page.

Currently on revision 225 in the SVN repository.

The good news is that I have more time to work on this, as my train-based commutes now let me think and hack!

The bad news is I am like a week late with this Gruedorf post :(