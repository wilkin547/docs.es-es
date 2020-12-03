---
title: 'Cambio importante: .NET deja de tener compatibilidad integrada con WinRT'
description: Obtenga información sobre el cambio importante de interoperabilidad en .NET 5.0 donde se ha quitado de .NET la compatibilidad integrada con WinRT.
ms.date: 10/13/2020
ms.openlocfilehash: 61d8e26d06c232a7bfa1891a2159f5232f747b8a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760200"
---
# <a name="built-in-support-for-winrt-is-removed-from-net"></a>.NET deja de tener compatibilidad integrada con WinRT

Se ha quitado la compatibilidad integrada para el consumo de las API [Windows en tiempo de ejecución (WinRT)](/uwp/winrt-cref/winrt-type-system) en .NET.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="change-description"></a>Descripción del cambio

Anteriormente, CoreCLR podía consumir [archivos de metadatos de Windows (WinMD)](/uwp/winrt-cref/winmd-files) con el fin de activar y consumir tipos de WinRT. A partir de la versión .NET 5.0, CoreCLR ya no puede consumir archivos WinMD directamente.

Si se intenta hacer referencia a un ensamblado no admitido, se obtendrá <xref:System.IO.FileNotFoundException>, mientras que, si se activa una clase WinRT, se obtendrá <xref:System.PlatformNotSupportedException>.

Este cambio importante se ha realizado por los siguientes motivos:

- Para que WinRT se pueda desarrollar y mejorar por separado del entorno de ejecución de .NET.
- Para favorecer la simetría con sistemas de interoperabilidad proporcionados para otros sistemas operativos, como iOS y Android.
- Para aprovechar las ventajas de otras características de .NET, como las características de C#, la vinculación de lenguaje intermedio (IL) y la compilación de antemano (AOT).
- Para simplificar el código base del entorno de ejecución de .NET.

## <a name="recommended-action"></a>Acción recomendada

- Quite las referencias al [paquete Microsoft.Windows.SDK.Contracts](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts).  En su lugar, especifique la versión de las API de Windows a las que quiera acceder a través de la propiedad `TargetFramework` del proyecto.  Por ejemplo:

  ```xml
  <TargetFramework>net5.0-windows10.0.19041</TargetFramework>
  ```

- Use la cadena de herramientas de [C#/WinRT](/windows/uwp/csharp-winrt/) para generar o personalizar los tipos y las API de WinRT en .NET 5.0 y versiones posteriores.

## <a name="affected-apis"></a>API afectadas

- <xref:System.IO.WindowsRuntimeStorageExtensions?displayProperty=fullName>
- <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.WindowsRuntime?displayProperty=fullName>
- <xref:System.WindowsRuntimeSystemExtensions?displayProperty=fullName>
- <xref:Windows.Foundation.Point?displayProperty=fullName>
- <xref:Windows.Foundation.Size?displayProperty=fullName>
- <xref:Windows.UI.Color?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.IO.WindowsRuntimeStorageExtensions`
- `T: System.IO.WindowsRuntimeStreamExtensions`
- `N:System.Runtime.InteropServices.WindowsRuntime`
- `T:System.WindowsRuntimeSystemExtensions`
- `T:Windows.Foundation.Point`
- `T:Windows.Foundation.Size`
- `T:Windows.UI.Color`

### Category

Interop

-->
