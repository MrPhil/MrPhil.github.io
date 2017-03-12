---
id: 236
title: 'SilverLight DevCamp Nugget #3'
date: 2007-11-12T20:30:53+00:00
author: MrPhil
layout: post
guid: http://www.mrphilgames.com/?p=236
permalink: /silverlight-devcamp-nugget-3/
categories:
  - News
---
An interesting question is how pop-up blockers and such interact with SilverLight. I personally had troubles with AVG freaking out when I was installing the SilverLight SDK. I finally got it to install correctly after I disable the &#8220;Resident shield.&#8221; I then promptly turned it back on only to have it mess up the creation of a SilverLight project. So at this point AVG gets turned off any time I’m dealing with SilverLight.

For now protection software makers’ are playing catching up and are slowly becoming aware of SilverLight. I’d wager that pop-ups will be a problem for about a year, so plan accordingly.

When [Pete Brown](http://web.archive.org/web/20071117034604/http://community.irritatedvowel.com/blogs/pete_browns_blog/default.aspx) was building the [Carbon Calculator](http://web.archive.org/web/20071117034604/http://community.irritatedvowel.com/blogs/pete_browns_blog/archive/2007/07/07/Silverlight-1.1-Carbon-Offset-Calculator-is-out_2100_.aspx) pop-up blockers where a big concern. His solution was to use a page redirect and query strings. The crux of the problem is if a blocker comes up, then the user has to enable pop-ups, which causes the page to refreshed, thereby zapping all the data!