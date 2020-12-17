---
title: 'Herramienta de diagnóstico dotnet-counters: CLI de .NET'
description: Obtenga información sobre cómo instalar y usar la herramienta dotnet-counter de la CLI para la investigación del rendimiento y la supervisión del estado de primer nivel ad hoc.
ms.date: 11/17/2020
ms.openlocfilehash: 48e3b038ddb5c9421367612a592c5ba6b9459791
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009552"
---
# <a name="investigate-performance-counters-dotnet-counters"></a>Investigación de los contadores de rendimiento (dotnet-counters)

**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores

## <a name="install"></a>Instalar

Hay dos maneras de descargar e instalar `dotnet-counters`:

- **Herramienta global dotnet:**

  Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-counters) de `dotnet-counters`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):

  ```dotnetcli
  dotnet tool install --global dotnet-counters
  ```

- **Descarga directa:**

  descargue el archivo ejecutable de la herramienta que coincida con la plataforma:

  | SO  | Plataforma |
  | --- | -------- |
  | Windows | [x86](https://aka.ms/dotnet-counters/win-x86) \| [x64](https://aka.ms/dotnet-counters/win-x64) \| [arm](https://aka.ms/dotnet-counters/win-arm) \| [arm-x64](https://aka.ms/dotnet-counters/win-arm64) |
  | macOS   | [x64](https://aka.ms/dotnet-counters/osx-x64) |
  | Linux   | [x64](https://aka.ms/dotnet-counters/linux-x64) \| [arm](https://aka.ms/dotnet-counters/linux-arm) \| [arm64](https://aka.ms/dotnet-counters/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-counters/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-counters/linux-musl-arm64) |

## <a name="synopsis"></a>Sinopsis

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a>Descripción

`dotnet-counters` es una herramienta de supervisión de rendimiento diseñada para la investigación del rendimiento y la supervisión del estado de primer nivel ad hoc. Puede observar los valores del contador de rendimiento que se publican a través de la API <xref:System.Diagnostics.Tracing.EventCounter>. Por ejemplo, se pueden supervisar rápidamente cosas como el uso de la CPU o la velocidad de las excepciones que se producen en la aplicación .NET Core para ver si hay algo sospechoso antes de profundizar en una investigación de rendimiento más seria mediante `PerfView` o `dotnet-trace`.

## <a name="options"></a>Opciones

- **`--version`**

  Muestra la versión de la utilidad dotnet-counters.

- **`-h|--help`**

  Muestra la ayuda de la línea de comandos.

## <a name="commands"></a>Comandos

| Comando                                             |
|-----------------------------------------------------|
| [dotnet-counters collect](#dotnet-counters-collect) |
| [dotnet-counters list](#dotnet-counters-list)       |
| [dotnet-counters monitor](#dotnet-counters-monitor) |
| [dotnet-counters ps](#dotnet-counters-ps)           |

## <a name="dotnet-counters-collect"></a>dotnet-counters collect

Recopila periódicamente los valores de contador seleccionados y los exporta a un formato de archivo especificado para su posterior procesamiento.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [-n|--name] [--diagnostic-port] [--refresh-interval] [--counters <COUNTERS>] [--format] [-o|--output] [-- <command>]
```

### <a name="options"></a>Opciones

- **`-p|--process-id <PID>`**

  Id. del proceso del que se van a recopilar datos de contador.

- **`-n|--name <name>`**

  Nombre del proceso del que se van a recopilar datos de contador.

- **`--diagnostic-port`**

  Nombre del puerto de diagnóstico que se va a crear. Vea [Uso del puerto de diagnóstico](#using-diagnostic-port) para saber cómo usar esta opción a fin de iniciar los contadores de supervisión desde el inicio de la aplicación.

- **`--refresh-interval <SECONDS>`**

  Número de segundos de retraso entre la actualización de los contadores mostrados.

- **`--counters <COUNTERS>`**

  Una lista de contadores separados por comas. Los contadores pueden ser `provider_name[:counter_name]` especificados. Si se usa `provider_name` sin una lista de contadores que cumplan los requisitos, se mostrarán todos los contadores del proveedor. Para descubrir los nombres del proveedor y del contador, use el comando [dotnet-counters list](#dotnet-counters-list).

- **`--format <csv|json>`**

  Formato que se va a exportar. Actualmente disponibles: csv, json.

- **`-o|--output <output>`**

  Nombre del archivo de salida.

- **`-- <command>` (solo para seleccionar como destino aplicaciones que ejecutan .NET 5.0 o versiones posteriores)**

  Después de los parámetros de configuración de la colección, el usuario puede anexar `--` seguido de un comando para iniciar una aplicación de .NET con un entorno de ejecución de 5.0 como mínimo. `dotnet-counters` iniciará un proceso con el comando proporcionado y recopilará las métricas solicitadas. Esto suele ser útil para recopilar métricas de la ruta de acceso de inicio de la aplicación y se puede usar para diagnosticar o supervisar los problemas que se producen antes o poco después del punto de entrada principal.

  > [!NOTE]
  > El uso de esta opción supervisa el primer proceso de .NET 5.0 que se comunica con la herramienta, lo que significa que, si el comando inicia varias aplicaciones de .NET, solo recopilará la primera. Por tanto, se recomienda usar esta opción en aplicaciones independientes, o bien utilizar la opción `dotnet exec <app.dll>`.

  > [!NOTE]
  > El inicio de un archivo ejecutable de .NET por medio de dotnet-counters redirigirá su entrada o salida, y no podrá interactuar con su stdin/stdout. La salida de la herramienta por medio de Ctrl + C o SIGTERM finalizará con seguridad la herramienta y el proceso secundario. Si el proceso secundario termina antes que la herramienta, la herramienta también se cerrará y el seguimiento se debe poder ver de forma segura. Si necesita usar stdin/stdout, puede usar la opción `--diagnostic-port`. Para obtener más información, vea [Uso del puerto de diagnóstico](#using-diagnostic-port).

### <a name="examples"></a>Ejemplos

- Recopilación de todos los contadores en un intervalo de actualización de tres segundos y generación de un archivo CSV como salida:

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

- Inicie `dotnet mvc.dll` como un proceso secundario y comience a recopilar contadores de tiempo de ejecución y contadores de hospedaje de ASP.NET Core del inicio, y guárdelo como una salida JSON:

  ```console
  > dotnet-counters collect --format json --counters System.Runtime,Microsoft.AspNetCore.Hosting -- dotnet mvc.dll
  Starting a counter session. Press Q to quit.
  File saved to counter.json
  ```

## <a name="dotnet-counters-list"></a>dotnet-counters list

Muestra una lista de nombres y descripciones de contador, agrupada por proveedor.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a>Ejemplo

```console
> dotnet-counters list
Showing well-known counters only. Specific processes may support additional counters.

System.Runtime
    cpu-usage                                    Amount of time the process has utilized the CPU (ms)
    working-set                                  Amount of working set used by the process (MB)
    gc-heap-size                                 Total heap size reported by the GC (MB)
    gen-0-gc-count                               Number of Gen 0 GCs / min
    gen-1-gc-count                               Number of Gen 1 GCs / min
    gen-2-gc-count                               Number of Gen 2 GCs / min
    time-in-gc                                   % time in GC since the last GC
    gen-0-size                                   Gen 0 Heap Size
    gen-1-size                                   Gen 1 Heap Size
    gen-2-size                                   Gen 2 Heap Size
    loh-size                                     LOH Heap Size
    alloc-rate                                   Allocation Rate
    assembly-count                               Number of Assemblies Loaded
    exception-count                              Number of Exceptions / sec
    threadpool-thread-count                      Number of ThreadPool Threads
    monitor-lock-contention-count                Monitor Lock Contention Count
    threadpool-queue-length                      ThreadPool Work Items Queue Length
    threadpool-completed-items-count             ThreadPool Completed Work Items Count
    active-timer-count                           Active Timers Count

Microsoft.AspNetCore.Hosting
    requests-per-second                  Request rate
    total-requests                       Total number of requests
    current-requests                     Current number of requests
    failed-requests                      Failed number of requests
```

> [!NOTE]
> Los contadores de `Microsoft.AspNetCore.Hosting` se muestran cuando hay procesos identificados que admiten estos contadores, por ejemplo, cuando una aplicación ASP.NET Core se está ejecutando en el equipo host.

## <a name="dotnet-counters-monitor"></a>dotnet-counters monitor

Muestra la actualización periódica de los valores de los contadores seleccionados.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [-n|--name] [--diagnostic-port] [--refresh-interval] [--counters] [-- <command>]
```

### <a name="options"></a>Opciones

- **`-p|--process-id <PID>`**

  Id. del proceso que se va a supervisar.

- **`-n|--name <name>`**

  Nombre del proceso que se va a supervisar.

- **`--diagnostic-port`**

  Nombre del puerto de diagnóstico que se va a crear. Vea [Uso del puerto de diagnóstico](#using-diagnostic-port) para saber cómo usar esta opción a fin de iniciar los contadores de supervisión desde el inicio de la aplicación.

- **`--refresh-interval <SECONDS>`**

  Número de segundos de retraso entre la actualización de los contadores mostrados.

- **`--counters <COUNTERS>`**

  Una lista de contadores separados por comas. Los contadores pueden ser `provider_name[:counter_name]` especificados. Si se usa `provider_name` sin una lista de contadores que cumplan los requisitos, se mostrarán todos los contadores del proveedor. Para descubrir los nombres del proveedor y del contador, use el comando [dotnet-counters list](#dotnet-counters-list).

 **`-- <command>` (solo para seleccionar como destino aplicaciones que ejecutan .NET 5.0 o versiones posteriores)**

  Después de los parámetros de configuración de la colección, el usuario puede anexar `--` seguido de un comando para iniciar una aplicación de .NET con un entorno de ejecución de 5.0 como mínimo. `dotnet-counters` iniciará un proceso con el comando proporcionado y supervisará las métricas solicitadas. Esto suele ser útil para recopilar métricas de la ruta de acceso de inicio de la aplicación y se puede usar para diagnosticar o supervisar los problemas que se producen antes o poco después del punto de entrada principal.

  > [!NOTE]
  > El uso de esta opción supervisa el primer proceso de .NET 5.0 que se comunica con la herramienta, lo que significa que, si el comando inicia varias aplicaciones de .NET, solo recopilará la primera. Por tanto, se recomienda usar esta opción en aplicaciones independientes, o bien utilizar la opción `dotnet exec <app.dll>`.

  > [!NOTE]
  > El inicio de un archivo ejecutable de .NET por medio de dotnet-counters redirigirá su entrada o salida, y no podrá interactuar con su stdin/stdout. La salida de la herramienta por medio de Ctrl + C o SIGTERM finalizará con seguridad la herramienta y el proceso secundario. Si el proceso secundario termina antes que la herramienta, la herramienta también se cerrará y el seguimiento se debe poder ver de forma segura. Si necesita usar stdin/stdout, puede usar la opción `--diagnostic-port`. Para obtener más información, vea [Uso del puerto de diagnóstico](#using-diagnostic-port).

### <a name="examples"></a>Ejemplos

- Supervisión de todos los contadores de `System.Runtime` con un intervalo de actualización de 3 segundos:

  ```console
  > dotnet-counters monitor --process-id 1902  --refresh-interval 3 --counters System.Runtime
  Press p to pause, r to resume, q to quit.
      Status: Running

  [System.Runtime]
      % Time in GC since last GC (%)                                 0
      Allocation Rate (B / 1 sec)                                5,376
      CPU Usage (%)                                                  0
      Exception Count (Count / 1 sec)                                0
      GC Fragmentation (%)                                          48.467
      GC Heap Size (MB)                                              0
      Gen 0 GC Count (Count / 1 sec)                                 1
      Gen 0 Size (B)                                                24
      Gen 1 GC Count (Count / 1 sec)                                 1
      Gen 1 Size (B)                                                24
      Gen 2 GC Count (Count / 1 sec)                                 1
      Gen 2 Size (B)                                           272,000
      IL Bytes Jitted (B)                                       19,449
      LOH Size (B)                                              19,640
      Monitor Lock Contention Count (Count / 1 sec)                  0
      Number of Active Timers                                        0
      Number of Assemblies Loaded                                    7
      Number of Methods Jitted                                     166
      POH (Pinned Object Heap) Size (B)                             24
      ThreadPool Completed Work Item Count (Count / 1 sec)           0
      ThreadPool Queue Length                                        0
      ThreadPool Thread Count                                        2
      Working Set (MB)                                              19
  ```

- Supervisión de únicamente el uso de la CPU y el tamaño del montón de GC de `System.Runtime`:

  ```console
  > dotnet-counters monitor --process-id 1902 --counters System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- Supervisión de los valores `EventCounter` del elemento `EventSource` definido por el usuario. Para obtener más información, consulte [Tutorial: Medición del rendimiento mediante EventCounters en .NET Core](event-counter-perf.md).

  ```console
  > dotnet-counters monitor --process-id 1902 --counters Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```

- Inicie `my-aspnet-server.exe` y supervise el número de ensamblados cargados desde su inicio (solo para .NET 5.0 o versiones posteriores):

  > [!IMPORTANT]
  > Esto solo funciona para las aplicaciones que ejecutan .NET 5.0 o una versión posterior.

  ```console
  > dotnet-counters monitor --counters System.Runtime[assembly-count] -- my-aspnet-server.exe

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      Number of Assemblies Loaded                   24
  ```
  
- Inicie `my-aspnet-server.exe` con `arg1` y `arg2` como argumentos de la línea de comandos y supervise su espacio de trabajo y el tamaño del montón de GC desde su inicio (solo para .NET 5.0 o versiones posteriores):

  > [!IMPORTANT]
  > Esto solo funciona para las aplicaciones que ejecutan .NET 5.0 o una versión posterior.

  ```console
  > dotnet-counters monitor --counters System.Runtime[working-set,gc-heap-size] -- my-aspnet-server.exe arg1 arg2
  ```

  ```console
  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      GC Heap Size (MB)                                 39
      Working Set (MB)                                  59
  ```

## <a name="dotnet-counters-ps"></a>dotnet-counters ps

Muestra una lista de los procesos de dotnet que se pueden supervisar.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a>Ejemplo

```console
> dotnet-counters ps
  
  15683 WebApi     /home/user/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```

## <a name="using-diagnostic-port"></a>Uso del puerto de diagnóstico

  > [!IMPORTANT]
  > Esto solo funciona para las aplicaciones que ejecutan .NET 5.0 o una versión posterior.

El puerto de diagnóstico es una característica nueva del entorno de ejecución que se ha agregado en .NET 5 y permite iniciar la supervisión o la recopilación de contadores desde el inicio de la aplicación. Para hacer esto con `dotnet-counters`, puede usar `dotnet-counters <collect|monitor> -- <command>`, tal como se describe en los ejemplos anteriores, o bien la opción `--diagnostic-port`.

El uso de `dotnet-counters <collect|monitor> -- <command>` para iniciar la aplicación como un proceso secundario es la manera más sencilla de realizar una supervisión rápida desde el inicio.

Sin embargo, si quiere obtener un control más preciso sobre la vigencia de la aplicación supervisada (por ejemplo, supervisar la aplicación solo durante los primeros 10 minutos y continuar la ejecución), o si necesita interactuar con la aplicación mediante la CLI, el uso de la opción `--diagnostic-port` le permite controlar la aplicación de destino que se supervisa y `dotnet-counters`.

1. El comando siguiente hace que dotnet-counters cree un socket de diagnóstico denominado `myport.sock` y que espere a una conexión.

    > ```dotnet-cli
    > dotnet-counters collect --diagnostic-port myport.sock
    > ```

    Salida:

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ```

2. En una consola independiente, inicie la aplicación de destino con la variable de entorno `DOTNET_DiagnosticPorts` establecida en el valor de la salida de `dotnet-counters`.

    > ```bash
    > export DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ./my-dotnet-app arg1 arg2
    > ```

    Esto debe habilitar `dotnet-counters` para empezar a recopilar contadores en `my-dotnet-app`:

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=myport.sock
    > Starting a counter session. Press Q to quit.
    > ```

    > [!IMPORTANT]
    > Iniciar la aplicación con `dotnet run` puede resultar problemático porque la CLI de dotnet puede generar muchos procesos secundarios que no sean la aplicación. Además, dichos procesos secundarios pueden conectarse a `dotnet-counters` antes que la aplicación, lo que causa que esta se suspenda en tiempo de ejecución. Se recomienda usar directamente una versión independiente de la aplicación o `dotnet exec` para iniciar la aplicación.
