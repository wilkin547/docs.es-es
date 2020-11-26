---
title: 'Herramienta de diagnóstico dotnet-gcdump: CLI de .NET'
description: Aprenda a instalar y usar la herramienta de la CLI dotnet-gcdump para recopilar volcados de memoria de GC (recolector de elementos no utilizados) de procesos de .NET en vivo mediante EventPipe de .NET.
ms.date: 11/17/2020
ms.openlocfilehash: 59de1845ada9e5bdd0b24bf4312517283324ce94
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826045"
---
# <a name="heap-analysis-tool-dotnet-gcdump"></a><span data-ttu-id="f9ca2-103">Herramienta de análisis del montón (dotnet-gcdump)</span><span class="sxs-lookup"><span data-stu-id="f9ca2-103">Heap analysis tool (dotnet-gcdump)</span></span>

<span data-ttu-id="f9ca2-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="f9ca2-104">**This article applies to:** ✔️ .NET Core 3.1 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="f9ca2-105">Instalar</span><span class="sxs-lookup"><span data-stu-id="f9ca2-105">Install</span></span>

<span data-ttu-id="f9ca2-106">Hay dos maneras de descargar e instalar `dotnet-gcdump`:</span><span class="sxs-lookup"><span data-stu-id="f9ca2-106">There are two ways to download and install `dotnet-gcdump`:</span></span>

- <span data-ttu-id="f9ca2-107">**Herramienta global dotnet:**</span><span class="sxs-lookup"><span data-stu-id="f9ca2-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="f9ca2-108">Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-gcdump) de `dotnet-gcdump`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="f9ca2-108">To install the latest release version of the `dotnet-gcdump` [NuGet package](https://www.nuget.org/packages/dotnet-gcdump), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-gcdump
  ```

- <span data-ttu-id="f9ca2-109">**Descarga directa:**</span><span class="sxs-lookup"><span data-stu-id="f9ca2-109">**Direct download:**</span></span>

  <span data-ttu-id="f9ca2-110">Descargue el archivo ejecutable de la herramienta que coincida con la plataforma:</span><span class="sxs-lookup"><span data-stu-id="f9ca2-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="f9ca2-111">SO</span><span class="sxs-lookup"><span data-stu-id="f9ca2-111">OS</span></span>  | <span data-ttu-id="f9ca2-112">Plataforma</span><span class="sxs-lookup"><span data-stu-id="f9ca2-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="f9ca2-113">Windows</span><span class="sxs-lookup"><span data-stu-id="f9ca2-113">Windows</span></span> | <span data-ttu-id="f9ca2-114">[x86](https://aka.ms/dotnet-gcdump/win-x86) \| [x64](https://aka.ms/dotnet-gcdump/win-x64) \| [arm](https://aka.ms/dotnet-gcdump/win-arm) \| [arm-x64](https://aka.ms/dotnet-gcdump/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="f9ca2-114">[x86](https://aka.ms/dotnet-gcdump/win-x86) \| [x64](https://aka.ms/dotnet-gcdump/win-x64) \| [arm](https://aka.ms/dotnet-gcdump/win-arm) \| [arm-x64](https://aka.ms/dotnet-gcdump/win-arm64)</span></span> |
  | <span data-ttu-id="f9ca2-115">macOS</span><span class="sxs-lookup"><span data-stu-id="f9ca2-115">macOS</span></span>   | [<span data-ttu-id="f9ca2-116">x64</span><span class="sxs-lookup"><span data-stu-id="f9ca2-116">x64</span></span>](https://aka.ms/dotnet-gcdump/osx-x64) |
  | <span data-ttu-id="f9ca2-117">Linux</span><span class="sxs-lookup"><span data-stu-id="f9ca2-117">Linux</span></span>   | <span data-ttu-id="f9ca2-118">[x64](https://aka.ms/dotnet-gcdump/linux-x64) \| [arm](https://aka.ms/dotnet-gcdump/linux-arm) \| [arm64](https://aka.ms/dotnet-gcdump/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-gcdump/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-gcdump/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="f9ca2-118">[x64](https://aka.ms/dotnet-gcdump/linux-x64) \| [arm](https://aka.ms/dotnet-gcdump/linux-arm) \| [arm64](https://aka.ms/dotnet-gcdump/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-gcdump/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-gcdump/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="f9ca2-119">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="f9ca2-119">Synopsis</span></span>

```console
dotnet-gcdump [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="f9ca2-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9ca2-120">Description</span></span>

<span data-ttu-id="f9ca2-121">La herramienta global `dotnet-gcdump` recopila volcados de memoria de GC (recolector de elementos no utilizados) de procesos de .NET en vivo mediante [EventPipe](./eventpipe.md).</span><span class="sxs-lookup"><span data-stu-id="f9ca2-121">The `dotnet-gcdump` global tool collects GC (Garbage Collector) dumps of live .NET processes using [EventPipe](./eventpipe.md).</span></span> <span data-ttu-id="f9ca2-122">Los volcados de memoria de GC se crean desencadenando un GC en el proceso de destino, activando eventos especiales y regenerando el gráfico de raíces de objeto a partir del flujo de eventos.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-122">GC dumps are created by triggering a GC in the target process, turning on special events, and regenerating the graph of object roots from the event stream.</span></span> <span data-ttu-id="f9ca2-123">Este proceso permite recopilar volcados de memoria de GC mientras el proceso se está ejecutando y con una sobrecarga mínima.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-123">This process allows for GC dumps to be collected while the process is running and with minimal overhead.</span></span> <span data-ttu-id="f9ca2-124">Estos volcados de memoria son útiles para varios escenarios:</span><span class="sxs-lookup"><span data-stu-id="f9ca2-124">These dumps are useful for several scenarios:</span></span>

- <span data-ttu-id="f9ca2-125">Comparar el número de objetos del montón en varios puntos en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-125">Comparing the number of objects on the heap at several points in time.</span></span>
- <span data-ttu-id="f9ca2-126">Analizar raíces de objetos (responder a preguntas como "¿qué sigue teniendo una referencia a este tipo?").</span><span class="sxs-lookup"><span data-stu-id="f9ca2-126">Analyzing roots of objects (answering questions like, "what still has a reference to this type?").</span></span>
- <span data-ttu-id="f9ca2-127">Recopilar estadísticas generales sobre los recuentos de objetos en el montón.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-127">Collecting general statistics about the counts of objects on the heap.</span></span>

### <a name="view-the-gc-dump-captured-from-dotnet-gcdump"></a><span data-ttu-id="f9ca2-128">Ver el volcado de memoria de GC capturado por dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="f9ca2-128">View the GC dump captured from dotnet-gcdump</span></span>

<span data-ttu-id="f9ca2-129">En Windows, los archivos `.gcdump` se pueden ver en [PerfView](https://github.com/microsoft/perfview) o en Visual Studio para analizarlos.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-129">On Windows, `.gcdump` files can be viewed in [PerfView](https://github.com/microsoft/perfview) for analysis or in Visual Studio.</span></span> <span data-ttu-id="f9ca2-130">Actualmente, no es posible abrir un archivo `.gcdump` en plataformas que no sean de Windows.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-130">Currently, There is no way of opening a `.gcdump` on non-Windows platforms.</span></span>

<span data-ttu-id="f9ca2-131">Puede recopilar varios archivos `.gcdump` y abrirlos simultáneamente en Visual Studio para obtener una comparativa.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-131">You can collect multiple `.gcdump`s and open them simultaneously in Visual Studio to get a comparison experience.</span></span>

## <a name="options"></a><span data-ttu-id="f9ca2-132">Opciones</span><span class="sxs-lookup"><span data-stu-id="f9ca2-132">Options</span></span>

- **`--version`**

  <span data-ttu-id="f9ca2-133">Muestra la versión del servicio `dotnet-gcdump`.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-133">Displays the version of the `dotnet-gcdump` utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="f9ca2-134">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-134">Shows command-line help.</span></span>

## `dotnet-gcdump collect`

<span data-ttu-id="f9ca2-135">Recopila un volcado de memoria de GC de un proceso que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-135">Collects a GC dump from a currently running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="f9ca2-136">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="f9ca2-136">Synopsis</span></span>

```console
dotnet-gcdump collect [-h|--help] [-p|--process-id <pid>] [-o|--output <gcdump-file-path>] [-v|--verbose] [-t|--timeout <timeout>] [-n|--name <name>]
```

### <a name="options"></a><span data-ttu-id="f9ca2-137">Opciones</span><span class="sxs-lookup"><span data-stu-id="f9ca2-137">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="f9ca2-138">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-138">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="f9ca2-139">Identificador del proceso del que se va a recopilar el volcado de memoria de GC.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-139">The process ID to collect the GC dump from.</span></span>

- **`-o|--output <gcdump-file-path>`**

  <span data-ttu-id="f9ca2-140">Ruta de acceso donde se deben escribir los volcados de memoria de GC recopilados.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-140">The path where collected GC dumps should be written.</span></span> <span data-ttu-id="f9ca2-141">El valor predeterminado es *.\\AAAAMMDD\_HHMMSS\_\<pid>.gcdump*.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-141">Defaults to *.\\YYYYMMDD\_HHMMSS\_\<pid>.gcdump*.</span></span>

- **`-v|--verbose`**

  <span data-ttu-id="f9ca2-142">Obtener resultados del registro mientras recopila el volcado de memoria de GC.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-142">Output the log while collecting the GC dump.</span></span>

- **`-t|--timeout <timeout>`**

  <span data-ttu-id="f9ca2-143">Dejar de recopilar el volcado de memoria de GC si tarda más de la cantidad de segundos indicada.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-143">Give up on collecting the GC dump if it takes longer than this many seconds.</span></span> <span data-ttu-id="f9ca2-144">El valor predeterminado es 30.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-144">The default value is 30.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="f9ca2-145">Nombre del proceso del que se va a recopilar el volcado de memoria de GC.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-145">The name of the process to collect the GC dump from.</span></span>

## `dotnet-gcdump ps`

<span data-ttu-id="f9ca2-146">Enumera los procesos de dotnet de los que se pueden recopilar volcados de memoria de GC.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-146">Lists the dotnet processes that GC dumps can be collected for.</span></span>

### <a name="synopsis"></a><span data-ttu-id="f9ca2-147">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="f9ca2-147">Synopsis</span></span>

```console
dotnet-gcdump ps
```

## `dotnet-gcdump report <gcdump_filename>`

<span data-ttu-id="f9ca2-148">Crear un informe a partir de un volcado de memoria de GC generado anteriormente o de un proceso en ejecución y escribir en `stdout`.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-148">Generate a report from a previously generated GC dump or from a running process, and write to `stdout`.</span></span>

### <a name="synopsis"></a><span data-ttu-id="f9ca2-149">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="f9ca2-149">Synopsis</span></span>

```console
dotnet-gcdump report [-h|--help] [-p|--process-id <pid>] [-t|--report-type <HeapStat>]
```

### <a name="options"></a><span data-ttu-id="f9ca2-150">Opciones</span><span class="sxs-lookup"><span data-stu-id="f9ca2-150">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="f9ca2-151">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-151">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="f9ca2-152">Identificador del proceso del que se va a recopilar el volcado de memoria de GC.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-152">The process ID to collect the GC dump from.</span></span>

- **`-t|--report-type <HeapStat>`**

  <span data-ttu-id="f9ca2-153">Tipo de informe que se va a generar.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-153">The type of report to generate.</span></span> <span data-ttu-id="f9ca2-154">Opciones disponibles: heapstat (predeterminado).</span><span class="sxs-lookup"><span data-stu-id="f9ca2-154">Available options: heapstat (default).</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="f9ca2-155">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="f9ca2-155">Troubleshoot</span></span>

- <span data-ttu-id="f9ca2-156">No hay información de tipo en gcdump.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-156">There is no type information in the gcdump.</span></span>

   <span data-ttu-id="f9ca2-157">Antes de .NET Core 3.1, se producía un problema por el que una memoria caché de tipos no se borraba entre varios gcdump cuando se invocaba con EventPipe.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-157">Prior to .NET Core 3.1, there was an issue where a type cache was not cleared between gcdumps when they were invoked with EventPipe.</span></span> <span data-ttu-id="f9ca2-158">El resultado fue que los eventos necesarios para determinar la información de tipo no se enviaban al segundo gcdump y a los siguientes.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-158">This resulted in the events needed for determining type information not being sent for the second and subsequent gcdumps.</span></span> <span data-ttu-id="f9ca2-159">Esto se corrigió en la versión preliminar 2 de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-159">This was fixed in .NET Core 3.1-preview2.</span></span>

- <span data-ttu-id="f9ca2-160">Los tipos COM y estáticos no se encuentran en el volcado de memoria de GC.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-160">COM and static types aren't in the GC dump.</span></span>

   <span data-ttu-id="f9ca2-161">Antes de la versión preliminar 2 de .NET Core 3.1, se producía un problema por el que los tipos estáticos y COM no se enviaban cuando se invocaba el volcado de memoria de GC a través de EventPipe.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-161">Prior to .NET Core 3.1-preview2, there was an issue where static and COM types weren't sent when the GC dump was invoked via EventPipe.</span></span> <span data-ttu-id="f9ca2-162">Esto se ha corregido en la versión preliminar 2 de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="f9ca2-162">This has been fixed in .NET Core 3.1-preview2.</span></span>
