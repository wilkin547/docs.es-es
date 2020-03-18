---
title: Comando dotnet vstest
description: El comando dotnet vstest compila un proyecto y todas sus dependencias.
ms.date: 02/27/2020
ms.openlocfilehash: 88e5b6a8966d78d0746f9ea5ccbccab142a2e0f6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156938"
---
# <a name="dotnet-vstest"></a>dotnet vstest

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet-vstest`: ejecuta pruebas desde los archivos especificados.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings] [--Tests]
    [--TestAdapterPath] [--Platform] [--Framework] [--Parallel]
    [--TestCaseFilter] [--logger] [-lt|--ListTests]
    [--ParentProcessId] [--Port] [--Diag] [--Blame]
    [--InIsolation] [[--] <args>...]] [-?|--Help]
```

## <a name="description"></a>Descripción

El comando `dotnet-vstest` ejecuta la aplicación de línea de comandos `VSTest.Console` para ejecutar pruebas unitarias automatizadas.

## <a name="arguments"></a>Argumentos

- **`TEST_FILE_NAMES`**

  Ejecutar pruebas desde los ensamblados especificados. Separar varios nombres de ensamblado de prueba con espacios. Se admite caracteres comodín.

## <a name="options"></a>Opciones

- **`--Settings <Settings File>`**

  Configuración que se usará al ejecutar las pruebas.

- **`--Tests <Test Names>`**

  Ejecuta las pruebas con nombres que coinciden con los Separar varios valores con comas.

- **`--TestAdapterPath`**

  Usar adaptadores de prueba personalizados desde una ruta de acceso especificada (si existe) en la serie de pruebas.

- **`--Platform <Platform type>`**

  Identificar la arquitectura de la plataforma usada en la ejecución de pruebas. Valores válidos son `x86`, `x64` y `ARM`.

- **`--Framework <Framework Version>`**

  Identificar la versión de .NET Framework usada en la ejecución de pruebas. Ejemplos de valores válidos son `.NETFramework,Version=v4.6` o `.NETCoreApp,Version=v1.0`. Otros valores admitidos son `Framework40`, `Framework45`, `FrameworkCore10` y `FrameworkUap10`.

- **`--Parallel`**

  Ejecuta pruebas en paralelo. De forma predeterminada, todos los núcleos disponibles en el equipo están disponibles para su uso. Especifique un número explícito de núcleos mediante la configuración de la propiedad `MaxCpuCount` en el nodo `RunConfiguration` del archivo *runsettings*.

- **`--TestCaseFilter <Expression>`**

  Ejecuta pruebas que coinciden con la expresión dada. `<Expression>` tiene el formato `<property>Operator<value>[|&<Expression>]`, donde Operator es `=`, `!=` o `~`. El operador `~` tiene semántica "contains" y se aplica a las propiedades de cadena como `DisplayName`. Los paréntesis `()` se usan para agrupar subexpresiones.

- **`-?|--Help`**

  Imprime una corta ayuda para el comando.

- **`--logger <Logger Uri/FriendlyName>`**

  Especifica un registrador para resultados de pruebas.

  - Para publicar resultados de pruebas en Team Foundation Server, use el proveedor de registrador `TfsPublisher`:

    ```console
    /logger:TfsPublisher;
        Collection=<team project collection url>;
        BuildName=<build name>;
        TeamProject=<team project name>
        [;Platform=<Defaults to "Any CPU">]
        [;Flavor=<Defaults to "Debug">]
        [;RunTitle=<title>]
    ```

  - Para registrar los resultados en un archivo de resultados de pruebas (TRX) de Visual Studio, use el proveedor de registrador `trx`. Este modificador, crea un archivo en el directorio de resultados de pruebas con un nombre de archivo de registro dado. Si no se proporciona `LogFileName`, se crea un nombre de archivo único para contener los resultados de las pruebas.

    ```console
    /logger:trx [;LogFileName=<Defaults to unique file name>]
    ```

- **`-lt|--ListTests <File Name>`**

  Muestra todas las pruebas detectadas del contenedor de pruebas especificado.

- **`--ParentProcessId <ParentProcessId>`**

  Id. de proceso del proceso principal responsable de iniciar el proceso actual.

- **`--Port <Port>`**

  Especifica el puerto para la conexión de socket y la recepción de mensajes de eventos.

- **`--Diag <Path to log file>`**

  Permite registros detallados para la plataforma de prueba. Los registros se escriben en el archivo proporcionado.

- **`--Blame`**

  Ejecuta las pruebas en el modo de culpabilidad. Esta opción es útil para aislar las pruebas problemáticas que hacen que el host de prueba se bloquee. Crea un archivo de salida en el directorio actual como *Sequence.xml* que captura el orden de ejecución de pruebas antes del bloqueo.

- **`--InIsolation`**

  Ejecuta las pruebas en un proceso aislado. De este modo, es menos probable que el proceso *vstest.console.exe* se detenga por un error de las pruebas, pero es posible que las pruebas se ejecuten más despacio.

- **`@<file>`**

  Lee el archivo de respuesta para ver más opciones.

- **`args`**

  Especifica argumentos adicionales para pasar al adaptador. Los argumentos se especifican como pares de nombre-valor en el formato `<n>=<v>`, donde `<n>` es el nombre del argumento y `<v>` es el valor del argumento. Use un espacio para separar varios argumentos.

## <a name="examples"></a>Ejemplos

Ejecución de pruebas en *mytestproject.dll*:

```dotnetcli
dotnet vstest mytestproject.dll
```

Ejecución de pruebas en *mytestproject.dll*, exportación a una carpeta personalizada con nombre personalizado:

```dotnetcli
dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path
```

Ejecución de pruebas en *mytestproject.dll* y *myothertestproject.exe*:

```dotnetcli
dotnet vstest mytestproject.dll myothertestproject.exe
```

Ejecutar pruebas `TestMethod1`:

```dotnetcli
dotnet vstest /Tests:TestMethod1
```

Ejecutar pruebas `TestMethod1` y `TestMethod2`:

```dotnetcli
dotnet vstest /Tests:TestMethod1,TestMethod2
```
