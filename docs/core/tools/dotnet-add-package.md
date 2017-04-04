---
title: Comando dotnet-add package - .NET Core CLI | Documentos de Microsoft
description: "El comando dotnet-add package constituye una opción práctica para agregar la referencia de paquetes NuGet a un proyecto."
keywords: dotnet-add, CLI, comando de la CLI, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 88e0da69-a5ea-46cc-8b46-5493242b7af9
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: 41b46e879056d385ceb3abaec27db974cab812e3
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-add-package"></a>dotnet-add package

## <a name="name"></a>Name

`dotnet-add package`: agrega una referencia de paquete a un archivo del proyecto.

## <a name="synopsis"></a>Sinopsis

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-v|--version] [-f|--framework] [-n|--no-restore] [-s|--source] [--package-directory] [-h|--help]`

## <a name="description"></a>Descripción

El comando `dotnet add package` constituye una opción práctica para agregar una referencia de paquete a un archivo del proyecto. Después de ejecutar el comando, existe una comprobación de compatibilidad para garantizar que el paquete es compatible con los marcos del proyecto. Si se pasa la comprobación, un elemento `<PackageReference>` se agrega al archivo del proyecto y [dotnet restore](dotnet-restore.md) se ejecuta.

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

El archivo *ToDo.csproj* contiene ahora un elemento [`<PackageReference>`](https://docs.microsoft.com/nuget/consume-packages/package-references-in-project-files) para el paquete al que hace referencia.

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

