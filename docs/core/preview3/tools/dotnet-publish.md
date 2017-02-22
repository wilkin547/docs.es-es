---
title: Comando dotnet-publish | Microsoft Docs
description: El comando dotnet-publish publica el proyecto de .NET Core en un directorio.
keywords: dotnet-publish, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 10/07/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f2ef275a-7c5e-430a-8c30-65f52af62771
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 0d222382640fc239760f8f51c69f1f306674d7ca

---

#<a name="dotnet-publish-net-core-tools-rc4"></a>dotnet-publish (.NET Core Tools RC4)

> [!WARNING]
> Este tema se aplica a .NET Core Tools RC4. Para la versión .NET Core Tools Preview 2, consulte el tema [dotnet-publish](../../tools/dotnet-publish.md).

## <a name="name"></a>Nombre

`dotnet-publish`: empaqueta la aplicación y todas sus dependencias en una carpeta y la deja lista para publicarse.

## <a name="synopsis"></a>Sinopsis

`dotnet publish [project] 
    [--help] [--framework]  
    [--runtime] [--output]  
    [--version-suffix] [--configuration]`

## <a name="description"></a>Descripción

`dotnet publish` compila la aplicación, lee sus dependencias especificadas en el archivo project.json y publica el conjunto resultante de archivos en un directorio. 

Dependiendo del tipo de aplicación portátil, el directorio resultante contendrá lo siguiente:

1. *Implementación dependiente del marco*: código de lenguaje intermedio (IL) de la aplicación y todas las dependencias administradas de la aplicación.
2. *Implementación autocontenida*: igual que anteriormente más el tiempo de ejecución completo para la plataforma de destino.

Para más información, consulte el tema [Implementación de aplicaciones .NET Core](../deploying/index.md).

## <a name="options"></a>Opciones

`[project]` 

El proyecto para publicar, cuyo valor predeterminado es el directorio actual si no se especifica `[project]`. 

`-h|--help`

Imprime una corta ayuda para el comando.  

`-f|--framework <FRAMEWORK>`

Publica la aplicación para un identificador de marco determinado (FID). 

`-r|--runtime <RUNTIME_IDENTIFIER>`

Publica la aplicación para un determinado entorno de tiempo de ejecución. Para obtener una lista de identificadores de tiempo de ejecución (RID) que puede usar, consulte el [catálogo de RID](../../rid-catalog.md).

`-o|--output <OUTPUT_PATH>`

Especifique la ruta donde colocar el directorio. Si no se especifica, se toma como predeterminada *_./bin/[configuration]/[framework]/_* para aplicaciones portátiles o *_./bin/[configuration]/[framework]/[runtime]_* para implementaciones autocontenidas.

`--version-suffix [VERSION_SUFFIX]`

Define qué `*` debe reemplazarse por el campo de versión en el archivo del proyecto.

`-c|--configuration [Debug|Release]`

Configuración para usar al publicar. El valor predeterminado es `Debug`.

## <a name="examples"></a>Ejemplos

Publica una aplicación:

`dotnet publish`

Publica la aplicación con el archivo de proyecto especificado:

`dotnet publish ~/projects/app1/app1.csproj`
    
Publicación de la aplicación actual con el marco `netcoreapp1.0`:

`dotnet publish --framework netcoreapp1.0`
    
Publica la aplicación actual con el marco `netcoreapp1.0` y el entorno de tiempo de ejecución para `OS X 10.10` (este RID tiene que existir en el archivo de proyecto):

`dotnet publish --framework netcoreapp1.0 --runtime osx.10.11-x64`

## <a name="see-also"></a>Vea también
* [Marcos](../../../standard/frameworks.md)
* [Catálogo de identificadores de tiempo de ejecución (RID)](../../rid-catalog.md)



<!--HONumber=Feb17_HO2-->


