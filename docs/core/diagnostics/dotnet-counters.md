---
title: 'dotnet-counters: .Net Core'
description: Obtenga información sobre cómo instalar y usar la herramienta de línea de comandos dotnet-counter.
author: sdmaclea
ms.author: stmaclea
ms.date: 10/14/2019
ms.openlocfilehash: b2fab239713d9d19c580580496e73a91ceafcc52
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321541"
---
# <a name="dotnet-counters"></a><span data-ttu-id="6bc89-103">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="6bc89-103">dotnet-counters</span></span>

<span data-ttu-id="6bc89-104">**Este artículo se aplica a: ✓** SDK de .NET Core 3.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="6bc89-104">**This article applies to: ✓** .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-counters"></a><span data-ttu-id="6bc89-105">Instalación de dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="6bc89-105">Install dotnet-counters</span></span>

<span data-ttu-id="6bc89-106">Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-counters) de `dotnet-counters`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="6bc89-106">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a><span data-ttu-id="6bc89-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="6bc89-107">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="6bc89-108">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6bc89-108">Description</span></span>

<span data-ttu-id="6bc89-109">`dotnet-counters` es una herramienta de supervisión de rendimiento diseñada para la investigación del rendimiento y la supervisión del estado de primer nivel ad hoc.</span><span class="sxs-lookup"><span data-stu-id="6bc89-109">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="6bc89-110">Puede observar los valores del contador de rendimiento que se publican a través de la API <xref:System.Diagnostics.Tracing.EventCounter>.</span><span class="sxs-lookup"><span data-stu-id="6bc89-110">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="6bc89-111">Por ejemplo, se pueden supervisar rápidamente cosas como el uso de la CPU o la velocidad de las excepciones que se producen en la aplicación .NET Core para ver si hay algo sospechoso antes de profundizar en una investigación de rendimiento más seria mediante `PerfView` o `dotnet-trace`.</span><span class="sxs-lookup"><span data-stu-id="6bc89-111">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="6bc89-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="6bc89-112">Options</span></span>

- **`--version`**

  <span data-ttu-id="6bc89-113">Muestra la versión de la utilidad dotnet-counters.</span><span class="sxs-lookup"><span data-stu-id="6bc89-113">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="6bc89-114">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="6bc89-114">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="6bc89-115">Comandos</span><span class="sxs-lookup"><span data-stu-id="6bc89-115">Commands</span></span>

| <span data-ttu-id="6bc89-116">Comando</span><span class="sxs-lookup"><span data-stu-id="6bc89-116">Command</span></span>                                             |
| --------------------------------------------------- |
| [<span data-ttu-id="6bc89-117">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="6bc89-117">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="6bc89-118">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="6bc89-118">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |

## <a name="dotnet-counters-list"></a><span data-ttu-id="6bc89-119">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="6bc89-119">dotnet-counters list</span></span>

<span data-ttu-id="6bc89-120">Muestra una lista de nombres y descripciones de contador, agrupada por proveedor.</span><span class="sxs-lookup"><span data-stu-id="6bc89-120">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="6bc89-121">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="6bc89-121">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="6bc89-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6bc89-122">Example</span></span>

```console
> dotnet-counters list

    Showing well-known counters only. Specific processes may support additional counters.
    System.Runtime
        cpu-usage                    Amount of time the process has utilized the CPU (ms)
        working-set                  Amount of working set used by the process (MB)
        gc-heap-size                 Total heap size reported by the GC (MB)
        gen-0-gc-count               Number of Gen 0 GCs / sec
        gen-1-gc-count               Number of Gen 1 GCs / sec
        gen-2-gc-count               Number of Gen 2 GCs / sec
        exception-count              Number of Exceptions / sec
```

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="6bc89-123">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="6bc89-123">dotnet-counters monitor</span></span>

<span data-ttu-id="6bc89-124">Muestra la actualización periódica de los valores de los contadores seleccionados.</span><span class="sxs-lookup"><span data-stu-id="6bc89-124">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="6bc89-125">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="6bc89-125">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list]
```

### <a name="options"></a><span data-ttu-id="6bc89-126">Opciones</span><span class="sxs-lookup"><span data-stu-id="6bc89-126">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="6bc89-127">Id. del proceso que se va a supervisar.</span><span class="sxs-lookup"><span data-stu-id="6bc89-127">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="6bc89-128">Número de segundos de retraso entre la actualización de los contadores mostrados.</span><span class="sxs-lookup"><span data-stu-id="6bc89-128">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="6bc89-129">Una lista de contadores separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="6bc89-129">A space separated list of counters.</span></span> <span data-ttu-id="6bc89-130">Los contadores pueden ser `provider_name[:counter_name]` especificados.</span><span class="sxs-lookup"><span data-stu-id="6bc89-130">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="6bc89-131">Si `provider_name` se usa sin un elemento `counter_name` calificado, se mostrarán todos los contadores.</span><span class="sxs-lookup"><span data-stu-id="6bc89-131">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="6bc89-132">Para descubrir los nombres del proveedor y del contador, use el comando [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="6bc89-132">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

### <a name="examples"></a><span data-ttu-id="6bc89-133">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6bc89-133">Examples</span></span>

- <span data-ttu-id="6bc89-134">Supervisión de todos los contadores de `System.Runtime` con un intervalo de actualización de 3 segundos:</span><span class="sxs-lookup"><span data-stu-id="6bc89-134">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902  --refresh-interval 3 System.Runtime

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      Working Set (MB)                            1982
      GC Heap Size (MB)                            811
      Gen 0 GC / second                             20
      Gen 1 GC / second                              4
      Gen 2 GC / second                              1
      Number of Exceptions / sec                     4
  ```

- <span data-ttu-id="6bc89-135">Supervisión de únicamente el uso de la CPU y el tamaño del montón de GC de `System.Runtime`:</span><span class="sxs-lookup"><span data-stu-id="6bc89-135">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="6bc89-136">Supervisión de los valores `EventCounter` del elemento `EventSource` definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="6bc89-136">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="6bc89-137">Para obtener más información, consulte [Tutorial: Cómo medir el rendimiento de eventos muy frecuentes con EventCounters](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).</span><span class="sxs-lookup"><span data-stu-id="6bc89-137">For more information, see [Tutorial: How to measure performance for very frequent events using EventCounters](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```
