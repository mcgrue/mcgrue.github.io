---
id: 317
title: Guilty by Association, Charged With an Array of Punishments
date: 2008-12-15T02:11:51+00:00
author: mcgrue
layout: page
guid: http://www.egometry.com/?page_id=317
---
Even with my widget, I seem to miss the mark sometime in posting to gruedorf in a timely fashion.  I&#8217;ll need to make a version 3 of it where it starts ringing annoyingly when alerted people get under 24 hours to go.

Even though I may be late in posting, I am not late in doing.  Over the last week I&#8217;ve committed 20 new revisions to the verge-rpg.com repository.  Go me.

This weeks changes bring us thread stickiness, thread deletion/undeletion, and message deletion/undeletion, all with lovely YUI dialogs for the administrator.  

I also created moderson, who is like [testerson](http://www.google.com/search?q=testerson) but is only a moderator and not a god-like admin.  peon remains sad and lonely.

I was planning on closing out the last of the forum stuff today, but I thought it&#8217;d be a good idea to move over to bbcode instead of using filtered html, for various reasons.  This quickly became a thorn in my ass.

The way that the old code works on query-fetching is to have a query like:

`<br />
SELECT message.*, user.username FROM ...<br />
` 

And then it&#8217;d unpack the results from the query like this:

`<br />
list( $a, $b, $c, $d, $e, $f, $g, $h, $i, $j, $k, $l, $m, $o )<br />
= mysql_fetch_row( $result );`

 ``

`$this->_id          		= $a;<br />
$this->_message_board_fk    	= $b;<br />
$this->_parent_fk       	= $c;<br />
/// ...and so on<br />
` 

This served my younger, more innocent 2003-self just fine. However, my older, wiser, more curmudgeonly current iteration is bound slightly by the whippersnapper&#8217;s naive choices. For one, the moment I add a field to the \`message\` table (like, say, a &#8216;version&#8217; field to switch upon different rendering techniques), that field&#8217;s value suddenly becomes what used to be \`user.username\` prior to the change. Which is&#8230; inconvenient, at the best.

Then I had the task of finding a BBCode parser. After vetting a few (one of which had bbcode smileys **BASE 64 ENCODED WITHIN THE PHP FILE**), I went with the [PEAR one](http://pear.php.net/package/HTML_BBCodeParser), which still needed a bit of grooming and prodding to get to work in my multi-platform, non-PATH-munging world.

After several (annoying) hours, I now have a working bbcode parser working in my CakePHP project, safe, snug, and committed as of r