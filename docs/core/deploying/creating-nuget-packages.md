---
title: Creación de un paquete NuGet con la CLI de .NET Core
description: Obtenga información sobre cómo crear un paquete NuGet con el comando "dotnet pack".
author: cartermp
ms.date: 06/20/2016
ms.technology: dotnet-cli
ms.openlocfilehash: 3f8e75a501cfc48e1c416f71e91290cab1a4ffae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920920"
---
# <a name="how-to-create-a-nuget-package-with-the-net-core-cli"></a>Creación de un paquete NuGet con la CLI de .NET Core

> [!NOTE]
> A continuación se muestran ejemplos de línea de comandos mediante Unix. El comando `dotnet pack`, tal como se muestra aquí, funciona del mismo modo en Windows.

Está previsto que las bibliotecas .NET Standard y .NET Core se distribuyan como paquetes NuGet. De hecho, es así como se distribuyen y consumen todas las bibliotecas estándar .NET. Esto se hace más fácil con el comando `dotnet pack`.

Imagine que acaba de escribir una nueva biblioteca sorprendente que quiere distribuir a través de NuGet. Puede crear un paquete NuGet con herramientas multiplataforma para hacer exactamente eso. En el ejemplo siguiente, hay una biblioteca denominada **SuperAwesomeLibrary** con destino a `netstandard1.0`.

Si tiene dependencias transitivas; es decir, un proyecto que depende de otro paquete, asegúrese de restaurar los paquetes para toda la solución con el comando `dotnet restore` antes de crear un paquete NuGet. Si no lo hace, el comando `dotnet pack` no funcionará correctamente.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Después de asegurarse de que se restauran los paquetes, puede ir hasta el directorio donde reside una biblioteca:

```console
cd src/SuperAwesomeLibrary
```

Luego, es solo cuestión de un comando desde la línea de comandos:

```dotnetcli
dotnet pack
```

La carpeta */bin/Debug* tendrá un aspecto similar al siguiente:

```console
$ ls bin/Debug
netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

Esto genera un paquete que se puede depurar. Si quiere compilar un paquete NuGet con archivos binarios de versión comercial, todo lo que tiene que hacer es agregar el modificador `--configuration` (o`-c`) y usar `release` como argumento.

```dotnetcli
dotnet pack --configuration release
```

La carpeta */bin* tendrá ahora una carpeta *versión* que contiene el paquete NuGet con archivos binarios de versión:

```console
$ ls bin/release
netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

Y ahora tiene los archivos necesarios para publicar un paquete de NuGet.

## <a name="dont-confuse-dotnet-pack-with-dotnet-publish"></a>`dotnet pack`No confunda `dotnet publish` con

Es importante tener en cuenta que en ningún momento participa el comando `dotnet publish`. El comando `dotnet publish` se destina a la implementación de aplicaciones con todas sus dependencias en el mismo conjunto, no a la generación de un paquete NuGet que se distribuya y consuma a través de NuGet.

## <a name="see-also"></a>Vea también

- [Inicio rápido: Creación y publicación de un paquete](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)
