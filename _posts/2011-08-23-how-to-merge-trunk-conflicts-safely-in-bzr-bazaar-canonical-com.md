---
id: 1207
title: How to merge trunk conflicts safely in bzr (bazaar.canonical.com/)
date: 2011-08-23T15:57:02+00:00
author: mcgrue
layout: post
guid: http://www.egometry.com/?p=1207
permalink: /tech/how-to-merge-trunk-conflicts-safely-in-bzr-bazaar-canonical-com/
categories:
  - Technology
tags:
  - bzr
  - sadness
---
Sadly, the openstack community currently uses bzr instead of git. Instead of rebasing, this is the process by which I have to deal with tree conflicts &#8220;safely&#8221;?

<pre>bzr branch lp:trunk_project merge_temp_dir
cd merge_temp_dir && bzr merge ../your_original_branch
vi path_to_the_conflicted_files #and make your merges
bzr resolved
bzr commit -m "resolving commits."
bzr push --overwrite lp~myusername/path/to/my/branch
</pre>

I hate this. And I&#8217;m storing it here so I can reference it in the future.