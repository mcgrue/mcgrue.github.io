---
id: 714
title: Split-Testing and Late-Night Coding
date: 2009-03-05T00:26:45+00:00
author: mcgrue
excerpt: 'When testing a feature wrapped in a spiffy-keen augmentation of an experiment system live, please remember to take into account that you have a 50% chance to land in the "nothing happens" side of the experiment.  This will probably save you a lot of trouble.'
layout: revision
guid: http://www.egometry.com/gruedorf/713-revision/
permalink: /gruedorf/713-revision/
---
### Experiments!

<a href=http://joblivious.wordpress.com/2009/02/24/advanced-tdd-two-birds-with-one-stone/ target=_blank>Split Tests</a> are a very powerful way to determine if a thing you are doing is in your best interest or not. If you aren&#8217;t familiar with A/B tests, the very high level is that you show half of your users one thing, half another thing, and you compare the results of each set of users.

### Humanity

One of the more mundane, human problems you can run into as an engineer is tiredness. Tunnel vision sets in, and you focus on specific tasks. If you&#8217;re solving a complex math problem, you make an arithmetic error. If you&#8217;re a coder not using TDD, often you&#8217;re running into syntax errors or the like.

These things happen.

### Process

At IMVU, we deploy code <a href=http://timothyfitz.wordpress.com/2009/02/10/continuous-deployment-at-imvu-doing-the-impossible-fifty-times-a-day/ target=_blank>fifty times a day</a>. The code you just wrote goes out to the production cluster without waiting for QE people to sign off on it, or for your manager to approve it. 

Engineering under TDD acts like a blanket to shield you from a lot of problems. You know from the get-go if you broke something in a more interesting way (assuming said interesting way was protected by a test). The tests exist to protect you before you get near the production systems. A failed test on your buildbot is a _good_ thing, because that&#8217;s a broken thing your customers never had to deal with. As someone who had jobs where he was tacitly encouraged to code untested fixes on the fly on the production machines in other jobs, this is a godlike boon.

However, things go wrong, and sandboxes and production environments still can disagree! This is why the final step of pushing code live to a production server is **always**, <u>always</u>, _always_ verify your change manually out in the live website.

And if it&#8217;s not verified (or if your change breaks things in _very_ unexpected ways, causing die spikes or high database load or the such), to revert to a previous known good state and investigate further.

### Moral

Now that all of the background for tonight is set up, I&#8217;ll skip the actual stupidity, and jump straight to the conclusion:

_When testing a feature wrapped in a spiffy-keen augmentation of an experiment system live, please remember to take into account that you have a 50% chance to land in the &#8220;nothing happens&#8221; side of the experiment. This will probably save you a lot of trouble._

It was a pleasant surprise when I looked up to see a wonderful forest around me. I&#8217;d just been staring at this one tree over here.

At least I wasn&#8217;t alone in this glaring human-error oversight.