---
id: 247
title: Obscured References
date: 2008-11-29T13:40:46+00:00
author: mcgrue
excerpt: 'This whole conundrum is a non-issue in the modern world of programming, what with fancy objects and classes and types.  '
layout: revision
guid: http://www.egometry.com/gruedorf/244-revision-2/
permalink: /gruedorf/244-revision-2/
---
<figure id="attachment_245" style="width: 300px" class="wp-caption alignright">[<img class="size-medium wp-image-245" title="2008-11-29_so_say_we_all" src="http://www.egometry.com/wp-content/uploads/2008/11/2008-11-29_so_say_we_all-300x237.png" alt="There are now 4 characters on screen.  Whee." width="300" height="237" srcset="https://www.egometry.com/i/2008/11/2008-11-29_so_say_we_all-300x237.png 300w, https://www.egometry.com/i/2008/11/2008-11-29_so_say_we_all.png 648w" sizes="(max-width: 300px) 85vw, 300px" />](http://www.egometry.com/wp-content/uploads/2008/11/2008-11-29_so_say_we_all.png)<figcaption class="wp-caption-text">There are now 4 characters on screen. Whee.</figcaption></figure> 

So, Sully&#8217;s Battlesystem had a problem.

It worked well as long as you had character 0 in party slot 0, and character 1 in party slot 1, but as soon as anything changed from that configuration&#8230; shit got _real_.

The problem was due entirely to vergec&#8217;s type-poor environment.  In the battle system party[party\_idx] and party\_idx were used interchangeably.  Hey, they&#8217;re both ints and they look the same, right?

After identifying the source of the issue, it was a matter of a global search on &#8220;party[&#8221; and identifying the spots where it was misused.  I&#8217;ve also wrapped this whole operation in a function to give a level of english for humans to see and go &#8220;oh, maybe I should give thought to this.&#8221;

> This whole conundrum is a non-issue in the modern world of programming, what with fancy objects and classes and types.

The most fun part about this is, once I solved the party reference problem, there was a renderstack problem of exactly the same type, where renderstack references and sprite references (which are stored in two different int-indexed global stacks) were used interchangeably. I was already in the mindset to solve this issue.

The whole task is documented between r187 and r197 in the [sully svn repository](http://www.verge-rpg.com/svn/sully/).  Top to bottom the tasks were about 8 hours of braining and typing.

It&#8217;s my fault for continuing down this path of madness, but there&#8217;s a massive amount of code and effort in this so I have lock-in.  Converting the whole thing to Lua would still have these issues to track down.