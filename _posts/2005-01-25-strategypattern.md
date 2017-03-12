---
id: 188
title: Strategy Pattern
date: 2005-01-25T23:40:20+00:00
author: MrPhil
layout: post
guid: http://www.mrphilgames.com/?p=188
permalink: /strategypattern/
categories:
  - News
---
Taking [Alastair Patrick](http://alpatrick.blogspot.com/)’s example of applying patterns to game making I present the strategy pattern. The strategy pattern encapsulates behavior allowing flexibility and object composition. This means a group of classes (as ships) can have some behavior in common, but also room for different flavors without having a lot of overrides and duplicate code. Here’s an example in code. Note, I’ve even written it so the behavior can be changed at runtime!

> public interface AttackBehavior
> 
> {
> 
> void Attack();
> 
> }
> 
> public class AttackWithNoWeapon : AttackBehavior
> 
> {
> 
> public AttackWithNoWeapon()
> 
> {
> 
> //
> 
> // TODO: Add constructor logic here
> 
> //
> 
> }
> 
> public void Attack()
> 
> {
> 
> Console.Out.WriteLine( &#8220;No weapon to attack with.&#8221; );
> 
> }
> 
> }
> 
> public class AttackWithRedLaser : AttackBehavior
> 
> {
> 
> public AttackWithRedLaser()
> 
> {
> 
> //
> 
> // TODO: Add constructor logic here
> 
> //
> 
> }
> 
> public void Attack()
> 
> {
> 
> Console.Out.WriteLine( &#8220;Firing red lasers.&#8221; );
> 
> }
> 
> }
> 
> public class AttackWithReinforcedIceProjectile : AttackBehavior
> 
> {
> 
> public AttackWithReinforcedIceProjectile()
> 
> {
> 
> //
> 
> // TODO: Add constructor logic here
> 
> //
> 
> }
> 
> public void Attack()
> 
> {
> 
> Console.Out.WriteLine( &#8220;Firing Reinforced Ice Projectiles &#8221; );
> 
> }
> 
> }
> 
> public interface FlyBehavior
> 
> {
> 
> void Fly();
> 
> }
> 
> public class FlyWithIonEngines : FlyBehavior
> 
> {
> 
> public FlyWithIonEngines()
> 
> {
> 
> //
> 
> // TODO: Add constructor logic here
> 
> //
> 
> }
> 
> public void Fly()
> 
> {
> 
> Console.Out.WriteLine( &#8220;Moved 4 parsecs.&#8221; );
> 
> }
> 
> }
> 
> public class FlyWithNoEngines : FlyBehavior
> 
> {
> 
> public FlyWithNoEngines()
> 
> {
> 
> //
> 
> // TODO: Add constructor logic here
> 
> //
> 
> }
> 
> public void Fly()
> 
> {
> 
> Console.Out.WriteLine( &#8220;Movement determined by gravity and inertia.&#8221; );
> 
> }
> 
> }
> 
> public class FlyWithSolarSails : FlyBehavior
> 
> {
> 
> public FlyWithSolarSails()
> 
> {
> 
> //
> 
> // TODO: Add constructor logic here
> 
> //
> 
> }
> 
> public void Fly()
> 
> {
> 
> Console.Out.WriteLine( &#8220;Low Solar Wind, move .5 parsecs.&#8221; );
> 
> }
> 
> }
> 
> public abstract class Ship
> 
> {
> 
> protected FlyBehavior flyBehavior = null;
> 
> protected AttackBehavior attackBehavior = null;
> 
> public Ship()
> 
> {
> 
> }
> 
> public abstract void Display();
> 
> public void PerformFly()
> 
> {
> 
> flyBehavior.Fly();
> 
> }
> 
> public void PerformAttack()
> 
> {
> 
> attackBehavior.Attack();
> 
> }
> 
> public void Repair()
> 
> {
> 
> Console.Out.WriteLine( &#8220;Repair teams dispatched, 10% improvement.&#8221; );
> 
> }
> 
> public void SetFlyBehavior( FlyBehavior fb )
> 
> {
> 
> flyBehavior = fb;
> 
> }
> 
> public void SetAttackBehavior( AttackBehavior ab )
> 
> {
> 
> attackBehavior = ab;
> 
> }
> 
> }
> 
> public class TerranMarkI : Ship
> 
> {
> 
> public TerranMarkI()
> 
> {
> 
> flyBehavior = new FlyWithIonEngines();
> 
> attackBehavior = new AttackWithRedLaser();
> 
> }
> 
> public override void Display()
> 
> {
> 
> Console.Out.WriteLine( &#8220;This is a Terran Mark I ship.&#8221; );
> 
> }
> 
> }
> 
> public class NeiwckronMkI : Ship
> 
> {
> 
> public NeiwckronMkI()
> 
> {
> 
> SetAttackBehavior( new AttackWithNoWeapon() );
> 
> SetFlyBehavior( new FlyWithIonEngines() );
> 
> }
> 
> public override void Display()
> 
> {
> 
> Console.Out.WriteLine( &#8220;A Neiwckron Mark I ship.&#8221; );
> 
> }
> 
> }
> 
> public class TheMain
> 
> {
> 
> /// <summary> 
> 
> /// The main entry point for the application.
> 
> /// </summary> 
> 
> [STAThread]
> 
> static void Main() 
> 
> {
> 
> Ship s1 = new TerranMarkI();
> 
> s1.PerformAttack();
> 
> s1.PerformFly();
> 
> Ship s2 = new NeiwckronMkI();
> 
> s2.PerformFly();
> 
> s2.SetFlyBehavior( new FlyWithSolarSails() );
> 
> s2.PerformFly();
> 
> }
> 
> }</blockquote> 
> 
> _When I am not writing about making games, procrastinating or watching movies I&#8217;m working on a science fiction strategy game (sometimes called 4X or empire builder.) Email me questions, ideas and jokes at mrphil (at) mrphilgames . com_