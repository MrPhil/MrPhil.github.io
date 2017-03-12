---
id: 350
title: Things I learned at Torque Boot Camp Day 2
date: 2005-10-12T21:30:47+00:00
author: MrPhil
layout: post
guid: http://www.mrphilgames.com/?p=350
permalink: /things_i_learne_3/
categories:
  - News
---
&#8211; Successful people just fiddle with Torque for a good while before trying to make a game
  
&#8211; SceneObject bins help limit the amount of collision math/processing that is needed
  
&#8211; Portals are about DIF not DTS
  
&#8211; Gotcha using RenderTransform() instead of normal Transform()
  
&#8211; GameBase datablocks, processTick(), ControlObjects
  
&#8211; ShapeBase
  
&#8230; Assumes a 3D world
  
&#8230; TGE isnt totally thread safe
  
&#8230;&#8230; this is one of the improvements in TGS
  
&#8230;&#8230; Atlas and IRC needed multi-threading ability
  
&#8230; MountingImages
  
&#8230; Events are not the same as Call-Backs CallBacks are in process, meaning they are part of the Tick process, but Events are processed outside the tick loop
  
&#8211; Player
  
&#8230; ConsoleMethod( Player, MethodName, Const Char*, 3, 3, help string );
  
&#8230; Argv array of arguments, C++ args, not script arguments
  
&#8230; dSscanf d is for dynmaix; cross-platform consistency, but might act a little different than a standard lib function
  
&#8230; Con::executef purpose so C++ can call script, Dont block b/c its during a tick (most likely)
  
&#8230; Schedule 0 means next available moment (After tick and other sensitive work)
  
&#8230; SimEvent would be a good way to hook in a non-Torque application with TCP/IP