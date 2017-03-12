---
id: 1310
title: 'Unity3D #pragma strict Gotch'
date: 2011-12-29T22:27:28+00:00
author: MrPhil
layout: post
guid: http://www.mrphilgames.com/?p=1310
permalink: /unity3d-pragma-strict-gotch/
categories:
  - News
---
I was working with some code in a book today and could not figure out why a variable was giving me problems.

> Unknown idenifier: &#8216;mesh&#8217;. (BCE0005)

I don&#8217;t usually program using JavaScript much less with MonoDevlop, so it took me a while.  Turns out, it&#8217;s a little thing:

> #pragma strict

I was using it, and the book wasn&#8217;t.  They didn&#8217;t declare the variable in the example unlike ALL the other ones! That&#8217;s why it is unknown, it IS unknown.  The sample code that came with the book compiled because it doesn&#8217;t have the #pragma strict.