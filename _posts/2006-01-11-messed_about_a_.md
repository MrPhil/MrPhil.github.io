---
id: 322
title: Messed about a little today with Torque’s networking code
date: 2006-01-11T21:17:36+00:00
author: MrPhil
layout: post
guid: http://www.mrphilgames.com/?p=322
permalink: /messed_about_a_/
categories:
  - News
---
I messed about a little today with Torque’s networking code. I was looking to see if they used bit packing. I was also curious to see how difficult it would be to create a plug-in system that allowed you to use different compression techniques. It definitely has an interesting system that tries to only move the data that has changed (as opposed to the whole object every time something in it changes.) I haven’t tracked down the part that actually packs the variables, because it wasn’t part of the variable classes like I expected. They are probably either doing it in the object (i.e. the author customizes the packing for each object) or at the stream level. I’ll definitely need to create some sort of test bed before I attempt to muck around.