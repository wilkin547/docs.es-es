---
title: 'Cambio importante: Uso de Microsoft.NET.Sdk por parte de las aplicaciones de WinForms y WPF'
description: Obtenga información sobre el cambio importante en .NET 5 donde las aplicaciones Windows Forms y Windows Presentation Framework ahora usan el SDK de .NET en lugar del SDK para WinForms y WPF de .NET Core.
ms.date: 09/18/2020
ms.openlocfilehash: 408233f6f8801fb3d4e53beab28c26a777a4a3e1
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256210"
---
# <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a>Uso de Microsoft.NET.Sdk por parte de las aplicaciones de WinForms y WPF

Las aplicaciones de Windows Forms y Windows Presentation Framework (WPF) ahora usan el SDK de .NET (`Microsoft.NET.Sdk`) en lugar del SDK para WinForms y WPF de .NET Core (`Microsoft.NET.Sdk.WindowsDesktop`).

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET Core, las aplicaciones de WinForms y WPF usaban un [SDK de proyecto](../../../project-sdk/overview.md) independiente (`Microsoft.NET.Sdk.WindowsDesktop`). A partir de .NET 5, el SDK de WinForms y WPF se ha unificado con el SDK de .NET (`Microsoft.NET.Sdk`). Además, los nuevos [monikers de la plataforma de destino (TFM)](../../../../standard/frameworks.md) reemplazan a `netcoreapp` y `netstandard` en .NET 5. En el ejemplo siguiente se muestran los cambios que se deben realizar en un archivo de proyecto de WPF al redestinarlo a .NET 5 o una versión posterior.

En versiones anteriores de .NET Core:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

En .NET 5 y versiones posteriores:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

## <a name="version-introduced"></a>Versión introducida

SDK 5.0.100 de .NET

## <a name="recommended-action"></a>Acción recomendada

En el archivo del proyecto de WPF o Windows Forms:

- Actualice el atributo `Sdk` a `Microsoft.NET.Sdk`.
- Actualice la propiedad `TargetFramework` a `net5.0-windows`.

## <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

### Affected APIs

Not detectable via API analysis.

### Category

- Windows Forms
- Windows Presentation Framework (WPF)

-->
