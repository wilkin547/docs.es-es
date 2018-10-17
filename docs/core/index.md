---
title: Guía de .NET Core
description: .NET Core es una implementación modular y de alto rendimiento de .NET para crear aplicaciones de Windows, Linux y Mac. Obtenga información sobre .NET Core para comenzar.
author: richlander
ms.author: mairaw
ms.date: 08/01/2018
ms.custom: updateeachrelease
ms.openlocfilehash: 692d49cc940925f629e55cf5cc103522bd3cbb38
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2018
ms.locfileid: "49348986"
---
# <a name="net-core-guide"></a>Guía de .NET Core

[.NET Core](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT) es una plataforma de desarrollo de uso general de [código abierto](about.md) de cuyo mantenimiento se encargan Microsoft y la comunidad .NET en [GitHub](https://github.com/dotnet/core). Es multiplataforma, admite Windows, macOS y Linux y puede usarse en aplicaciones de dispositivo, nube e IoT.

Consulte [Acerca de .NET Core](about.md) para más información sobre .NET Core, incluidas sus características, idiomas y marcos admitidos y principales API.

Consulte los [tutoriales de .NET Core](tutorials/index.md) para aprender a crear una aplicación .NET Core sencilla. En unos minutos su primera aplicación estará lista y funcionando. Si quiere probar .NET Core en su explorador, consulte la guía de inicio rápido [Números en C#](../csharp/quick-starts/numbers-in-csharp.yml).

## <a name="download-net-core-21"></a>Descarga de .NET Core 2.1

Descargue el [SDK de .NET Core 2.1](https://www.microsoft.com/net/download) para probar .NET Core en la máquina Windows, macOS o Linux. Visite [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) si prefiere usar contenedores de Docker.

Si busca otra versión de .NET Core, todas las versiones de .NET Core están disponibles en la [página de descargas de .NET Core](https://www.microsoft.com/net/download/archives).

## <a name="net-core-21"></a>.NET Core 2.1

La última versión es [.NET Core 2.1](whats-new/dotnet-core-2-1.md). Las nuevas características incluyen: herramientas globales, API de alto rendimiento (como <xref:System.Span%601?displayProperty=nameWithType>), compilación JIT en capas, mejoras de rendimiento de [compilación](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) y [tiempo de ejecución](https://blogs.msdn.microsoft.com/dotnet/2018/04/18/performance-improvements-in-net-core-2-1/) y compatibilidad con Alpine y ARM32.

## <a name="create-your-first-application"></a>Creación de la primera aplicación

Después de instalar el SDK de .NET Core, abra un símbolo del sistema. Escriba los comandos `dotnet` siguientes para crear y ejecutar una aplicación de C#.

```console
dotnet new console
dotnet run
```

Debería ver los siguientes resultados:

```console
Hello World!
```

## <a name="support"></a>Compatibilidad

[Microsoft admite](https://www.microsoft.com/net/support/policy) .NET Core en Windows, macOS y Linux. Varias veces al año, por lo general mensualmente, se actualiza para aumentar la seguridad y la calidad.

Las distribuciones binarias de .NET Core se compilan y prueban en servidores mantenidos por Microsoft en Azure y reciben el mismo soporte técnico que cualquier otro producto de Microsoft.

[Red Hat admite .NET Core](http://redhatloves.net/) en Red Hat Enterprise Linux (RHEL). Red Hat compila .NET Core desde el código fuente y permite que esté disponible en [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/). Red Hat y Microsoft colaboran para asegurarse de que .NET Core funciona bien en RHEL.
