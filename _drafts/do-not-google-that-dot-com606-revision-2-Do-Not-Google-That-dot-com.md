---
id: 608
title: 'Do Not Google That!  (dot com)'
date: 2009-02-12T20:22:48+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/606-revision-2/
permalink: /gruedorf/606-revision-2/
---
### The Premise

Late at night a few days ago in [imvu.com&#8217;s](http://imvu.com) secret lair, #engineering&#8230;

<pre style="width: 510px; padding: 20px;  background-color: #efefef;"><b>&lt;Veep></b> from an article on an ultimate fighting controversy about a guy
       putting slippery stuff on to gain an unfair advantage:
<b>&lt;Veep></b> Oh, and a fair word of warning to those looking to do additional
       research: Do not Google "oily sweat wrestling men." 
       Just don't do it. Some things can't be unseen.
<b>&lt;Grue></b> :D
<b>&lt;Grue></b> That which does not kill you will make you OH GOD.
<b>&lt;Veep></b> that would be a good webpage: "things you shouldn't search for on
       google", with http://www.google.com/search?q=  links
<b>&lt;Grue></b> hm, yeah.
<b>&lt;Grue></b> simple apps are simple.
<b>&lt;Grue></b> it's something that you need not even moderate the submission to.
<b>&lt;Veep></b> No match for "DONOTGOOGLETHAT.COM".
<b>&lt;Grue></b> This is a compelling application, veep.
<b>&lt;Veep></b> thanks.
<b>&lt;Grue></b> you calling dibs?
<b>&lt;Veep></b> no, my queue of unfinished projects is large. if you want it, you 
       can have it.
</pre>

### The Addiction

I have a problem with domain name purchasing. They&#8217;re all so pretty. Most of my domains are empty, so the idea of a fully operational site made within a few hours of coding was very appealing to me. 

I haven&#8217;t had a simple project since I made my [exceptionally puerile knockoff of ipchicken.com](http://ipbeer.com) (whose sole functionality is to display <span style="font-family: monospace;">$_SERVER[&#8216;REMOTE_ADDR&#8217;]</span> and <span style="font-family: monospace;">$_SERVER[&#8216;HTTP_USER_AGENT&#8217;]</span> to the user, and doa ip2latlon lookup to feed to gmaps. Oh: and a <s>gif</s> png of urine.). The idea of completing an &#8220;art project&#8221; website in less than half a day and throwing some ads on it to potentially make it so it can be cash-neutral for my lifetime as far as domain re-registration costs go is oddly, strangely, _irrationally_ appealing to me. And this felt like that.

So I bought <a href=http://donotgooglethat.com/>donotgooglethat.com</a>.

And then I bought <a href=http://dontgooglethat.com/>dontgooglethat.com</a> and made donotgooglethat.com 301 redirect to this one. _Because I have a problem with buying domains_.

### The Implementation

Who needs security or user auth on a site meant to provide terrible, sullied links to the underbelly of the googleverse?

#### Style decisions

I started out by ripping apart a copy of everyone&#8217;s favorite search page. After taking out a bunch of stuff (wow, they use tables!) I was left with a raw googlish-looking site. I replaced the topbar links with a few links to some of my sites, and added the minimalist google ads to the side, with a link to the real google on the right. 

My goal is to be googlish but not confusable with the Real McCoy for legal reasons, so I opted not to go with any rainbow text or [the google Font](http://www.identifont.com/show?HF) (Catull, for you typography nerds).

Even so, I&#8217;m wary of using the trademarked term. Worse comes to worse I&#8217;m out $14 for reg costs and have a cute story.

Finally I grabbed two icons from the <a href=http://www.famfamfam.com/archive/silk-icons-thats-your-lot/>Silk Icon Set</a> over at famfamfam. Even though I&#8217;m a <a href=http://www.verge-rpg.com/gallery/gallery.php?sully>competent sprite artist</a>, I was trying to get this done as quickly as possible.

#### User Experience Decisions

I wanted to keep it damned simple. So I opted for only showing the top ten &#8220;worst&#8221; searches that were upvoted, without an option for pagination. There are no &#8220;about&#8221; pages since the links go straight to google searches, so there&#8217;s no need for SEO&#8217;d urls or concern for &#8220;losing valuable index space&#8221; by not exposing all of the content. Who cares? Not this site!

Each of the top ten links can be voted up or down. On successful vote (or failure!) you&#8217;re notified above the dontGOOGLEthat header. You can add a new search by clicking on the yellow button after entering some (hopefully offensive) text into the search box, or just by searching (done via an async post onClick of the &#8220;No Don&#8217;t Search&#8221; button).

The search results go to an adsense&#8217;d google personal search result page, which I chose to keep unbranded. The rationale here was that I want this thing to basically net $7 a year, so the least annoying way to do that would be to tie any possible revenue into the only real thing it does: making searches. Even so, I&#8217;m not pleased with the results; <a href=http://twitter.com/benmcgraw/status/1205056882>Google Safesearch</a> seems to be on by default, and I couldn&#8217;t find anything (in the five minutes I scanned for it) in the customized search api to turn it off programatically or via a pref setting in adsense. 

I decided to put a minimal amount of discouragement for vote-hammering by putting a session-based lock on votes in. However, anyone with half a brain and an ounce of desire can get around it. Really: I don&#8217;t care. Should I start caring, it wouldn&#8217;t be that hard to fix it or just disable voting&#8230;

To get a small amount of churn, the most recent search shows up at the bottom with a googlish <font color=red>New!</font> next to it, and the option to upvote it there.

Also to promote searching, I did the same very simple trick google did to up their revenue long ago: a 

<pre>document.getElementById('q').focus();</pre>

on page load. This just puts the cursor straight into the search form, so when you load the page and type, the input goes straight there. Such a tiny trick, and it netted them millions and millions more dolars in revenue. _And_ it improved the user experience.

#### Codey Decisions

MySQL Database: One table. Three fields: id, query, and votes. Trivial.

Two queries per page load: one to get the top ten votes, one to get the most recent post. The votes field has an index (normal), so both queries are optimally cheap.

One of two optional queries per page load: an insert of a new search term or an up/down vote. The insert actually is two queries: one to see if a search already exists, and if it doesn&#8217;t: do an insert (and if it does, and you haven&#8217;t already voted on it, upvote it!). 

No templating. No javascript libraries. A few boilerplate functions (mainly query error reporting stuff I handrolled years ago that&#8217;s been very faithful and useful). A few lifted javascript functions (because who needs to include all of jQuery for a single XMLHttpRequest call?). A google analytics tracker just for the hell of it, because analytics are fun!

There is only the main index and the About page, and the about page has no preprocessing logic. 

The index weighs in at 12kb, and 297 lines.

A few tests shows that the main index presently renders in 0.008s from a cold start and in 0.001s afterwards. I assume this 8x speedup is just Filesystem or OS or MySQL or Apache level caching, since I sure didn&#8217;t put any caching in myself.

The whole operation was 4 hours top to bottom, sans tweaks here and there for the past few days. This is roundtrip from registration, administrative stuff like editing my dns entries, apache conf files, setting up the database user, setting up an adsense and analytics account, and then implementation. The actual coding part was between 60 and 120 minutes, mostly debug stemming from sandbox/server inconsistencies. A lot of time was also wasted talking to [the girlfriend](http://sheisept.com) on gtalk.

For contrast, this blog post has taken about 90 minutes in a text editor, and currently weighs 8kb. The line count is lower, but the lines are far longer; English is a less concise language than PHP&#8230; but even English is more internally consistent than PHP.

#### And that&#8217;s it!

I&#8217;d like to see if it gets some use, but I&#8217;m not exactly sure who to expose it to to see if anyone cares. I thought about posting it to 4chan, but I don&#8217;t think it&#8217;s got enough shock value for that, especially since it defaults to safesearch. 

Even if it rots in obscurity, though, it&#8217;s a tiny completed work, so I&#8217;m all good by it. 

If anyone has any comments or suggestions: please leave them!