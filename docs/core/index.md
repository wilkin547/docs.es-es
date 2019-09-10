---
title: Guía de .NET Core
description: .NET Core es una implementación modular y de alto rendimiento de .NET para crear aplicaciones de Windows, Linux y Mac. Obtenga información sobre .NET Core para comenzar.
author: richlander
ms.date: 08/01/2018
ms.custom: updateeachrelease
ms.openlocfilehash: 0007c1c6a9939c46f123535f9053ac1d4ced7266
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70848944"
---
# <a name="net-core-guide"></a>Guía de .NET Core

[.NET Core](about.md) es una plataforma de desarrollo de uso general de [código abierto](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT) de cuyo mantenimiento se encargan Microsoft y la comunidad .NET en [GitHub](https://github.com/dotnet/core). Es multiplataforma, admite Windows, macOS y Linux y puede usarse para compilar aplicaciones de dispositivo, nube e IoT.

Consulte [Acerca de .NET Core](about.md) para más información sobre .NET Core, incluidas sus características, idiomas y marcos admitidos y principales API.

Consulte los [tutoriales de .NET Core](tutorials/index.md) para aprender a crear una aplicación .NET Core sencilla. En unos minutos su primera aplicación estará lista y funcionando. Si quiere probar .NET Core en su explorador, consulte el tutorial en línea [Números en C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml).

## <a name="download-net-core-22"></a>Descarga de .NET Core 2.2

Descargue el [SDK de .NET Core 2.2](https://dotnet.microsoft.com/download) para probar .NET Core en su equipo Windows, macOS o Linux. Visite [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) si prefiere usar contenedores de Docker.

Si busca otra versión de .NET Core, todas las versiones de .NET Core están disponibles en la [página de descargas de .NET Core](https://dotnet.microsoft.com/download/dotnet-core).

## <a name="net-core-22"></a>.NET Core 2.2

La última versión es [.NET Core 2.2](whats-new/dotnet-core-2-2.md). Entre las nuevas características destacan las implementaciones dependientes de marcos, los enlaces de inicio, la autenticación de AAD con Azure SQL y la compatibilidad con Windows ARM32.

## <a name="create-your-first-application"></a>Creación de la primera aplicación

Después de instalar el SDK de .NET Core, abra un símbolo del sistema. Escriba los comandos `dotnet` siguientes para crear y ejecutar una aplicación de C#.

```console
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
