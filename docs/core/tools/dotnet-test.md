---
title: 'Comando dotnet-test: CLI de .NET Core | Microsoft Docs'
description: El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado.
keywords: dotnet-test, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/25/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 4bf0aef4-148a-41c6-bb95-0a9e1af8762e
ms.translationtype: Human Translation
ms.sourcegitcommit: ae036cfcad341ffc859336a7ab2a49feec145715
ms.openlocfilehash: 734cf337fdd0d33f6c2b6d929b795b2307135550
ms.contentlocale: es-es
ms.lasthandoff: 05/18/2017

---

#<a name="dotnet-test"></a>dotnet-test

## <a name="name"></a>Name

`dotnet-test`: controlador de prueba de .NET usado para ejecutar pruebas unitarias.

## <a name="synopsis"></a>Sinopsis

`dotnet test [<PROJECT>] [-s|--settings] [-t|--list-tests] [--filter] [-a|--test-adapter-path] [-l|--logger] [-c|--configuration] [-f|--framework] [-o|--output] [-d|--diag] [--no-build] [-v|--verbosity] [-h|--help]`

## <a name="description"></a>Descripción

El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado. Las pruebas unitarias son proyectos de aplicación de consola que tienen dependencias en el marco de pruebas unitarias (por ejemplo, MSTest, NUnit o xUnit) y en el ejecutor de pruebas de dotnet de ese marco de pruebas unitarias. Estas se empaquetan como paquetes de NuGet y se restauran como dependencias ordinarias para el proyecto.

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

Filtra las pruebas del proyecto actual con la expresión dada. Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details). Para información adicional y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Running selective unit tests](../testing/selective-unit-tests.md) (Ejecución de pruebas unitarias selectivas).

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

## <a name="filter-option-details"></a>Detalles de la opción de filtro

`--filter <EXPRESSION>`

`<Expression>` tiene el formato `<property><operator><value>[|&<Expression>]`.

`<property>` es un atributo del tipo `Test Case`. Las siguientes son las propiedades admitidas por los marcos de pruebas unitarias populares:

| Marco de prueba | Propiedades admitidas                                                                                      |
| :------------: | --------------------------------------------------------------------------------------------------------- |
| MSTest         | <ul><li>FullyQualifiedName</li><li>Name</li><li>ClassName</li><li>Prioridad</li><li>TestCategory</li></ul> |
| Xunit          | <ul><li>FullyQualifiedName</li><li>DisplayName</li><li>Rasgos</li></ul>                                   |

`<operator>` describe la relación entre la propiedad y el valor:

| "??" | Función        |
| :------: | --------------- |
| `=`      | Coincidencia exacta     |
| `!=`     | Coincidencia no exacta |
| `~`      | Contiene        |

`<value>` es una cadena. Todas las búsquedas distinguen mayúsculas de minúsculas.

Una expresión sin `<operator>` automáticamente se considera un `contains` en la propiedad `FullyQualifiedName` (por ejemplo, `dotnet test --filter xyz` es lo mismo que `dotnet test --filter FullyQualifiedName~xyz`).

Las expresiones se pueden combinar con operadores condicionales:

| "??" | Función |
| :------: | :------: |
| `|`      | O       |
| `&`      | AND      |

Cuando se utilizan operadores condicionales puede encerrar expresiones entre paréntesis (por ejemplo, `(Name~TestMethod1) | (Name~TestMethod2)`).

Para obtener información adicional y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).

## <a name="see-also"></a>Vea también

[Marcos y destinos](../../standard/frameworks.md)   
[Catálogo de identificadores de entorno de ejecución (RID) de .NET Core](../rid-catalog.md)

