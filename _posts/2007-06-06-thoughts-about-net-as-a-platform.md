---
id: 220
title: Thoughts about .Net as a platform
date: 2007-06-06T20:22:10+00:00
author: MrPhil
layout: post
guid: http://www.mrphilgames.com/?p=220
permalink: /thoughts-about-net-as-a-platform/
categories:
  - News
---
#### Framework != Common Runtime Library

You might not know that Microsoft has split the concept of the “Framework” from the CLR (Common Runtime Library). The .Net 3.0 Framework has the 2.0 CLR plus Windows Presentation Foundation (WPF), Windows Workflow Foundation (WF), Windows Communication Foundation (WCF), and Windows CardSpace. Vista has the 3.0 .Net Framework installed standard.  This means you can develop games on the 2.0 CLR and they will run on Vista without having to worry about installing a Framework.Put another way all new computers will run you 2.0 games.Watch out though because the 3.5 Framework will have a new version of the CLR.

#### .Net Framework Download Sizes (Redistributable Package x86)

<table>
  <tr>
    <td>
      <span style="text-decoration: underline;">Version</span>
    </td>
    
    <td>
      <span style="text-decoration: underline;">Size</span>
    </td>
    
    <td>
      <span style="text-decoration: underline;">Dial-up 56k</span>
    </td>
    
    <td>
      <span style="text-decoration: underline;">DSL 256k</span>
    </td>
    
    <td>
      <span style="text-decoration: underline;">DSL 756k</span>
    </td>
  </tr>
  
  <tr>
    <td>
      1.1
    </td>
    
    <td>
      23.1 MB
    </td>
    
    <td>
      57 mins
    </td>
    
    <td>
      13 mins
    </td>
    
    <td>
      4 mins
    </td>
  </tr>
  
  <tr>
    <td>
      2.0
    </td>
    
    <td>
      22.4 MB
    </td>
    
    <td>
      55 mins
    </td>
    
    <td>
      12 mins
    </td>
    
    <td>
      4 mins
    </td>
  </tr>
  
  <tr>
    <td>
      3.0
    </td>
    
    <td>
      25.2 MB*
    </td>
    
    <td>
      62 mins
    </td>
    
    <td>
      14 mins
    </td>
    
    <td>
      5 mins
    </td>
  </tr>
  
  <tr>
    <td>
      XNA
    </td>
    
    <td>
      66.7 MB**
    </td>
    
    <td>
      111 mins
    </td>
    
    <td>
      24 mins
    </td>
    
    <td>
      18 mins
    </td>
  </tr>
  
  <tr>
    <td colspan="5">
      * The 3.0 download is actually a couple megs plus the 2.0 Framework
    </td>
  </tr>
  
  <tr>
    <td colspan="5">
      ** This is a rare worst case scenario; it includes the XNA dlls, the 2.0 Framework and DirectX 9.0c
    </td>
  </tr>
</table>

I think people have over emphasized the download time problem.It is even less of a problem now because every new computer sold today has it installed! I think the real issue is the all the Mac customers&#8217; dollars you will be missing.[Mono](http://www.mono-project.com/Main_Page)is a potential solution but I’m pretty sure it will not be compatible with XNA.

My personal position is that the speed of development with C# out weights the extra dollars a Mac release could earn because you can make games faster.When you add the potential market of Xbox 360 it seems like and even smarter direction to go. That said, the number one reason I’m using C# is because I love C# and I don’t WANT to use something else. Part of being indie is doing it your own stubborn wrong headed way!

#### .Net Complied?

There are ways to compile .Net to native code or virtualize the .Net Framework and eliminate the need for installing the framework. I have no personal experience with this but I do know about these products:[VM Lösungen](http://thinstall.com/solutions/net_virtual.php) [Salamander](http://www.remotesoft.com/linker/) I’ve also heard of people using [Mono](http://www.mono-project.com/Main_Page) to create a similar solution, but that sounds like way too much work.

#### Further research

&#8220;Land of Legends&#8221; – was made with .Net pre-XNA

&#8220;World Wind&#8221; – NASA’s solution to the .Net/MDCX installation problem

<http://msdn2.microsoft.com/en-us/library/ms994415.aspx> &#8211; makes your website detect and install on clients without the framework

[http://www.indiegamer.com](http://www.indiegamer.com/) &#8211; .Net has been talked about a lot there, be sure to look into the [archives](http://forums.indiegamer.com/archive/index.php/) too.