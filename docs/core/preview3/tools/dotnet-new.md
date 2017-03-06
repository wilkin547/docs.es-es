---
title: Comando dotnet-new | Microsoft Docs
description: El comando dotnet-new crea nuevos proyectos de .NET Core en el directorio actual.
keywords: dotnet-new, CLI, comando de CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 02/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fcc3ed2e-9265-4d50-b59e-dc2e5c190b34
translationtype: Human Translation
ms.sourcegitcommit: 96fd8ea3e55ea33e0bdd0bf3c50a10d0de6db1a1
ms.openlocfilehash: f0c62647c5817db2057c60a7a95a62f08f7889a5

---
#<a name="dotnet-new-net-core-tools-rc4"></a>dotnet-new (.NET Core Tools RC4)

> [!WARNING]
> Este tema se aplica a .NET Core Tools RC4. Para la versión .NET Core Tools Preview 2, consulte el tema [dotnet-new](../../tools/dotnet-new.md).

## <a name="name"></a>Nombre
dotnet-new: crea un nuevo proyecto de .NET Core en el directorio actual.

## <a name="synopsis"></a>Sinopsis
```
dotnet new [template] [-lang|--language] [-n|--name] [-o|--output] [-h|--help]
dotnet new [template] [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

## <a name="description"></a>Descripción
El comando `dotnet new` proporciona una manera cómoda de inicializar un proyecto de .NET Core válido, junto con código fuente de ejemplo para probar el conjunto de herramientas de la interfaz de la línea de comandos (CLI). 

Este comando se invoca en el contexto de un directorio. Cuando se invoca, el comando aplicará la técnica scaffolding a los recursos y archivos de acuerdo con la plantilla y las opciones pasadas al comando. 

Después de esto, el proyecto está listo para ser compilado o editarse adicionalmente. 

## <a name="arguments"></a>Argumentos
template: la plantilla de la que se va a crear una instancia cuando se invoca el comando.

El comando contiene una lista predeterminada de plantillas; use `dotnet new --help`. 

## <a name="options"></a>Opciones

`-l|--list`         

Lista las plantillas que contienen el nombre especificado.

`-lang|--language`  

Especifica el idioma de la plantilla que se va a crear.

`-n|--name`         

El nombre de la salida que se va a crear. Si no se especifica ningún nombre, se usa el nombre del directorio actual.

`-o|--output`       

La ubicación para colocar la salida generada.

`-all|--show-all`   

Muestra todas las plantillas para un tipo específico de proyecto.

`-h|--help`

Imprime la ayuda para el comando.

## <a name="template-options"></a>Opciones de plantilla
Cada plantilla de proyecto puede tener opciones adicionales disponibles. Las plantillas básicas, por ejemplo, cuentan con lo siguiente.

**console, xunit, mstest**

`-f|--framework`: especifica la plataforma de destino. Valores: netcoreapp1.0 o netcoreapp1.1 (Valor predeterminado: netcoreapp1.0)

**web, webapi**

`-f|--framework`: especifica la plataforma de destino. Valores: netcoreapp1.0 o netcoreapp1.1 (Valor predeterminado: netcoreapp1.0)
 
**mvc**

`-f|--framework`: especifica la plataforma de destino. Valores: netcoreapp1.0 o netcoreapp1.1 (Valor predeterminado: netcoreapp1.0)

`-au|--authentication`: el tipo de autenticación que se va a usar. Valores: None o Individual (predeterminado: None)

`-uld|--use-local-db`: si se va a usar o no LocalDB en lugar de SQLite. Valores: true o false (valor predeterminado: false)

**classlib**

`-f|--framework`: especifica la plataforma de destino. Valores: netcoreapp1.0, netcoreapp1.1 y netstandard1.0 - 1.6 (Valor predeterminado: netstandard1.4).

## <a name="examples"></a>Ejemplos

Cree un proyecto de aplicación de consola con F# en el directorio actual:

`dotnet new console -lang f#` 
   
Cree un nuevo proyecto de aplicación MVC de ASP.NET Core C# en el directorio actual sin autenticación destinado a .NET Core 1.0:  

`dotnet new mvc -au None -f netcoreapp1.0`
 
Cree una nueva aplicación de XUnit destinada a .NET Core 1.1:

`dotnet new xunit --Framework netcoreapp1.1`

Enumere todas las plantillas disponibles para MVC:

`dotnet new mvc -l`


<!--HONumber=Feb17_HO3-->


