---
id: 364
title: Bzzzzz dump
date: 2005-03-17T21:37:43+00:00
author: MrPhil
layout: post
guid: http://www.mrphilgames.com/?p=364
permalink: /bzzzzz-dump/
categories:
  - News
---
Last .Plan’s Results:
  
So I’m definitely a T2D convert. I’ve halted all work on my custom engine and am going 100% T2D. I did the tutorial and liked it a lot. Here’s a small screen capture of my game’s starmap in T2D (can you find the fleet icon?)

<img href=http://www.mrphilgames.com/images/ss/StarmapSS.jpg</img>
  
[image]http://www.mrphilgames.com/images/ss/StarmapSS2.jpg[/image]
  
And here it is zoomed out.

I also added a splash screen. 

I’ve stopped my work on adding Torque script as a language to Visual Studio. It will take a sizable effort to accomplish and I’d rather work on my game or website.

I’ve picked UltraEdit (v11) as my Toque Script editor because it is inexpensive, has the best smart indenting, allows me to add Torque Script as a language pretty easily, and I can customize the highlighting colors. The one feature it has that stands out among them all is the function jumping/listing tool. Navigating using this make life SOOOO much easier. 

The only thing I wish it had was the magic formatting feature you get with Visual Studio .Net. Oh well, maybe that’ll be in the next version. Here’s a list of why I eliminated all the other options (note the list is rough because some things I scratch off the second they where unintuitive or missing a feature I wanted):

[url=http://www.editplus.com/]EditPlus[/url] &#8211; No smart indenting and for $30 might as well get UltraEdit and get smart indenting! (To be fair this was my third choice)
  
[url=http://www.jedit.org/]jEdit[/url] with [url=http://torqueide.sourceforge.net]TIDE[/url] &#8211; Slow, function jumping system stupid, no brace formatting and no projects of course this will come back to haunt me when I want to debug.
  
[url=http://www.notepad.org/]NotePad[/url] – Name a feature. It doesn’t have it.
  
[url=http://www.eclipse.org/]Eclipse[/url] with [url=http://opensource.kruxgames.com/torquedit/]TorqueEdit[/url] – My Microsoft centric brain can’t comprehend your advance Java GUI concepts
  
[url=http://www.twinno.com/brainedpro/]Brain Editor Professional[/url] &#8211; Demo was expired when I installed it, didn’t take time to fight with it
  
[url=http://www.context.cx/]ConTEXT[/url] &#8211; Good file browser, semi-auto-indenting, Free! I almost picked this one.
  
[url=www.multiedit.com]MultiEdit[/url] &#8211; $495!!! You realize what that kind of money that is? You can freaking get a new computer for $500! I doubt Microsoft’s Visual Studio Express will costs more than that!
  
[url=www.slickedit.com]SlickEdit[/url] – an eclipse plug-in, see My Microsoft centric brain above.
  
[url=vim.sf.net]Vim[/url] – nice in that command line, telnet kind of way
  
[url=www.emacs.org]Emacs[/url] – didn’t bother, see Vim

[url=http://www.textpad.com/]Textpad[/url] &#8211; no brace matching formatting, or auto complete
  
[url=http://www.crimsoneditor.com/]Crimson Editor[/url] – looked like so many I had tried already so I didn’t bother
  
[url=http://home.t-online.de/home/Jens.Altmann/jfe_eng.htm]Jens&#8217; File Editor[/url] &#8211; according to website is doesn’t have brace matching, function jumping or auto complete so I didn’t bother downloading it, but it was a clever idea to give it a girls name.

I also figured out a cool way to make UltraEdit help me find compile errors in the console log. I added the log as a syntax language and defined the error messages as functions. This way they show up as a list in the function-jumping window. I promise to add it as a resource down the road when I’ve ‘dog fooded’ it for a while.

My new tasks:
  
&#8211; Add simple main menu screen with new game button
  
&#8211; Add short command line switch to by-pass the tedious splash screen and main menu I just got done adding. 😀
  
&#8211; Get object picking so I can place more fleets
  
&#8211; Add Purchase
  
&#8212; Allow user to click on icons of items he wants to buy
  
&#8212; Allow user to click on items in ‘shopping cart’ to change mind about buying that ten billion dollar Battleship with full compliment of fighters
  
&#8212; Guess they’ll need a commit or next button to finish the phase.