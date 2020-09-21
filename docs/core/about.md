---
title: Información general sobre .NET Core
description: Obtenga información sobre las características y la composición de .NET Core y compárela con otras implementaciones de .NET.
ms.date: 03/26/2020
ms.openlocfilehash: e99939cf85cc441fd473e4d033e22b1a5d053638
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539013"
---
# <a name="net-core-overview"></a>Información general sobre .NET Core

> [!div class="button"]
> [Descargar .NET Core](https://dotnet.microsoft.com/download)

.NET Core tiene las siguientes características:

- **Multiplataforma:** se ejecuta en los [sistemas operativos](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md) Windows, macOS y Linux.
- **Código abierto:** el marco .NET Core es de [código abierto](https://github.com/dotnet/core), con licencias de MIT y Apache 2. .NET Core es un proyecto de [.NET Foundation](https://dotnetfoundation.org/).
- **Moderno:** implementa paradigmas modernos como programación asincrónica, patrones que no son de copia que usan estructuras y gobernanza de recursos para contenedores.
- **Rendimiento:**  Proporciona [alto rendimiento](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-core-3-0/) con características como [intrínsecos de hardware](https://devblogs.microsoft.com/dotnet/hardware-intrinsics-in-net-core/), [compilación en niveles](https://github.com/dotnet/coreclr/blob/master/Documentation/design-docs/tiered-compilation.md) e [Intervalo\<T>](../standard/memory-and-spans/index.md).
- **Coherente entre entornos:** el código se ejecuta con el mismo comportamiento en varios sistemas operativos y varias arquitecturas, como x64, x86 y ARM.
- **Herramientas de línea de comandos:**  incluye herramientas de línea de comandos sencillas que se pueden usar para el desarrollo local y la integración continua.
- **Implementación flexible:** se puede incluir .NET Core en la aplicación o de forma paralela (instalaciones a nivel de usuario o de sistema). Se puede usar con [contenedores de Docker](docker/introduction.md).

## <a name="languages"></a>Lenguajes

Los lenguajes [C#](../csharp/index.yml), [Visual Basic](../visual-basic/index.yml) y [F#](../fsharp/index.yml) pueden usarse a fin de escribir aplicaciones y bibliotecas para .NET Core. Puede usar estos idiomas en su editor de texto o en su entorno de desarrollo integrado (IDE) favorito, incluidos:

- [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)
- [Visual Studio Code](https://code.visualstudio.com/download)

La integración del editor la proporcionan, en parte, los colaboradores de los proyectos [OmniSharp](https://www.omnisharp.net/) e [Ionide](https://ionide.io).

## <a name="apis"></a>API

.NET Core expone marcos para compilar cualquier tipo de aplicación:

* Aplicaciones en la nube con [ASP.NET Core](/aspnet/core/)
* Aplicaciones móviles con [Xamarin](/xamarin)
* Aplicaciones de IoT con [System.Device.GPIO](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0)
* Aplicaciones cliente de Windows con [WPF](../desktop-wpf/overview/index.md) y Windows Forms
* Aprendizaje automático [ML.NET](../machine-learning/index.yml)

Se incluyen muchas API que satisfacen necesidades comunes, como las siguientes:

- Tipos primitivos, como <xref:System.Boolean?displayProperty=nameWithType> y <xref:System.Int32?displayProperty=nameWithType>.
- Colecciones, como <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> y <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>.
- Tipos de utilidades, como <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> y <xref:System.IO.FileStream?displayProperty=nameWithType>.
- Tipos de datos, como <xref:System.Data.DataSet?displayProperty=nameWithType> y <xref:System.Data.Entity.DbSet?displayProperty=nameWithType>.
- Tipos de alto rendimiento, como <xref:System.Span%601?displayProperty=nameWithType>, <xref:System.Numerics.Vector?displayProperty=nameWithType> y [Canalizaciones](../standard/io/pipelines.md).

.NET Core proporciona compatibilidad con las API .NET Framework y Mono API implementando la especificación de [.NET Standard](../standard/net-standard.md).

## <a name="composition"></a>Composición

.NET Core consta de las siguientes partes:

- El [runtime de .NET Core](https://github.com/dotnet/runtime/tree/master/src/coreclr), que proporciona un sistema de tipos, la carga de ensamblados, un colector de elementos no usados, interoperabilidad nativa y otros servicios básicos. Las [bibliotecas de .NET Core Framework](https://github.com/dotnet/runtime/tree/master/src/libraries) proporcionan tipos de datos primitivos, tipos de composición de aplicaciones y utilidades fundamentales.
- El [runtime de ASP.NET](https://github.com/dotnet/aspnetcore), el cual proporciona un marco para crear aplicaciones modernas conectadas a Internet y basadas en la nube, como aplicaciones web, aplicaciones de IoT y back-ends móviles.
- El [SDK de .NET Core](https://github.com/dotnet/sdk) y los compiladores de lenguaje ([Roslyn](https://github.com/dotnet/roslyn) y [F#](https://github.com/microsoft/visualfsharp)) que habilitan la experiencia de desarrollador de .NET Core.
- El [comando dotnet](./tools/dotnet.md), que se usa para iniciar aplicaciones .NET Core y comandos de CLI. Se selecciona y lo hospeda, proporciona una directiva de carga de ensamblados e inicia aplicaciones y herramientas.

### <a name="open-source"></a>Código Abierto

[.NET Core](about.md) es una plataforma de desarrollo [de código abierto](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT) para uso general. Se pueden crear aplicaciones de .NET Core para Windows, macOS y Linux con procesadores x64, x86, ARM32 y ARM64. Se proporcionan marcos y API para la [nube](/aspnet/core/), [IoT](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0), la [Interfaz de usuario de cliente](../desktop-wpf/overview/index.md) y el [aprendizaje automático](../machine-learning/index.yml).

## <a name="support"></a>Soporte técnico

[Microsoft admite](https://dotnet.microsoft.com/platform/support/policy) .NET Core en Windows, macOS y Linux. Se actualiza por motivos de seguridad y calidad periódicamente (el segundo martes de cada mes).

Las distribuciones binarias de .NET Core se compilan y prueban en servidores mantenidos por Microsoft en Azure y siguen las prácticas de seguridad e ingeniería de Microsoft.

[Red Hat admite .NET Core](https://developers.redhat.com/topics/dotnet/) en Red Hat Enterprise Linux (RHEL). Red Hat compila .NET Core desde el código fuente y permite que esté disponible en [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/). Red Hat y Microsoft colaboran para asegurarse de que .NET Core funciona bien en RHEL.

[Tizen admite .NET Core](https://developer.tizen.org/development/training/.net-application) en plataformas Tizen.
