---
title: 'Comando dotnet test: CLI de .NET Core'
description: El comando “dotnet test” se usa para ejecutar pruebas unitarias en un proyecto determinado.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 04af96bb53cc4fdac2e52311f9197eb1ee2b112d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-test"></a>dotnet test

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nombre

`dotnet test`: controlador de prueba de .NET usado para ejecutar pruebas unitarias.

## <a name="synopsis"></a>Sinopsis

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)


```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```
---

## <a name="description"></a>Description

El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado. El comando `dotnet test` inicia la aplicación de la consola de ejecutor de pruebas especificada para un proyecto. El ejecutor de pruebas ejecuta las pruebas que se definen para un marco de pruebas unitarias (por ejemplo, MSTest, NUnit o xUnit) y notifica el éxito o fracaso de cada prueba. El ejecutor de pruebas y la biblioteca de pruebas unitarias se empaquetan como paquetes de NuGet y se restauran como dependencias ordinarias para el proyecto.

Los proyectos de prueba especifican el ejecutor de pruebas usando un elemento `<PackageReference>` ordinario, como se puede ver en este archivo de proyecto de ejemplo:

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a>Argumentos

`PROJECT`

Especifica una ruta de acceso al proyecto de prueba. Si se omite, se toma como predeterminado el directorio actual.

## <a name="options"></a>Opciones

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.

`-c|--configuration {Debug|Release}`

Define la configuración de compilación. El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

Habilita el recopilador de datos para la ejecución de pruebas. Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.

`-f|--framework <FRAMEWORK>`

Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.

`--filter <EXPRESSION>`

Filtra las pruebas del proyecto actual con la expresión dada. Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details). Para información adicional y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Running selective unit tests](../testing/selective-unit-tests.md) (Ejecución de pruebas unitarias selectivas).

`-h|--help`

Imprime una corta ayuda para el comando.

`-l|--logger <LoggerUri/FriendlyName>`

Especifica un registrador para los resultados de pruebas.

`--no-build`

No compila el proyecto de prueba antes de ejecutarlo.

`--no-restore`

No realiza una restauración implícita al ejecutar el comando.

`-o|--output <OUTPUT_DIRECTORY>`

Directorio donde se encuentran los archivos binarios que se ejecutarán.

`-r|--results-directory <PATH>`

El directorio donde se guardarán los resultados de pruebas. Si no existe, se creará el directorio especificado.

`-s|--settings <SETTINGS_FILE>`

Configuración que se usará al ejecutar las pruebas.

`-t|--list-tests`

Enumera todas las pruebas detectadas en el proyecto actual.

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.

`-c|--configuration {Debug|Release}`

Define la configuración de compilación. El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.

`-f|--framework <FRAMEWORK>`

Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.

`--filter <EXPRESSION>`

Filtra las pruebas del proyecto actual con la expresión dada. Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details). Para información adicional y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Running selective unit tests](../testing/selective-unit-tests.md) (Ejecución de pruebas unitarias selectivas).

`-h|--help`

Imprime una corta ayuda para el comando.

`-l|--logger <LoggerUri/FriendlyName>`

Especifica un registrador para los resultados de pruebas.

`--no-build`

No compila el proyecto de prueba antes de ejecutarlo.

`-o|--output <OUTPUT_DIRECTORY>`

Directorio donde se encuentran los archivos binarios que se ejecutarán.

`-s|--settings <SETTINGS_FILE>`

Configuración que se usará al ejecutar las pruebas.

`-t|--list-tests`

Enumera todas las pruebas detectadas en el proyecto actual.

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

---

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
| MSTest         | <ul><li>FullyQualifiedName</li><li>nombre</li><li>ClassName</li><li>Prioridad</li><li>TestCategory</li></ul> |
| Xunit          | <ul><li>FullyQualifiedName</li><li>DisplayName</li><li>Rasgos</li></ul>                                   |

`<operator>` describe la relación entre la propiedad y el valor:

| Operador | Función        |
| :------: | --------------- |
| `=`      | Coincidencia exacta     |
| `!=`     | Coincidencia no exacta |
| `~`      | Contiene        |

`<value>` es una cadena. Todas las búsquedas distinguen mayúsculas de minúsculas.

Una expresión sin `<operator>` automáticamente se considera un `contains` en la propiedad `FullyQualifiedName` (por ejemplo, `dotnet test --filter xyz` es lo mismo que `dotnet test --filter FullyQualifiedName~xyz`).

Las expresiones se pueden combinar con operadores condicionales:

| Operador | Función |
| :------: | :------: |
| <code>&#124;</code>      | O       |
| `&`      | AND      |

Si usa operadores condicionales (por ejemplo, `(Name~TestMethod1) | (Name~TestMethod2)`), puede incluir las expresiones entre paréntesis.

Para información adicional y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Running selective unit tests](../testing/selective-unit-tests.md) (Ejecución de pruebas unitarias selectivas).

## <a name="see-also"></a>Vea también

 [Marcos y destinos](../../standard/frameworks.md)  
 [Catálogo de identificadores de entorno de ejecución (RID) de .NET Core](../rid-catalog.md)
