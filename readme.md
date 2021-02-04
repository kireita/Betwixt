Betwixt - Easy Tweening Library for .Net
============================

Betwixt is a quick way to ease and tween between any generic types, and provides a robust fast API to allow you to do
whatever you set out to do, in the easiest way possible.

This is a fork from [Jewelots's Betwixt(https://github.com/Jewelots/Betwixt) all credit and coding is done by the original author.
I only converted it to a .Net Core Library, to have no compatibility issues.

If you want to  know how each function behaves please check [this](https://easings.net/) site.

# Examples

BackInOut
[](https://i.imgur.com/LqNKasd.mp4)

BounceInOut
[](https://i.imgur.com/cPLweew.mp4)

CircInOut
[](https://i.imgur.com/CkTZ2yO.mp4)

CubicInOut
[](https://i.imgur.com/olFcx9p.mp4)

ElasticInOut
[](https://i.imgur.com/fOvyzUh.mp4)

ExpoInOut
[](https://i.imgur.com/6b8CWno.mp4)

QuadInOut
[](https://i.imgur.com/waNyRiQ.mp4)

QuartInOut
[](https://i.imgur.com/QDEjltq.mp4)

QuintInOut
[](https://i.imgur.com/EImyX9F.mp4)

SineInOut
[](https://i.imgur.com/4dpXeim.mp4)

# Download

You can get the latest repository here, or download precompiled library files from the [releases tab](https://github.com/Jewelots/Betwixt/releases)

You can also get this package using Nuget!

For x86: PM > Install-Package betwixt

# Usage

Please reference the documentation located in the [/doc](/doc) folder. Here is a very small overview, however:

General Use:
```csharp
// Initialisation
Tweener<float> tweener = new Tweener<float>(0, 10, 2, Ease.Elastic.Out);
// Update
tweener.Update(deltaTime);
// Anywhere
float newValue = tweener.Value;
```


You can also use your own custom type, with it's own lerp function (or let generics handle it)

```csharp
TimeSpan length = TimeSpan.FromSeconds(3);
Tweener<Vector2> tweener = new Tweener<Vector2>(startVector, endVector, length, Ease.Linear, Vector2.Lerp);
```


You can also specify your own ease function and make it into a set (or use the function directly)

```csharp
IEase myEaseSet = Generic.CreateFromOut(myEaseOutFunction);
Tweener<float> tweener = new Tweener<float>(0, 10, 2, myEaseSet.InOut);
```


Betwixt is incredibly flexible, and as long as your ease function matches the correct signature, you can use anything you want!

If you had a custom graph curve which had a "float GetValueAtTime(float time)" function you could even use:

```csharp
CustomGraphCurve myCustomGraphCurve = new CustomGraphCurve(graphPoints);

Tweener<float> tweener = new Tweener<float>(0, 10, 2, myCustomGraphCurve.GetValueAtTime);
```


Hopefully this inspires you to think of creative ways to use Betwixt!