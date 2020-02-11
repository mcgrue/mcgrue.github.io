---
id: 82
title: 'HUD&#8217;s Up! (oooh, redundantish.)'
date: 2008-10-20T00:12:19+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/?p=82
permalink: /gruedorf/9-autosave/
---
### HUD&#8217;s Up! (oooh, redundantish.)

<div style="float: right; padding: 4px; margin: 4px;">
  <img src=/files/gruedorf_challenge/003/2007-10-28_0_slidey!.PNG alt="Steampunky meters and sliding banners and names, oh my!"><br /><span style="color: silver; font-size: -1;">Bet you didn&#8217;t know there was gonna be<br /> tools&#8230; other than me, that is. :(</span>
</div>

Today&#8217;s Gruedorf update is all about the game&#8217;s heads-up display. I&#8217;ve been meaning to implement this for years now, but I&#8217;ve been putting it off continuously.

The Astrad is inspired _heavily_ by Wild Arms and Lufia 2. The top-left meter will be similar to the Wild Arms 3 encounter meter that lets you skip out on battles, except it&#8217;ll (when implemented) be more of a builds-up-pressure type thing than the Wild Arms 3 &#8220;countdown&#8221; gauge. At least, that&#8217;ll be what happens in &#8220;field&#8221; areas. I&#8217;ve got a few uses in mind for it as a feedback device in &#8220;Town&#8221; areas, mostly for use in conjunction with the equipped tool.

Note, the graphics for the meter aren&#8217;t final at all. There&#8217;ll be more of a papery feel to the center bit, with a green->red metery type thing, I think. I plan on more pipes and lights (more than the current count of zero, at least) on the widgety area, so steam can leak out of the apparatus when the meter&#8217;s in the red zone and lights can blink and such.

### You&#8217;re such a tool.

The brown boxy area to the right of the metery area is the currently-selected-tool indicator. Currently empty because I&#8217;ll be getting to the tools section next update, it&#8217;ll have a left/right button to mouse-flip through them, a &#8220;help&#8221; button to summon a description of the tool and everything that you &#8220;know&#8221; in game that it does thusfar (ie, you need to be told what it does by someone or need to use it in a certain way before said atom of information shows up on the help screen).

There&#8217;ll also be somewhere in the HUD, most likely directly right of the toolbox, a meter showing Onam&#8217;s current MP level. This is because some of the &#8220;tools&#8221; are actually magic spells that can be used upon the environment. And not 0MP spells like Lufia 2&#8217;s &#8220;Reset&#8221; spell!

### Out, out, damn spot!

<div style="float: right; padding: 4px; margin: 4px;">
  <img src=/files/gruedorf_challenge/003/2007-10-28_1_fadey!.PNG alt="Steampunky meters and sliding banners and names, oh my!"><br /><span style="color: silver; font-size: -1;">Transitionlicious. The UI fades away when not in use.</span>
</div>

In &#8220;peaceful&#8221; areas, the Heads-Up Display will fade away when the mouse has been left alone for more than three seconds, as long as nothing is changing up there. As soon as an alert summons it back, it&#8217;ll come back. Such triggers like flipping through active skills with whatever controller buttons are mapped to that action, moving the mouse, triggering a HUD message banner, and so on

### Electronic Rodents

You all may have noticed that last week&#8217;s release and this week&#8217;s release both have mousey components. Well, The Astrad is mainly a computer game, so it&#8217;s foolish to not use the main UI device of the common computo-box for the game. I&#8217;m planning on having every element necessary for gameplay accessible both via 8-button controller mappings (that&#8217;d be a digital D-pad, A/B/X/Y/L/R/Select/Start just like a SNES) that you can map to the keyboard or a compatible joystick, and simultaneously only need a mouse (if present). Sorry kids, you need a mouse or a keyboard or a controller to play this game. No telekinetic controls yet. :(

Movement via mouse is planned much akin to how <a href=http://actionsketch.com/ target=_new>Ragecage/Tristan</a> accomplished it in <a href=http://www.verge-rpg.com/gallery/gallery.php?snowscape target=_new2>The Snowscape Battle System HoV entry</a>. That being an A* implementation where you click on an unobstructed tile and it tries to find a path. My system will be a bit more picky in that it will only try to find a path through visible areas fairly close to the screen&#8217;s visible boundaries. No autowalking across town if there&#8217;s a large obstructed area in the way between two visible points.

### The Astrad

Today&#8217;s last point of order: I don&#8217;t recall if I ever publicly explained that &#8220;Saga of the Stars&#8221; is the translated title of the game, whereas &#8220;The Astrad&#8221; is the real title. It&#8217;s shorter, lexicographically close to the beginning of any name list, and has a properly gruvian level of pretense, what with the faked Latin and the idea of evoking &#8220;The Aeneid&#8221; and &#8220;The Iliad&#8221; (which, of course, will not hold even the meanest candle to my finished work when completed. Take **_THAT_**, Virgil!)

So, in effect, I&#8217;ll probably still call it SotS while referring to it as &#8220;The Astrad&#8221;. Think of it as PSX meaning &#8220;Playstation&#8221; due to changing plans. Or whatever. You can retcon whatever story you&#8217;d like.

<a href=/files/gruedorf\_challenge/003/sots\_2007-10-28_003.rar>Click here to download the third Gruedorf release of Saga of the Stars/The Astrad/Grutopian Delight/etc etc etc</a>. You&#8217;ll be glad you did&#8230; unless I&#8217;m _lying_.