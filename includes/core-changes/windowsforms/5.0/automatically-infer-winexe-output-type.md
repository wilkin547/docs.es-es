---
ms.openlocfilehash: 54bee14f6de409550357194e905b6ee5d8ef8f18
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679009"
---
### <a name="outputtype-set-to-winexe-for-wpf-and-winforms-apps"></a>OutputType establecido en WinExe para aplicaciones de WPF y WinForms

`OutputType` se establece de forma automática en `WinExe` para aplicaciones de Windows Presentation Foundation (WPF) y Windows Forms. Cuando `OutputType` se establece en `WinExe`, no se abre una ventana de la consola al ejecutar la aplicación.

#### <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, se usa el valor especificado para `OutputType` en el archivo del proyecto. Por ejemplo:

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

A partir de .NET 5.0, `OutputType` se establece de forma automática en `WinExe` para las aplicaciones de WPF y Windows Forms. Por ejemplo:

```xml
<PropertyGroup>
  <OutputType>WinExe</OutputType>
</PropertyGroup>
```

#### <a name="reason-for-change"></a>Motivo del cambio

Se supone que la mayoría de los usuarios no quieren que se abra una ventana de consola cuando se ejecuta una aplicación de WPF o Windows Forms. Además, [ahora que estos tipos de aplicación usan el SDK de .NET](../../../../docs/core/compatibility/wpf.md#winforms-and-wpf-apps-use-microsoftnetsdk) en lugar del SDK de Escritorio de Windows, se establecerá el valor predeterminado correcto. Incluso si se agrega compatibilidad para seleccionar iOS y Android como destino, será más fácil seleccionar varias plataformas de destino si todas usan el mismo tipo de salida.

#### <a name="version-introduced"></a>Versión introducida

.NET 5.0 (versión preliminar 8)

#### <a name="recommended-action"></a>Acción recomendada

No es necesario que realice ninguna acción. Pero si quiere revertir al comportamiento anterior, establezca la propiedad `DisableWinExeOutputInference` en `true` en el archivo del proyecto.

```xml
<DisableWinExeOutputInference>true</DisableWinExeOutputInference>
```

#### <a name="category"></a>Categoría

- Windows Forms
- Windows Presentation Framework (WPF)

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
