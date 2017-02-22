---
title: Comando dotnet-pack | Microsoft Docs
description: El comando dotnet-pack crea paquetes de NuGet para el proyecto .NET Core.
keywords: dotnet-pack, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 10/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8dbbb3f7-b817-4161-a6c8-a3489d05e051
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 8e266f9b34923b0ab69140d78a20afeca00e0b7c

---

#<a name="dotnet-pack-net-core-tools-rc4"></a>dotnet-pack (.NET Core Tools RC4)

> [!WARNING]
> Este tema se aplica a .NET Core Tools RC4. Para la versión .NET Core Tools Preview 2, consulte el tema [dotnet-pack](../../tools/dotnet-pack.md).

## <a name="name"></a>Nombre

`dotnet-pack`: empaqueta el código en un paquete de NuGet.

## <a name="synopsis"></a>Sinopsis

`dotnet pack [--help] [--output]  
    [--no-build] [--include-symbols]
    [--include-source] [--servicable]
    [--configuration]  [--version-suffix]
    [project]`  

## <a name="description"></a>Descripción

El comando `dotnet pack` compila el proyecto y crea paquetes de NuGet. El resultado de este comando es un paquete de NuGet. Si la opción `--include-symbols` está presente, se crea otro paquete que contiene los símbolos de depuración. 

Las dependencias de NuGet del proyecto que se empaquetan se agregan al archivo `nuspec`, por lo que se pueden resolver cuando se instala el paquete. Las referencias de proyecto a proyecto no se empaquetan dentro del proyecto. Actualmente, debe disponer de un paquete por proyecto si tiene dependencias de proyecto a proyecto.

`dotnet pack`de forma predeterminada, primero compila el proyecto. Si desea evitar esto, pase la opción `--no-build`. Esto puede ser útil en escenarios de compilación de integración continua (CI) en el que conoce el código que se compiló anteriormente. 

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.  

`[project]` 
    
El proyecto para empaquetar. Puede ser una ruta de acceso a un archivo [csproj](csproj.md) o a un directorio. Si se omite, tomará como predeterminado el directorio actual. 

`-o|--output <OUTPUT_DIRECTORY>`

Coloca los paquetes compilados en el directorio especificado. 

`--no-build`

No compila el proyecto antes de empaquetarlo. 

`--include-source`

Incluye los archivos de origen en el paquete de NuGet. Los archivos de origen se incluyen en la carpeta `src` dentro de `nupkg`. 

`--include-symbols`

Genera el nupkg de símbolos. 

`-c|--configuration <Debug|Release>`

Configuración para usar al compilar el proyecto. Si no se especifica, se tomará como predeterminada `Debug`.

`--version-suffix`

Actualiza la estrella en el sufijo de la versión del paquete `-*` con una cadena especificada.

## <a name="examples"></a>Ejemplos

Empaquetado del proyecto en el directorio actual:

`dotnet pack`

Empaquetado del proyecto app1:

`dotnet pack ~/projects/app1/project.csproj`
    
Empaquetado del proyecto en el directorio actual y colocación de los paquetes resultantes en la carpeta especificada:

`dotnet pack --output nupkgs`

Empaquetado del proyecto en el directorio actual en la carpeta especificada y omisión del paso de compilación:

`dotnet pack --no-build --output nupkgs`

Empaquetado del proyecto actual y actualización de la versión de los paquetes resultantes con el sufijo dado. Por ejemplo, la versión `1.0.0-*` se actualiza a `1.0.0-ci-1234`.

`dotnet pack --version-suffix "ci-1234"`


<!--HONumber=Feb17_HO2-->


