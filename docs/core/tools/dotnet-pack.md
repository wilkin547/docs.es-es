---
title: Comando dotnet-pack | Microsoft Docs
description: El comando dotnet-pack crea paquetes de NuGet para el proyecto .NET Core.
keywords: dotnet-pack, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8dbbb3f7-b817-4161-a6c8-a3489d05e051
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 88289a09a22bf20ec9089ec6a74269cd682a305b
ms.lasthandoff: 03/07/2017

---

#<a name="dotnet-pack"></a>dotnet-pack

## <a name="name"></a>Name

`dotnet-pack`: empaqueta el código en un paquete de NuGet.

## <a name="synopsis"></a>Sinopsis

```
dotnet pack [project] [-o|--output] [--no-build] [--include-symbols] [--include-source] [-c|--configuration] [--version-suffix] [-s|--serviceable] [-v|--verbosity]
dotnet pack [-h|--help]
```

## <a name="description"></a>Descripción

El comando `dotnet pack` compila el proyecto y crea paquetes de NuGet. El resultado de este comando es un paquete de NuGet. Si la opción `--include-symbols` está presente, se crea otro paquete que contiene los símbolos de depuración. 

Las dependencias de NuGet del proyecto que se empaquetan se agregan al archivo `nuspec`, por lo que se pueden resolver cuando se instala el paquete. Las referencias de proyecto a proyecto no se empaquetan dentro del proyecto. Actualmente, debe disponer de un paquete por proyecto si tiene dependencias de proyecto a proyecto.

`dotnet pack`de forma predeterminada, primero compila el proyecto. Si desea evitar esto, pase la opción `--no-build`. Esto puede ser útil en escenarios de compilación de integración continua (CI) en el que conoce el código que se compiló anteriormente. 

## <a name="arguments"></a>Argumentos

`project` 
    
El proyecto para empaquetar. Puede ser una ruta de acceso a un archivo [csproj](csproj.md) o a un directorio. Si se omite, tomará como predeterminado el directorio actual. 

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.  

`-o|--output <OUTPUT_DIRECTORY>`

Coloca los paquetes compilados en el directorio especificado. 

`--no-build`

No compila el proyecto antes de empaquetarlo. 

`--include-symbols`

Genera el nupkg de símbolos. 

`--include-source`

Incluye los archivos de origen en el paquete de NuGet. Los archivos de origen se incluyen en la carpeta `src` dentro de `nupkg`. 

`-c|--configuration <Debug|Release>`

Configuración para usar al compilar el proyecto. Si no se especifica, se tomará como predeterminada `Debug`.

`--version-suffix <VERSION_SUFFIX>`

Define el valor de la propiedad MSBuild $(VersionSuffix) en el proyecto.

`-s|--serviceable`

Establece la marca de servicio en el paquete. Para obtener más información, vea https://aka.ms/nupkgservicing.

`--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

## <a name="examples"></a>Ejemplos

Empaquetado del proyecto en el directorio actual:

`dotnet pack`

Empaquetado del proyecto app1:

`dotnet pack ~/projects/app1/project.csproj`
    
Empaquetado del proyecto en el directorio actual y colocación de los paquetes resultantes en la carpeta especificada:

`dotnet pack --output nupkgs`

Empaquetado del proyecto en el directorio actual en la carpeta especificada y omisión del paso de compilación:

`dotnet pack --no-build --output nupkgs`

Empaquetado del proyecto actual y actualización de la versión del paquete resultante con el sufijo dado. El sufijo de la versión del proyecto está configurado como `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` en el archivo *.csproj*.

`dotnet pack --version-suffix "ci-1234"`
