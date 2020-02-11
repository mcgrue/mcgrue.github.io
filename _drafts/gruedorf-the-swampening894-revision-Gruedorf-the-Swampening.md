---
id: 895
title: 'Gruedorf: the Swampening'
date: 2009-07-15T12:48:46+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/894-revision/
permalink: /gruedorf/894-revision/
---
Between putting in incredible hours at work, and a few Magic: the Gathering pre-release events in the last week, I haven&#8217;t had much time for gruedorfing.

However, I still got 14 commits in.  (All of them Friday morning.)

The work done was all in finalizing the /downloads/complete-new-os/ page, and tracking down and fixing errors that had cropped up in the upload process.

The second item distresses me, presently, since a solid upload system was the main impetus for the rewrite.  finding out that uploads are still fragile and very prone to breaking with forward development, combined with the fact that I don&#8217;t have a testing strategy for roundtrip uploads, means I&#8217;m kinda nervous.

So, anyone out there have a good solution for a round-trip integration test where you upload, via flash and javascript, a unique file, and then verify that the file exists on a unix filesystem, and then verify that a corresponding database entry and further corresponding webpage works?

Moving forward, I&#8217;ll be working on an administrative page to allow file owners/admins to associate file instances as older