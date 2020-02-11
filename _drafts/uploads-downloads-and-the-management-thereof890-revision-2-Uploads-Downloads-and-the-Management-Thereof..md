---
id: 892
title: Uploads, Downloads, and the Management Thereof.
date: 2009-07-08T08:35:45+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/890-revision-2/
permalink: /gruedorf/890-revision-2/
---
After some prodding, I managed to get the <a href="http://www.gearleaf.com/node/39" target=_blank>dorf</a> back into <a href=http://www.johnweng.com/gruedorf/ target=_blank>gruedorf</a>. Let the games resume.

Since last I posted about <a href=http://beta.verge-rpg.com/ target=_blank>beta.vrpg</a>progress 58 revisions have occurred. In that time:

  * I got file submissions up.
  * I got (simple, title-based) file searches up.
  * I got most of the file details page up (thread spawning, screenshot uploading pending).
  * I did a _lot_ of database reworking and massaging, mainly to get to a point where&#8230;
  * &#8230;single file entries can have multiple physical files attached, so one game can have file links to every OS it&#8217;s released on

Oh, and I made a <a href=http://beta.verge-rpg.com/simulated-bad-error target=_blank>Silly 500 Internal Service Error page</a>.

Definitely the most important part of this work.

Going forward will be finishing the file management side of things (letting you deprecate old versions of files in favor of new ones, showing a browsable history, letting you edit and delete files you own), and cranking out the community-based side of things (ie, image uploading and talkback threads on file pages.) After that, advanced search options and a browsable file index, and the section should be complete.

I&#8217;m mainly excited to see a upload system that hasn&#8217;t seen a failure yet. This was one of the major failures of the current vrpg that prompted the rewrite. I used <a target=_blank href=http://www.swfupload.org/>swfupload</a> for the actual UI/handling of the upload, and integrating it went very smoothly.