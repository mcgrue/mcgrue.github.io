---
id: 899
title: How to make a folder unwritable in windows (chmod 000), even for administrators
date: 2009-08-04T13:56:15+00:00
author: mcgrue
layout: post
guid: http://www.egometry.com/?p=899
permalink: /?p=899
categories:
  - Technology
tags:
  - administrator
  - chmod
  - permissions
  - windows
---
Unreadable, unwritable, unexecutable.  In linux, you&#8217;d chmod 000 the file or folder, and suddenly it&#8217;s forbidden for all.

In windows, if you&#8217;re an administrator, the very visible read-only checkbox in a file&#8217;s properties is just a mild suggestion.

But there is a way to make windows listen to you!

1. Turn off simple file sharing (go to an explorer window, go to Tools > Folder Options&#8230;, click on the View tab,  scroll to the bottom of the checkbox list and uncheck &#8220;Use simple file sharing (Recommended)&#8221; ).

2. Explore to the file or folder you wish to deny access to.  Right-click on it, and select properties.  Click to the Security tab.  There will now be a &#8220;Permissions for Administrators&#8221; section at the bottom.

Deny everything.  EVERYTHING.

And now you&#8217;ve forbidden even the god-like administrators of windows from accessing that file.  Congrats!