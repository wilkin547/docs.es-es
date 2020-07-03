---
ms.openlocfilehash: d21b2e092d460fdfc367d0f490228ed44ad5c6cc
ms.sourcegitcommit: 63bb83322814f5e5e5c5b69939b14a3139a6ca7e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2020
ms.locfileid: "85365664"
---
### <a name="built-in-support-for-winrt-is-removed-from-net"></a>.NET deja de tener compatibilidad integrada con WinRT

Se ha quitado la compatibilidad integrada para el consumo de las API [Windows en tiempo de ejecución (WinRT)](/uwp/winrt-cref/winrt-type-system) en .NET.

#### <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 6)

#### <a name="change-description"></a>Descripción del cambio

Anteriormente, CoreCLR podía consumir [archivos de metadatos de Windows (WinMD)](/uwp/winrt-cref/winmd-files) con el fin de activar y consumir tipos de WinRT. A partir de la versión .NET 5.0, CoreCLR ya no puede consumir archivos WinMD directamente.

Si se intenta hacer referencia a un ensamblado no admitido, se obtendrá <xref:System.IO.FileNotFoundException>, mientras que, si se activa una clase WinRT, se obtendrá <xref:System.PlatformNotSupportedException>.

Este cambio importante se ha realizado por los siguientes motivos:

- Para que WinRT se pueda desarrollar y mejorar por separado del entorno de ejecución de .NET.
- Para favorecer la simetría con sistemas de interoperabilidad proporcionados para otros sistemas operativos, como iOS y Android.
- Para aprovechar las ventajas de otras características de .NET, como las características de C#, la vinculación de lenguaje intermedio (IL) y la compilación de antemano (AOT).
- Para simplificar el código base del entorno de ejecución de .NET.

#### <a name="recommended-action"></a>Acción recomendada

- Quite las referencias al [paquete Microsoft.Windows.SDK.Contracts](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts) y reemplácelas por referencias al [paquete Microsoft.Windows.SDK.NET](https://www.nuget.org/packages/microsoft.windows.sdk.net).

- Use la cadena de herramientas de [C#/WinRT](/windows/uwp/csharp-winrt/) para generar o personalizar los tipos y las API de WinRT en .NET 5.0 y versiones posteriores.

#### <a name="category"></a>Categoría

Interop

#### <a name="affected-apis"></a>API afectadas

- <xref:System.IO.WindowsRuntimeStorageExtensions?displayProperty=fullName>
- <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.WindowsRuntime?displayProperty=fullName>
- <xref:System.WindowsRuntimeSystemExtensions?displayProperty=fullName>
- <xref:Windows.Foundation.Point?displayProperty=fullName>
- <xref:Windows.Foundation.Size?displayProperty=fullName>
- <xref:Windows.UI.Color?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.IO.WindowsRuntimeStorageExtensions`
- `T: System.IO.WindowsRuntimeStreamExtensions`
- `N:System.Runtime.InteropServices.WindowsRuntime`
- `T:System.WindowsRuntimeSystemExtensions`
- `T:Windows.Foundation.Point`
- `T:Windows.Foundation.Size`
- `T:Windows.UI.Color`

-->
