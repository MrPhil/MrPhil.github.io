---
id: 194
title: 'Tom Miller&#8217;s render loop, a revision'
date: 2006-10-09T00:04:36+00:00
author: MrPhil
layout: post
guid: http://www.mrphilgames.com/?p=194
permalink: /tom_miller_mana/
categories:
  - News
---
Tom Miller, Managed DirectX’s father figure, has made several posts on the game loop or render loop for the managed environment. His lastest post on the subject was back in May 2005. I’m writing the render loop for Alien Sovereign using GDI+, so I needed to tweak his code a little to make it work for a non-DirectX renderer. Here is my version source:

> #region Source
  
> /* This code is an adaptation by Philip Ludington (of Mr.
  
> * Phil Games) from the DirectX SDK file DXMUTMisc.cs, and
  
> * Tom Miller&#8217;s blog post &#8220;My last post on render loops
  
> \* (hopefully)..&#8221; \* http://blogs.msdn.com/tmiller/archive/2005/05/05/415008.aspx*/#endregionusing System;
  
> using System.Collections.Generic;
  
> using System.Windows.Forms;
  
> using System.Runtime.InteropServices;
> 
> namespace Company.Program
  
> {
  
> #region Enum, deligates, struct etc.
  
> public enum WindowMessage : uint { // Misc messages Destroy = 0x0002, Close = 0x0010, Quit = 0x0012, Paint = 0x000F, SetCursor = 0x0020, ActivateApplication = 0x001C, EnterMenuLoop = 0x0211, ExitMenuLoop = 0x0212, NonClientHitTest = 0x0084, PowerBroadcast = 0x0218, SystemCommand = 0x0112, GetMinMax = 0x0024, // Keyboard messages KeyDown = 0x0100, KeyUp = 0x0101, Character = 0x0102, SystemKeyDown = 0x0104, SystemKeyUp = 0x0105, SystemCharacter = 0x0106, // Mouse messages MouseMove = 0x0200, LeftButtonDown = 0x0201, LeftButtonUp = 0x0202, LeftButtonDoubleClick = 0x0203, RightButtonDown = 0x0204, RightButtonUp = 0x0205, RightButtonDoubleClick = 0x0206, MiddleButtonDown = 0x0207, MiddleButtonUp = 0x0208, MiddleButtonDoubleClick = 0x0209, MouseWheel = 0x020a, XButtonDown = 0x020B, XButtonUp = 0x020c, XButtonDoubleClick = 0x020d, MouseFirst = LeftButtonDown, // Skip mouse move,
  
> // it happens a lot and there is another
  
> // message for that MouseLast = XButtonDoubleClick, // Sizing EnterSizeMove = 0x0231, ExitSizeMove = 0x0232, Size = 0x0005, } [StructLayout( LayoutKind.Sequential )] public struct Message
  
> {
  
> public IntPtr hWnd;
  
> public WindowMessage msg;
  
> public IntPtr wParam;
  
> public IntPtr lParam;
  
> public uint time;
  
> public System.Drawing.Point p;
  
> }
  
> #endregion /// /// Program /// static class Program
  
> {
  
> #region Member Variables
  
> private static Form1 form1;
  
> #endregion #region Properties
  
> #endregion #region Constructors (including static)
  
> #endregion #region Public members
  
> /// /// The main entry point for the application. /// [STAThread] static void Main()
  
> {
  
> Application.EnableVisualStyles();
  
> Application.SetCompatibleTextRenderingDefault(
  
> false );
> 
> form1 = new Form1();
> 
> // Hook the application&#8217;s idle event Application.Idle += new EventHandler(
  
> OnApplicationIdle );
> 
> Application.Run( form1 );
  
> }
> 
> // We won&#8217;t use this maliciously
  
> [System.Security.SuppressUnmanagedCodeSecurity]
  
> [DllImport( &#8220;User32.dll&#8221;, CharSet
  
> = CharSet.Auto )]
  
> public static extern bool PeekMessage(
  
> out Message msg,
  
> IntPtr hWnd, uint messageFilterMin,
  
> uint messageFilterMax,
  
> uint flags );
  
> #endregion #region Private (helper) methods
  
> static private void OnApplicationIdle( object sender,
  
> EventArgs e )
  
> {
  
> while( AppStillIdle )
  
> {
  
> // Render a frame during idle time
  
> // (no messages are waiting) Update(); Render(); } } private static void Render()
  
> {
  
> throw new Exception(
  
> &#8220;The method or operation is not implemented.&#8221; );
  
> }
  
> private static void Update()
  
> {
  
> throw new Exception(
  
> &#8220;The method or operation is not implemented.&#8221; );
  
> }
  
> static private bool AppStillIdle
  
> {
  
> get
  
> {
  
> Message msg;
  
> return !PeekMessage( out msg,
  
> IntPtr.Zero, 0, 0, 0 );
  
> }
  
> }
  
> #endregion }}