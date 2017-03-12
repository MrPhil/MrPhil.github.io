---
id: 136
title: Your Own “Servlet” or HTML Spew Machine
date: 2004-09-22T18:23:25+00:00
author: MrPhil
layout: post
guid: http://www.mrphilgames.com/?p=136
permalink: /your_own_servle/
categories:
  - News
---
So you want a quick way to spew your own html?

Create an aspx page and remove all the html and then in the code behind replace the Page_Load procedure with:

> private void Page_Load(object sender, System.EventArgs e)
  
> {
      
> Response.Clear();
      
> Response.ClearHeaders();
      
> Response.ContentType = &#8220;Text/HTML&#8221;;
      
> Response.AppendHeader( &#8220;your header&#8221;, &#8220;your value&#8221; );
      
> Response.Write( &#8220;Your spew&#8221; );
  
> }

Of course you don&#8217;t have to spew html.

-Mr.Phil

When I am not writing about making games, procrastinating or watching movies I&#8217;m working on a science fiction strategy game (sometimes called 4X or empire builder.) Email me questions, ideas and jokes at mrphil (at) mrphilgames . com