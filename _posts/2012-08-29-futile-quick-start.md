---
id: 1747
title: Futile Quick Start
date: 2012-08-29T22:46:07+00:00
author: MrPhil
layout: post
guid: http://www.mrphilgames.com/?p=1747
permalink: /futile-quick-start/
image:
  - ""
seo_follow:
  - 'false'
seo_noindex:
  - 'false'
categories:
  - News
---
[Futile](http://struct.ca/futile/) is a framework that allows you to control rendering within Unity programmatically. This is a boon to anyone interested in 2D games and finds, like myself, that Unity impedes 2D game development.

  1. Get [Futile from Github](http://github.com/MattRix/Futile)
  2. Import the Futile.unitypackage into you Unity project, _Assets->Import Package->Custom Package&#8230;_
  3. Create an Empty GameObject and call it _Futile Camera_, _GameObject->Create Empty_
  4. Find the Futile script in the Project Pane and drag it to the _Futile Camera_ object you just created.
  5. Make or find a fun and silly image, I like this one: [OMG IT SPINS](http://i.imgur.com/5dpt2.jpg)
  6. Now put it in you Unity project under the Asset folder and call it _OMG_.
  7. Click on the image and set the _Texture Type_ to _Advance_ and then the _Non Power of 2_ to _None_.
  8. Create a new Script file and name it _FunWithFutile.cs_ and drag it to the _Futile Camera_ object.
  9. Now copy the code below into you script file. <pre class="brush:csharp">using UnityEngine;

public class FunWithFutile : MonoBehaviour
{
    // Use this for initialization
    void Start()
    {
        FutileParams futileParams =
            new FutileParams(true, true, true, true);

        futileParams.AddResolutionLevel(
            1024, 1, 1, "");

        futileParams.origin = new Vector2(
             0.5f, 0.5f);

        Futile.instance.Init(futileParams);

        Futile.atlasManager.LoadImage("OMG");
        FSprite fSprite = new FSprite("OMG");
        Futile.stage.AddChild(fSprite);
    }

    // Update is called once per frame
    void Update()
    {

    }
}</pre>

 10. Press play and be impressed!