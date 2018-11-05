---
title: Creación de un paquete de NuGet con herramientas multiplataforma
description: Obtenga información sobre cómo crear un paquete NuGet con el comando "dotnet pack".
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.technology: dotnet-cli
ms.openlocfilehash: 0be8d302568bc08d2c3dacfdf5738eff4b97d4b2
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2018
ms.locfileid: "48848106"
---
# <a name="how-to-create-a-nuget-package-with-cross-platform-tools"></a>Cómo crear un paquete de NuGet con herramientas multiplataforma

> [!NOTE]
> A continuación se muestran ejemplos de línea de comandos mediante Unix.  El comando `dotnet pack`, tal como se muestra aquí, funciona del mismo modo en Windows.

Para .NET Core 1.0, está previsto que las bibliotecas se distribuyan como paquetes de NuGet.  De hecho, es así como se distribuyen y consumen todas las bibliotecas estándar .NET.  Esto se hace más fácil con el comando `dotnet pack`.

Imagine que acaba de escribir una nueva biblioteca sorprendente que quiere distribuir a través de NuGet.  Puede crear un paquete de NuGet con herramientas multiplataforma para hacer exactamente eso.  En el ejemplo siguiente, hay una biblioteca denominada **SuperAwesomeLibrary** con destino a `netstandard1.0`.

Si tiene dependencias transitivas; es decir, un proyecto que depende de otro paquete, deberá asegurarse de restaurar los paquetes para toda la solución con el comando `dotnet restore` antes de crear un paquete de NuGet.  Si no lo hace, el comando `dotnet pack` no funcionará correctamente.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]


Después de asegurarse de que se restauran los paquetes, puede ir hasta el directorio donde reside una biblioteca:

`$ cd src/SuperAwesomeLibrary`

Luego, es solo cuestión de un comando desde la línea de comandos:
    
`$ dotnet pack`

Su carpeta `/bin/Debug` tendrá un aspecto similar al siguiente:

```
$ ls bin/Debug

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

Tenga en cuenta que esto producirá un paquete que se puede depurar.  Si quiere compilar un paquete de NuGet con archivos binarios de versión comercial, todo lo que tiene que hacer es agregar el modificador `-c`/`--configuration` y usar `release` como argumento.

`$ dotnet pack --configuration release`

Su `/bin` carpeta tendrá ahora una `release` carpeta que contiene el paquete de NuGet con archivos binarios de versión:

```
$ ls bin/release

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

Y ahora tiene los archivos necesarios para publicar un paquete de NuGet.

## <a name="dont-confuse-dotnet-pack-with-dotnet-publish"></a>`dotnet pack`No confunda `dotnet publish` con

Es importante tener en cuenta que en ningún momento participa el comando `dotnet publish`.  El comando `dotnet publish` es para la implementación de aplicaciones con todas sus dependencias en el mismo paquete, no para generar un paquete de NuGet para distribuir y consumir a través de NuGet.
