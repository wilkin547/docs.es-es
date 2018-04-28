---
title: 'Comando dotnet add package: CLI de .NET Core'
description: El comando “dotnet add package” constituye una opción práctica para agregar la referencia de un paquete de NuGet a un proyecto.
author: mairaw
ms.author: mairaw
ms.date: 08/11/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 3a8752ff83e069d21ebbda346efef34b17360e3b
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-add-package"></a>dotnet add package

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nombre

`dotnet add package`: agrega una referencia de paquete a un archivo del proyecto.

## <a name="synopsis"></a>Sinopsis

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-h|--help] [-v|--version] [-f|--framework] [-n|--no-restore] [-s|--source] [--package-directory]`

## <a name="description"></a>Description

El comando `dotnet add package` constituye una opción práctica para agregar una referencia de paquete a un archivo del proyecto. Después de ejecutar el comando, existe una comprobación de compatibilidad para garantizar que el paquete es compatible con los marcos del proyecto. Si se pasa la comprobación, un elemento `<PackageReference>` se agrega al archivo del proyecto y [dotnet restore](dotnet-restore.md) se ejecuta.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Por ejemplo, si agrega `Newtonsoft.Json` a *ToDo.csproj* se producirá un resultado similar al del siguiente ejemplo:

```
  Writing C:\Users\mairaw\AppData\Local\Temp\tmp95A8.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'C:\projects\ToDo\ToDo.csproj'.
log  : Restoring packages for C:\projects\ToDo\ToDo.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 235ms
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'C:\projects\ToDo\ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '10.0.3' added to file 'C:\projects\ToDo\ToDo.csproj'.
```

El archivo *ToDo.csproj* contiene ahora un elemento [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) para el paquete al que hace referencia.

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

## <a name="arguments"></a>Argumentos

`PROJECT`

Especifica el archivo del proyecto. Si no se especifica, el comando busca uno en el directorio actual.

`PACKAGE_NAME`

La referencia de paquete que se va a agregar.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.

`-v|--version <VERSION>`

Versión del paquete.

`-f|--framework <FRAMEWORK>`

Agrega una referencia de paquete solo cuando se destina a un [marco](../../standard/frameworks.md) específico.

`-n|--no-restore`

Agrega una referencia de paquete sin realizar una vista previa de restauración y una comprobación de compatibilidad.

`-s|--source <SOURCE>`

Usa un origen de paquete específico NuGet durante la operación de restauración.

`--package-directory <PACKAGE_DIRECTORY>`

Restaura el paquete al directorio especificado.

## <a name="examples"></a>Ejemplos

Agregar un paquete de NuGet `Newtonsoft.Json` a un proyecto:

`dotnet add package Newtonsoft.Json`

Agregar una versión específica de un paquete a un proyecto:

`dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0`

Agregar un paquete con un origen de NuGet específico:

`dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json`
