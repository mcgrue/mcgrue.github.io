---
id: 318
title: Guilty by Association,
date: 2008-12-15T01:59:31+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/317-revision/
permalink: /gruedorf/317-revision/
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
list( $a, $b, $c, $d, $e, $f, $g, $h, $i, $j, $k, $l, $m, $o ) = mysql_fetch_row( $result );</p>
<p>$this->_id          		= $a;<br />
$this->_message_board_fk    	= $b;<br />
$this->_parent_fk       	= $c;<br />
`