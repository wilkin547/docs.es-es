---
ms.openlocfilehash: 975e331ad3e7bd7e0e8f49b62795c6acc7031ca9
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656355"
---
### <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a>Uso de Microsoft.NET.Sdk por parte de las aplicaciones de WinForms y WPF

Las aplicaciones de Windows Forms y Windows Presentation Framework (WPF) ahora usan el SDK de .NET (`Microsoft.NET.Sdk`) en lugar del SDK para WinForms y WPF de .NET Core (`Microsoft.NET.Sdk.WindowsDesktop`).

#### <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET Core, las aplicaciones de WinForms y WPF usaban un [SDK de proyecto](../../../../docs/core/project-sdk/overview.md) independiente (`Microsoft.NET.Sdk.WindowsDesktop`). A partir de .NET 5.0, el SDK de WinForms y WPF se ha unificado con el SDK de .NET (`Microsoft.NET.Sdk`). Además, los nuevos [monikers de la plataforma de destino (TFM)](../../../../docs/standard/frameworks.md) reemplazan a `netcoreapp` y `netstandard` en .NET 5. En el ejemplo siguiente se muestran los cambios que se deben realizar en un archivo de proyecto de WPF al redestinarlo a .NET 5.0 o una versión posterior.

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

#### <a name="version-introduced"></a>Versión introducida

.NET 5.0 (versión preliminar 8)

#### <a name="recommended-action"></a>Acción recomendada

En el archivo del proyecto de WPF o Windows Forms:

- Actualice el atributo `Sdk` a `Microsoft.NET.Sdk`.
- Actualice la propiedad `TargetFramework` a `net5.0-windows`.

#### <a name="category"></a>Categoría

- Windows Forms
- Windows Presentation Framework (WPF)

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
