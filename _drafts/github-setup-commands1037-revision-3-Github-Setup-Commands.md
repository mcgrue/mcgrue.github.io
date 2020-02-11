---
id: 1041
title: Github Setup Commands
date: 2010-12-25T23:18:52+00:00
author: mcgrue
layout: revision
guid: http://www.egometry.com/gruedorf/1037-revision-3/
permalink: /gruedorf/1037-revision-3/
---
(This is mainly because I keep forgetting them and I don&#8217;t want to keep making new repositories to see these steps.)

## Global setup:

### Download and install Git, and then&#8230;

<pre>git config --global user.name "MY NAME"
git config --global user.email MY@EMAIL.COM</pre>

## Next steps:

<pre>mkdir 
cd MY-NEW-REPOSTORY
git init
touch README
git add README
git commit -m 'first commit'
git remote add origin git@github.com:GITHUB-USERNAME/MY-NEW-REPOSTORY.git
git push origin master</pre>

## Existing Git Repo?

<pre>cd existing_git_repo
git remote add origin git@github.com:GITHUB-USERNAME/MY-NEW-REPOSTORY.git
git push origin master</pre>