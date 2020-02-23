---
title: Comando dotnet test
description: El comando “dotnet test” se usa para ejecutar pruebas unitarias en un proyecto determinado.
ms.date: 05/29/2018
ms.openlocfilehash: 909815151265117395c6d8d13b4443a245c05f9e
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451199"
---
# <a name="dotnet-test"></a>dotnet test

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>NOMBRE

`dotnet test`: controlador de prueba de .NET usado para ejecutar pruebas unitarias.

## <a name="synopsis"></a>Sinopsis

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

```dotnetcli
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] 
    [-v|--verbosity] [-- <RunSettings arguments>]

dotnet test [-h|--help]
```

# <a name="net-core-20"></a>[.NET Core 2.0](#tab/netcore20)

```dotnetcli
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]

dotnet test [-h|--help]
```

# <a name="net-core-1x"></a>[.NET Core 1.x](#tab/netcore1x)

```dotnetcli
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]

dotnet test [-h|--help]
```

---

## <a name="description"></a>Descripción

El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado. El comando `dotnet test` inicia la aplicación de la consola de ejecutor de pruebas especificada para un proyecto. El ejecutor de pruebas ejecuta las pruebas que se definen para un marco de pruebas unitarias (por ejemplo, MSTest, NUnit o xUnit) y notifica el éxito o fracaso de cada prueba. Si todas las pruebas son correctas, el ejecutor de pruebas devuelve 0 como un código de salida; en caso contrario, si se produce algún error en una prueba, devuelve 1. El ejecutor de pruebas y la biblioteca de pruebas unitarias se empaquetan como paquetes de NuGet y se restauran como dependencias ordinarias para el proyecto.

Los proyectos de prueba especifican el ejecutor de pruebas usando un elemento `<PackageReference>` ordinario, como se puede ver en este archivo de proyecto de ejemplo:

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a>Argumentos

`PROJECT`

Ruta de acceso al proyecto de prueba. Si no se especifica, se toma como predeterminado el directorio actual.

## <a name="options"></a>Opciones

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.

`--blame`

Ejecuta las pruebas en el modo de culpabilidad. Esta opción es útil para aislar las pruebas problemáticas que hacen que el host de prueba se bloquee. Crea un archivo de salida en el directorio actual como *Sequence.xml* que captura el orden de ejecución de pruebas antes del bloqueo.

`-c|--configuration {Debug|Release}`

Define la configuración de compilación. El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

Habilita el recopilador de datos para la ejecución de pruebas. Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.

`-f|--framework <FRAMEWORK>`

Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.

`--filter <EXPRESSION>`

Filtra las pruebas del proyecto actual con la expresión dada. Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details). Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).

`-h|--help`

Imprime una corta ayuda para el comando.

`-l|--logger <LoggerUri/FriendlyName>`

Especifica un registrador para los resultados de pruebas.

`--no-build`

No compila el proyecto de prueba antes de ejecutarlo. También establece la marca `--no-restore` de forma implícita.

`--no-restore`

No ejecuta una restauración implícita al ejecutar el comando.

`-o|--output <OUTPUT_DIRECTORY>`

Directorio donde se encuentran los archivos binarios que se ejecutarán.

`-r|--results-directory <PATH>`

El directorio donde se guardarán los resultados de pruebas. Si el directorio especificado no existe, se crea.

`-s|--settings <SETTINGS_FILE>`

El archivo `.runsettings` que se usará para ejecutar las pruebas. [Configuración de pruebas unitarias con un archivo `.runsettings`.](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

`-t|--list-tests`

Enumera todas las pruebas detectadas en el proyecto actual.

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

`RunSettings arguments`

Argumentos pasados como configuraciones de RunSettings para la prueba. Los argumentos se especifican como `[name]=[value]` pares después de "-- " (tenga en cuenta el espacio después de --). Se usa un espacio para separar varios pares de `[name]=[value]`.

Ejemplo: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`

Para obtener más información sobre RunSettings, vea [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md) (vstest.console.exe: paso de argumentos RunSettings).

# <a name="net-core-20"></a>[.NET Core 2.0](#tab/netcore20)

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

Filtra las pruebas del proyecto actual con la expresión dada. Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details). Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).

`-h|--help`

Imprime una corta ayuda para el comando.

`-l|--logger <LoggerUri/FriendlyName>`

Especifica un registrador para los resultados de pruebas.

`--no-build`

No compila el proyecto de prueba antes de ejecutarlo. También establece la marca `--no-restore` de forma implícita.

`--no-restore`

No ejecuta una restauración implícita al ejecutar el comando.

`-o|--output <OUTPUT_DIRECTORY>`

Directorio donde se encuentran los archivos binarios que se ejecutarán.

`-r|--results-directory <PATH>`

El directorio donde se guardarán los resultados de pruebas. Si el directorio especificado no existe, se crea.

`-s|--settings <SETTINGS_FILE>`

El archivo `.runsettings` que se usará para ejecutar las pruebas. [Configuración de pruebas unitarias con un archivo `.runsettings`.](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

`-t|--list-tests`

Enumera todas las pruebas detectadas en el proyecto actual.

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

# <a name="net-core-1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.

`-c|--configuration {Debug|Release}`

Define la configuración de compilación. El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.

`-f|--framework <FRAMEWORK>`

Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.

`--filter <EXPRESSION>`

Filtra las pruebas del proyecto actual con la expresión dada. Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details). Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).

`-h|--help`

Imprime una corta ayuda para el comando.

`-l|--logger <LoggerUri/FriendlyName>`

Especifica un registrador para los resultados de pruebas.

`--no-build`

No compila el proyecto de prueba antes de ejecutarlo.

`-o|--output <OUTPUT_DIRECTORY>`

Directorio donde se encuentran los archivos binarios que se ejecutarán.

`-s|--settings <SETTINGS_FILE>`

El archivo `.runsettings` que se usará para ejecutar las pruebas. [Configuración de pruebas unitarias con un archivo `.runsettings`.](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

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

Ejecute las pruebas en el proyecto en el directorio actual y genere un archivo de resultados de prueba en formato trx:

`dotnet test --logger trx`

## <a name="filter-option-details"></a>Detalles de la opción de filtro

`--filter <EXPRESSION>`

`<Expression>` tiene el formato `<property><operator><value>[|&<Expression>]`.

`<property>` es un atributo del tipo `Test Case`. Las siguientes son las propiedades admitidas por los marcos de pruebas unitarias populares:

| Marco de prueba | Propiedades admitidas                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| MSTest         | <ul><li>FullyQualifiedName</li><li>NOMBRE</li><li>ClassName</li><li>Prioridad</li><li>TestCategory</li></ul> |
| xUnit          | <ul><li>FullyQualifiedName</li><li>DisplayName</li><li>Rasgos</li></ul>                                   |

`<operator>` describe la relación entre la propiedad y el valor:

| Operador | Función        |
| :------: | --------------- |
| `=`      | Coincidencia exacta     |
| `!=`     | Coincidencia no exacta |
| `~`      | Contiene        |
| `!~`     | No contiene    |

`<value>` es una cadena. Todas las búsquedas distinguen mayúsculas de minúsculas.

Una expresión sin `<operator>` automáticamente se considera un `contains` en la propiedad `FullyQualifiedName` (por ejemplo, `dotnet test --filter xyz` es lo mismo que `dotnet test --filter FullyQualifiedName~xyz`).

Las expresiones se pueden combinar con operadores condicionales:

| Operador            | Función |
| ------------------- | -------- |
| <code>&#124;</code> | O       |
| `&`                 | AND      |

Si usa operadores condicionales (por ejemplo, `(Name~TestMethod1) | (Name~TestMethod2)`), puede incluir las expresiones entre paréntesis.

Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).

## <a name="see-also"></a>Vea también

- [Marcos y destinos](../../standard/frameworks.md)
- [Catálogo de identificadores de entorno de ejecución (RID) de .NET Core](../rid-catalog.md)
