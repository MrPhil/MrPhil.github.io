---
id: 1182
title: Can I choose in which screen corner Steam notifications show up?
date: 2009-10-31T07:53:08+00:00
author: MrPhil
layout: post
guid: http://www.mrphilgames.com/?p=1182
permalink: /can-i-choose-in-which-screen-corner-steam-notifications-show-up/
categories:
  - News
---
This was moved here from GameLegend.com after StackExchange took the site down.
  
As long as I can remember, <a href="http://store.steampowered.com/" rel="nofollow">Steam</a> notifications always popped up in the bottom right corner. I had a hard drive crash and had to reinstall Steam, and now they are showing up in the top right corner. Is this something that was recently (Oct. 2009) changed by Valve, and more importantly, is there a setting to choose which corner to show notifications?

> Have you looked under File > Settings > In-game ?
> 
> Steam does not have a setting anywhere in the user interface that allows you to change the notification pop up location, but it is possible to modify it using a text editor.
> 
> There is a caveat to this, but in general you can edit the file **SteamScheme.res** in the directory _Steam\resource_ and change the setting for **Notifications.PanelPosition** to one of the following:
> 
>   * BottomRight
>   * BottomLeft
>   * TopRight
>   * TopLeft
> 
> This file is also included in custom Steam skins, so if you are using one you would edit the **SteamScheme.res** file in your applied skin folder (_Steam\skins\Your Skin Here\resource_) in the same manner.
> 
> Now for the caveat&#8230; Valve may now override this setting on a per-game basis and it appears to be impossible to change.
> 
> The first time I noticed this happen was with a Left 4 Dead update in October of 2009 that moved my notifications from the bottom right to the top right corner. I searched high and low through the Left 4 Dead directory but never found a setting to override this behavior anywhere.
> 
> A petition on <a title="[PETITION] Change position of the STEAM info bar to the upper right corner please." href="http://forums.steampowered.com/forums/showthread.php?t=932124" rel="nofollow">the official Left 4 Dead forums</a> was started about this topic, and apparently Valve listened.