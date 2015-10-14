Some handy and workaround for Unity3D

How to turn off 3D backface culling aka double side
---
* refer : http://forum.unity3d.com/threads/two-sided-cutout-shader-for-u3-wanted.93189/
* backup : https://github.com/katopz/unity-handy/blob/master/%24DoublesidedCutout.unitypackage

How to use .NET 4.5 via Unity [which stuck at .NET 3.5](http://blogs.unity3d.com/2014/05/20/the-future-of-scripting-in-unity/)
---
* UnmanagedExports (updated Dec 19, 2012, 12:23 PM) : via [nuget](https://www.nuget.org/packages/UnmanagedExports) and [web site]( https://sites.google.com/site/robertgiesecke/Home/uploads/unmanagedexports) : `PM> Install-Package UnmanagedExports`
* IKVM : http://www.ikvm.net/userguide/tutorial.html

How to create and fade in GUI panel
---
* https://youtu.be/Mzt1rEEdeOI?t=861

How to render GUITextures behind the 3D : refer to [this](http://forum.unity3d.com/threads/how-to-set-guitexture-behind-of-3d-object.119520/)
---
1. add a new layer in the inspector
1. and set the GUITexture's layer to this new layer. 
1. select your Main Camera, click on 'Culling Mask' and uncheck the layer you just made, this will stop the main camera rendering objects (GUITextures) on this layer. 
1. go and create a second Camera and set its 'Clear Flags' to 'Depth Only' and its 'Culling Mask' to only render the layer you set up earlier for the GUITextures, 
1. finally change this Camera's 'Depth' to -1. 
1. Main camera and second camera all needs to be set as 'Depth Only'

How to present pixel perfect GUITextures
---
```csharp
BackgroundTexture.pixelInset = new Rect(0, 0, Screen.width, Screen.height);
BackgroundTexture.transform.localScale = Vector3.zero;
```

