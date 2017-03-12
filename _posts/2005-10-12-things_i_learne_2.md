---
id: 352
title: Things I learned at Torque Boot Camp Day 1
date: 2005-10-12T21:31:23+00:00
author: MrPhil
layout: post
guid: http://www.mrphilgames.com/?p=352
permalink: /things_i_learne_2/
categories:
  - News
---
&#8211; Use Doxygen for your own code because one day you might have to hire someone to work with your stuff, or it might be months before you go back to that area of the code
  
&#8211; ShowTool Pro saves a lot of time debugging art asset problems and is worth its weight in gold, and it is written in Torque!
  
&#8211; DTS can have concave shapes
  
&#8211; DIF no concave shapes, this allows BPS trees which perform much faster, but cant fully animate
  
&#8211; LOD is based on pixel height not distance from camera
  
&#8211; Jill pack is a great learning tool
  
&#8211; Atlas is faster than TGE terrain engine
  
&#8211; All of TGE is in TSG, you arent losing any functionality and is probably the way to go for a new project these days
  
&#8211; You must use Mono sounds not Stereo when working with 3D emiters
  
&#8211; DNA replication for grass and tress eliminates server bandwidth problems, this way you can provide the effects without having to simulate every blade of grass and twig in the tree.
  
&#8211; Portals can help a lot with scene frame rate problems on interiors
  
&#8211; 4 is the average number of LOD
  
&#8211; TCL is a scripting language, stands for Tool Command Language
  
&#8211; Two useful console commands: Tree(), [object].Dump()
  
&#8211; The car metaphor: A game engine is like a car, it has all the parts and systems needed to start up, idle, turn, heat, cool etc. But needs a driver (the script) in order to truly be useful moving people around. The script is like the driver pressing the gas pedal and turning the steering wheel.
  
&#8211; SimObject provides smart referencing which is mucho help dealing with pointers, especially protection from stale pointers
  
&#8211; A SimObject maybe a member of only ONE SimGroup
  
&#8211; When a SimGroup is deleted so are all its members
  
&#8211; SimSet has an onDeleteNotify()
  
&#8211; There is a SimSetIterator
  
&#8211; A client is sent a Datablock ONCE when the mission starts this means that if you change a value in a Datablock after the mission has begun the client will never know about it
  
&#8211; Datablocks are like the Ten Commandments, once they got handed down that was that, no changes would propagate to all the copies
  
&#8211; Network scoping is more like the smelling than seeing because something can be in scope even when it is impossible to see
  
&#8211; Hysteresis is a hard word to explain
  
&#8211; There is voice code in Torque, but almost always it is better to use a third party tool like Team Speak
  
&#8211; A Ghost(ed) object is simply a model on the client of an object that the server has authority (ie control) over. The client has to sometimes predict what has happened since the last time it heard from the server, but once the client hears from the server again those predict values are throw out (ie changes to a Ghosted object do not affect the real object.)
  
&#8211; A tick is sent every 32 milliseconds
  
&#8211; 1000 milliseconds = 1 second
  
&#8211; Playing with un/pack can be easy to mess up because one-bit mistakes can bring the whole house down