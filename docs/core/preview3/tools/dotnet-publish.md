---
title: Comando dotnet-publish | .NET Core SDK
description: El comando dotnet-publish publica el proyecto de .NET Core en un directorio.
keywords: dotnet-publish, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 10/07/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8a7e1c52-5c57-4bf5-abad-727450ebeefd
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: e480c32faa22859de74e06f3a199fba1c0720c46

---

#<a name="dotnet-publish"></a>dotnet-publish

## <a name="name"></a>Name

`dotnet-publish` - Empaqueta la aplicación y todas sus dependencias en una carpeta y lo deja listo para publicarse

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



<!--HONumber=Nov16_HO3-->


