---
title: 'Comando dotnet-test: CLI de .NET Core | Microsoft Docs'
description: El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado.
keywords: dotnet-test, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 4bf0aef4-148a-41c6-bb95-0a9e1af8762e
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: 26b5834135db8041995a137f5008d00cdf14d820
ms.lasthandoff: 03/22/2017

---

#<a name="dotnet-test"></a>dotnet-test

## <a name="name"></a>Name

`dotnet-test`: controlador de prueba de .NET usado para ejecutar pruebas unitarias.

## <a name="synopsis"></a>Sinopsis

`dotnet test [<PROJECT>] [-s|--settings] [-t|--list-tests] [--filter] [-a|--test-adapter-path] [-l|--logger] [-c|--configuration] [-f|--framework] [-o|--output] [-d|--diag] [--no-build] [-v|--verbosity] [-h|--help]`

## <a name="description"></a>Descripción

El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado. Las pruebas unitarias son proyectos de biblioteca de clases que tienen dependencias en el marco de pruebas unitarias (por ejemplo, MSText, NUnit o xUnit) y en el ejecutor de pruebas de dotnet de ese marco de pruebas unitarias. Estas se empaquetan como paquetes de NuGet y se restauran como dependencias ordinarias para el proyecto.

Los proyectos de prueba también deben especificar el ejecutor de pruebas. Para ello se utiliza un elemento `<PackageReference>` ordinario, como se puede ver en el siguiente archivo de proyecto de ejemplo:

[!code-xml[Plantilla de XUnit Basic](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="options"></a>Opciones

`PROJECT`
    
Especifica una ruta de acceso al proyecto de prueba. Si se omite, se toma como predeterminado el directorio actual.

`-h|--help`

Imprime una corta ayuda para el comando.

`-s|--settings <SETTINGS_FILE>`

Configuración que se usará al ejecutar las pruebas. 

`-t|--list-tests`

Enumera todas las pruebas detectadas en el proyecto actual. 

`--filter <EXPRESSION>`

Filtra las pruebas del proyecto actual con la expresión dada. Para más información sobre la compatibilidad de filtrado, consulte [Running selective unit tests in Visual Studio using TestCaseFilter](https://aka.ms/vstest-filtering) (Ejecutar pruebas unitarias selectivas en Visual Studio mediante TestCaseFilter).

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas. 

`-l|--logger <LoggerUri/FriendlyName>`

Especifica un registrador para los resultados de pruebas. 

`-c|--configuration <CONFIGURATION>`

Configuración con la que se va a realizar la compilación. El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.

`-f|--framework <FRAMEWORK>`

Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.

`-o|--output <OUTPUT_DIRECTORY>`

Directorio donde se encuentran los archivos binarios que se ejecutarán.

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado. 

`--no-build` 

No compila el proyecto de prueba antes de ejecutarlo.

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

## <a name="examples"></a>Ejemplos

Ejecución de las pruebas en el proyecto en el directorio actual:

`dotnet test` 

Ejecute las pruebas en el proyecto `test1`:

`dotnet test ~/projects/test1/test1.csproj` 

## <a name="see-also"></a>Vea también

* [Marcos de trabajo de destino](../../standard/frameworks.md)
* [Catálogo de identificadores de tiempo de ejecución (RID)](../rid-catalog.md)
