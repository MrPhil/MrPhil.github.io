---
id: 259
title: DOH!, Pause = Thread.Sleep(42)
date: 2006-06-25T20:43:56+00:00
author: MrPhil
layout: post
guid: http://www.mrphilgames.com/?p=259
permalink: /doh_pause_threa/
categories:
  - News
---
<div>
  <div>
    <p>
      So I&#8217;ve been working with .Net for years and today I put something together that made me feel foolish for not already realizing. Especially since I&#8217;ve used Threads before and even timed them out. I just never had the concept of needing to pause my code bump up next to the fact that my “normal” code is in a thread too.  I’ve gotten so used to only dealing with threading stuff in special situations I guess I forget that my everyday code is threading too. So if you want to pause your code for a certain number of milliseconds do this
    </p>
    
    <pre>     System.Threading.Thread.Sleep( milliseconds );</pre>
    
    <p>
      Not:
    </p>
    
    <pre>    DateTime stop = DateTime.Now.AddMilliseconds( milliseconds );
    while( DateTime.Now &lt; stop );</pre>
    
    <p>
      Or some other machination with DateTimes and loops.
    </p>
    
    <p>
      Oh well, it not really my fault it is simply a side affect of global warming.
    </p>
  </div>
</div>