---
id: 157
title: Interesting Fail States and more
date: 2004-03-22T23:13:00+00:00
author: MrPhil
layout: post
guid: http://www.mrphilgames.com/?p=157
permalink: /playtestingstrategiestuto/
categories:
  - News
---
I spent my first day at the Game Developer Conference this year in the “Play Testing Strategies Tutorial” by Michelle Gamboa, Ray Kowalewski, and Prodipto Roy.

Pathfinding pains

Roy talked about the structure of play balance. To highlight the often glazed over problem of dependencies he told a short story. During scripted battles for a game the range units always seemed to be dominating the field. On first glance it appeared the ranged units hit for too much damage, killing their melee opponents before they could engage them in hand-to-hand combat. On closer scrutiny it was discovered that melee units could never “find” their opponents because the pathfinding algorithm was incomplete. It is important, boys and girls, to understand your dependencies.

Klingon Battle Complexities

Roy led an exercise of identifying what parts of a game will need play testing. Before doing the exercise I did not appreciate the complexity of the task. I was surprised how varied the things you need to cover are. Here are a few of the things I missed during the exercise.

Learning curve, did the player get lost, or bored
   
Balance within the games stages (Early, middle late etc.)
   
Technology rates, how fast the player got access to improvements?
   
Race Attributes, Is the Klingon’s Battle Bonus to outrageous?
   
Player Bonus, maybe special skills from earlier campaigns
   
Game pacing, did the player get bored because it was too slow
   
Hero development, did the player find the &#8220;level ups&#8221; satisfying
  
It was interesting how complex the interaction of variables became and although you can give a priority to different elements you eventually have to defer to the design. I definitely see a danger here. The play testing could water down the &#8220;coolness&#8221; of the design in the name of balance. For example, the Klingons are an interesting race because of their strength and aggressiveness twisted around a strong sense of honor. If you weren&#8217;t careful you could balance all the strength out of the race and lose what makes them cool. So balance could mean that Klingons always win a scout ship vs. scout ship battle, of course, it also probably means that their sense of honor doesn&#8217;t allow them to break treaties without considerable unrest among their people.

Interesting Fail States

If winning is fun can losing be too? Gamboa brought up this interesting concept and got my attention. It is possible to design fail states that are so interesting as to entertain the player. A great example is Burnout&copyright;. This is a run of the mill car racing game, until you have an accident. Then the game pauses and we get a slow motion replay of the carnage. Now that is cool. I&#8217;d wager that this ability to turned failure into fun is the only reason the game has been so successful.

Beta Builders

Kowalwski talk about the great advantages holding a beta has, so great in fact he couldn&#8217;t image a better scenario. Not only do you get feedback on the game you are also building an online community. This dual nature gives you an advantage because the game&#8217;s direction is push toward what the growing community likes and enjoys. Giving it a greater chance of success. It also doesn&#8217;t have the expense of providing offices for interns, or the image risk of fixing problems after the release.

Philip Ludington aka Mr. Phil is a computer programmer who dreams of making computer games for a living, but is highly prone to procastination.