---
title: Guía de .NET Core
description: .NET Core es una implementación modular y de alto rendimiento de .NET para crear aplicaciones Windows, Linux y macOS. Obtenga información sobre .NET Core para comenzar.
author: richlander
ms.date: 12/04/2019
ms.custom: updateeachrelease
ms.openlocfilehash: 6d2ce5951fa01ca3945ce0e64aa58fbadc8ab5af
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546554"
---
# <a name="net-core-guide"></a>Guía de .NET Core

[.NET Core](about.md) es una plataforma de desarrollo de uso general de [código abierto](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT) de cuyo mantenimiento se encargan Microsoft y la comunidad .NET en [GitHub](https://github.com/dotnet/core). Es multiplataforma, admite Windows, macOS y Linux y puede usarse para compilar aplicaciones de dispositivo, nube e IoT.

Consulte [Acerca de .NET Core](about.md) para más información sobre .NET Core, incluidas sus características, idiomas y marcos admitidos y principales API.

Consulte los [tutoriales de .NET Core](tutorials/index.md) para aprender a crear una aplicación .NET Core sencilla. En unos minutos su primera aplicación estará lista y funcionando. Si quiere probar .NET Core en su explorador, consulte el tutorial en línea [Números en C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml).

## <a name="download-net-core"></a>Descarga de .NET Core

Descargue el [SDK de .NET Core](https://dotnet.microsoft.com/download) para probar .NET Core en su máquina Windows, macOS o Linux. Si prefiere usar contenedores de Docker, visite [Docker Hub de .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/).

Si busca otra versión de .NET Core, todas las versiones de .NET Core están disponibles en la [página de descargas de .NET Core](https://dotnet.microsoft.com/download/dotnet-core).

## <a name="net-core-31"></a>.NET Core 3.1

La última versión es .NET Core 3.1. En la versión 3.1 se incluyen mejoras menores con respecto a .NET Core 3.0, pero .NET Core 3.1 es una [versión admitida a largo plazo](https://dotnet.microsoft.com/platform/support/policy/dotnet-core). Para más información sobre la versión .NET Core 3.1, vea [Novedades de .NET Core 3.1](./whats-new/dotnet-core-3-1.md).

## <a name="create-your-first-application"></a>Creación de la primera aplicación

Después de instalar el SDK de .NET Core, abra un símbolo del sistema. Escriba los comandos `dotnet` siguientes para crear y ejecutar una aplicación C#:

```dotnetcli
dotnet new console
dotnet run
```

Debería ver los siguientes resultados:

```output
Hello World!
```

## <a name="support"></a>Soporte técnico

[Microsoft admite](https://dotnet.microsoft.com/platform/support/policy) .NET Core en Windows, macOS y Linux. Varias veces al año, por lo general mensualmente, se actualiza para aumentar la seguridad y la calidad.

Las distribuciones binarias de .NET Core se compilan y prueban en servidores mantenidos por Microsoft en Azure y reciben el mismo soporte técnico que cualquier otro producto de Microsoft.

[Red Hat admite .NET Core](http://redhatloves.net/) en Red Hat Enterprise Linux (RHEL). Red Hat compila .NET Core desde el código fuente y permite que esté disponible en [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/). Red Hat y Microsoft colaboran para asegurarse de que .NET Core funciona bien en RHEL.
