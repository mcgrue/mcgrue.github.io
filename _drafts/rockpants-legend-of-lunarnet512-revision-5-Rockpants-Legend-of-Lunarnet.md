---
id: 517
title: Rockpants, Legend of Lunarnet
date: 2009-02-07T14:53:48+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/512-revision-5/
permalink: /gruedorf/512-revision-5/
---
### Hotpants, the Lunarnet Bot

For over a year, on the Lunarnet IRC Network, <a href=http://halfassured.com>Gayo</a> had a bot running around many channels with a variety of commands. 

It would pull a quote from his quotefile if you used **!q**. It could generate slashfiction on the fly if you used **!slash**. It would generate gibberish on some commands. It would pull from and if you ever did a ! command that it didn&#8217;t recognize, it&#8217;d md5 the string and modulus the result to the size of the array of all known commands, so that no matter what, a line starting with an exclamation point would trigger _some_ sort of reaction from the bot, and always the same mapping for the same nonsense command. **!penis** would always do what **!penis** did before&#8230; unless the list changed.

And if you ever did a lone **!**, it would emit a number.

And if you ever did it again, it would emit another number, _exactly one less than the previous one_.

Nobody knew of this at first. Gayo kept his trap shut when he re-tooled from a static list of commands to a &#8220;everything will do something&#8221; structure, and implemented the counter then. The lone **!**&#8216;s existence went months without anyone noticing it.

And then it was discovered. How curious: it&#8217;s counting down.

We&#8217;d hit a !, and it&#8217;d say 912323. We&#8217;d do a !slash and a !q and a !, and then it&#8217;d say 912320. It became very clear that it was counting down it&#8217;s every use, and we became very interested in what would happen when it ran out.

Increasingly over months in various rooms of lunarnet, groups of people would spam the bot in idle hours. Speculation grew high. Some imagined it&#8217;d do nothing, by intent or programming flaw. Others speculated that it&#8217;d just keep counting into the negatives. But most of us were hoping for something&#8230; awesome.

Gayo says that when the feature was installed, it was set to 1000000. It took over a year to hit the end. When we got into the 500,000&#8217;s, people started passing around a large text file consisting only of exclamation points and newlines and using mIRC&#8217;s /play command on it overnight to help run down the counter.

Then, one night, after months of the lunarnet community speculating and joining into the count-diminishing effort, the end was finally in sight:

### The Final Countdown

* * *

<pre style="line-height: 150%"><b>&lt;Zack></b> ALRIGHTY THEN
<b>&lt;Lucca></b> Here we go!
<b>&lt;Zack></b> !
<b style="color: #FF00FF;">&lt;Hotpants></b> 8
<b>&lt;ketsugi></b> !7
<b style="color: #FF00FF;">&lt;Hotpants></b> Qrngu Ung: gur Ung gung Znxrf Lbh Qvr
<b>&lt;ketsugi></b> !6
<b style="color: #FF00FF;">&lt;Hotpants></b> Qrrc-Sevrq Cresbeznapr bs gur Gurgna!
<b>&lt;Shastao></b> !
<b style="color: #FF00FF;">&lt;Hotpants></b> 5
<b>&lt;ketsugi></b> !5
<b style="color: #FF00FF;">&lt;Hotpants></b> Ø_ø
<b>&lt;Zack></b> !
<b style="color: #FF00FF;">&lt;Hotpants></b> 3
<b>&lt;Random></b> !
<b style="color: #FF00FF;">&lt;Hotpants></b> 2
<b>&lt;Zack></b> !
<b style="color: #FF00FF;">&lt;Hotpants></b> 1
<b>&lt;Random></b> !
<b style="color: #FF00FF;">&lt;Hotpants></b> 0
<b>&lt;ketsugi></b> !
<b>&lt;Zack></b> ...
<b>&lt;ketsugi></b> ...
<b>&lt;Random></b> :D :D :D :D :D :D
* ketsugi laughs
<b>&lt;Zack></b> HA
<b>&lt;Lucca></b> ...WHAT A GREAT PAYOFF ;D
<b>&lt;Etir></b> What, it says 0.
<b>&lt;Zack></b> Bravo, Gayo
<b style="color: #FF00FF;">&lt;Hotpants></b> It's been a long road, getting from there to here...
<b>&lt;ketsugi></b> !
<b>&lt;Zack></b> ...
<b>&lt;ketsugi></b> !
<b>&lt;Lucca></b> ...no look!
<b>&lt;ketsugi></b> !
<b>&lt;Etir></b> :o
<b>&lt;ketsugi></b> hm
<b>&lt;Zack></b> STOP
<b>&lt;Lucca></b> It's talking! :o
<b>&lt;Shastao></b> stop you twits
<b style="color: #FF00FF;">&lt;Hotpants></b> It's been a long time, but my time is finally near!
<b>&lt;ketsugi></b> no more?
<b>&lt;ketsugi></b> ah
<b>&lt;ketsugi></b> ...
<b>&lt;Zack></b> Mr. Roboto!
<b style="color: #FF00FF;">&lt;Hotpants></b> For I will see my dream come alive at last...I will touch the sky!
<b>&lt;ketsugi></b> Gayo needs a headcheck
<b style="color: #FF00FF;">&lt;Hotpants></b> No, they're not gonna hold me down no more; no, they're not gonna change my mind!
<b>&lt;Etir></b> Well duh
<b style="color: #FF00FF;">&lt;Hotpants></b> 'Cause I've got faaaith of the heaaart, and I'm going where my heart will take me!
<b style="color: #FF00FF;">&lt;Hotpants></b> I've got faith to believe I can do anything.
<b>&lt;Zeke></b> HA HA HA HA HA
<b style="color: #FF00FF;">&lt;Hotpants></b> I've got streeeength of the soooul, nothing's gonna bend or break me!
* Lucca stares. O_o
<b style="color: #FF00FF;">&lt;Hotpants></b> I can reeeeeeach any staaaaaaar....
<b>&lt;Zack></b> ...
* Zeke awards Gayo a purple heart.
<b style="color: #FF00FF;">&lt;Hotpants></b> I've got faith!
* Etir snickers
<b style="color: #FF00FF;">&lt;Hotpants></b> (I've got faith.)
<b style="color: #FF00FF;">&lt;Hotpants></b> (I've got faith.)
<b style="color: #FF00FF;">&lt;Hotpants></b> Faith of the heeearrt.
<b style="color: #FF00FF;">&lt;Hotpants></b> THANK YOU, THANK YOU ALL
<b style="color: #FF00FF;">&lt;Hotpants></b> IT WAS A LONG, STRANGE TRIP, BUT IN THE END, WE MADE IT, AND I THINK WE ALL LEARNED SOMETHING ALONG THE WAY
<b style="color: #FF00FF;">&lt;Hotpants></b> I COULDN'T HAVE MADE IT WITHOUT MY MANAGER GAYO, AND BAHAMUT, AND EVERYONE BACK HOME WHO SUPPORTED ME
<b>&lt;Lucca></b> Gaaah! ;D
<b>&lt;Zack></b> HEH.
<b style="color: #FF00FF;">&lt;Hotpants></b> THANKS YOU GUYS, THIS IS FOR YOU AS MUCH AS FOR ME
<b>&lt;Random></b> Is someone logging this?
<b style="color: #FF00FF;">&lt;Hotpants></b> I TELL YOU
<b>&lt;Shastao></b> duh
<b>&lt;ketsugi></b> My client at home is, if no one else
<b style="color: #FF00FF;">&lt;Hotpants></b> I BEEN A LOT OF PLACES ON THIS TOUR, BUT I GOTTA SAY, NO PEOPLE OUT THERE KNOW HOW TO PARTY LIKE #RPGCAFE PEOPLE
<b>&lt;Lucca></b> Damn right!
<b>&lt;Zack></b> Huzzah.
<b style="color: #FF00FF;">&lt;Hotpants></b> CMON YEAH GIVE IT UP
<b>&lt;Shastao></b> and Rand hit the 0 :P
<b style="color: #FF00FF;">&lt;Hotpants></b> YEAH, YEAH, YEAH!!!
<b>&lt;Zack></b> There's your claim to fame, Rand.
<b  style="color: #FF00FF;"> * Hotpants is now known as Rockpants</b>
<b>&lt;Etir></b> Forever known as "that guy who hit 0"
<b>&lt;Random></b> Whoo!
<b>&lt;ketsugi></b> ...
<b>&lt;Zack></b> ...
<b>&lt;Lucca></b> OH GOD!
<b>&lt;Etir></b> ...haha
<b>&lt;Zack></b> Bwahahah
<b style="color: red;">&lt;Rockpants></b> ONE TWO THREE FOUR
* Mune` has quit IRC (Ping timeout)
<b>&lt;ketsugi></b> o_O
<b style="color: red;">&lt;Rockpants></b> STOP!
<b>&lt;Zack></b> o_o
<b style="color: red;">&lt;Rockpants></b> IN THE NAAAAME OF LOVE
* Shastao thuds
* Mune` has joined #rpgcafe
<b>&lt;Lucca></b> Yeah! ;D
<b>&lt;Etir></b> lol!
* Lucca swoons for rockpants
<b>&lt;Zack></b> Bwahaha.
<b style="color: red;">&lt;Rockpants></b> BEFORE YOU BREAK MY HEART
<b style="color: red;">&lt;Rockpants></b> BABY, BABY
<b style="color: red;">&lt;Rockpants></b> I'M AWARE OF WHERE YOU GO
<b style="color: red;">&lt;Rockpants></b> EACH TIME YOU LEAVE MY DOOR
<b>&lt;Shastao></b> how long is this?
<b style="color: red;">&lt;Rockpants></b> I WATCH YOU WALK DOWN THE STREET
<b>&lt;Zack></b> No clue
<b style="color: red;">&lt;Rockpants></b> KNOWING THE OTHER LOVE YOU'LL MEET
<b style="color: red;">&lt;Rockpants></b> BUT THIS TIME BEFORE YOU RUN TO HER
<b>&lt;Lucca></b> brb
<b style="color: red;">&lt;Rockpants></b> LEAVING ME ALONE AND HURT
<b style="color: red;">&lt;Rockpants></b> THINK IT OVER
<b style="color: red;">&lt;Rockpants></b> AFTER I'VE BEEN GOOD TO YOU?
<b style="color: red;">&lt;Rockpants></b> THINK IT OVER
<b style="color: red;">&lt;Rockpants></b> AFTER I'VE BEEN SWEET TO YOU?
<b style="color: red;">&lt;Rockpants></b> STOP!!!
<b>&lt;Etir></b> This would be perfect if it reset to 1,000,000 again for round 2 at the end. ;)
<b>&lt;Zack></b> Oh god. :P
<b style="color: red;">&lt;Rockpants></b> IN THE NAAME OF LOVE
<b style="color: red;">&lt;Rockpants></b> BEFORE YOU BREAK MY HEART
<b style="color: red;">&lt;Rockpants></b> (clasps hands over heart)
<b style="color: red;">&lt;Rockpants></b> STOP! IN THE NAME OF LOVE
<b style="color: red;">&lt;Rockpants></b> BEFORE YOU BREEEAK MY HEART
<b style="color: red;">&lt;Rockpants></b> THINK IT OOOVER
<b style="color: red;">&lt;Rockpants></b> THINK IT OOOVER
<b style="color: red;">&lt;Rockpants></b> YEAH YEAH
<b style="color: red;">&lt;Rockpants></b> ETC ETC
<b style="color: red;">&lt;Rockpants></b> I WILL NOW RECITE FROM "THE WRECK OF THE HESPERUS," BY LONGFELLOW
<b style="color: red;">&lt;Rockpants></b> COLDER AND LOUDER BLEW THE WIND
<b style="color: red;">&lt;Rockpants></b> A GALE FROM THE NORTHWEST
<b style="color: red;">&lt;Rockpants></b> THE SNOW FELL HISSING IN THE BRINE
<b style="color: red;">&lt;Rockpants></b> AND THE BILLOWS FROTHED LIKE YEAST
* Shastao is now known as Shas-zzz
<b style="color: red;">&lt;Rockpants></b> DOWN CAME THE STORM AND SMOTE AMAIN
<b>&lt;ketsugi></b> amain?
<b style="color: red;">&lt;Rockpants></b> THE VESSEL IN ITS STRENGTH
<b style="color: red;">&lt;Rockpants></b> SHE SHUDDERED AND PAUSED LIKE A FRIGHTED STEED
<b>&lt;Katt></b> o_o
<b style="color: red;">&lt;Rockpants></b> THEN LEAPT HER CABLE'S LENGTH
<b>&lt;Zack></b> Ooookaaay..
<b>&lt;Random></b> ...He's had how many months to work on this?
<b style="color: red;">&lt;Rockpants></b> HLAGHLAGHLGHAHGH BALLS HONK
<b>&lt;Zack></b> Not sure.
<b style="color: red;">&lt;Rockpants></b> BONG BONG BONG BONG
<b>&lt;Zack></b> Anywhere from 2 to 6, maybe. I dunno
<b style="color: red;">&lt;Rockpants></b> LORD JESUS COME CARRY ME HOME
<b style="color: red;">* Rockpants has left #rpgcafe (SPORK)</b>
<b>&lt;Zack></b> ...
<b>&lt;Ashton></b> ...
<b>&lt;DooM_GazE></b> ...
<b>&lt;Zack></b> Ladies and gentlemen, Rockpants has left the channel.
<b>&lt;Etir></b> hahahahaha
</pre>