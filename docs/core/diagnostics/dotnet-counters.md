---
title: 'dotnet-counters: .Net Core'
description: Obtenga información sobre cómo instalar y usar la herramienta de línea de comandos dotnet-counter.
ms.date: 02/26/2020
ms.openlocfilehash: dc95297478784ca06fe442a939f8489a40b29da7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147183"
---
# <a name="dotnet-counters"></a><span data-ttu-id="17e78-103">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="17e78-103">dotnet-counters</span></span>

<span data-ttu-id="17e78-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="17e78-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-counters"></a><span data-ttu-id="17e78-105">Instalación de dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="17e78-105">Install dotnet-counters</span></span>

<span data-ttu-id="17e78-106">Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-counters) de `dotnet-counters`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="17e78-106">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a><span data-ttu-id="17e78-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="17e78-107">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="17e78-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="17e78-108">Description</span></span>

<span data-ttu-id="17e78-109">`dotnet-counters` es una herramienta de supervisión de rendimiento diseñada para la investigación del rendimiento y la supervisión del estado de primer nivel ad hoc.</span><span class="sxs-lookup"><span data-stu-id="17e78-109">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="17e78-110">Puede observar los valores del contador de rendimiento que se publican a través de la API <xref:System.Diagnostics.Tracing.EventCounter>.</span><span class="sxs-lookup"><span data-stu-id="17e78-110">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="17e78-111">Por ejemplo, se pueden supervisar rápidamente cosas como el uso de la CPU o la velocidad de las excepciones que se producen en la aplicación .NET Core para ver si hay algo sospechoso antes de profundizar en una investigación de rendimiento más seria mediante `PerfView` o `dotnet-trace`.</span><span class="sxs-lookup"><span data-stu-id="17e78-111">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="17e78-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="17e78-112">Options</span></span>

- **`--version`**

  <span data-ttu-id="17e78-113">Muestra la versión de la utilidad dotnet-counters.</span><span class="sxs-lookup"><span data-stu-id="17e78-113">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="17e78-114">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="17e78-114">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="17e78-115">Comandos</span><span class="sxs-lookup"><span data-stu-id="17e78-115">Commands</span></span>

| <span data-ttu-id="17e78-116">Comando</span><span class="sxs-lookup"><span data-stu-id="17e78-116">Command</span></span>                                             |
| --------------------------------------------------- |
| [<span data-ttu-id="17e78-117">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="17e78-117">dotnet-counters collect</span></span>](#dotnet-counters-collect) |
| [<span data-ttu-id="17e78-118">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="17e78-118">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="17e78-119">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="17e78-119">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |
| [<span data-ttu-id="17e78-120">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="17e78-120">dotnet-counters ps</span></span>](#dotnet-counters-ps) |

## <a name="dotnet-counters-collect"></a><span data-ttu-id="17e78-121">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="17e78-121">dotnet-counters collect</span></span>

<span data-ttu-id="17e78-122">Recopila periódicamente los valores de contador seleccionados y los exporta a un formato de archivo especificado para su posterior procesamiento.</span><span class="sxs-lookup"><span data-stu-id="17e78-122">Periodically collect selected counter values and export them into a specified file format for post-processing.</span></span>

### <a name="synopsis"></a><span data-ttu-id="17e78-123">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="17e78-123">Synopsis</span></span>

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list] [--format] [-o|--output]
```

### <a name="options"></a><span data-ttu-id="17e78-124">Opciones</span><span class="sxs-lookup"><span data-stu-id="17e78-124">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="17e78-125">Id. del proceso que se va a supervisar.</span><span class="sxs-lookup"><span data-stu-id="17e78-125">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="17e78-126">Número de segundos de retraso entre la actualización de los contadores mostrados.</span><span class="sxs-lookup"><span data-stu-id="17e78-126">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="17e78-127">Una lista de contadores separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="17e78-127">A space separated list of counters.</span></span> <span data-ttu-id="17e78-128">Los contadores pueden ser `provider_name[:counter_name]` especificados.</span><span class="sxs-lookup"><span data-stu-id="17e78-128">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="17e78-129">Si `provider_name` se usa sin un elemento `counter_name` calificado, se mostrarán todos los contadores.</span><span class="sxs-lookup"><span data-stu-id="17e78-129">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="17e78-130">Para descubrir los nombres del proveedor y del contador, use el comando [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="17e78-130">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

- **`--format <csv|json>`**

  <span data-ttu-id="17e78-131">El formato que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="17e78-131">TThe format to be exported.</span></span> <span data-ttu-id="17e78-132">Actualmente disponibles: csv, json.</span><span class="sxs-lookup"><span data-stu-id="17e78-132">Currently available: csv, json.</span></span>

- **`-o|--output <output>`**

  <span data-ttu-id="17e78-133">Nombre del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="17e78-133">The name of the output file.</span></span>

### <a name="examples"></a><span data-ttu-id="17e78-134">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="17e78-134">Examples</span></span>

- <span data-ttu-id="17e78-135">Recopilación de todos los contadores en un intervalo de actualización de tres segundos y generación de un archivo CSV como salida:</span><span class="sxs-lookup"><span data-stu-id="17e78-135">Collect all counters at a refresh interval of 3 seconds and generate a csv as output:</span></span>

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

## <a name="dotnet-counters-list"></a><span data-ttu-id="17e78-136">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="17e78-136">dotnet-counters list</span></span>

<span data-ttu-id="17e78-137">Muestra una lista de nombres y descripciones de contador, agrupada por proveedor.</span><span class="sxs-lookup"><span data-stu-id="17e78-137">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="17e78-138">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="17e78-138">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="17e78-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17e78-139">Example</span></span>

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

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="17e78-140">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="17e78-140">dotnet-counters monitor</span></span>

<span data-ttu-id="17e78-141">Muestra la actualización periódica de los valores de los contadores seleccionados.</span><span class="sxs-lookup"><span data-stu-id="17e78-141">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="17e78-142">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="17e78-142">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list]
```

### <a name="options"></a><span data-ttu-id="17e78-143">Opciones</span><span class="sxs-lookup"><span data-stu-id="17e78-143">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="17e78-144">Id. del proceso que se va a supervisar.</span><span class="sxs-lookup"><span data-stu-id="17e78-144">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="17e78-145">Número de segundos de retraso entre la actualización de los contadores mostrados.</span><span class="sxs-lookup"><span data-stu-id="17e78-145">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="17e78-146">Una lista de contadores separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="17e78-146">A space separated list of counters.</span></span> <span data-ttu-id="17e78-147">Los contadores pueden ser `provider_name[:counter_name]` especificados.</span><span class="sxs-lookup"><span data-stu-id="17e78-147">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="17e78-148">Si `provider_name` se usa sin un elemento `counter_name` calificado, se mostrarán todos los contadores.</span><span class="sxs-lookup"><span data-stu-id="17e78-148">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="17e78-149">Para descubrir los nombres del proveedor y del contador, use el comando [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="17e78-149">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

### <a name="examples"></a><span data-ttu-id="17e78-150">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="17e78-150">Examples</span></span>

- <span data-ttu-id="17e78-151">Supervisión de todos los contadores de `System.Runtime` con un intervalo de actualización de 3 segundos:</span><span class="sxs-lookup"><span data-stu-id="17e78-151">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

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

- <span data-ttu-id="17e78-152">Supervisión de únicamente el uso de la CPU y el tamaño del montón de GC de `System.Runtime`:</span><span class="sxs-lookup"><span data-stu-id="17e78-152">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="17e78-153">Supervisión de los valores `EventCounter` del elemento `EventSource` definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="17e78-153">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="17e78-154">Para obtener más información, consulte [Tutorial: Cómo medir el rendimiento de eventos muy frecuentes con EventCounters](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).</span><span class="sxs-lookup"><span data-stu-id="17e78-154">For more information, see [Tutorial: How to measure performance for very frequent events using EventCounters](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```
  
## <a name="dotnet-counters-ps"></a><span data-ttu-id="17e78-155">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="17e78-155">dotnet-counters ps</span></span>

<span data-ttu-id="17e78-156">Muestra una lista de los procesos de dotnet que se pueden supervisar.</span><span class="sxs-lookup"><span data-stu-id="17e78-156">Display a list of dotnet processes that can be monitored.</span></span>

### <a name="synopsis"></a><span data-ttu-id="17e78-157">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="17e78-157">Synopsis</span></span>

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a><span data-ttu-id="17e78-158">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17e78-158">Example</span></span>

```console
> dotnet-counters ps
  
  15683 WebApi     /home/suwhang/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```
