---
title: Seguimiento de aplicaciones de .NET con PerfCollect.
description: Tutorial en el que se le guía través de la recopilación de un seguimiento con perfcollect en .NET.
ms.topic: tutorial
ms.date: 10/23/2020
ms.openlocfilehash: d6ee77fea5c419e00e684e8b1472278f752544b0
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104874191"
---
# <a name="trace-net-applications-with-perfcollect"></a><span data-ttu-id="3e046-103">Seguimiento de aplicaciones de .NET con PerfCollect</span><span class="sxs-lookup"><span data-stu-id="3e046-103">Trace .NET applications with PerfCollect</span></span>

<span data-ttu-id="3e046-104">**Este artículo se aplica a: ✔️** SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="3e046-104">**This article applies to: ✔️** .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="3e046-105">Cuando se producen problemas de rendimiento en Linux, la recopilación de un seguimiento con `perfcollect` se puede usar para recopilar información detallada sobre lo que ocurre en el equipo en el momento del problema de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="3e046-105">When performance problems are encountered on Linux, collecting a trace with `perfcollect` can be used to gather detailed information about what was happening on the machine at the time of the performance problem.</span></span>

<span data-ttu-id="3e046-106">`perfcollect` es un script de bash que aprovecha [Linux Tracing Tookit-Next Generation (LTTng)](https://lttng.org), el kit de herramientas de seguimiento de Linux de próxima generación, para recopilar eventos escritos en el entorno de ejecución o cualquier elemento [EventSource](xref:System.Diagnostics.Tracing.EventListener), así como [perf](https://perf.wiki.kernel.org/) para recopilar ejemplos de CPU del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="3e046-106">`perfcollect` is a bash script that leverages [Linux Tracing Tookit-Next Generation (LTTng)](https://lttng.org) to collect events written from the runtime or any [EventSource](xref:System.Diagnostics.Tracing.EventListener), as well as [perf](https://perf.wiki.kernel.org/) to collect CPU samples of the target process.</span></span>

## <a name="prepare-your-machine"></a><span data-ttu-id="3e046-107">Preparación del equipo</span><span class="sxs-lookup"><span data-stu-id="3e046-107">Prepare your machine</span></span>

<span data-ttu-id="3e046-108">Siga estos pasos para preparar el equipo a fin de recopilar un seguimiento de rendimiento con `perfcollect`.</span><span class="sxs-lookup"><span data-stu-id="3e046-108">Follow these steps to prepare your machine to collect a performance trace with `perfcollect`.</span></span>

> [!NOTE]
> <span data-ttu-id="3e046-109">Si está en un entorno de contenedor, el contenedor debe tener la funcionalidad `SYS_ADMIN`.</span><span class="sxs-lookup"><span data-stu-id="3e046-109">If you are in a container environment, your container needs to have `SYS_ADMIN` capability.</span></span> <span data-ttu-id="3e046-110">Para obtener más información sobre el seguimiento de aplicaciones dentro de contenedores con PerfCollect, vea [Recopilación de diagnósticos en contenedores](./diagnostics-in-containers.md).</span><span class="sxs-lookup"><span data-stu-id="3e046-110">For more information on tracing applications inside containers using PerfCollect, see [Collect diagnostics in containers](./diagnostics-in-containers.md).</span></span>

1. <span data-ttu-id="3e046-111">Descargue `perfcollect`.</span><span class="sxs-lookup"><span data-stu-id="3e046-111">Download `perfcollect`.</span></span>

    > ```bash
    > curl -OL https://aka.ms/perfcollect
    > ```

2. <span data-ttu-id="3e046-112">Haga que el script sea ejecutable.</span><span class="sxs-lookup"><span data-stu-id="3e046-112">Make the script executable.</span></span>

    > ```bash
    > chmod +x perfcollect
    > ```

3. <span data-ttu-id="3e046-113">Instale los requisitos previos de seguimiento; son las bibliotecas de seguimiento reales.</span><span class="sxs-lookup"><span data-stu-id="3e046-113">Install tracing prerequisites - these are the actual tracing libraries.</span></span>

    > ```bash
    > sudo ./perfcollect install
    > ```

    <span data-ttu-id="3e046-114">Esto instalará los siguientes requisitos previos en el equipo:</span><span class="sxs-lookup"><span data-stu-id="3e046-114">This will install the following prerequisites on your machine:</span></span>

    1. <span data-ttu-id="3e046-115">`perf`: subsistema de eventos de rendimiento de Linux y aplicación complementaria del visor o recopilación de modo de usuario.</span><span class="sxs-lookup"><span data-stu-id="3e046-115">`perf`: the Linux Performance Events subsystem and companion user-mode collection/viewer application.</span></span> <span data-ttu-id="3e046-116">`perf` forma parte del origen del kernel de Linux, pero normalmente no se instala de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3e046-116">`perf` is part of the Linux kernel source, but is not usually installed by default.</span></span>

    2. <span data-ttu-id="3e046-117">`LTTng`: se usa para capturar datos de eventos emitidos en tiempo de ejecución por CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="3e046-117">`LTTng`: Used to capture event data emitted at runtime by CoreCLR.</span></span> <span data-ttu-id="3e046-118">Después, estos datos se usan para analizar el comportamiento de varios componentes del entorno de ejecución, como el GC, JIT y el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="3e046-118">This data is then used to analyze the behavior of various runtime components such as the GC, JIT, and thread pool.</span></span>

<span data-ttu-id="3e046-119">Las versiones recientes de .NET Core y la herramienta perf de Linux admiten la resolución automática de nombres de método para el código del marco.</span><span class="sxs-lookup"><span data-stu-id="3e046-119">Recent versions of .NET Core and the Linux perf tool support automatic resolution of method names for framework code.</span></span> <span data-ttu-id="3e046-120">Si trabaja con la versión 3.1 o anterior de .NET Core, se necesita un paso adicional.</span><span class="sxs-lookup"><span data-stu-id="3e046-120">If you are working with .NET Core version 3.1 or less, an extra step is necessary.</span></span> <span data-ttu-id="3e046-121">Para obtener más información, vea [Resolución de símbolos de marco](#resolve-framework-symbols).</span><span class="sxs-lookup"><span data-stu-id="3e046-121">See [Resolving Framework Symbols](#resolve-framework-symbols) for details.</span></span>

<span data-ttu-id="3e046-122">Para resolver los nombres de métodos de archivos DLL nativos del entorno de ejecución (como libcoreclr.so), `perfcollect` resolverá sus símbolos al convertir los datos, pero solo si los símbolos de estos archivos binarios están presentes.</span><span class="sxs-lookup"><span data-stu-id="3e046-122">For resolving method names of native runtime DLLs (such as libcoreclr.so), `perfcollect` will resolve symbols for them when it converts the data, but only if the symbols for these binaries are present.</span></span> <span data-ttu-id="3e046-123">Para obtener más información, vea la sección [Obtención de símbolos para el entorno de ejecución nativo](#get-symbols-for-the-native-runtime).</span><span class="sxs-lookup"><span data-stu-id="3e046-123">See [Getting Symbols for the Native Runtime](#get-symbols-for-the-native-runtime) section for details.</span></span>

## <a name="collect-a-trace"></a><span data-ttu-id="3e046-124">Recopilación de un seguimiento</span><span class="sxs-lookup"><span data-stu-id="3e046-124">Collect a trace</span></span>

1. <span data-ttu-id="3e046-125">Debe tener dos shells disponibles: uno para controlar el seguimiento, denominado **[Trace]** , y otro para ejecutar la aplicación, denominado **[App]** .</span><span class="sxs-lookup"><span data-stu-id="3e046-125">Have two shells available - one for controlling tracing, referred to as **[Trace]**, and one for running the application, referred to as **[App]**.</span></span>

2. <span data-ttu-id="3e046-126">**[Trace]** Inicie la recolección.</span><span class="sxs-lookup"><span data-stu-id="3e046-126">**[Trace]** Start collection.</span></span>

    > ```bash
    > sudo ./perfcollect collect sampleTrace
    > ```

    <span data-ttu-id="3e046-127">Salida esperada:</span><span class="sxs-lookup"><span data-stu-id="3e046-127">Expected Output:</span></span>

    > ```bash
    > Collection started.  Press CTRL+C to stop.
    > ```

3. <span data-ttu-id="3e046-128">**[App]** Configure el shell de aplicaciones con las variables de entorno siguientes; esto habilita la configuración de seguimiento de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="3e046-128">**[App]** Set up the application shell with the following environment variables - this enables tracing configuration of CoreCLR.</span></span>

    > ```bash
    > export COMPlus_PerfMapEnabled=1
    > export COMPlus_EnableEventLog=1
    > ```

4. <span data-ttu-id="3e046-129">**[App]** Ejecute la aplicación; permita que se ejecute siempre que sea necesario para capturar el problema de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="3e046-129">**[App]** Run the app - let it run as long as you need to in order to capture the performance problem.</span></span> <span data-ttu-id="3e046-130">La longitud exacta puede ser tan breve como sea necesario, siempre y cuando capture el período de tiempo en el que se produce el problema de rendimiento que se quiere investigar.</span><span class="sxs-lookup"><span data-stu-id="3e046-130">The exact length can be as short as you need as long as it sufficiently captures the window of time where the performance problem you want to investigate occurs.</span></span>

    > ```bash
    > dotnet run
    > ```

5. <span data-ttu-id="3e046-131">**[Trace]** Detenga la recolección; presione Ctrl + C.</span><span class="sxs-lookup"><span data-stu-id="3e046-131">**[Trace]** Stop collection - hit CTRL+C.</span></span>

    > ```bash
    > ^C
    > ...STOPPED.
    >
    > Starting post-processing. This may take some time.
    >
    > Generating native image symbol files
    > ...SKIPPED
    > Saving native symbols
    > ...FINISHED
    > Exporting perf.data file
    > ...FINISHED
    > Compressing trace files
    > ...FINISHED
    > Cleaning up artifacts
    > ...FINISHED
    >
    > Trace saved to sampleTrace.trace.zip
    > ```

    <span data-ttu-id="3e046-132">Ahora el archivo de seguimiento comprimido se almacena en el directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="3e046-132">The compressed trace file is now stored in the current working directory.</span></span>

## <a name="view-a-trace"></a><span data-ttu-id="3e046-133">Visualización de un seguimiento</span><span class="sxs-lookup"><span data-stu-id="3e046-133">View a trace</span></span>

<span data-ttu-id="3e046-134">Hay una serie de opciones para ver el seguimiento que se ha recopilado.</span><span class="sxs-lookup"><span data-stu-id="3e046-134">There are a number of options for viewing the trace that was collected.</span></span> <span data-ttu-id="3e046-135">Los seguimientos se ven mejor con [PerfView](https://aka.ms/perfview) en Windows, pero se pueden ver directamente en Linux mediante el propio `PerfCollect` o `TraceCompass`.</span><span class="sxs-lookup"><span data-stu-id="3e046-135">Traces are best viewed using [PerfView](https://aka.ms/perfview) on Windows, but they can be viewed directly on Linux using `PerfCollect` itself or `TraceCompass`.</span></span>

### <a name="use-perfcollect-to-view-the-trace-file"></a><span data-ttu-id="3e046-136">Uso de PerfCollect para ver el archivo de seguimiento</span><span class="sxs-lookup"><span data-stu-id="3e046-136">Use PerfCollect to view the trace file</span></span>

<span data-ttu-id="3e046-137">Puede usar perfcollect para ver el seguimiento que se ha recopilado.</span><span class="sxs-lookup"><span data-stu-id="3e046-137">You can use perfcollect itself to view the trace that you collected.</span></span> <span data-ttu-id="3e046-138">Para ello, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="3e046-138">To do this, use the following command:</span></span>

```bash
./perfcollect view sampleTrace.trace.zip
```

<span data-ttu-id="3e046-139">De forma predeterminada, se mostrará el seguimiento de la CPU de la aplicación mediante `perf`.</span><span class="sxs-lookup"><span data-stu-id="3e046-139">By default, this will show the CPU trace of the application using `perf`.</span></span>

<span data-ttu-id="3e046-140">Para examinar los eventos recopilados a través de `LTTng`, puede pasar la marca `-viewer lttng` a fin de ver los eventos individuales:</span><span class="sxs-lookup"><span data-stu-id="3e046-140">To look at the events that were collected via `LTTng`, you can pass in the flag `-viewer lttng` to see the individual events:</span></span>

```bash
./perfcollect view sampleTrace.trace.zip -viewer lttng
```

<span data-ttu-id="3e046-141">Se usará el visor `babeltrace` para imprimir la carga de eventos:</span><span class="sxs-lookup"><span data-stu-id="3e046-141">This will use `babeltrace` viewer to print the events payload:</span></span>

```bash
# [01:02:18.189217659] (+0.020132603) ubuntu-xenial DotNETRuntime:ExceptionThrown_V1: { cpu_id = 0 }, { ExceptionType = "System.Exception", ExceptionMessage = "An exception happened", ExceptionEIP = 139875671834775, ExceptionHRESULT = 2148734208, ExceptionFlags = 16, ClrInstanceID = 0 }
# [01:02:18.189250227] (+0.020165171) ubuntu-xenial DotNETRuntime:ExceptionCatchStart: { cpu_id = 0 }, { EntryEIP = 139873639728404, MethodID = 139873626968120, MethodName = "void [helloworld] helloworld.Program::Main(string[])", ClrInstanceID = 0 }
```

### <a name="use-perfview-to-open-the-trace-file"></a><span data-ttu-id="3e046-142">Uso de PerfView para abrir el archivo de seguimiento</span><span class="sxs-lookup"><span data-stu-id="3e046-142">Use PerfView to open the trace file</span></span>

<span data-ttu-id="3e046-143">Para ver una vista agregada del ejemplo de CPU y de los eventos, puede usar `PerfView` en un equipo Windows.</span><span class="sxs-lookup"><span data-stu-id="3e046-143">To see an aggregate view of both the CPU sample and the events, you can use `PerfView` on a Windows machine.</span></span>

1. <span data-ttu-id="3e046-144">Copie el archivo trace.zip de Linux en un equipo Windows.</span><span class="sxs-lookup"><span data-stu-id="3e046-144">Copy the trace.zip file from Linux to a Windows machine.</span></span>

2. <span data-ttu-id="3e046-145">Descargue PerfView de <https://aka.ms/perfview>.</span><span class="sxs-lookup"><span data-stu-id="3e046-145">Download PerfView from <https://aka.ms/perfview>.</span></span>

3. <span data-ttu-id="3e046-146">Ejecución de PerfView.exe</span><span class="sxs-lookup"><span data-stu-id="3e046-146">Run PerfView.exe</span></span>

    > ```cmd
    > PerfView.exe <path to trace.zip file>
    > ```

<span data-ttu-id="3e046-147">PerfView mostrará la lista de vistas que se admiten en función de los datos contenidos en el archivo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3e046-147">PerfView will display the list of views that are supported based on the data contained in the trace file.</span></span>

- <span data-ttu-id="3e046-148">Para las investigaciones de CPU, elija **CPU stacks** (Pilas de CPU).</span><span class="sxs-lookup"><span data-stu-id="3e046-148">For CPU investigations, choose **CPU stacks**.</span></span>

- <span data-ttu-id="3e046-149">Para obtener información detallada sobre la recolección de elementos no utilizados, elija **GCStats**.</span><span class="sxs-lookup"><span data-stu-id="3e046-149">For detailed GC information, choose **GCStats**.</span></span>

- <span data-ttu-id="3e046-150">Para obtener información de JIT en función de un proceso, módulo o método, elija **JITStats**.</span><span class="sxs-lookup"><span data-stu-id="3e046-150">For per-process/module/method JIT information, choose **JITStats**.</span></span>

- <span data-ttu-id="3e046-151">Si no hay ninguna vista de la información que necesita, puede intentar buscar los eventos en la vista de eventos sin procesar.</span><span class="sxs-lookup"><span data-stu-id="3e046-151">If there is not a view for the information you need, you can try looking for the events in the raw events view.</span></span>  <span data-ttu-id="3e046-152">Elija **Events** (Eventos).</span><span class="sxs-lookup"><span data-stu-id="3e046-152">Choose **Events**.</span></span>

<span data-ttu-id="3e046-153">Para obtener más información sobre cómo interpretar las vistas en PerfView, vea los vínculos de ayuda en la propia vista, o bien elija **Help > Users Guide** (Ayuda > Guía de usuarios) en la ventana principal de PerfView.</span><span class="sxs-lookup"><span data-stu-id="3e046-153">For more information on how to interpret views in PerfView, see help links in the view itself, or from the main window in PerfView, choose **Help->Users Guide**.</span></span>

> [!NOTE]
> <span data-ttu-id="3e046-154">Los eventos escritos mediante la API <xref:System.Diagnostics.Tracing.EventSource?displayProperty=nameWithType> (incluidos los de Framework) no se mostrarán bajo el nombre de su proveedor.</span><span class="sxs-lookup"><span data-stu-id="3e046-154">Events written via <xref:System.Diagnostics.Tracing.EventSource?displayProperty=nameWithType> API (including the events from Framework) won't show up under their provider name.</span></span> <span data-ttu-id="3e046-155">En su lugar, se escriben como eventos `EventSourceEvent` en el proveedor `Microsoft-Windows-DotNETRuntime` y sus cargas se serializan en JSON.</span><span class="sxs-lookup"><span data-stu-id="3e046-155">Instead, they are written as `EventSourceEvent` events under `Microsoft-Windows-DotNETRuntime` provider and their payloads are JSON serialized.</span></span>

### <a name="use-tracecompass-to-open-the-trace-file"></a><span data-ttu-id="3e046-156">Uso de TraceCompass para abrir el archivo de seguimiento</span><span class="sxs-lookup"><span data-stu-id="3e046-156">Use TraceCompass to open the trace file</span></span>

<span data-ttu-id="3e046-157">[Eclipse TraceCompass](https://www.eclipse.org/tracecompass/) es otra opción que puede usar para ver los seguimientos.</span><span class="sxs-lookup"><span data-stu-id="3e046-157">[Eclipse TraceCompass](https://www.eclipse.org/tracecompass/) is another option you can use to view the traces.</span></span> <span data-ttu-id="3e046-158">`TraceCompass` también funciona en equipos Linux, por lo que no es necesario trasladar el seguimiento a un equipo Windows.</span><span class="sxs-lookup"><span data-stu-id="3e046-158">`TraceCompass` works on Linux machines as well, so you don't need to move your trace over to a Windows machine.</span></span> <span data-ttu-id="3e046-159">Para usar `TraceCompass` y abrir el archivo de seguimiento, tendrá que descomprimirlo.</span><span class="sxs-lookup"><span data-stu-id="3e046-159">To use `TraceCompass` to open your trace file, you will need to unzip the file.</span></span>

```bash
unzip myTrace.trace.zip
```

<span data-ttu-id="3e046-160">`perfcollect` guardará el seguimiento de LTTng que ha recopilado en un formato de archivo CTF en un subdirectorio de `lttngTrace`.</span><span class="sxs-lookup"><span data-stu-id="3e046-160">`perfcollect` will save the LTTng trace it collected into a CTF file format in a subdirectory in the `lttngTrace`.</span></span> <span data-ttu-id="3e046-161">En concreto, el archivo CTF se ubicará en un directorio como `lttngTrace/auto-20201025-101230\ust\uid\1000\64-bit\`.</span><span class="sxs-lookup"><span data-stu-id="3e046-161">Specifically, the CTF file will be located in a directory that looks like `lttngTrace/auto-20201025-101230\ust\uid\1000\64-bit\`.</span></span>

<span data-ttu-id="3e046-162">Puede abrir el archivo de seguimiento CTF en `TraceCompass` si selecciona `File -> Open Trace` y, después, el archivo `metadata`.</span><span class="sxs-lookup"><span data-stu-id="3e046-162">You can open the CTF trace file in `TraceCompass` by selecting `File -> Open Trace` and select the `metadata` file.</span></span>

<span data-ttu-id="3e046-163">Para obtener más información, consulte la [documentación de `TraceCompass`](https://www.eclipse.org/tracecompass/).</span><span class="sxs-lookup"><span data-stu-id="3e046-163">For more details, please refer to [`TraceCompass` documentation](https://www.eclipse.org/tracecompass/).</span></span>

## <a name="resolve-framework-symbols"></a><span data-ttu-id="3e046-164">Resolución de símbolos de marco</span><span class="sxs-lookup"><span data-stu-id="3e046-164">Resolve framework symbols</span></span>

<span data-ttu-id="3e046-165">Los símbolos de marco se deben generar manualmente en el momento de recopilar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3e046-165">Framework symbols need to be manually generated at the time the trace is collected.</span></span> <span data-ttu-id="3e046-166">Son diferentes de los símbolos de nivel de aplicación porque el marco se compila previamente, mientras que el código de la aplicación se compila Just-In-Time.</span><span class="sxs-lookup"><span data-stu-id="3e046-166">They are different than app-level symbols because the framework is pre-compiled while app code is just-in-time-compiled.</span></span> <span data-ttu-id="3e046-167">Para el código de marco precompilado en código nativo, debe llamar a `crossgen`, que sabe cómo generar la asignación desde el código nativo al nombre de los métodos.</span><span class="sxs-lookup"><span data-stu-id="3e046-167">For framework code that was precompiled to native code, you need to call `crossgen` that knows how to generate the mapping from the native code to the name of the methods.</span></span>

<span data-ttu-id="3e046-168">`perfcollect` puede administrar de forma automática la mayoría de los detalles, pero debe tener `crossgen` disponible.</span><span class="sxs-lookup"><span data-stu-id="3e046-168">`perfcollect` can handle most of the details for you, but it needs to have `crossgen` available.</span></span> <span data-ttu-id="3e046-169">De forma predeterminada, no se instala con la distribución de .NET.</span><span class="sxs-lookup"><span data-stu-id="3e046-169">By default it is not installed with .NET distribution.</span></span> <span data-ttu-id="3e046-170">Si `crossgen` no está presente, `perfcollect` muestra una advertencia y le remite a estas instrucciones.</span><span class="sxs-lookup"><span data-stu-id="3e046-170">If `crossgen` is not there, `perfcollect` warns you and refers you to these instructions.</span></span> <span data-ttu-id="3e046-171">Para corregirlo todo, tendrá que capturar exactamente la versión correcta de crossgen para el entorno de ejecución que use.</span><span class="sxs-lookup"><span data-stu-id="3e046-171">To fix things you need to fetch exactly the right version of crossgen for the runtime you are using.</span></span> <span data-ttu-id="3e046-172">Si coloca la herramienta crossgen en el mismo directorio que los archivos DLL del entorno de ejecución de .NET (por ejemplo, libcoreclr.so), `perfcollect` puede encontrarla y agregar de forma automática los símbolos de marco al archivo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3e046-172">If you place the crossgen tool in the same directory as the .NET Runtime DLLs (for example, libcoreclr.so), then `perfcollect` can find it and add the framework symbols to the trace file for you.</span></span>

<span data-ttu-id="3e046-173">Normalmente, al crear una aplicación de .NET, genera el archivo DLL para el código que se ha escrito y usa una copia compartida del entorno de ejecución para el resto.</span><span class="sxs-lookup"><span data-stu-id="3e046-173">Normally when you create a .NET application, it just generates the DLL for the code you wrote, using a shared copy of the runtime for the rest.</span></span>   <span data-ttu-id="3e046-174">Pero también puede generar lo que se denomina una versión "independiente" de una aplicación, que contendrá todos los archivos DLL del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3e046-174">However you can also generate what is called a 'self-contained' version of an application and this contains all runtime DLLs.</span></span> <span data-ttu-id="3e046-175">`crossgen` forma parte del paquete NuGet que se usa para crear aplicaciones independientes, por lo que una manera de obtener la versión correcta de `crossgen` es crear un paquete independiente de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3e046-175">`crossgen` is part of the NuGet package that is used to create self-contained apps, so one way of getting the right version of `crossgen` is to create a self-contained package of your application.</span></span>

<span data-ttu-id="3e046-176">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3e046-176">For example:</span></span>

   >```bash
   > mkdir helloWorld
   > cd helloWorld
   > dotnet new console
   > dotnet publish --self-contained -r linux-x64
   >```

<span data-ttu-id="3e046-177">Esto crea una aplicación Hola mundo y la compila como una aplicación independiente.</span><span class="sxs-lookup"><span data-stu-id="3e046-177">This creates a new Hello World application and builds it as a self-contained app.</span></span>

<span data-ttu-id="3e046-178">Como efecto secundario de la creación de la aplicación independiente, la herramienta dotnet descargará un paquete NuGet denominado runtime.linux-x64.microsoft.netcore.app y lo colocará en el directorio ~/.nuget/packages/runtime.linux-x64.microsoft.netcore.app/VERSIÓN, donde VERSIÓN es el número de versión del entorno de ejecución de .NET Core (por ejemplo, 2.1.0).</span><span class="sxs-lookup"><span data-stu-id="3e046-178">As a side effect of creating the self-contained application the dotnet tool will download a NuGet package called runtime.linux-x64.microsoft.netcore.app and place it in the directory ~/.nuget/packages/runtime.linux-x64.microsoft.netcore.app/VERSION, where VERSION is the version number of your .NET Core runtime (for example, 2.1.0).</span></span> <span data-ttu-id="3e046-179">En él hay un directorio de herramientas, que contiene la herramienta crossgen que necesita.</span><span class="sxs-lookup"><span data-stu-id="3e046-179">Under that is a tools directory and inside there is the crossgen tool you need.</span></span> <span data-ttu-id="3e046-180">A partir de .NET Core 3.0, la ubicación del paquete es ~/.nuget/packages/microsoft.netcore.app.runtime.linux-x64/VERSIÓN.</span><span class="sxs-lookup"><span data-stu-id="3e046-180">Starting with .NET Core 3.0, the package location is ~/.nuget/packages/microsoft.netcore.app.runtime.linux-x64/VERSION.</span></span>

<span data-ttu-id="3e046-181">La herramienta `crossgen` se debe colocar junto al entorno de ejecución que se usa realmente en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3e046-181">The `crossgen` tool needs to be put next to the runtime that is actually used by your application.</span></span> <span data-ttu-id="3e046-182">Normalmente, la aplicación usa la versión compartida de .NET Core que se instala en /usr/share/dotnet/shared/Microsoft.NETCore.App/VERSIÓN, donde VERSIÓN es el número de versión del entorno de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="3e046-182">Typically your app uses the shared version of .NET Core that is installed at /usr/share/dotnet/shared/Microsoft.NETCore.App/VERSION where VERSION is the version number of the .NET Runtime.</span></span> <span data-ttu-id="3e046-183">Se trata de una ubicación compartida, por lo que debe ser superusuario para modificarla.</span><span class="sxs-lookup"><span data-stu-id="3e046-183">This is a shared location, so you need to be super-user to modify it.</span></span> <span data-ttu-id="3e046-184">Si VERSIÓN es 2.1.0, los comandos para actualizar `crossgen` serían los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3e046-184">If the VERSION is 2.1.0 the commands to update `crossgen` would be:</span></span>

   >```bash
   > sudo bash
   > cp ~/.nuget/packages/runtime.linux-x64.microsoft.netcore.app/2.1.0/tools/crossgen /usr/share/dotnet/shared/Microsoft.NETCore.App/2.1.0
   >```

<span data-ttu-id="3e046-185">Una vez que haya hecho esto, `perfcollect` usará crossgen para incluir símbolos de marco.</span><span class="sxs-lookup"><span data-stu-id="3e046-185">Once you have done this, `perfcollect` will use crossgen to include framework symbols.</span></span> <span data-ttu-id="3e046-186">La advertencia que `perfcollect` solía emitir debería desaparecer.</span><span class="sxs-lookup"><span data-stu-id="3e046-186">The warning that `perfcollect` used to issue should go away.</span></span> <span data-ttu-id="3e046-187">Esto solo debe pasar una vez por equipo (hasta que actualice el entorno de ejecución).</span><span class="sxs-lookup"><span data-stu-id="3e046-187">This only has to be one once per machine (until you update your runtime).</span></span>

### <a name="alternative-turn-off-use-of-precompiled-code"></a><span data-ttu-id="3e046-188">Alternativa: Desactivación del uso de código precompilado</span><span class="sxs-lookup"><span data-stu-id="3e046-188">Alternative: Turn off use of precompiled code</span></span>

<span data-ttu-id="3e046-189">Si no tiene la capacidad de actualizar el entorno de ejecución de .NET (para agregar `crossgen`), o bien si el procedimiento anterior no ha funcionado por algún motivo, hay otro enfoque para obtener los símbolos de marco.</span><span class="sxs-lookup"><span data-stu-id="3e046-189">If you don't have the ability to update the .NET Runtime (to add `crossgen`), or if the above procedure did not work for some reason, there is another approach to getting framework symbols.</span></span> <span data-ttu-id="3e046-190">Puede indicarle al entorno de ejecución que simplemente no use el código de marco precompilado.</span><span class="sxs-lookup"><span data-stu-id="3e046-190">You can tell the runtime to simply not use the precompiled framework code.</span></span> <span data-ttu-id="3e046-191">El código se compilará Just-In-Time y `crossgen` no será necesario.</span><span class="sxs-lookup"><span data-stu-id="3e046-191">The code will be Just-In-Time compiled and `crossgen` is not needed.</span></span>

> [!NOTE]
> <span data-ttu-id="3e046-192">La elección de este enfoque puede aumentar el tiempo de inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3e046-192">Choosing this approach may increase the startup time for your application.</span></span>

<span data-ttu-id="3e046-193">Para hacerlo, puede agregar la siguiente variable de entorno:</span><span class="sxs-lookup"><span data-stu-id="3e046-193">To do this, you can add the following environment variable:</span></span>

```bash
export COMPlus_ZapDisable=1
```

<span data-ttu-id="3e046-194">Con este cambio, debería obtener los símbolos para todo el código de .NET.</span><span class="sxs-lookup"><span data-stu-id="3e046-194">With this change, you should get the symbols for all .NET code.</span></span>

## <a name="get-symbols-for-the-native-runtime"></a><span data-ttu-id="3e046-195">Obtención de símbolos para el entorno de ejecución nativo</span><span class="sxs-lookup"><span data-stu-id="3e046-195">Get symbols for the native runtime</span></span>

<span data-ttu-id="3e046-196">En la mayoría de los casos le interesará el código propio, que `perfcollect` resuelve de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3e046-196">Most of the time you are interested in your own code, which `perfcollect` resolves by default.</span></span> <span data-ttu-id="3e046-197">En ocasiones resulta útil ver lo que ocurre dentro de los archivos DLL de .NET (el objetivo de la última sección), pero a veces es interesante lo que sucede en los archivos DLL del entorno de ejecución nativo (normalmente libcoreclr.so).</span><span class="sxs-lookup"><span data-stu-id="3e046-197">Sometimes it is useful to see what is going on inside the .NET DLLs (which is what the last section was about), but sometimes what is going on in the native runtime dlls (typically libcoreclr.so), is interesting.</span></span>  <span data-ttu-id="3e046-198">`perfcollect` resolverá los símbolos para estos archivos DLL al convertir sus datos, pero solo si los símbolos están presentes (y cerca de la biblioteca para la que están destinados).</span><span class="sxs-lookup"><span data-stu-id="3e046-198">`perfcollect` will resolve the symbols for these when it converts its data, but only if the symbols for these native DLLs are present (and are beside the library they are for).</span></span>

<span data-ttu-id="3e046-199">Hay un comando global denominado [dotnet-symbol](https://github.com/dotnet/symstore/blob/main/src/dotnet-symbol/README.md#symbol-downloader-dotnet-cli-extension) que se encarga de ello.</span><span class="sxs-lookup"><span data-stu-id="3e046-199">There is a global command called [dotnet-symbol](https://github.com/dotnet/symstore/blob/main/src/dotnet-symbol/README.md#symbol-downloader-dotnet-cli-extension) that does this.</span></span> <span data-ttu-id="3e046-200">Para usar dotnet-symbol a fin de obtener símbolos del entorno de ejecución nativo:</span><span class="sxs-lookup"><span data-stu-id="3e046-200">To use dotnet-symbol to get native runtime symbols:</span></span>

1. <span data-ttu-id="3e046-201">Instale `dotnet-symbol`:</span><span class="sxs-lookup"><span data-stu-id="3e046-201">Install `dotnet-symbol`:</span></span>

    ```bash
    dotnet tool install -g dotnet-symbol
    ```

2. <span data-ttu-id="3e046-202">Descargue los símbolos.</span><span class="sxs-lookup"><span data-stu-id="3e046-202">Download the symbols.</span></span> <span data-ttu-id="3e046-203">Si la versión instalada del entorno de ejecución de .NET Core es la 2.1.0, el comando para hacerlo es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="3e046-203">If your installed version of the .NET Core runtime is 2.1.0, the command to do this is:</span></span>

    ```bash
    mkdir mySymbols
    dotnet symbol --symbols --output mySymbols  /usr/share/dotnet/shared/Microsoft.NETCore.App/2.1.0/lib*.so
    ```

3. <span data-ttu-id="3e046-204">Copie los símbolos en el lugar correcto.</span><span class="sxs-lookup"><span data-stu-id="3e046-204">Copy the symbols to the correct place.</span></span>

    ```bash
    sudo cp mySymbols/* /usr/share/dotnet/shared/Microsoft.NETCore.App/2.1.0
    ```

    <span data-ttu-id="3e046-205">Si no lo puede hacer porque no tiene acceso de escritura al directorio adecuado, puede usar `perf buildid-cache` para agregar los símbolos.</span><span class="sxs-lookup"><span data-stu-id="3e046-205">If this cannot be done because you do not have write access to the appropriate directory, you can use `perf buildid-cache` to add the symbols.</span></span>

<span data-ttu-id="3e046-206">Después, debe obtener nombres simbólicos para los archivos DLL nativos al ejecutar `perfcollect`.</span><span class="sxs-lookup"><span data-stu-id="3e046-206">After this, you should get symbolic names for the native dlls when you run `perfcollect`.</span></span>

## <a name="collect-in-a-docker-container"></a><span data-ttu-id="3e046-207">Recopilación en un contenedor de Docker</span><span class="sxs-lookup"><span data-stu-id="3e046-207">Collect in a Docker container</span></span>

<span data-ttu-id="3e046-208">Para obtener más información sobre cómo usar `perfcollect` en entornos de contenedor, vea [Recopilación de diagnósticos en contenedores](./diagnostics-in-containers.md).</span><span class="sxs-lookup"><span data-stu-id="3e046-208">For more information on how to use `perfcollect` in container environments, see [Collect diagnostics in containers](./diagnostics-in-containers.md).</span></span>

## <a name="learn-more-about-collection-options"></a><span data-ttu-id="3e046-209">Más información sobre las opciones de recopilación</span><span class="sxs-lookup"><span data-stu-id="3e046-209">Learn more about collection options</span></span>

<span data-ttu-id="3e046-210">Puede especificar las siguientes marcas opcionales con `perfcollect` para que se adapte mejor a sus necesidades de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="3e046-210">You can specify the following optional flags with `perfcollect` to better suit your diagnostic needs.</span></span>

### <a name="collect-for-a-specific-duration"></a><span data-ttu-id="3e046-211">Recopilación con una duración específica</span><span class="sxs-lookup"><span data-stu-id="3e046-211">Collect for a specific duration</span></span>

<span data-ttu-id="3e046-212">Si quiere recopilar un seguimiento con una duración específica, puede usar la opción `-collectsec` seguida de un número que especifique el total de segundos durante los que se va a recopilar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3e046-212">When you want to collect a trace for a specific duration, you can use `-collectsec` option followed by a number specifying the total seconds to collect a trace for.</span></span>

### <a name="collect-threadtime-traces"></a><span data-ttu-id="3e046-213">Recopilación de seguimientos de tiempo de subproceso</span><span class="sxs-lookup"><span data-stu-id="3e046-213">Collect threadtime traces</span></span>

<span data-ttu-id="3e046-214">Si especifica `-threadtime` con `perfcollect`, podrá recopilar datos de uso de CPU por subproceso.</span><span class="sxs-lookup"><span data-stu-id="3e046-214">Specifying `-threadtime` with `perfcollect` lets you collect per-thread CPU usage data.</span></span> <span data-ttu-id="3e046-215">Esto le permite analizar el lugar en el que está consumiendo su tiempo de CPU cada subproceso.</span><span class="sxs-lookup"><span data-stu-id="3e046-215">This lets you analyze where every thread was spending its CPU time.</span></span>

### <a name="collect-traces-for-managed-memory-and-garbage-collector-performance"></a><span data-ttu-id="3e046-216">Recopilación de seguimientos de memoria administrada y rendimiento del recolector de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="3e046-216">Collect traces for managed memory and garbage collector performance</span></span>

<span data-ttu-id="3e046-217">Las siguientes opciones le permiten recopilar específicamente los eventos de GC del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3e046-217">The following options let you specifically collect the GC events from the runtime.</span></span>

* `perfcollect collect -gccollectonly`

<span data-ttu-id="3e046-218">Recopile solo un conjunto mínimo de eventos de recopilación de GC.</span><span class="sxs-lookup"><span data-stu-id="3e046-218">Collect only a minimal set of GC Collection events.</span></span> <span data-ttu-id="3e046-219">Este es el perfil de recopilación de eventos de GC menos detallado y con el menor impacto en el rendimiento de la aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="3e046-219">This is the least verbose GC eventing collection profile with the lowest impact on the target app's performance.</span></span> <span data-ttu-id="3e046-220">Este comando es análogo al comando `PerfView.exe /GCCollectOnly collect` en PerfView.</span><span class="sxs-lookup"><span data-stu-id="3e046-220">This command is analogous to `PerfView.exe /GCCollectOnly collect` command in PerfView.</span></span>

* `perfcollect collect -gconly`

<span data-ttu-id="3e046-221">Recopile eventos de recopilación de GC más detallados con eventos JIT, Loader y de excepción.</span><span class="sxs-lookup"><span data-stu-id="3e046-221">Collect more verbose GC collection events with JIT, Loader, and Exception events.</span></span> <span data-ttu-id="3e046-222">Esto solicita eventos más detallados (como la información de asignación y la información de combinación de GC) y tendrá un impacto mayor en el rendimiento de la aplicación de destino que la opción `-gccollectonly`.</span><span class="sxs-lookup"><span data-stu-id="3e046-222">This requests more verbose events (such as the allocation information and GC join information) and will have more impact to the target app's performance than `-gccollectonly` option.</span></span> <span data-ttu-id="3e046-223">Este comando es análogo al comando `PerfView.exe /GCOnly collect` en PerfView.</span><span class="sxs-lookup"><span data-stu-id="3e046-223">This command is analogous to `PerfView.exe /GCOnly collect` command in PerfView.</span></span>

* `perfcollect collect -gcwithheap`

<span data-ttu-id="3e046-224">Recopile los eventos de recopilación de GC más detallados; incluye también un seguimiento de los movimientos y la supervivencia del montón.</span><span class="sxs-lookup"><span data-stu-id="3e046-224">Collect the most verbose GC collection events which tracks the heap survival and movements as well.</span></span> <span data-ttu-id="3e046-225">Esto proporciona un análisis exhaustivo del comportamiento del GC, pero incurrirá en un costo de alto rendimiento, ya que cada GC puede tardar más del doble.</span><span class="sxs-lookup"><span data-stu-id="3e046-225">This gives in-depth analysis of the GC behavior but will incur high performance cost as each GC can take more than two times longer.</span></span> <span data-ttu-id="3e046-226">Es recomendable que comprenda la implicación del rendimiento del uso de esta opción de seguimiento cuando realice el seguimiento en entornos de producción.</span><span class="sxs-lookup"><span data-stu-id="3e046-226">It is recommended you understand the performance implication of using this trace option when tracing in production environments.</span></span>
