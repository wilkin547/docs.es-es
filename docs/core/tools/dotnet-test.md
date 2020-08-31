---
title: Comando dotnet test
description: El comando “dotnet test” se usa para ejecutar pruebas unitarias en un proyecto determinado.
ms.date: 04/29/2020
ms.openlocfilehash: d67521084330b206afca89baf59228b99ca799a1
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656760"
---
# <a name="dotnet-test"></a>dotnet test

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet test`: controlador de prueba de .NET usado para ejecutar pruebas unitarias.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION> | <DIRECTORY> | <DLL>]
    [-a|--test-adapter-path <ADAPTER_PATH>] [--blame] [--blame-crash]
    [--blame-crash-dump-type <DUMP_TYPE>] [--blame-crash-collect-always]
    [--blame-hang] [--blame-hang-dump-type <DUMP_TYPE>]
    [--blame-hang-timeout <TIMESPAN>]
    [-c|--configuration <CONFIGURATION>]
    [--collect <DATA_COLLECTOR_NAME>]
    [-d|--diag <LOG_FILE>] [-f|--framework <FRAMEWORK>]
    [--filter <EXPRESSION>] [--interactive]
    [-l|--logger <LOGGER>] [--no-build]
    [--nologo] [--no-restore] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--results-directory <RESULTS_DIR>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--settings <SETTINGS_FILE>] [-t|--list-tests]
    [-v|--verbosity <LEVEL>] [[--] <RunSettings arguments>]

dotnet test -h|--help
```

## <a name="description"></a>Descripción

El comando `dotnet test` se usa para ejecutar pruebas unitarias en una solución determinada. El comando `dotnet test` compila la solución y ejecuta una aplicación host de prueba para cada proyecto de prueba de la solución. El host de prueba ejecuta las pruebas en el proyecto especificado mediante un marco de pruebas (por ejemplo, MSTest, NUnit o xUnit) e informa del éxito o el error de cada prueba. Si todas las pruebas son correctas, el ejecutor de pruebas devuelve 0 como un código de salida; en caso contrario, si se produce algún error en una prueba, devuelve 1.

En el caso de los proyectos con varios destinos, las pruebas se ejecutan para cada plataforma de destino. El host de pruebas y el marco de pruebas unitarias se empaquetan como paquetes NuGet y se restauran como dependencias ordinarias para el proyecto.

Los proyectos de prueba especifican el ejecutor de pruebas usando un elemento `<PackageReference>` ordinario, como se puede ver en este archivo de proyecto de ejemplo:

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

Donde `Microsoft.NET.Test.Sdk` es el host de prueba y `xunit` es el marco de pruebas. Y `xunit.runner.visualstudio` es un adaptador de prueba, que permite que el marco xUnit funcione con el host de prueba.

### <a name="implicit-restore"></a>Restauración implícita

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a>Argumentos

- **`PROJECT | SOLUTION | DIRECTORY | DLL`**

  - Ruta de acceso al proyecto de prueba.
  - Ruta de acceso a la solución.
  - Ruta de acceso a un directorio que contiene un proyecto o una solución.
  - Ruta de acceso a un archivo *.dll* del proyecto de prueba.

  Si no se especifica, se busca un proyecto o una solución en el directorio actual.

## <a name="options"></a>Opciones

- **`-a|--test-adapter-path <ADAPTER_PATH>`**

  Ruta de acceso a un directorio en el que se van hacer búsquedas de adaptadores de prueba adicionales. Solo se inspeccionan los archivos *.dll* con el sufijo `.TestAdapter.dll`. Si no se especifica, la búsqueda se realiza en el directorio del archivo *.dll* de la prueba.

- **`--blame`**

  Ejecuta las pruebas en el modo de culpabilidad. Esta opción es útil para aislar las pruebas problemáticas que hacen que el host de prueba se bloquee. Cuando se detecta un bloqueo, crea un archivo de secuencia en `TestResults/<Guid>/<Guid>_Sequence.xml` que captura el orden de las pruebas ejecutadas antes del bloqueo.

- **`--blame-crash`** (Disponible desde el SDK de versión preliminar de .NET 5.0)

  Ejecuta las pruebas en modo de culpa y recopila un volcado de memoria cuando el host de prueba se cierra de forma inesperada. Esta opción solo se admite en Windows. Un directorio que contenga *procdump.exe* y *procdump64.exe* debe estar en la variable de entorno PATH o PROCDUMP_PATH. [Descargue las herramientas](https://docs.microsoft.com/sysinternals/downloads/procdump). Implica `--blame`.

- **`--blame-crash-dump-type <DUMP_TYPE>`** (Disponible desde el SDK de versión preliminar de .NET 5.0)

  El tipo de volcado de memoria que se va a recopilar. Implica `--blame-crash`.

- **`--blame-crash-collect-always`** (Disponible desde el SDK de versión preliminar de .NET 5.0)

  Recopila un volcado de memoria en la salida de host de prueba esperada e inesperada.

- **`--blame-hang`** (Disponible desde el SDK de versión preliminar de .NET 5.0)

  Ejecute las pruebas en modo de culpa y recopile un volcado de bloqueo cuando una prueba supere el tiempo de espera especificado.

- **`--blame-hang-dump-type <DUMP_TYPE>`** (Disponible desde el SDK de versión preliminar de .NET 5.0)

  El tipo de volcado de memoria que se va a recopilar. Debe ser `full`, `mini` o `none`. Cuando se especifica `none`, el host de prueba finaliza en el tiempo de espera, pero no se recopila ningún volcado. Implica `--blame-hang`.

- **`--blame-hang-timeout <TIMESPAN>`** (Disponible desde el SDK de versión preliminar de .NET 5.0)

  Tiempo de espera por prueba, después del cual se desencadena un volcado de bloqueo y finaliza el proceso de host de prueba. El valor de tiempo de espera se especifica en uno de los siguientes formatos:
  
  - 1,5 h
  - 90 m
  - 5400 s
  - 5 400 000 ms

  Cuando no se usa ninguna unidad (por ejemplo, 5 400 000), se supone que el valor está en milisegundos. Cuando se usa junto con las pruebas basadas en datos, el comportamiento de tiempo de espera depende del adaptador de prueba usado. En xUnit y NUnit, el tiempo de espera se renueva después de cada caso de prueba. En MSTest, el tiempo de espera se usa en todos los casos de prueba. Esta opción se admite en Windows con netcoreapp2.1 y versiones posteriores, y en Linux con netcoreapp3.1 y versiones posteriores. macOS no se admite.

- **`-c|--configuration <CONFIGURATION>`**

  Define la configuración de compilación. El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.

- **`--collect <DATA_COLLECTOR_NAME>`**

  Habilita el recopilador de datos para la ejecución de pruebas. Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).
  
  Para recopilar la cobertura de código en cualquier plataforma compatible con .NET Core, instale [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/README.md) y use la opción `--collect:"XPlat Code Coverage"`.

  En Windows, puede recopilar la cobertura de código mediante la opción `--collect "Code Coverage"`. Esta opción genera un archivo *.coverage*, que se puede abrir en Visual Studio 2019 Enterprise. Para más información, vea [Uso de cobertura de código](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested) y [Personalización del análisis de cobertura de código](/visualstudio/test/customizing-code-coverage-analysis).

- **`-d|--diag <LOG_FILE>`**

  Habilita el modo de diagnóstico de la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado y en los archivos que hay junto a él. El proceso que registra los mensajes determina qué archivos se crean, como `*.host_<date>.txt` para el registro del host de prueba y `*.datacollector_<date>.txt` para el registro del recopilador de datos.

- **`-f|--framework <FRAMEWORK>`**

  Fuerza el uso del host de prueba de `dotnet` o .NET Framework para los archivos binarios de prueba. Esta opción solo determina el tipo de host que se va a usar. La versión de Framework real que se va a usar viene determinada por *runtimeConfig.json* del proyecto de prueba. Si no se especifica, se usa el [atributo de ensamblado TargetFramework](/dotnet/api/system.runtime.versioning.targetframeworkattribute) para determinar el tipo de host. Si ese atributo se quita de *.dll*, se usa el host de .NET Framework.

- **`--filter <EXPRESSION>`**

  Filtra las pruebas del proyecto actual con la expresión dada. Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details). Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

- **`--interactive`**

  Permite que el comando se detenga y espere una entrada o una acción del usuario. Por ejemplo, para completar la autenticación. Disponible desde el SDK de .NET Core 3.0.

- **`-l|--logger <LOGGER>`**

  Especifica un registrador para los resultados de pruebas. A diferencia de MSBuild, la prueba de dotnet no acepta abreviaturas: en lugar de `-l "console;v=d"` use `-l "console;verbosity=detailed"`.

- **`--no-build`**

  No compila el proyecto de prueba antes de ejecutarlo. También establece la marca - `--no-restore` de forma implícita.

- **`--nologo`**

  Ejecuta pruebas sin mostrar la pancarta de Microsoft TestPlatform. Disponible desde el SDK de .NET Core 3.0.

- **`--no-restore`**

  No ejecuta una restauración implícita al ejecutar el comando.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Directorio donde se encuentran los archivos binarios que se ejecutarán. Si no se especifica la ruta de acceso predeterminada es `./bin/<configuration>/<framework>/`.  En el caso de los proyectos con varias plataformas de destino (a través de la propiedad `TargetFrameworks`), también debe definir `--framework` al especificar esta opción. `dotnet test` siempre ejecuta las pruebas desde el directorio de salida. Puede usar <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> para consumir recursos de prueba en el directorio de salida.

- **`-r|--results-directory <RESULTS_DIR>`**

  El directorio donde se guardarán los resultados de pruebas. Si el directorio especificado no existe, se crea. El valor predeterminado es `TestResults` en el directorio que contiene el archivo del proyecto.

- **`--runtime <RUNTIME_IDENTIFIER>`**

  Runtime de destino que probar.

- **`-s|--settings <SETTINGS_FILE>`**

  El archivo `.runsettings` que se usará para ejecutar las pruebas. El elemento `TargetPlatform` (x86|x64) no tiene ningún efecto en `dotnet test`. Para ejecutar pruebas destinadas a x86, instale la versión x86 de .NET Core. El valor de bits de *dotnet.exe* que se encuentra en la ruta de acceso es lo que se usará para ejecutar las pruebas. Para obtener más información, vea los siguientes recursos:

  - [Configuración de pruebas unitarias con un archivo `.runsettings`.](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [Configuración de una serie de pruebas](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  Enumera las pruebas detectadas en vez de ejecutar las pruebas.

- **`-v|--verbosity <LEVEL>`**

  Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`. De manera predeterminada, es `minimal`. Para obtener más información, vea <xref:Microsoft.Build.Framework.LoggerVerbosity>.

- Argumentos de **`RunSettings`**

 Los argumentos `RunSettings` insertados se pasan como los últimos argumentos en la línea de comandos después de "-- " (fíjese en el espacio después de --). Los argumentos `RunSettings` insertados se especifican como pares de `[name]=[value]`. Se usa un espacio para separar varios pares de `[name]=[value]`.

  Ejemplo: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`

  Para obtener más información, vea [Paso de argumentos de RunSettings a través de la línea de comandos](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).

## <a name="examples"></a>Ejemplos

- Ejecución de las pruebas en el proyecto en el directorio actual:

  ```dotnetcli
  dotnet test
  ```

- Ejecute las pruebas en el proyecto `test1`:

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- Ejecute las pruebas del proyecto en el directorio actual y genere un archivo de resultados de prueba en formato trx:

  ```dotnetcli
  dotnet test --logger trx
  ```

- Ejecute las pruebas del proyecto en el directorio actual y genere un archivo de cobertura de código (después de instalar la integración de recopiladores de [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/Documentation/VSTestIntegration.md)):

  ```dotnetcli
  dotnet test --collect:"XPlat Code Coverage"
  ```

- Ejecute las pruebas en el proyecto en el directorio actual y genere un archivo de cobertura de código (solo en Windows):

  ```dotnetcli
  dotnet test --collect "Code Coverage"
  ```

- Ejecute las pruebas del proyecto en el directorio actual y regístrese con el nivel de detalle pormenorizado en la consola:

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

- Ejecute las pruebas del proyecto en el directorio actual e informe de las pruebas que estaban en curso cuando se bloqueó el host de prueba:

  ```dotnetcli
  dotnet test --blame
  ```

## <a name="filter-option-details"></a>Detalles de la opción de filtro

`--filter <EXPRESSION>`

`<Expression>` tiene el formato `<property><operator><value>[|&<Expression>]`.

`<property>` es un atributo del tipo `Test Case`. Las siguientes son las propiedades admitidas por los marcos de pruebas unitarias populares:

| Marco de prueba | Propiedades admitidas                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| MSTest         | <ul><li>FullyQualifiedName</li><li>NOMBRE</li><li>ClassName</li><li>Prioridad</li><li>TestCategory</li></ul> |
| xUnit          | <ul><li>FullyQualifiedName</li><li>DisplayName</li><li>Rasgos</li></ul>                                   |
| NUnit          | <ul><li>FullyQualifiedName</li><li>NOMBRE</li><li>TestCategory</li><li>Prioridad</li></ul>                                   |

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
- [Paso de argumentos runsettings a través de la línea de comandos](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
