---
id: 142
title: Object Cloning Using Reflection
date: 2005-01-10T18:25:02+00:00
author: MrPhil
layout: post
guid: http://www.mrphilgames.com/?p=142
permalink: /object_cloning_/
categories:
  - News
---
Today on [Alastair Patrick’s blog he shared a way to use reflection to clone objects](http://alpatrick.blogspot.com/2005/01/prototype-pattern-using-reflection.html) which I found really interesting. I took the liberty of expanding the example a little so I could better understand the effects deep and shallow cloning had. I also replaced his main() with a NUnit test.

> using System;
> 
> using System.Reflection;
> 
> using NUnit.Framework;
> 
> public class DeepCopyAttribute : Attribute
> 
> {
> 
> }
> 
> public class PrototypeCloner
> 
> { 
> 
> public object Clone( object prototype )
> 
> {
> 
> object clone = CreateNewInstance( prototype.GetType() );
> 
> CopyPropertyValuesFromPrototype( clone, prototype );
> 
> return clone;
> 
> }
> 
> private object CreateNewInstance(Type type)
> 
> {
> 
> ConstructorInfo defaultConstructor = type.GetConstructor( new Type[0] );
> 
> return defaultConstructor.Invoke(new object[0]);
> 
> } 
> 
> private bool IsPropertyDeepCopied( PropertyInfo property )
> 
> { 
> 
> if( property.GetCustomAttributes( typeof(DeepCopyAttribute), true).Length
> 
> != 0 )
> 
> {
> 
> return true;
> 
> }
> 
> else
> 
> {
> 
> return false;
> 
> }
> 
> }
> 
> private void CopyPropertyValuesFromPrototype(object clone, object prototype)
> 
> {
> 
> foreach (PropertyInfo property in prototype.GetType().GetProperties()) 
> 
> {
> 
> if (IsPropertyDeepCopied(property))
> 
> {
> 
> object prototypeProperty = property.GetValue(prototype, null); 
> 
> object cloneProperty = Clone(prototypeProperty); 
> 
> property.SetValue(clone, cloneProperty, null); 
> 
> }
> 
> else
> 
> {
> 
> property.SetValue(clone, property.GetValue(prototype, null), null);
> 
> }
> 
> }
> 
> }
> 
> }
> 
> public abstract class Weapon 
> 
> {
> 
> }
> 
> public class LaserDisruptor: Weapon
> 
> {
> 
> public float RateOfFire
> 
> {
> 
> get
> 
> {
> 
> return rateOfFire;
> 
> }
> 
> set
> 
> {
> 
> rateOfFire = value;
> 
> }
> 
> }
> 
> private float rateOfFire = 1000;
> 
> }
> 
> public abstract class Entity {}
> 
> public class SpaceMonkey: Entity
> 
> {
> 
> public float Speed
> 
> {
> 
> get
> 
> {
> 
> return speed;
> 
> }
> 
> set
> 
> {
> 
> speed = value;
> 
> }
> 
> }
> 
> private float speed = 5;
> 
> private Weapon deepCopyWeapon = new LaserDisruptor();
> 
> [DeepCopyAttribute()]
> 
> public Weapon DeepCopyWeapon
> 
> {
> 
> get
> 
> {
> 
> return deepCopyWeapon;
> 
> }
> 
> set
> 
> {
> 
> deepCopyWeapon = value;
> 
> }
> 
> }
> 
> private Weapon shallowCopyWeapon = new LaserDisruptor();
> 
> public Weapon ShallowCopyWeapon
> 
> {
> 
> get
> 
> {
> 
> return shallowCopyWeapon;
> 
> }
> 
> set
> 
> {
> 
> shallowCopyWeapon = value;
> 
> }
> 
> }
> 
> }
> 
> [TestFixture]
> 
> public class PrototypeClonerTests
> 
> {
> 
> [Test]
> 
> public void Clone()
> 
> {
> 
> SpaceMonkey prototypeObject = new SpaceMonkey(); 
> 
> PrototypeCloner cloner = new PrototypeCloner();
> 
> Entity clonedObject = null;
> 
> clonedObject = (Entity)cloner.Clone(prototypeObject);
> 
> SpaceMonkey clonedMonkey = (SpaceMonkey)clonedObject;
> 
> // Testing for Equality
> 
> Assert.AreEqual( prototypeObject.Speed, clonedMonkey.Speed, &#8220;Fail1&#8221; );
> 
> // &#8212; This is false because it is a Deep Copy property and this class
> 
> // doesn&#8217;t override the Equals or == operator so the Assert&#8217;s
> 
> // AreSame and AreEqual tests have the identical result
> 
> Assert.IsFalse( 
> 
> prototypeObject.DeepCopyWeapon == clonedMonkey.DeepCopyWeapon,
> 
> &#8220;Fail2&#8221; );
> 
> Assert.AreEqual( 
> 
> ((LaserDisruptor)prototypeObject.DeepCopyWeapon).RateOfFire,
> 
> ((LaserDisruptor)clonedMonkey.DeepCopyWeapon).RateOfFire, &#8220;Fail3&#8221; );
> 
> // &#8212; Are equal, as in the same object because it is the Shallow Copy
> 
> Assert.AreEqual( prototypeObject.ShallowCopyWeapon, 
> 
> clonedMonkey.ShallowCopyWeapon,
> 
> &#8220;Fail4&#8221; );
> 
> Assert.AreEqual( 
> 
> ((LaserDisruptor)prototypeObject.ShallowCopyWeapon).RateOfFire,
> 
> ((LaserDisruptor)clonedMonkey.ShallowCopyWeapon).RateOfFire, &#8220;Fail5&#8221; );
> 
> // Testing for Same
> 
> // &#8212; Only the DeepCopyAttribute properties should be the same
> 
> // &#8212; Not same because it is not a referance object (float)
> 
> Assert.IsFalse( 
> 
> object.ReferenceEquals( prototypeObject.Speed, clonedMonkey.Speed ),
> 
> &#8220;Fail6&#8221; );
> 
> // &#8212; Not same because it is a DeepCopyAttribute
> 
> Assert.IsFalse( 
> 
> object.ReferenceEquals( prototypeObject.DeepCopyWeapon, 
> 
> clonedMonkey.DeepCopyWeapon),
> 
> &#8220;Fail7&#8221; );
> 
> // &#8212; Not same because it is not a referance object (float)
> 
> Assert.IsFalse( object.ReferenceEquals( 
> 
> ((LaserDisruptor)prototypeObject.DeepCopyWeapon).RateOfFire,
> 
> ((LaserDisruptor)clonedMonkey.DeepCopyWeapon).RateOfFire), &#8220;Fail8&#8221; );
> 
> // &#8212; The only referance object that isn&#8217;t a deep copy Are Same
> 
> Assert.AreSame( prototypeObject.ShallowCopyWeapon, 
> 
> clonedMonkey.ShallowCopyWeapon,
> 
> &#8220;Fail9&#8221; );
> 
> // &#8212; Not same because it is not a referance object (float)
> 
> Assert.IsFalse( object.ReferenceEquals( 
> 
> ((LaserDisruptor)prototypeObject.ShallowCopyWeapon).RateOfFire,
> 
> ((LaserDisruptor)clonedMonkey.ShallowCopyWeapon).RateOfFire), 
> 
> &#8220;Fail10&#8221; );
> 
> }
> 
> }