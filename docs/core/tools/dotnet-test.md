---
title: Comando dotnet test
description: El comando “dotnet test” se usa para ejecutar pruebas unitarias en un proyecto determinado.
ms.date: 04/29/2020
ms.openlocfilehash: a8218b6596601069b89a60ad018adf89a1f47cf6
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624896"
---
# <a name="dotnet-test"></a>dotnet test

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet test`: controlador de prueba de .NET usado para ejecutar pruebas unitarias.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION>]
    [-a|--test-adapter-path <PATH_TO_ADAPTER>] [--blame]
    [-c|--configuration <CONFIGURATION>]
    [--collect <DATA_COLLECTOR_FRIENDLY_NAME>]
    [-d|--diag <PATH_TO_DIAGNOSTICS_FILE>] [-f|--framework <FRAMEWORK>]
    [--filter <EXPRESSION>] [--interactive]
    [-l|--logger <LOGGER_URI/FRIENDLY_NAME>] [--no-build]
    [--nologo] [--no-restore] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--results-directory <PATH>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--settings <SETTINGS_FILE>] [-t|--list-tests]
    [-v|--verbosity <LEVEL>] [[--] <RunSettings arguments>]

dotnet test -h|--help
```

## <a name="description"></a>Descripción

El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado. El comando `dotnet test` inicia la aplicación de la consola de ejecutor de pruebas especificada para un proyecto. El ejecutor de pruebas ejecuta las pruebas que se definen para un marco de pruebas unitarias (por ejemplo, MSTest, NUnit o xUnit) y notifica el éxito o fracaso de cada prueba. Si todas las pruebas son correctas, el ejecutor de pruebas devuelve 0 como un código de salida; en caso contrario, si se produce algún error en una prueba, devuelve 1. En el caso de los proyectos con varios destinos, las pruebas se ejecutan para cada plataforma de destino. El ejecutor de pruebas y la biblioteca de pruebas unitarias se empaquetan como paquetes de NuGet y se restauran como dependencias ordinarias para el proyecto.

Los proyectos de prueba especifican el ejecutor de pruebas usando un elemento `<PackageReference>` ordinario, como se puede ver en este archivo de proyecto de ejemplo:

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

### <a name="implicit-restore"></a>Restauración implícita

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a>Argumentos

- **`PROJECT | SOLUTION`**

  Ruta de acceso a la solución o proyecto de prueba. Si no se especifica, se toma como predeterminado el directorio actual.

## <a name="options"></a>Opciones

- **`-a|--test-adapter-path <PATH_TO_ADAPTER>`**

  Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas.

- **`--blame`**

  Ejecuta las pruebas en el modo de culpabilidad. Esta opción es útil para aislar las pruebas problemáticas que hacen que el host de prueba se bloquee. Crea un archivo de salida en el directorio actual como *Sequence.xml* que captura el orden de ejecución de pruebas antes del bloqueo.

- **`-c|--configuration <CONFIGURATION>`**

  Define la configuración de compilación. El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración predeterminada del SDK.

- **`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  Habilita el recopilador de datos para la ejecución de pruebas. Para obtener más información, consulte [Monitor and analyze test run](https://aka.ms/vstest-collect) (Supervisar y analizar ejecuciones de pruebas).

- **`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  Habilita el modo de diagnóstico de la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado.

- **`-f|--framework <FRAMEWORK>`**

  Busca archivos binarios de prueba para un [marco](../../standard/frameworks.md) específico.

- **`--filter <EXPRESSION>`**

  Filtra las pruebas del proyecto actual con la expresión dada. Para más información, consulte la sección [Detalles de la opción de filtro](#filter-option-details). Para obtener más información y ejemplos sobre cómo usar el filtrado de pruebas unitarias selectivas, vea [Ejecución de pruebas unitarias selectivas](../testing/selective-unit-tests.md).

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

- **`--interactive`**

  Permite que el comando se detenga y espere una entrada o una acción del usuario. Por ejemplo, para completar la autenticación. Disponible desde el SDK de .NET Core 3.0.

- **`-l|--logger <LOGGER_URI/FRIENDLY_NAME>`**

  Especifica un registrador para los resultados de pruebas. A diferencia de MSBuild, la prueba de dotnet no acepta abreviaturas: en lugar de `-l "console;v=d"` use `-l "console;verbosity=detailed"`.

- **`--no-build`**

  No compila el proyecto de prueba antes de ejecutarlo. También establece la marca - `--no-restore` de forma implícita.

- **`--nologo`**

  Ejecuta pruebas sin mostrar la pancarta de Microsoft TestPlatform. Disponible desde el SDK de .NET Core 3.0.

- **`--no-restore`**

  No ejecuta una restauración implícita al ejecutar el comando.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Directorio donde se encuentran los archivos binarios que se ejecutarán. Si no se especifica la ruta de acceso predeterminada es `./bin/<configuration>/<framework>/`.  En el caso de los proyectos con varias plataformas de destino (a través de la propiedad `TargetFrameworks`), también debe definir `--framework` al especificar esta opción. `dotnet test` siempre ejecuta las pruebas desde el directorio de salida. Puede usar <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> para consumir recursos de prueba en el directorio de salida.

- **`-r|--results-directory <PATH>`**

  El directorio donde se guardarán los resultados de pruebas. Si el directorio especificado no existe, se crea. El valor predeterminado es `TestResults` en el directorio que contiene el archivo del proyecto.

- **`--runtime <RUNTIME_IDENTIFIER>`**

  Runtime de destino que probar.

- **`-s|--settings <SETTINGS_FILE>`**

  El archivo `.runsettings` que se usará para ejecutar las pruebas. Tenga en cuenta que el elemento `TargetPlatform` (x86|x64) no tiene ningún efecto en `dotnet test`. Para ejecutar pruebas destinadas a x86, instale la versión x86 de .NET Core. El valor de bits de *dotnet.exe* que se encuentra en la ruta de acceso es lo que se usará para ejecutar las pruebas. Para obtener más información, vea los siguientes recursos:

  - [Configuración de pruebas unitarias con un archivo `.runsettings`.](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [Configuración de una serie de pruebas](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  Enumera todas las pruebas detectadas en el proyecto actual.

- **`-v|--verbosity <LEVEL>`**

  Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`. De manera predeterminada, es `minimal`. Para obtener más información, vea <xref:Microsoft.Build.Framework.LoggerVerbosity>.

- Argumentos de **`RunSettings`**

  Los argumentos se pasan como configuraciones de `RunSettings` para la prueba. Los argumentos se especifican como `[name]=[value]` pares después de "-- " (tenga en cuenta el espacio después de --). Se usa un espacio para separar varios pares de `[name]=[value]`.

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

- Ejecute las pruebas del proyecto en el directorio actual y regístrese con el nivel de detalle pormenorizado en la consola:

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

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
- [Paso de argumentos runsettings a través de la línea de comandos](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
