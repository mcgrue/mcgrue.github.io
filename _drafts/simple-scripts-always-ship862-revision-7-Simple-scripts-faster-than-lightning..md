---
id: 872
title: Simple scripts, faster than lightning.
date: 2009-07-01T02:58:51+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/862-revision-7/
permalink: /gruedorf/862-revision-7/
---
## Simple needs, simple deeds.

A need for a simple one-off occurred monday afternoon at work. Some non-engineer coworkers needed to be shown how to make some non-<a href="http://en.wikipedia.org/wiki/ISO\_8859-1" target=\_blank>Latin-1</a> text into html entities. 

Basically, they needed a 5 line php script.

Right before sending them to [any number of sites that already do this 5-line operation](http://www.google.com/search?q=html+entity+converter), I decide, what the hell, [I&#8217;ll just make one of my own](). 

Here&#8217;s my <a href="http://www.egometry.com/html-entitizer/" target=_blank>HTML Entitizer</a>. Suitable for all your HTML entitizing needs, large _or_ small!

## PHP in <u>Escape from &#76;&#46;&#65;&#46;</u><a href="http://www.zefrank.com/thewiki/the\_show:\_05-10-06" target=_blank style="font-size:40%; color: #eee;">(jokesfornerds)</a>

One of the reasons PHP is so popular is the fact that it&#8217;s got so many handy little functions. In this case, [htmlentities()](http://php.net/manual/en/function.htmlentities.php) is the blade of PHP&#8217;s swiss army knife that we&#8217;re using. Of course, indiscriminate use of functions like this cause problems like double-escaped characters (&amp;) showing up in databases. 

<a href="http://www.egometry.com/i/2009/07/swiss-army-everything.jpg" rel="lightbox[pics862]" title="PHP, the swiss-army knife."><img src="http://www.egometry.com/i/2009/07/swiss-army-everything.thumbnail.jpg" alt="PHP, the swiss-army knife." width="200" height="152" class="attachment wp-att-864 alignright" /></a>PHP&#8217;s solution to this sort of thing is generally to throw new corkscrews and toothpicks onto it&#8217;s ever-growing pile of tools on it&#8217;s knife. If you look at the [documentation page for htmlentities()](http://php.net/manual/en/function.htmlentities.php), you can see that as of version 5.2.3 of PHP, another optional parameter was added: double_encode. Which will

Getting the right escape order can be hard, especially for novices or small teams inheriting code from other small teams. To date I don&#8217;t think I&#8217;ve inherited work on a webapp whose database wasn&#8217;t littered with extraneous &&#8217;s and rogue \&#8217;s. It&#8217;s only by virtue of verge-rpg.com having a single developer who is really, _really_ annoyed by this problem the the point of neuroticism that &amp; never appears in the database except in <a href="http://verge-rpg.com/boards/display\_thread.php?id=131844#post131851" target=\_blank>posts that actually wanted to display &</a>.

Although even this level of OCD-database-cleansing didn&#8217;t prevent <a href="http://verge-rpg.com/boards/display\_thread.php?id=131844#post131850" target=\_blank>escaping-related errors on the first go-round</a>.

## Teh Sick Implementation (sic)

So, the only time-consuming part of getting this script into my wordpress site (other than me taking a bloody half hour to blog about a 2-minute job) was convincing wordpress that it should allow <span style="color: red;"><?php</span> fragments into my posts.

Luckily, other people before me have wanted this very thing. WordPress&#8217;s biggest strength is again one of PHP&#8217;s: if you want it, it&#8217;s already been made for you. In this case the <a href="http://bluesome.net/post/2005/08/18/50/%20Exec-PHP" target=_blank>Exec-PHP</a> module will let admin-level users of your blog post for-reals, actual PHP into your posts! You&#8217;d better hope your admins don&#8217;t have their accounts compromised! <span style="font-size:40%; color: #eee;">(&#8230;one moment. Changing my password.)</span>

In PHP&#8217;s case, the code that you want that&#8217; already been written for you is [in every single function&#8217;s talkback thread](http://www.php.net/manual/en/function.htmlentities.php#84612). These functions may not be hyper-optimized or the best solution for any given problem, but they generally are what you want to prove a point. You scan the docs, you grab the code, you put it in your site, and you move on to the next problem in your own app.

Quick and dirty, the way PHP likes it.

For the curious, here&#8217;s the solution I spat out:

<pre style="background-color: #ddd;">&lt;h1&gt;Escape html&lt;/h1&gt;
&lt;p&gt;This is a simple script to give the escaped codes for some html. Useful
for making foreign languages play nice with html, regardless of how the
server handles string encoding.&lt;/p&gt;
&lt;?

if( isset($_POST['escape_me']) ) {
echo( 
    '&lt;h2&gt;Your escaped html&lt;/h2&gt;&lt;div style="background-color: #ddd; padding: 8px;"&gt;' 
);

echo(
    str_replace(
        '&', 
        '&amp;',
        htmlentities(
            stripslashes(
                $_POST['escape_me']
            ),
            ENT_NOQUOTES,
            'UTF-8'
        )
    )
);
echo( '&lt;/div&gt;' );
}
?&gt;
&lt;form action='/html-entitizer/' method='POST'&gt;
Text to escape:
&lt;textarea name='escape_me' style='width: 550px; height: 200px;'&gt;&lt;/textarea&gt;
&lt;input type='submit' value='Create my html entities'&gt;
&lt;/form&gt;
</pre>

(weird formatting so it doesn&#8217;t run off the side of the screen; I don&#8217;t actually code like that. Mosl)