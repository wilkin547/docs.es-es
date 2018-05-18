---
title: 'Comando dotnet vstest: CLI de .NET Core'
description: El comando dotnet vstest compila un proyecto y todas sus dependencias.
author: guardrex
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: 981b56aa46afd5ca313ee0be0ca10843ef70e939
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-vstest"></a>dotnet vstest

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nombre

`dotnet-vstest`: ejecuta pruebas desde los archivos especificados.

## <a name="synopsis"></a>Sinopsis

`dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath] [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger] [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]`

## <a name="description"></a>Description

El comando `dotnet-vstest` ejecuta la aplicación de línea de comandos `VSTest.Console` para ejecutar pruebas de aplicaciones de interfaz de usuario codificadas y unitarias automatizadas.

## <a name="arguments"></a>Argumentos

`TEST_FILE_NAMES`

Ejecutar pruebas desde los ensamblados especificados. Separar varios nombres de ensamblado de prueba con espacios.

## <a name="options"></a>Opciones

`--Settings|/Settings:<Settings File>`

Configuración que se usará al ejecutar las pruebas.

`--Tests|/Tests:<Test Names>`

Ejecuta las pruebas con nombres que coinciden con los Separar varios valores con comas.

`--TestAdapterPath|/TestAdapterPath`

Usar adaptadores de prueba personalizados desde una ruta de acceso especificada (si existe) en la serie de pruebas.

`--Platform|/Platform:<Platform type>`

Identificar la arquitectura de la plataforma usada en la ejecución de pruebas. Valores válidos son `x86`, `x64` y `ARM`.

`--Framework|/Framework:<Framework Version>`

Identificar la versión de .NET Framework usada en la ejecución de pruebas. Ejemplos de valores válidos son `.NETFramework,Version=v4.6`, `.NETCoreApp,Version=v1.0`, etc. Otros valores admitidos son `Framework35`, `Framework40`, `Framework45` y `FrameworkCore10`.

`--Parallel|/Parallel`

Ejecutar pruebas en paralelo. De forma predeterminada, todos los núcleos disponibles en el equipo están disponibles para su uso. Establecer un número explícito de núcleos con un archivo de configuración.

`--TestCaseFilter|/TestCaseFilter:<Expression>`

Ejecuta pruebas que coinciden con la expresión dada. `<Expression>` tiene el formato `<property>Operator<value>[|&<Expression>]`, donde Operator es `=`, `!=` o `~`.  El operador `~` tiene semántica "contains" y se aplica a las propiedades de cadena como `DisplayName`. Los paréntesis `()` se usan para agrupar expresiones secundarias.

`-?|--Help|/?|/Help`

Imprime una corta ayuda para el comando.

`--logger|/logger:<Logger Uri/FriendlyName>`

Especifica un registrador para resultados de pruebas.  

* Para publicar resultados de pruebas en Team Foundation Server, use el proveedor de registrador `TfsPublisher`:

  ```
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* Para registrar los resultados en un archivo de resultados de pruebas (TRX) de Visual Studio, use el proveedor de registrador `trx`. Este modificador, crea un archivo en el directorio de resultados de pruebas con un nombre de archivo de registro dado. Si no se proporciona `LogFileName`, se crea un nombre de archivo único para contener los resultados de las pruebas.

  ```
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

Muestra las pruebas detectadas del contenedor de pruebas especificado.

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

Id. de proceso del proceso principal responsable de iniciar el proceso actual.

`--Port|/Port:<Port>`

Especifica el puerto para la conexión de socket y la recepción de mensajes de eventos.

`--Diag|/Diag:<Path to log file>`

Permite registros detallados para la plataforma de prueba. Los registros se escriben en el archivo proporcionado.

`args`

Especifica argumentos adicionales para pasar al adaptador. Los argumentos se especifican como pares de nombre-valor en el formato `<n>=<v>`, donde `<n>` es el nombre del argumento y `<v>` es el valor del argumento. Use un espacio para separar varios argumentos.

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

