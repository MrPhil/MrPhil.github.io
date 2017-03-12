---
id: 1250
title: XNA SpriteFonts
date: 2011-08-30T00:08:52+00:00
author: MrPhil
layout: post
guid: http://www.mrphilgames.com/?p=1250
permalink: /xna-spritefonts/
categories:
  - Iron Roads
---
While working on Iron Roads today, I tried to use the custom font [Radius](http://www.urbanfonts.com/fonts/Radius.htm) (a free font from Urban Fonts.)   I like how the letters look like curving tracks you might see on a draftsman&#8217;s drawing or surveying map.  It has potential for the Iron Roads logo.  Anyway, I ran into a tricky problem that stumped me for a long while.

<p style="text-align: center;">
  <a href="http://www.mrphilgames.com/wp-content/uploads/2011/08/Iron-Roads-with-Radius-Font.png"><img class="size-full wp-image-1252 aligncenter" title="Iron Roads with Radius Font" src="http://www.mrphilgames.com/wp-content/uploads/2011/08/Iron-Roads-with-Radius-Font.png" alt="Iron Roads with Radius Font" width="463" height="71" srcset="http://www.mrphilgames.com/wp-content/uploads/2011/08/Iron-Roads-with-Radius-Font.png 661w, http://www.mrphilgames.com/wp-content/uploads/2011/08/Iron-Roads-with-Radius-Font-300x46.png 300w" sizes="(max-width: 463px) 100vw, 463px" /></a>
</p>

I followed the normal procedure as Microsoft describes in [Drawing Text with a Sprite](http://msdn.microsoft.com/en-us/library/bb447673(v=XNAGameStudio.40).aspx):

>   1. Right-click your Content project in Solution Explorer, click **Add**, and then click **New Item**.
>   2. In the **Add New Item** dialog box, click **Sprite Font**. You may find it convenient at this point to change the name of the new file from &#8220;SpriteFont1&#8221; to the friendly name of the font you intend to load (keeping the .spritefont file extension).  The friendly name identifies the font once it is installed on your computer, for example, &#8220;Courier New&#8221; or &#8220;Times New Roman.&#8221; When you reference the font in your code, you must use the friendly name you have assigned it. XNA Game Studio creates a new .spritefont file for your font and opens it.

At this point I had what I needed, but alas, it wouldn&#8217;t compile, complaining:

> The font family &#8220;Radius&#8221; could not be found. Please ensure the requested font is installed, and is a TrueType or OpenType font.

Took me a long while to figure it out, but it&#8217;s actually quite simple. **Install new fonts before starting up Visual Studio!** So, all I had to do was shut VS2010 down and start her up again, an Voila! New beautiful font displaying in my game!!!

[<img class="aligncenter size-medium wp-image-1258" title="Iron Roads Title Screen Draft Peek" src="http://www.mrphilgames.com/wp-content/uploads/2011/08/Iron-Roads-Title-Screen-Draft-Peek-300x62.png" alt="Iron Roads Title Screen Draft Peek" width="300" height="62" srcset="http://www.mrphilgames.com/wp-content/uploads/2011/08/Iron-Roads-Title-Screen-Draft-Peek-300x62.png 300w, http://www.mrphilgames.com/wp-content/uploads/2011/08/Iron-Roads-Title-Screen-Draft-Peek.png 615w" sizes="(max-width: 300px) 100vw, 300px" />](http://www.mrphilgames.com/wp-content/uploads/2011/08/Iron-Roads-Title-Screen-Draft-Peek.png)

<p style="text-align: center;">
  <em>Please note, this is a concept piece, not art assets are my original and I don&#8217;t claim copyright to them.</em>
</p>