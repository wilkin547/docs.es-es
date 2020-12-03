---
title: 'Cambio importante: Uso de Microsoft.NET.Sdk por parte de las aplicaciones de WinForms y WPF'
description: Obtenga información sobre el cambio importante en .NET 5.0 donde las aplicaciones Windows Forms y Windows Presentation Framework ahora usan el SDK de .NET en lugar del SDK para WinForms y WPF de .NET Core.
ms.date: 09/18/2020
ms.openlocfilehash: 5f25be44c390abc173f155351d8cb007a6b370b0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760216"
---
# <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a>Uso de Microsoft.NET.Sdk por parte de las aplicaciones de WinForms y WPF

Las aplicaciones de Windows Forms y Windows Presentation Framework (WPF) ahora usan el SDK de .NET (`Microsoft.NET.Sdk`) en lugar del SDK para WinForms y WPF de .NET Core (`Microsoft.NET.Sdk.WindowsDesktop`).

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET Core, las aplicaciones de WinForms y WPF usaban un [SDK de proyecto](../../../project-sdk/overview.md) independiente (`Microsoft.NET.Sdk.WindowsDesktop`). A partir de .NET 5.0, el SDK de WinForms y WPF se ha unificado con el SDK de .NET (`Microsoft.NET.Sdk`). Además, los nuevos [monikers de la plataforma de destino (TFM)](../../../../standard/frameworks.md) reemplazan a `netcoreapp` y `netstandard` en .NET 5. En el ejemplo siguiente se muestran los cambios que se deben realizar en un archivo de proyecto de WPF al redestinarlo a .NET 5.0 o una versión posterior.

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

En .NET 5.0 y versiones posteriores:

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

.NET 5.0

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
