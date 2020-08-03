---
title: Tutorial Depuración de una fuga de memoria
description: Obtenga información sobre cómo depurar una fuga de memoria en .NET Core.
ms.topic: tutorial
ms.date: 04/20/2020
ms.openlocfilehash: ff684f9b9402cb8b7b648e792a1d37ddcc96b399
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86924895"
---
# <a name="debug-a-memory-leak-in-net-core"></a><span data-ttu-id="1075a-103">Depuración de una fuga de memoria en .NET Core</span><span class="sxs-lookup"><span data-stu-id="1075a-103">Debug a memory leak in .NET Core</span></span>

<span data-ttu-id="1075a-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="1075a-104">**This article applies to:** ✔️ .NET Core 3.1 SDK and later versions</span></span>

<span data-ttu-id="1075a-105">En este tutorial se muestran las herramientas para analizar una fuga de memoria de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1075a-105">This tutorial demonstrates the tools to analyze a .NET Core memory leak.</span></span>

<span data-ttu-id="1075a-106">En este tutorial se usa una aplicación de ejemplo, diseñada para perder memoria de manera intencionada.</span><span class="sxs-lookup"><span data-stu-id="1075a-106">This tutorial uses a sample app, which is designed to intentionally leak memory.</span></span> <span data-ttu-id="1075a-107">El ejemplo se proporciona como ejercicio.</span><span class="sxs-lookup"><span data-stu-id="1075a-107">The sample is provided as an exercise.</span></span> <span data-ttu-id="1075a-108">Asimismo, puede analizar una aplicación que pierda memoria involuntariamente.</span><span class="sxs-lookup"><span data-stu-id="1075a-108">You can analyze an app that is unintentionally leaking memory too.</span></span>

<span data-ttu-id="1075a-109">En este tutorial va a:</span><span class="sxs-lookup"><span data-stu-id="1075a-109">In this tutorial, you will:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="1075a-110">Examinar el uso de memoria administrada con [dotnet-counters](dotnet-counters.md).</span><span class="sxs-lookup"><span data-stu-id="1075a-110">Examine managed memory usage with [dotnet-counters](dotnet-counters.md).</span></span>
> - <span data-ttu-id="1075a-111">Generar un archivo de volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="1075a-111">Generate a dump file.</span></span>
> - <span data-ttu-id="1075a-112">Analizar el uso de memoria mediante el archivo de volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="1075a-112">Analyze the memory usage using the dump file.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1075a-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1075a-113">Prerequisites</span></span>

<span data-ttu-id="1075a-114">En el tutorial se usa:</span><span class="sxs-lookup"><span data-stu-id="1075a-114">The tutorial uses:</span></span>

- <span data-ttu-id="1075a-115">[SDK de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core) o una versión posterior</span><span class="sxs-lookup"><span data-stu-id="1075a-115">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core) or a later version.</span></span>
- <span data-ttu-id="1075a-116">[dotnet-trace](dotnet-trace.md) para mostrar procesos.</span><span class="sxs-lookup"><span data-stu-id="1075a-116">[dotnet-trace](dotnet-trace.md) to list processes.</span></span>
- <span data-ttu-id="1075a-117">[dotnet-counters](dotnet-counters.md) para comprobar el uso de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="1075a-117">[dotnet-counters](dotnet-counters.md) to check managed memory usage.</span></span>
- <span data-ttu-id="1075a-118">[dotnet-dump](dotnet-dump.md) para recopilar y analizar un archivo de volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="1075a-118">[dotnet-dump](dotnet-dump.md) to collect and analyze a dump file.</span></span>
- <span data-ttu-id="1075a-119">Una aplicación de [destino de depuración de ejemplo](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) que se va a diagnosticar.</span><span class="sxs-lookup"><span data-stu-id="1075a-119">A [sample debug target](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) app to diagnose.</span></span>

<span data-ttu-id="1075a-120">En el tutorial se da por supuesto que el ejemplo y las herramientas están instalados y listos para usarse.</span><span class="sxs-lookup"><span data-stu-id="1075a-120">The tutorial assumes the sample and tools are installed and ready to use.</span></span>

## <a name="examine-managed-memory-usage"></a><span data-ttu-id="1075a-121">Análisis del uso de memoria administrada</span><span class="sxs-lookup"><span data-stu-id="1075a-121">Examine managed memory usage</span></span>

<span data-ttu-id="1075a-122">Antes de empezar a recopilar datos de diagnóstico que nos ayuden a establecer la causa principal de este escenario, debe asegurarse de que realmente está viendo una fuga de memoria (crecimiento de memoria).</span><span class="sxs-lookup"><span data-stu-id="1075a-122">Before you start collecting diagnostics data to help us root cause this scenario, you need to make sure you're actually seeing a memory leak (memory growth).</span></span> <span data-ttu-id="1075a-123">Puede usar la herramienta [dotnet-counters](dotnet-counters.md) para confirmar eso.</span><span class="sxs-lookup"><span data-stu-id="1075a-123">You can use the [dotnet-counters](dotnet-counters.md) tool to confirm that.</span></span>

<span data-ttu-id="1075a-124">Abra una ventana de consola y vaya al directorio donde descargó y descomprimió el [destino de depuración de ejemplo](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/).</span><span class="sxs-lookup"><span data-stu-id="1075a-124">Open a console window and navigate to the directory where you downloaded and unzipped the [sample debug target](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/).</span></span> <span data-ttu-id="1075a-125">Ejecute el destino:</span><span class="sxs-lookup"><span data-stu-id="1075a-125">Run the target:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="1075a-126">En una consola independiente, busque el identificador del proceso mediante la herramienta [dotnet-trace](dotnet-trace.md):</span><span class="sxs-lookup"><span data-stu-id="1075a-126">From a separate console, find the process ID using the [dotnet-trace](dotnet-trace.md) tool:</span></span>

```console
dotnet-trace ps
```

<span data-ttu-id="1075a-127">La salida debe ser similar a:</span><span class="sxs-lookup"><span data-stu-id="1075a-127">The output should be similar to:</span></span>

```console
4807 DiagnosticScena /home/user/git/samples/core/diagnostics/DiagnosticScenarios/bin/Debug/netcoreapp3.0/DiagnosticScenarios
```

<span data-ttu-id="1075a-128">Ahora, compruebe el uso de memoria administrada con la herramienta [dotnet-counters](dotnet-counters.md).</span><span class="sxs-lookup"><span data-stu-id="1075a-128">Now, check managed memory usage with the [dotnet-counters](dotnet-counters.md) tool.</span></span> <span data-ttu-id="1075a-129">`--refresh-interval` especifica el número de segundos entre las actualizaciones:</span><span class="sxs-lookup"><span data-stu-id="1075a-129">The `--refresh-interval` specifies the number of seconds between refreshes:</span></span>

```console
dotnet-counters monitor --refresh-interval 1 -p 4807
```

<span data-ttu-id="1075a-130">La salida en directo debe ser similar a:</span><span class="sxs-lookup"><span data-stu-id="1075a-130">The live output should be similar to:</span></span>

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[System.Runtime]
    # of Assemblies Loaded                           118
    % Time in GC (since last GC)                       0
    Allocation Rate (Bytes / sec)                 37,896
    CPU Usage (%)                                      0
    Exceptions / sec                                   0
    GC Heap Size (MB)                                  4
    Gen 0 GC / sec                                     0
    Gen 0 Size (B)                                     0
    Gen 1 GC / sec                                     0
    Gen 1 Size (B)                                     0
    Gen 2 GC / sec                                     0
    Gen 2 Size (B)                                     0
    LOH Size (B)                                       0
    Monitor Lock Contention Count / sec                0
    Number of Active Timers                            1
    ThreadPool Completed Work Items / sec             10
    ThreadPool Queue Length                            0
    ThreadPool Threads Count                           1
    Working Set (MB)                                  83
```

<span data-ttu-id="1075a-131">Establecimiento del foco en esta línea:</span><span class="sxs-lookup"><span data-stu-id="1075a-131">Focusing on this line:</span></span>

```console
    GC Heap Size (MB)                                  4
```

<span data-ttu-id="1075a-132">Puede ver que la memoria de montón administrado es de 4 MB justo después del inicio.</span><span class="sxs-lookup"><span data-stu-id="1075a-132">You can see that the managed heap memory is 4 MB right after startup.</span></span>

<span data-ttu-id="1075a-133">Ahora, visite la dirección URL `https://localhost:5001/api/diagscenario/memleak/20000`.</span><span class="sxs-lookup"><span data-stu-id="1075a-133">Now, hit the URL `https://localhost:5001/api/diagscenario/memleak/20000`.</span></span>

<span data-ttu-id="1075a-134">Observe que el uso de memoria ha aumentado a 30 MB.</span><span class="sxs-lookup"><span data-stu-id="1075a-134">Observe that the memory usage has grown to 30 MB.</span></span>

```console
    GC Heap Size (MB)                                 30
```

<span data-ttu-id="1075a-135">Al observar el uso de memoria, puede indicar con seguridad el aumento o la fuga de memoria.</span><span class="sxs-lookup"><span data-stu-id="1075a-135">By watching the memory usage, you can safely say that memory is growing or leaking.</span></span> <span data-ttu-id="1075a-136">El siguiente paso consiste en recopilar los datos adecuados para el análisis de memoria.</span><span class="sxs-lookup"><span data-stu-id="1075a-136">The next step is to collect the right data for memory analysis.</span></span>

### <a name="generate-memory-dump"></a><span data-ttu-id="1075a-137">Generación de un volcado de memoria</span><span class="sxs-lookup"><span data-stu-id="1075a-137">Generate memory dump</span></span>

<span data-ttu-id="1075a-138">Al analizar posibles fugas de memoria, debe tener acceso al montón de memoria de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1075a-138">When analyzing possible memory leaks, you need access to the app's memory heap.</span></span> <span data-ttu-id="1075a-139">A continuación, puede analizar el contenido de la memoria.</span><span class="sxs-lookup"><span data-stu-id="1075a-139">Then you can analyze the memory contents.</span></span> <span data-ttu-id="1075a-140">Al observarse las relaciones entre los objetos, se crean teorías de por qué no se libera la memoria.</span><span class="sxs-lookup"><span data-stu-id="1075a-140">Looking at relationships between objects, you create theories on why memory isn't being freed.</span></span> <span data-ttu-id="1075a-141">Un origen de datos de diagnóstico habitual es un volcado de memoria en Windows o el volcado de memoria principal equivalente en Linux.</span><span class="sxs-lookup"><span data-stu-id="1075a-141">A common diagnostics data source is a memory dump on Windows or the equivalent core dump on Linux.</span></span> <span data-ttu-id="1075a-142">Para generar un volcado de memoria de una aplicación .NET Core, puede usar la herramienta [dotnet-dump)](dotnet-dump.md).</span><span class="sxs-lookup"><span data-stu-id="1075a-142">To generate a dump of a .NET Core application, you can use the [dotnet-dump)](dotnet-dump.md) tool.</span></span>

<span data-ttu-id="1075a-143">Con el [destino de depuración de ejemplo](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) iniciado anteriormente, ejecute el siguiente comando para generar un volcado de memoria principal de Linux:</span><span class="sxs-lookup"><span data-stu-id="1075a-143">Using the [sample debug target](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) previously started, run the following command to generate a Linux core dump:</span></span>

```dotnetcli
dotnet-dump collect -p 4807
```

<span data-ttu-id="1075a-144">El resultado es un volcado de memoria principal ubicado en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="1075a-144">The result is a core dump located in the same folder.</span></span>

```console
Writing minidump with heap to ./core_20190430_185145
Complete
```

### <a name="restart-the-failed-process"></a><span data-ttu-id="1075a-145">Reinicio del proceso con errores</span><span class="sxs-lookup"><span data-stu-id="1075a-145">Restart the failed process</span></span>

<span data-ttu-id="1075a-146">Una vez recopilado el volcado de memoria, debe tener suficiente información para diagnosticar el proceso con errores.</span><span class="sxs-lookup"><span data-stu-id="1075a-146">Once the dump is collected, you should have sufficient information to diagnose the failed process.</span></span> <span data-ttu-id="1075a-147">Si el proceso con errores se ejecuta en un servidor de producción, ahora es el momento ideal para la corrección a corto plazo reiniciando el proceso.</span><span class="sxs-lookup"><span data-stu-id="1075a-147">If the failed process is running on a production server, now it's the ideal time for short-term remediation by restarting the process.</span></span>

<span data-ttu-id="1075a-148">En este tutorial, ya ha terminado con el [destino de depuración de ejemplo](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) y puede cerrarlo.</span><span class="sxs-lookup"><span data-stu-id="1075a-148">In this tutorial, you're now done with the [Sample debug target](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) and you can close it.</span></span> <span data-ttu-id="1075a-149">Vaya al terminal que inició el servidor y presione <kbd>CTRL+C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="1075a-149">Navigate to the terminal that started the server, and press <kbd>Ctrl+C</kbd>.</span></span>

### <a name="analyze-the-core-dump"></a><span data-ttu-id="1075a-150">Análisis del volcado de memoria principal</span><span class="sxs-lookup"><span data-stu-id="1075a-150">Analyze the core dump</span></span>

<span data-ttu-id="1075a-151">Ahora que ha generado un volcado de memoria principal, use la herramienta [dotnet-dump](dotnet-dump.md) para analizar el volcado de memoria:</span><span class="sxs-lookup"><span data-stu-id="1075a-151">Now that you have a core dump generated, use the [dotnet-dump](dotnet-dump.md) tool to analyze the dump:</span></span>

```dotnetcli
dotnet-dump analyze core_20190430_185145
```

<span data-ttu-id="1075a-152">Donde `core_20190430_185145` es el nombre del volcado de memoria principal que desea analizar.</span><span class="sxs-lookup"><span data-stu-id="1075a-152">Where `core_20190430_185145` is the name of the core dump you want to analyze.</span></span>

> [!NOTE]
> <span data-ttu-id="1075a-153">Si ve un error que indica que no se encuentra *libdl.so*, es posible que tenga que instalar el paquete *libc6-dev*.</span><span class="sxs-lookup"><span data-stu-id="1075a-153">If you see an error complaining that *libdl.so* cannot be found, you may have to install the *libc6-dev* package.</span></span> <span data-ttu-id="1075a-154">Para más información, consulte [Requisitos previos para .NET Core en Linux](../install/dependencies.md?pivots=os-linux).</span><span class="sxs-lookup"><span data-stu-id="1075a-154">For more information, see [Prerequisites for .NET Core on Linux](../install/dependencies.md?pivots=os-linux).</span></span>

<span data-ttu-id="1075a-155">Se le mostrará un mensaje en el que puede escribir comandos SOS.</span><span class="sxs-lookup"><span data-stu-id="1075a-155">You'll be presented with a prompt where you can enter SOS commands.</span></span> <span data-ttu-id="1075a-156">Normalmente, lo primero que desea ver es el estado general del montón administrado:</span><span class="sxs-lookup"><span data-stu-id="1075a-156">Commonly, the first thing you want to look at is the overall state of the managed heap:</span></span>

```console
> dumpheap -stat

Statistics:
              MT    Count    TotalSize Class Name
...
00007f6c1eeefba8      576        59904 System.Reflection.RuntimeMethodInfo
00007f6c1dc021c8     1749        95696 System.SByte[]
00000000008c9db0     3847       116080      Free
00007f6c1e784a18      175       128640 System.Char[]
00007f6c1dbf5510      217       133504 System.Object[]
00007f6c1dc014c0      467       416464 System.Byte[]
00007f6c21625038        6      4063376 testwebapi.Controllers.Customer[]
00007f6c20a67498   200000      4800000 testwebapi.Controllers.Customer
00007f6c1dc00f90   206770     19494060 System.String
Total 428516 objects
```

<span data-ttu-id="1075a-157">Aquí puede ver que la mayoría de los objetos son objetos `String` o `Customer`.</span><span class="sxs-lookup"><span data-stu-id="1075a-157">Here you can see that most objects are either `String` or `Customer` objects.</span></span>

<span data-ttu-id="1075a-158">Puede volver a usar el comando `dumpheap` con la tabla del método (MT) para obtener una lista de todas las instancias de `String`:</span><span class="sxs-lookup"><span data-stu-id="1075a-158">You can use the `dumpheap` command again with the method table (MT) to get a list of all the `String` instances:</span></span>

```console
> dumpheap -mt 00007faddaa50f90

         Address               MT     Size
...
00007f6ad09421f8 00007faddaa50f90       94
...
00007f6ad0965b20 00007f6c1dc00f90       80
00007f6ad0965c10 00007f6c1dc00f90       80
00007f6ad0965d00 00007f6c1dc00f90       80
00007f6ad0965df0 00007f6c1dc00f90       80
00007f6ad0965ee0 00007f6c1dc00f90       80

Statistics:
              MT    Count    TotalSize Class Name
00007f6c1dc00f90   206770     19494060 System.String
Total 206770 objects
```

<span data-ttu-id="1075a-159">Ahora puede usar el comando `gcroot` en una instancia de `System.String` para ver cómo y por qué se considera raíz el objeto.</span><span class="sxs-lookup"><span data-stu-id="1075a-159">You can now use the `gcroot` command on a `System.String` instance to see how and why the object is rooted.</span></span> <span data-ttu-id="1075a-160">Tenga paciencia, ya que este comando tarda varios minutos con un montón de 30 MB:</span><span class="sxs-lookup"><span data-stu-id="1075a-160">Be patient because this command takes several minutes with a 30-MB heap:</span></span>

```console
> gcroot -all 00007f6ad09421f8

Thread 3f68:
    00007F6795BB58A0 00007F6C1D7D0745 System.Diagnostics.Tracing.CounterGroup.PollForValues() [/_/src/System.Private.CoreLib/shared/System/Diagnostics/Tracing/CounterGroup.cs @ 260]
        rbx:  (interior)
            ->  00007F6BDFFFF038 System.Object[]
            ->  00007F69D0033570 testwebapi.Controllers.Processor
            ->  00007F69D0033588 testwebapi.Controllers.CustomerCache
            ->  00007F69D00335A0 System.Collections.Generic.List`1[[testwebapi.Controllers.Customer, DiagnosticScenarios]]
            ->  00007F6C000148A0 testwebapi.Controllers.Customer[]
            ->  00007F6AD0942258 testwebapi.Controllers.Customer
            ->  00007F6AD09421F8 System.String

HandleTable:
    00007F6C98BB15F8 (pinned handle)
    -> 00007F6BDFFFF038 System.Object[]
    -> 00007F69D0033570 testwebapi.Controllers.Processor
    -> 00007F69D0033588 testwebapi.Controllers.CustomerCache
    -> 00007F69D00335A0 System.Collections.Generic.List`1[[testwebapi.Controllers.Customer, DiagnosticScenarios]]
    -> 00007F6C000148A0 testwebapi.Controllers.Customer[]
    -> 00007F6AD0942258 testwebapi.Controllers.Customer
    -> 00007F6AD09421F8 System.String

Found 2 roots.
```

<span data-ttu-id="1075a-161">Puede ver que el objeto `Customer` mantiene directamente `String` y un objeto `CustomerCache` lo hace indirectamente.</span><span class="sxs-lookup"><span data-stu-id="1075a-161">You can see that the `String` is directly held by the `Customer` object and indirectly held by a `CustomerCache` object.</span></span>

<span data-ttu-id="1075a-162">Puede seguir volcando objetos para ver que la mayoría de los objetos `String` siguen un patrón similar.</span><span class="sxs-lookup"><span data-stu-id="1075a-162">You can continue dumping out objects to see that most `String` objects follow a similar pattern.</span></span> <span data-ttu-id="1075a-163">En este punto, la investigación proporcionó suficiente información para identificar la causa principal en su código.</span><span class="sxs-lookup"><span data-stu-id="1075a-163">At this point, the investigation provided sufficient information to identify the root cause in your code.</span></span>

<span data-ttu-id="1075a-164">Este procedimiento general le permite identificar el origen de las principales fugas de memoria.</span><span class="sxs-lookup"><span data-stu-id="1075a-164">This general procedure allows you to identify the source of major memory leaks.</span></span>

## <a name="clean-up-resources"></a><span data-ttu-id="1075a-165">Limpiar los recursos</span><span class="sxs-lookup"><span data-stu-id="1075a-165">Clean up resources</span></span>

<span data-ttu-id="1075a-166">En este tutorial, inició un servidor web de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1075a-166">In this tutorial, you started a sample web server.</span></span> <span data-ttu-id="1075a-167">Este servidor debería haberse apagado como se explica en la sección [Reinicio del proceso con errores](#restart-the-failed-process).</span><span class="sxs-lookup"><span data-stu-id="1075a-167">This server should have been shut down as explained in the [Restart the failed process](#restart-the-failed-process) section.</span></span>

<span data-ttu-id="1075a-168">También puede eliminar el archivo de volcado de memoria que se creó.</span><span class="sxs-lookup"><span data-stu-id="1075a-168">You can also delete the dump file that was created.</span></span>

## <a name="see-also"></a><span data-ttu-id="1075a-169">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1075a-169">See also</span></span>

- <span data-ttu-id="1075a-170">[dotnet-trace](dotnet-trace.md) para mostrar procesos</span><span class="sxs-lookup"><span data-stu-id="1075a-170">[dotnet-trace](dotnet-trace.md) to list processes</span></span>
- <span data-ttu-id="1075a-171">[dotnet-counters](dotnet-counters.md) para comprobar el uso de memoria administrada</span><span class="sxs-lookup"><span data-stu-id="1075a-171">[dotnet-counters](dotnet-counters.md) to check managed memory usage</span></span>
- <span data-ttu-id="1075a-172">[dotnet-dump](dotnet-dump.md) para recopilar y analizar un archivo de volcado de memoria</span><span class="sxs-lookup"><span data-stu-id="1075a-172">[dotnet-dump](dotnet-dump.md) to collect and analyze a dump file</span></span>
- [<span data-ttu-id="1075a-173">dotnet/diagnostics</span><span class="sxs-lookup"><span data-stu-id="1075a-173">dotnet/diagnostics</span></span>](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial)

## <a name="next-steps"></a><span data-ttu-id="1075a-174">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="1075a-174">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1075a-175">Depuración del uso elevado de CPU en .NET Core</span><span class="sxs-lookup"><span data-stu-id="1075a-175">Debug high CPU in .NET Core</span></span>](debug-highcpu.md)
