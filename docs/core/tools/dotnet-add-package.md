---
title: Comando dotnet-add package | Microsoft Docs
description: "El comando dotnet-add package constituye una opción práctica para agregar la referencia de paquetes NuGet a un proyecto."
keywords: dotnet-add, CLI, comando de la CLI, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 88e0da69-a5ea-46cc-8b46-5493242b7af9
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 806f4383452cb250f302dc30ab2d59f7e4772026
ms.lasthandoff: 03/07/2017

---
# <a name="dotnet-add-package"></a>dotnet-add package

## <a name="name"></a>Name

`dotnet-add package`: agrega una referencia de paquete a un archivo del proyecto.

## <a name="synopsis"></a>Sinopsis

```
dotnet add [project] package <package_name> [-v|--version] [-f|--framework] [-n|--no-restore] [-s|--source] [--package-directory]
dotnet add package [-h|--help]
```

## <a name="description"></a>Descripción

El comando `dotnet add package` constituye una opción práctica para agregar una referencia de paquete a un archivo del proyecto. Después de ejecutar el comando, existe una comprobación de compatibilidad para garantizar que el paquete que intenta agregarse es compatible con todos los marcos del proyecto. Si se pasa la comprobación, se ejecuta una [restauración](dotnet-restore.md) y el fragmento `<PackageReference>` se agrega al archivo del proyecto.

Por ejemplo, agregar `Newtonsoft.Json` a *ToDo.csproj* produce un resultado similar al siguiente:

```
Microsoft (R) Build Engine version 15.1.545.13942
Copyright (C) Microsoft Corporation. All rights reserved.

  Writing /var/folders/gj/1mgg_4jx7mbdqbhw1kgcpcjr0000gn/T/tmpm0kTMD.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'ToDo.csproj'.
log  : Restoring packages for ToDo.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 119ms
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/9.0.1/newtonsoft.json.9.0.1.nupkg
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/9.0.1/newtonsoft.json.9.0.1.nupkg 27ms
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '9.0.1' added to file 'ToDo.csproj'.
```

El archivo *ToDo.csproj* ahora contiene un fragmento [`<PackageReference>`](https://docs.microsoft.com/nuget/consume-packages/package-references-in-project-files) para el paquete al que se hace referencia.

```xml
<PackageReference Include="Newtonsoft.Json">
  <Version>9.0.1</Version>
</PackageReference>
```

## <a name="arguments"></a>Argumentos

`project`

El archivo del proyecto sobre el que actuar. Si no se especifica, el comando busca uno en el directorio actual.

`package_name`

La referencia de paquete que se va a agregar.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.

`-v|--version <VERSION>`

Versión del paquete.

`-f|--framework <FRAMEWORK>`

Agrega una referencia de paquete solo cuando el destino es un marco específico.

`-n|--no-restore`

Agrega una referencia de paquete sin realizar la vista previa de restauración y la comprobación de compatibilidad.

`-s|--source <SOURCE>`

Usa un origen de paquetes de NuGet específico que se usará durante la operación de restauración.

`--package-directory <PACKAGE_DIRECTORY>`

Restaura el paquete al directorio especificado.

## <a name="examples"></a>Ejemplos

Agregar un paquete de NuGet `Newtonsoft.Json` a un proyecto:

`dotnet add package Newtonsoft.Json`

Agregar una versión específica de un paquete a un proyecto:

`dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0`

Agregar un paquete con un origen de NuGet específico:

`dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json`

