---
title: 'Cambio importante: OutputType establecido en WinExe para aplicaciones de WPF y WinForms'
description: Obtenga información sobre el cambio importante en el SDK 5.0.100 de .NET, donde OutputType se establece automáticamente en WinExe para las aplicaciones Windows Forms.
ms.date: 09/18/2020
ms.openlocfilehash: 38d9b910374f9e44f7e35296808930c6a6d45f0d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100431469"
---
# <a name="outputtype-set-to-winexe-for-wpf-and-winforms-apps"></a>OutputType establecido en WinExe para aplicaciones de WPF y WinForms

`OutputType` se establece de forma automática en `WinExe` para aplicaciones de Windows Presentation Foundation (WPF) y Windows Forms. Cuando `OutputType` se establece en `WinExe`, no se abre una ventana de la consola al ejecutar la aplicación.

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores del SDK de .NET, se usa el valor especificado para `OutputType` en el archivo del proyecto. Por ejemplo:

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

A partir de la versión 5.0.100 del SDK de .NET, cuando `OutputType` se establece en `Exe`, se cambia de forma automática a `WinExe` para las aplicaciones WPF y Windows Forms que tienen como destino cualquier versión del marco, incluido .NET Framework.

```xml
<PropertyGroup>
  <OutputType>WinExe</OutputType>
</PropertyGroup>
```

 Si no se especifica `OutputType` en el archivo del proyecto, se usa `Library` como valor predeterminado y ese valor no cambia.

## <a name="reason-for-change"></a>Motivo del cambio

Se supone que la mayoría de los usuarios no quieren que se abra una ventana de consola cuando se ejecuta una aplicación de WPF o Windows Forms. Además, [ahora que estos tipos de aplicación usan el SDK de .NET](sdk-and-target-framework-change.md) en lugar del SDK de Escritorio de Windows, se establecerá el valor predeterminado correcto. Incluso si se agrega compatibilidad para seleccionar iOS y Android como destino, será más fácil seleccionar varias plataformas de destino si todas usan el mismo tipo de salida.

## <a name="version-introduced"></a>Versión introducida

.NET 5.0.100

## <a name="recommended-action"></a>Acción recomendada

No es necesario que realice ninguna acción. Pero si quiere revertir al comportamiento anterior, establezca la propiedad `DisableWinExeOutputInference` en `true` en el archivo del proyecto.

```xml
<DisableWinExeOutputInference>true</DisableWinExeOutputInference>
```

## <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

### Affected APIs

Not detectable via API analysis.

### Category

- Windows Forms
- Windows Presentation Framework (WPF)

-->
