---
title: Introducción e información general de .NET Core
description: .NET Core es una implementación modular y de alto rendimiento de .NET para crear aplicaciones Windows, Linux y macOS. Obtenga información sobre .NET Core para comenzar.
author: richlander
ms.date: 03/26/2020
ms.custom: updateeachrelease
ms.openlocfilehash: b28ad965e54680e2e1134c389266741ade28084f
ms.sourcegitcommit: 67cf756b033c6173a1bbd1cbd5aef1fccac99e34
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2020
ms.locfileid: "86226587"
---
# <a name="introduction-to-net-core"></a>Introducción a .NET Core

[.NET Core](about.md) es una plataforma de desarrollo [de código abierto](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT) para uso general. Puede crear aplicaciones de .NET Core para Windows, macOS y Linux para procesadores x64, x86, ARM32 y ARM64 mediante varios lenguajes de programación. Se proporcionan marcos y API para la [nube](/aspnet/core/), [IoT](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0), la [Interfaz de usuario de cliente](../desktop-wpf/overview/index.md) y el [aprendizaje automático](/dotnet/machine-learning/).

[Descargue el SDK de .NET Core](https://dotnet.microsoft.com/download) para probar .NET Core en el equipo. La última versión es [.NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).

## <a name="download-net-core"></a>Descarga de .NET Core

Puede obtener .NET Core de las siguientes maneras:

* [Instaladores para Windows y macOS](https://dotnet.microsoft.com/download)
* [Paquetes de Linux](https://docs.microsoft.com/dotnet/core/install/linux-package-managers)
* [Contenedores de Docker](https://hub.docker.com/_/microsoft-dotnet-core/)
* [Archivos ZIP y tar](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* [Scripts de instalación](https://dotnet.microsoft.com/download/dotnet-core/scripts)
* [Notas de la versión](https://github.com/dotnet/core/tree/master/release-notes)

## <a name="create-your-first-application"></a>Creación de la primera aplicación

Después de instalar el SDK de .NET Core, abra un símbolo del sistema. Use los comandos siguientes para crear y ejecutar una aplicación:

```dotnetcli
dotnet new console
dotnet run
```

Debería ver los siguientes resultados:

```output
Hello World!
```

## <a name="contribute"></a>Contribuir

.NET Core es una plataforma abierta. Todo el mundo puede participar.

* Registre las incidencias y preguntas sobre el producto en [Developer Community](https://developercommunity.visualstudio.com/spaces/61/index.html).
* Las contribuciones al producto se deben realizar en uno de los repositorios del proyecto, como [dotnet/runtime](https://github.com/dotnet/runtime), [dotnet/sdk](https://github.com/dotnet/sdk), [dotnet/rosyln](https://github.com/dotnet/roslyn) o [aspnetcore](https://github.com/dotnet/aspnetcore). Para obtener más información, vea [Repositorios de .NET Core](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md).

## <a name="support"></a>Soporte técnico

.NET Core es compatible con Microsoft en Windows, macOS y Linux, y con Red Hat en Red Hat Enterprise Linux.

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Tutoriales de .NET Core](tutorials/index.md)

> [!div class="nextstepaction"]
> [Prueba de .NET Core en el explorador](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml)
