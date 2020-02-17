---
title: Comando dotnet vstest
description: El comando dotnet vstest compila un proyecto y todas sus dependencias.
ms.date: 05/30/2018
ms.openlocfilehash: c3838617ed539cf56f2840b826e9de58833820fd
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215309"
---
# <a name="dotnet-vstest"></a>dotnet vstest

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>NOMBRE

`dotnet-vstest`: ejecuta pruebas desde los archivos especificados.

## <a name="synopsis"></a>Sinopsis

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath]
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger]
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [--Blame|/Blame] [--InIsolation|/InIsolation]
    [[--] <args>...]] [-?|--Help|/?|/Help]
```

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath] 
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger]
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath]
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger] 
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]
```

---

## <a name="description"></a>Descripción

El comando `dotnet-vstest` ejecuta la aplicación de línea de comandos `VSTest.Console` para ejecutar pruebas unitarias automatizadas.

## <a name="arguments"></a>Argumentos

`TEST_FILE_NAMES`

Ejecutar pruebas desde los ensamblados especificados. Separar varios nombres de ensamblado de prueba con espacios.

## <a name="options"></a>Opciones

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`--Settings|/Settings:<Settings File>`

Configuración que se usará al ejecutar las pruebas.

`--Tests|/Tests:<Test Names>`

Ejecuta las pruebas con nombres que coinciden con los Separar varios valores con comas.

`--TestAdapterPath|/TestAdapterPath`

Usar adaptadores de prueba personalizados desde una ruta de acceso especificada (si existe) en la serie de pruebas.

`--Platform|/Platform:<Platform type>`

Identificar la arquitectura de la plataforma usada en la ejecución de pruebas. Valores válidos son `x86`, `x64` y `ARM`.

`--Framework|/Framework:<Framework Version>`

Identificar la versión de .NET Framework usada en la ejecución de pruebas. Ejemplos de valores válidos son `.NETFramework,Version=v4.6` o `.NETCoreApp,Version=v1.0`. Otros valores admitidos son `Framework40`, `Framework45`, `FrameworkCore10` y `FrameworkUap10`.

`--Parallel|/Parallel`

Ejecutar pruebas en paralelo. De forma predeterminada, todos los núcleos disponibles en el equipo están disponibles para su uso. Especifique un número explícito de núcleos mediante la configuración de la propiedad MaxCpuCount en el nodo RunConfiguration del archivo runsettings.

`--TestCaseFilter|/TestCaseFilter:<Expression>`

Ejecuta pruebas que coinciden con la expresión dada. `<Expression>` tiene el formato `<property>Operator<value>[|&<Expression>]`, donde Operator es `=`, `!=` o `~`. El operador `~` tiene semántica "contains" y se aplica a las propiedades de cadena como `DisplayName`. Los paréntesis `()` se usan para agrupar expresiones secundarias.

`-?|--Help|/?|/Help`

Imprime una corta ayuda para el comando.

`--logger|/logger:<Logger Uri/FriendlyName>`

Especifica un registrador para resultados de pruebas.

* Para publicar resultados de pruebas en Team Foundation Server, use el proveedor de registrador `TfsPublisher`:

  ```console
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* Para registrar los resultados en un archivo de resultados de pruebas (TRX) de Visual Studio, use el proveedor de registrador `trx`. Este modificador, crea un archivo en el directorio de resultados de pruebas con un nombre de archivo de registro dado. Si no se proporciona `LogFileName`, se crea un nombre de archivo único para contener los resultados de las pruebas.

  ```console
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

Muestra todas las pruebas detectadas del contenedor de pruebas especificado.

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

Id. de proceso del proceso principal responsable de iniciar el proceso actual.

`--Port|/Port:<Port>`

Especifica el puerto para la conexión de socket y la recepción de mensajes de eventos.

`--Diag|/Diag:<Path to log file>`

Permite registros detallados para la plataforma de prueba. Los registros se escriben en el archivo proporcionado.

`--Blame|/Blame`

Ejecuta las pruebas en el modo de culpabilidad. Esta opción es útil para aislar las pruebas problemáticas que hacen que el host de prueba se bloquee. Crea un archivo de salida en el directorio actual como *Sequence.xml* que captura el orden de ejecución de pruebas antes del bloqueo.

`--InIsolation|/InIsolation`

Ejecuta las pruebas en un proceso aislado. De este modo, es menos probable que el proceso *vstest.console.exe* se detenga por un error de las pruebas, pero es posible que las pruebas se ejecuten más despacio.

`@<file>`

Lee el archivo de respuesta para ver más opciones.

`args`

Especifica argumentos adicionales para pasar al adaptador. Los argumentos se especifican como pares de nombre-valor en el formato `<n>=<v>`, donde `<n>` es el nombre del argumento y `<v>` es el valor del argumento. Use un espacio para separar varios argumentos.

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`--Settings|/Settings:<Settings File>`

Configuración que se usará al ejecutar las pruebas.

`--Tests|/Tests:<Test Names>`

Ejecuta las pruebas con nombres que coinciden con los Separar varios valores con comas.

`--TestAdapterPath|/TestAdapterPath`

Usar adaptadores de prueba personalizados desde una ruta de acceso especificada (si existe) en la serie de pruebas.

`--Platform|/Platform:<Platform type>`

Identificar la arquitectura de la plataforma usada en la ejecución de pruebas. Valores válidos son `x86`, `x64` y `ARM`.

`--Framework|/Framework:<Framework Version>`

Identificar la versión de .NET Framework usada en la ejecución de pruebas. Ejemplos de valores válidos son `.NETFramework,Version=v4.6` o `.NETCoreApp,Version=v1.0`. Otros valores admitidos son `Framework40`, `Framework45` y `FrameworkCore10`.

`--Parallel|/Parallel`

Ejecutar pruebas en paralelo. De forma predeterminada, todos los núcleos disponibles en el equipo están disponibles para su uso. Especifique un número explícito de núcleos mediante la configuración de la propiedad MaxCpuCount en el nodo RunConfiguration del archivo runsettings.

`--TestCaseFilter|/TestCaseFilter:<Expression>`

Ejecuta pruebas que coinciden con la expresión dada. `<Expression>` tiene el formato `<property>Operator<value>[|&<Expression>]`, donde Operator es `=`, `!=` o `~`. El operador `~` tiene semántica "contains" y se aplica a las propiedades de cadena como `DisplayName`. Los paréntesis `()` se usan para agrupar expresiones secundarias.

`-?|--Help|/?|/Help`

Imprime una corta ayuda para el comando.

`--logger|/logger:<Logger Uri/FriendlyName>`

Especifica un registrador para resultados de pruebas.

* Para publicar resultados de pruebas en Team Foundation Server, use el proveedor de registrador `TfsPublisher`:

  ```console
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* Para registrar los resultados en un archivo de resultados de pruebas (TRX) de Visual Studio, use el proveedor de registrador `trx`. Este modificador, crea un archivo en el directorio de resultados de pruebas con un nombre de archivo de registro dado. Si no se proporciona `LogFileName`, se crea un nombre de archivo único para contener los resultados de las pruebas.

  ```console
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

Muestra todas las pruebas detectadas del contenedor de pruebas especificado.

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

Id. de proceso del proceso principal responsable de iniciar el proceso actual.

`--Port|/Port:<Port>`

Especifica el puerto para la conexión de socket y la recepción de mensajes de eventos.

`--Diag|/Diag:<Path to log file>`

Permite registros detallados para la plataforma de prueba. Los registros se escriben en el archivo proporcionado.

`args`

Especifica argumentos adicionales para pasar al adaptador. Los argumentos se especifican como pares de nombre-valor en el formato `<n>=<v>`, donde `<n>` es el nombre del argumento y `<v>` es el valor del argumento. Use un espacio para separar varios argumentos.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`--Settings|/Settings:<Settings File>`

Configuración que se usará al ejecutar las pruebas.

`--Tests|/Tests:<Test Names>`

Ejecuta las pruebas con nombres que coinciden con los Separar varios valores con comas.

`--TestAdapterPath|/TestAdapterPath`

Usar adaptadores de prueba personalizados desde una ruta de acceso especificada (si existe) en la serie de pruebas.

`--Platform|/Platform:<Platform type>`

Identificar la arquitectura de la plataforma usada en la ejecución de pruebas. Valores válidos son `x86`, `x64` y `ARM`.

`--Framework|/Framework:<Framework Version>`

Identificar la versión de .NET Framework usada en la ejecución de pruebas. Ejemplos de valores válidos son `.NETFramework,Version=v4.6` o `.NETCoreApp,Version=v1.0`. Otros valores admitidos son `Framework40`, `Framework45` y `FrameworkCore10`.

`--Parallel|/Parallel`

Ejecutar pruebas en paralelo. De forma predeterminada, todos los núcleos disponibles en el equipo están disponibles para su uso. Especifique un número explícito de núcleos mediante la configuración de la propiedad MaxCpuCount en el nodo RunConfiguration del archivo runsettings.

`--TestCaseFilter|/TestCaseFilter:<Expression>`

Ejecuta pruebas que coinciden con la expresión dada. `<Expression>` tiene el formato `<property>Operator<value>[|&<Expression>]`, donde Operator es `=`, `!=` o `~`. El operador `~` tiene semántica "contains" y se aplica a las propiedades de cadena como `DisplayName`. Los paréntesis `()` se usan para agrupar expresiones secundarias.

`-?|--Help|/?|/Help`

Imprime una corta ayuda para el comando.

`--logger|/logger:<Logger Uri/FriendlyName>`

Especifica un registrador para resultados de pruebas.

* Para publicar resultados de pruebas en Team Foundation Server, use el proveedor de registrador `TfsPublisher`:

  ```console
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* Para registrar los resultados en un archivo de resultados de pruebas (TRX) de Visual Studio, use el proveedor de registrador `trx`. Este modificador, crea un archivo en el directorio de resultados de pruebas con un nombre de archivo de registro dado. Si no se proporciona `LogFileName`, se crea un nombre de archivo único para contener los resultados de las pruebas.

  ```console
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

Muestra todas las pruebas detectadas del contenedor de pruebas especificado.

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

Id. de proceso del proceso principal responsable de iniciar el proceso actual.

`--Port|/Port:<Port>`

Especifica el puerto para la conexión de socket y la recepción de mensajes de eventos.

`--Diag|/Diag:<Path to log file>`

Permite registros detallados para la plataforma de prueba. Los registros se escriben en el archivo proporcionado.

`args`

Especifica argumentos adicionales para pasar al adaptador. Los argumentos se especifican como pares de nombre-valor en el formato `<n>=<v>`, donde `<n>` es el nombre del argumento y `<v>` es el valor del argumento. Use un espacio para separar varios argumentos.

---

## <a name="examples"></a>Ejemplos

Ejecutar pruebas en `mytestproject.dll`:

`dotnet vstest mytestproject.dll`

Ejecutar pruebas en `mytestproject.dll`, exportando a carpeta personalizada con nombre personalizado:

`dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path`

Ejecutar pruebas en `mytestproject.dll` y `myothertestproject.exe`:

`dotnet vstest mytestproject.dll myothertestproject.exe`

Ejecutar pruebas `TestMethod1`:

`dotnet vstest /Tests:TestMethod1`

Ejecutar pruebas `TestMethod1` y `TestMethod2`:

`dotnet vstest /Tests:TestMethod1,TestMethod2`
