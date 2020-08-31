---
title: 'dotnet-gcdump: .NET Core'
description: Instalación y uso de la herramienta de línea de comandos dotnet-gcdump.
ms.date: 07/26/2020
ms.openlocfilehash: a7b19f4d7487677b975621e7267a17894dae2e3a
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656656"
---
# <a name="heap-analysis-tool-dotnet-gcdump"></a><span data-ttu-id="4df4e-103">Herramienta de análisis del montón (dotnet-gcdump)</span><span class="sxs-lookup"><span data-stu-id="4df4e-103">Heap analysis tool (dotnet-gcdump)</span></span>

<span data-ttu-id="4df4e-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="4df4e-104">**This article applies to:** ✔️ .NET Core 3.1 SDK and later versions</span></span>

## <a name="install-dotnet-gcdump"></a><span data-ttu-id="4df4e-105">Instalación de dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="4df4e-105">Install dotnet-gcdump</span></span>

<span data-ttu-id="4df4e-106">Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-gcdump) de `dotnet-gcdump`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="4df4e-106">To install the latest release version of the `dotnet-gcdump` [NuGet package](https://www.nuget.org/packages/dotnet-gcdump), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install -g dotnet-gcdump
```

## <a name="synopsis"></a><span data-ttu-id="4df4e-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="4df4e-107">Synopsis</span></span>

```console
dotnet-gcdump [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="4df4e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="4df4e-108">Description</span></span>

<span data-ttu-id="4df4e-109">La herramienta global `dotnet-gcdump` permite recopilar volcados de memoria de GC (recolector de elementos no utilizados) de procesos de .NET dinámicos.</span><span class="sxs-lookup"><span data-stu-id="4df4e-109">The `dotnet-gcdump` global tool is a way to collect GC (Garbage Collector) dumps of live .NET processes.</span></span> <span data-ttu-id="4df4e-110">Usa la tecnología EventPipe, que es una alternativa multiplataforma a ETW en Windows.</span><span class="sxs-lookup"><span data-stu-id="4df4e-110">It uses the EventPipe technology, which is a cross-platform alternative to ETW on Windows.</span></span> <span data-ttu-id="4df4e-111">Los volcados de memoria de GC se crean desencadenando un GC en el proceso de destino, activando eventos especiales y regenerando el gráfico de raíces de objeto a partir del flujo de eventos.</span><span class="sxs-lookup"><span data-stu-id="4df4e-111">GC dumps are created by triggering a GC in the target process, turning on special events, and regenerating the graph of object roots from the event stream.</span></span> <span data-ttu-id="4df4e-112">Este proceso permite recopilar volcados de memoria de GC mientras el proceso se está ejecutando y con una sobrecarga mínima.</span><span class="sxs-lookup"><span data-stu-id="4df4e-112">This process allows for GC dumps to be collected while the process is running and with minimal overhead.</span></span> <span data-ttu-id="4df4e-113">Estos volcados de memoria son útiles para varios escenarios:</span><span class="sxs-lookup"><span data-stu-id="4df4e-113">These dumps are useful for several scenarios:</span></span>

- <span data-ttu-id="4df4e-114">Comparar el número de objetos del montón en varios puntos en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="4df4e-114">Comparing the number of objects on the heap at several points in time.</span></span>
- <span data-ttu-id="4df4e-115">Analizar raíces de objetos (responder a preguntas como "¿qué sigue teniendo una referencia a este tipo?").</span><span class="sxs-lookup"><span data-stu-id="4df4e-115">Analyzing roots of objects (answering questions like, "what still has a reference to this type?").</span></span>
- <span data-ttu-id="4df4e-116">Recopilar estadísticas generales sobre los recuentos de objetos en el montón.</span><span class="sxs-lookup"><span data-stu-id="4df4e-116">Collecting general statistics about the counts of objects on the heap.</span></span>

### <a name="view-the-gc-dump-captured-from-dotnet-gcdump"></a><span data-ttu-id="4df4e-117">Ver el volcado de memoria de GC capturado por dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="4df4e-117">View the GC dump captured from dotnet-gcdump</span></span>

<span data-ttu-id="4df4e-118">En Windows, los archivos `.gcdump` se pueden ver en [PerfView](https://github.com/microsoft/perfview) o en Visual Studio para analizarlos.</span><span class="sxs-lookup"><span data-stu-id="4df4e-118">On Windows, `.gcdump` files can be viewed in [PerfView](https://github.com/microsoft/perfview) for analysis or in Visual Studio.</span></span> <span data-ttu-id="4df4e-119">Actualmente, no es posible abrir un archivo `.gcdump` en plataformas que no sean de Windows.</span><span class="sxs-lookup"><span data-stu-id="4df4e-119">Currently, There is no way of opening a `.gcdump` on non-Windows platforms.</span></span>

<span data-ttu-id="4df4e-120">Puede recopilar varios archivos `.gcdump` y abrirlos simultáneamente en Visual Studio para obtener una comparativa.</span><span class="sxs-lookup"><span data-stu-id="4df4e-120">You can collect multiple `.gcdump`s and open them simultaneously in Visual Studio to get a comparison experience.</span></span>

## <a name="options"></a><span data-ttu-id="4df4e-121">Opciones</span><span class="sxs-lookup"><span data-stu-id="4df4e-121">Options</span></span>

- **`--version`**

  <span data-ttu-id="4df4e-122">Muestra la versión del servicio `dotnet-gcdump`.</span><span class="sxs-lookup"><span data-stu-id="4df4e-122">Displays the version of the `dotnet-gcdump` utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="4df4e-123">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="4df4e-123">Shows command-line help.</span></span>

## `dotnet-gcdump collect`

<span data-ttu-id="4df4e-124">Recopila un volcado de memoria de GC de un proceso que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="4df4e-124">Collects a GC dump from a currently running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="4df4e-125">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="4df4e-125">Synopsis</span></span>

```console
dotnet-gcdump collect [-h|--help] [-p|--process-id <pid>] [-o|--output <gcdump-file-path>] [-v|--verbose] [-t|--timeout <timeout>] [-n|--name <name>]
```

### <a name="options"></a><span data-ttu-id="4df4e-126">Opciones</span><span class="sxs-lookup"><span data-stu-id="4df4e-126">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="4df4e-127">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="4df4e-127">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="4df4e-128">Identificador del proceso del que se va a recopilar el volcado de memoria de GC.</span><span class="sxs-lookup"><span data-stu-id="4df4e-128">The process ID to collect the GC dump from.</span></span>

- **`-o|--output <gcdump-file-path>`**

  <span data-ttu-id="4df4e-129">Ruta de acceso donde se deben escribir los volcados de memoria de GC recopilados.</span><span class="sxs-lookup"><span data-stu-id="4df4e-129">The path where collected GC dumps should be written.</span></span> <span data-ttu-id="4df4e-130">El valor predeterminado es *.\\AAAAMMDD\_HHMMSS\_\<pid>.gcdump*.</span><span class="sxs-lookup"><span data-stu-id="4df4e-130">Defaults to *.\\YYYYMMDD\_HHMMSS\_\<pid>.gcdump*.</span></span>

- **`-v|--verbose`**

  <span data-ttu-id="4df4e-131">Obtener resultados del registro mientras recopila el volcado de memoria de GC.</span><span class="sxs-lookup"><span data-stu-id="4df4e-131">Output the log while collecting the GC dump.</span></span>

- **`-t|--timeout <timeout>`**

  <span data-ttu-id="4df4e-132">Dejar de recopilar el volcado de memoria de GC si tarda más de la cantidad de segundos indicada.</span><span class="sxs-lookup"><span data-stu-id="4df4e-132">Give up on collecting the GC dump if it takes longer than this many seconds.</span></span> <span data-ttu-id="4df4e-133">El valor predeterminado es 30.</span><span class="sxs-lookup"><span data-stu-id="4df4e-133">The default value is 30.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="4df4e-134">Nombre del proceso del que se va a recopilar el volcado de memoria de GC.</span><span class="sxs-lookup"><span data-stu-id="4df4e-134">The name of the process to collect the GC dump from.</span></span>

## `dotnet-gcdump ps`

<span data-ttu-id="4df4e-135">Enumera los procesos de dotnet de los que se pueden recopilar volcados de memoria de GC.</span><span class="sxs-lookup"><span data-stu-id="4df4e-135">Lists the dotnet processes that GC dumps can be collected for.</span></span>

### <a name="synopsis"></a><span data-ttu-id="4df4e-136">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="4df4e-136">Synopsis</span></span>

```console
dotnet-gcdump ps
```

## `dotnet-gcdump report <gcdump_filename>`

<span data-ttu-id="4df4e-137">Crear un informe a partir de un volcado de memoria de GC generado anteriormente o de un proceso en ejecución y escribir en `stdout`.</span><span class="sxs-lookup"><span data-stu-id="4df4e-137">Generate a report from a previously generated GC dump or from a running process, and write to `stdout`.</span></span>

### <a name="synopsis"></a><span data-ttu-id="4df4e-138">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="4df4e-138">Synopsis</span></span>

```console
dotnet-gcdump report [-h|--help] [-p|--process-id <pid>] [-t|--report-type <HeapStat>]
```

### <a name="options"></a><span data-ttu-id="4df4e-139">Opciones</span><span class="sxs-lookup"><span data-stu-id="4df4e-139">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="4df4e-140">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="4df4e-140">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="4df4e-141">Identificador del proceso del que se va a recopilar el volcado de memoria de GC.</span><span class="sxs-lookup"><span data-stu-id="4df4e-141">The process ID to collect the GC dump from.</span></span>

- **`-t|--report-type <HeapStat>`**

  <span data-ttu-id="4df4e-142">Tipo de informe que se va a generar.</span><span class="sxs-lookup"><span data-stu-id="4df4e-142">The type of report to generate.</span></span> <span data-ttu-id="4df4e-143">Opciones disponibles: heapstat (predeterminado).</span><span class="sxs-lookup"><span data-stu-id="4df4e-143">Available options: heapstat (default).</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="4df4e-144">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="4df4e-144">Troubleshoot</span></span>

- <span data-ttu-id="4df4e-145">No hay información de tipo en gcdump.</span><span class="sxs-lookup"><span data-stu-id="4df4e-145">There is no type information in the gcdump.</span></span>

   <span data-ttu-id="4df4e-146">Antes de .NET Core 3.1, se producía un problema por el que una memoria caché de tipos no se borraba entre varios gcdump cuando se invocaba con EventPipe.</span><span class="sxs-lookup"><span data-stu-id="4df4e-146">Prior to .NET Core 3.1, there was an issue where a type cache was not cleared between gcdumps when they were invoked with EventPipe.</span></span> <span data-ttu-id="4df4e-147">El resultado fue que los eventos necesarios para determinar la información de tipo no se enviaban al segundo gcdump y a los siguientes.</span><span class="sxs-lookup"><span data-stu-id="4df4e-147">This resulted in the events needed for determining type information not being sent for the second and subsequent gcdumps.</span></span> <span data-ttu-id="4df4e-148">Esto se corrigió en la versión preliminar 2 de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="4df4e-148">This was fixed in .NET Core 3.1-preview2.</span></span>

- <span data-ttu-id="4df4e-149">Los tipos COM y estáticos no se encuentran en el volcado de memoria de GC.</span><span class="sxs-lookup"><span data-stu-id="4df4e-149">COM and static types aren't in the GC dump.</span></span>

   <span data-ttu-id="4df4e-150">Antes de la versión preliminar 2 de .NET Core 3.1, se producía un problema por el que los tipos estáticos y COM no se enviaban cuando se invocaba el volcado de memoria de GC a través de EventPipe.</span><span class="sxs-lookup"><span data-stu-id="4df4e-150">Prior to .NET Core 3.1-preview2, there was an issue where static and COM types weren't sent when the GC dump was invoked via EventPipe.</span></span> <span data-ttu-id="4df4e-151">Esto se ha corregido en la versión preliminar 2 de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="4df4e-151">This has been fixed in .NET Core 3.1-preview2.</span></span>
