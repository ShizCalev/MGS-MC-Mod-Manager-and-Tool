[![HelixToolkit](https://img.shields.io/badge/-Helix%20Toolkit-blue)](https://github.com/helix-toolkit/helix-toolkit) 

<img src='https://avatars3.githubusercontent.com/u/8432523?s=200&v=4' width='64' />

# Helix Toolkit

**Helix Toolkit is a collection of 3D components for .NET Framework.**

[**HelixToolkit.WPF:**](/Source/HelixToolkit.Wpf) 
Adds variety of functionalities/models on the top of internal WPF 3D models (Media3D namespace). 

[**HelixToolkit.Core.WPF:**](/Source/HelixToolkit.Core.Wpf) 
Adds variety of functionalities/models on the top of internal .NET Core WPF 3D models (Media3D namespace).

[**HelixToolkit.SharpDX.WPF:**](/Source/HelixToolkit.Wpf.SharpDX) 
Custom 3D Engine and XAML/MVVM compatible Scene Graphs based on [SharpDX](https://github.com/sharpdx/SharpDX)(DirectX 11) for high performance usage.

[**HelixToolkit.UWP:**](/Source/HelixToolkit.UWP) 
Custom 3D Engine and XAML/MVVM compatible Scene Graphs based on [SharpDX](https://github.com/sharpdx/SharpDX)(DirectX 11) for Universal Windows App.

[**HelixToolkit.SharpDX.Core:**](/Source/HelixToolkit.SharpDX.Core) 
Custom 3D Engine and Scene Graphs based on [SharpDX](https://github.com/sharpdx/SharpDX)(DirectX 11) for netstandard and .NET Core.

[**HelixToolkit.SharpDX.Core.Wpf:**](/Source/HelixToolkit.SharpDX.Core.Wpf) 
Wpf Wrapper Components based on `HelixToolkit.SharpDX.Core` for .NET Core Wpf.

[**HelixToolkit.WinUI:**](/Source/HelixToolkit.WinUI) 
Custom 3D Engine and XAML/MVVM compatible Scene Graphs based on [SharpDX](https://github.com/sharpdx/SharpDX)(DirectX 11) for WinUI.


[**HelixToolkit.SharpDX.Assimp:**](/Source/HelixToolkit.Wpf.SharpDX.Assimp) 
[Assimp.Net](https://bitbucket.org/Starnick/assimpnet/src/master/) 3D model importer/expoter support for HelixToolkit.SharpDX Components.

[**Examples:**](/Source/Examples)
Please download full source code to run examples. Or download [compiled version](https://ci.appveyor.com/project/objorke/helix-toolkit/branch/master/artifacts)

[![License: MIT](https://img.shields.io/github/license/helix-toolkit/helix-toolkit)](https://github.com/helix-toolkit/helix-toolkit/blob/develop/LICENSE)
[![Build status](https://ci.appveyor.com/api/projects/status/vbrornad55ln8tp4?svg=true)](https://ci.appveyor.com/project/holance/helix-toolkit-qqf1e)
[![Release](https://img.shields.io/github/release/helix-toolkit/helix-toolkit.svg?style=popout)](https://www.nuget.org/packages?q=Helix-Toolkit)
[![Chat](https://img.shields.io/gitter/room/helix-toolkit/helix-toolkit.svg)](https://gitter.im/helix-toolkit/helix-toolkit)

Description         | Value
--------------------|-----------------------
Web page            | http://helix-toolkit.github.io/
Wiki                | https://github.com/helix-toolkit/helix-toolkit/wiki
Documentation       | http://helix-toolkit.readthedocs.io/
Chat                | https://gitter.im/helix-toolkit/helix-toolkit
Source repository   | http://github.com/helix-toolkit/helix-toolkit
Latest build        | http://ci.appveyor.com/project/holance/helix-toolkit
Issue tracker       | http://github.com/helix-toolkit/helix-toolkit/issues
NuGet packages      | http://www.nuget.org/packages?q=HelixToolkit
Nightly build       | https://www.myget.org/F/helixtoolkit-nightly
StackOverflow       | http://stackoverflow.com/questions/tagged/helix-3d-toolkit
Twitter             | https://twitter.com/hashtag/Helix3DToolkit

## Project Build

**Visual Studio 2019. Windows 10 SDK (Min Ver.10.0.18362.0).**

## Notes

#### 1. Right-handed Cartesian coordinate system and row major matrix by default
HelixToolkit default is using right-handed Cartesian coordinate system, including Meshbuilder etc. To use left-handed Cartesian coordinate system (Camera.CreateLeftHandedSystem = true), user must manually correct the triangle winding order or IsFrontCounterClockwise in raster state description if using SharpDX. Matrices are row major by default.

#### 2. Performance [Topics](https://github.com/helix-toolkit/helix-toolkit/wiki/Tips-on-performance-optimization-(WPF.SharpDX-and-UWP)) for WPF.SharpDX and UWP.

#### 3. Following features are not supported currently on FeatureLevel 10 graphics card:
FXAA, Order Independant Transparent Rendering, Particle system, Tessellation.

#### 4. [Wiki](https://github.com/helix-toolkit/helix-toolkit/wiki) and useful [External Resources](https://github.com/helix-toolkit/helix-toolkit/wiki/External-References) on Computer Graphics.

## HelixToolkit Library Structure

### WPF Internal 3D Engine (DirectX9)

```mermaid
graph TD
    wpf[WPF Framework] --> hxWpf[HelixToolkit.Wpf]
    wpf --> hxCoreWpf[HelixToolkit.Core.Wpf]
```
### HelixToolkit DirectX11 Engine

```mermaid
graph TD
    hx[HelixToolkit] --> dx11[DirectX11 Engine]    
    dx11 --> hxSharpDX[HelixToolkit.Wpf.SharpDX]
    dx11 --> hxUWP[HelixToolkit.UWP]
    dx11 --> hxCore[HelixToolkit.SharpDX.Core]
    hxCore --> hxWinUI[HelixToolkit.SharpDX.Core.Wpf]
    hxCore --> hxSharpDXCoreWpf[HelixToolkit.WinUI]
    hxSharpDX --> hxAssimp[HelixToolkit.SharpDX.Assimp]
    hxUWP --> hxAssimp
    hxCore --> hxAssimp
```

## Bug Report
Please use the following template to report bugs.

- Version: [Example: 2.20]
- Package: [Example: Helixtoolkit.Wpf]
- Issue: 
- Reproduce Steps:
- Sample Code:

## News

#### 2024-02-27
[v2.25.0](https://github.com/helix-toolkit/helix-toolkit/releases/tag/v2.25.0) releases are available on nuget. [Release Note](/CHANGELOG.md)
- [WPF](https://www.nuget.org/packages/HelixToolkit.Wpf/2.25.0)
- [Core.WPF](https://www.nuget.org/packages/HelixToolkit.Core.Wpf/2.25.0)
- [WPF.Input](https://www.nuget.org/packages/HelixToolkit.Wpf.Input/2.25.0)
- [WPF.SharpDX](https://www.nuget.org/packages/HelixToolkit.Wpf.SharpDX/2.25.0)
- [UWP](https://www.nuget.org/packages/HelixToolkit.UWP/2.25.0)
- [SharpDX.Core](https://www.nuget.org/packages/HelixToolkit.SharpDX.Core/2.25.0)
- [SharpDX.Core.Wpf](https://www.nuget.org/packages/HelixToolkit.SharpDX.Core.Wpf/2.25.0)
- [WinUI](https://www.nuget.org/packages/HelixToolkit.WinUI/2.25.0)
- [SharpDX.Assimp](https://www.nuget.org/packages/HelixToolkit.SharpDX.Assimp/2.25.0)

#### Changes (Please refer to [Release Note](https://github.com/helix-toolkit/helix-toolkit/blob/master/CHANGELOG.md) for details)

#### 2023-03-17
Nightly build myget feed link has been updated to: https://www.myget.org/F/helixtoolkit-nightly
