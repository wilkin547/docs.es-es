---
title: 'Depuración del uso elevado de CPU: .NET Core'
description: Tutorial que le guiará a lo largo del proceso de depuración del uso elevado de CPU en .NET Core.
ms.topic: tutorial
ms.date: 07/20/2020
ms.openlocfilehash: ed22da3d53dfd1197de1f9b3c11ef31389cad690
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104872800"
---
# <a name="debug-high-cpu-usage-in-net-core"></a><span data-ttu-id="806df-103">Depuración del uso elevado de CPU en .NET Core</span><span class="sxs-lookup"><span data-stu-id="806df-103">Debug high CPU usage in .NET Core</span></span>

<span data-ttu-id="806df-104">**Este artículo se aplica a: ✔️** SDK de .NET Core 3.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="806df-104">**This article applies to: ✔️** .NET Core 3.1 SDK and later versions</span></span>

<span data-ttu-id="806df-105">En este tutorial, aprenderá a depurar un escenario de uso excesivo de CPU.</span><span class="sxs-lookup"><span data-stu-id="806df-105">In this tutorial, you'll learn how to debug an excessive CPU usage scenario.</span></span> <span data-ttu-id="806df-106">Con el repositorio de código fuente de ejemplo proporcionado, [Aplicación web de ASP.NET Core](/samples/dotnet/samples/diagnostic-scenarios), puede provocar un interbloqueo de forma intencionada.</span><span class="sxs-lookup"><span data-stu-id="806df-106">Using the provided example [ASP.NET Core web app](/samples/dotnet/samples/diagnostic-scenarios) source code repository, you can cause a deadlock intentionally.</span></span> <span data-ttu-id="806df-107">El punto de conexión experimentará un bloqueo y una acumulación de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="806df-107">The endpoint will experience a hang and thread accumulation.</span></span> <span data-ttu-id="806df-108">Aprenderá a usar diversas herramientas para diagnosticar este escenario con varios elementos clave de datos de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="806df-108">You'll learn how you can use various tools to diagnose this scenario with several key pieces of diagnostics data.</span></span>

<span data-ttu-id="806df-109">En este tutorial va a:</span><span class="sxs-lookup"><span data-stu-id="806df-109">In this tutorial, you will:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="806df-110">Investigar el uso elevado de CPU</span><span class="sxs-lookup"><span data-stu-id="806df-110">Investigate high CPU usage</span></span>
> - <span data-ttu-id="806df-111">Determinar el uso de CPU con [dotnet-counters](dotnet-counters.md)</span><span class="sxs-lookup"><span data-stu-id="806df-111">Determine CPU usage with [dotnet-counters](dotnet-counters.md)</span></span>
> - <span data-ttu-id="806df-112">Usar [dotnet-trace](dotnet-trace.md) para la generación de seguimiento</span><span class="sxs-lookup"><span data-stu-id="806df-112">Use [dotnet-trace](dotnet-trace.md) for trace generation</span></span>
> - <span data-ttu-id="806df-113">Realizar perfiles de rendimiento en PerfView</span><span class="sxs-lookup"><span data-stu-id="806df-113">Profile performance in PerfView</span></span>
> - <span data-ttu-id="806df-114">Diagnosticar y resolver el uso excesivo de CPU</span><span class="sxs-lookup"><span data-stu-id="806df-114">Diagnose and solve excessive CPU usage</span></span>

## <a name="prerequisites"></a><span data-ttu-id="806df-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="806df-115">Prerequisites</span></span>

<span data-ttu-id="806df-116">En el tutorial se usa:</span><span class="sxs-lookup"><span data-stu-id="806df-116">The tutorial uses:</span></span>

- <span data-ttu-id="806df-117">[SDK de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet) o una versión posterior</span><span class="sxs-lookup"><span data-stu-id="806df-117">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet) or a later version.</span></span>
- <span data-ttu-id="806df-118">[Destino de depuración de ejemplo](/samples/dotnet/samples/diagnostic-scenarios) para desencadenar el escenario</span><span class="sxs-lookup"><span data-stu-id="806df-118">[Sample debug target](/samples/dotnet/samples/diagnostic-scenarios) to trigger the scenario.</span></span>
- <span data-ttu-id="806df-119">[dotnet-trace](dotnet-trace.md) para enumerar los procesos y generar un perfil</span><span class="sxs-lookup"><span data-stu-id="806df-119">[dotnet-trace](dotnet-trace.md) to list processes and generate a profile.</span></span>
- <span data-ttu-id="806df-120">[dotnet-counters](dotnet-counters.md) para supervisar el uso de la CPU</span><span class="sxs-lookup"><span data-stu-id="806df-120">[dotnet-counters](dotnet-counters.md) to monitor cpu usage.</span></span>

## <a name="cpu-counters"></a><span data-ttu-id="806df-121">Contadores de CPU</span><span class="sxs-lookup"><span data-stu-id="806df-121">CPU counters</span></span>

<span data-ttu-id="806df-122">Antes de intentar recopilar datos de diagnóstico, debe observar una condición de CPU alta.</span><span class="sxs-lookup"><span data-stu-id="806df-122">Before attempting to collect diagnostics data, you need to observe a high CPU condition.</span></span> <span data-ttu-id="806df-123">Ejecute la [aplicación de ejemplo](/samples/dotnet/samples/diagnostic-scenarios) mediante el siguiente comando desde el directorio raíz del proyecto.</span><span class="sxs-lookup"><span data-stu-id="806df-123">Run the [sample application](/samples/dotnet/samples/diagnostic-scenarios) using the following command from the project root directory.</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="806df-124">Para encontrar el identificador de proceso, use el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="806df-124">To find the process ID, use the following command:</span></span>

```dotnetcli
dotnet-trace ps
```

<span data-ttu-id="806df-125">Anote el identificador de proceso de la salida del comando.</span><span class="sxs-lookup"><span data-stu-id="806df-125">Take note of the process ID from your command output.</span></span> <span data-ttu-id="806df-126">El identificador de proceso era `22884`, pero el suyo será diferente.</span><span class="sxs-lookup"><span data-stu-id="806df-126">Our process ID was `22884`, but yours will be different.</span></span> <span data-ttu-id="806df-127">Para comprobar el uso de CPU actual, use el comando de la herramienta [dotnet-counters](dotnet-counters.md):</span><span class="sxs-lookup"><span data-stu-id="806df-127">To check the current CPU usage, use the [dotnet-counters](dotnet-counters.md) tool command:</span></span>

```dotnetcli
dotnet-counters monitor --refresh-interval 1 -p 22884
```

<span data-ttu-id="806df-128">`refresh-interval` es el número de segundos entre los valores de CPU de sondeo de contador.</span><span class="sxs-lookup"><span data-stu-id="806df-128">The `refresh-interval` is the number of seconds between the counter polling CPU values.</span></span> <span data-ttu-id="806df-129">La salida debe ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="806df-129">The output should be similar to the following:</span></span>

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[System.Runtime]
    % Time in GC since last GC (%)                         0
    Allocation Rate / 1 sec (B)                            0
    CPU Usage (%)                                          0
    Exception Count / 1 sec                                0
    GC Heap Size (MB)                                      4
    Gen 0 GC Count / 60 sec                                0
    Gen 0 Size (B)                                         0
    Gen 1 GC Count / 60 sec                                0
    Gen 1 Size (B)                                         0
    Gen 2 GC Count / 60 sec                                0
    Gen 2 Size (B)                                         0
    LOH Size (B)                                           0
    Monitor Lock Contention Count / 1 sec                  0
    Number of Active Timers                                1
    Number of Assemblies Loaded                          140
    ThreadPool Completed Work Item Count / 1 sec           3
    ThreadPool Queue Length                                0
    ThreadPool Thread Count                                7
    Working Set (MB)                                      63
```

<span data-ttu-id="806df-130">Con la aplicación web en ejecución, inmediatamente después del inicio, no se consume CPU en absoluto y se muestra `0%`.</span><span class="sxs-lookup"><span data-stu-id="806df-130">With the web app running, immediately after startup, the CPU isn't being consumed at all and is reported at `0%`.</span></span> <span data-ttu-id="806df-131">Vaya a la ruta `api/diagscenario/highcpu` con `60000` como parámetro de ruta:</span><span class="sxs-lookup"><span data-stu-id="806df-131">Navigate to the `api/diagscenario/highcpu` route with `60000` as the route parameter:</span></span>

`https://localhost:5001/api/diagscenario/highcpu/60000`

<span data-ttu-id="806df-132">Ahora, vuelva a ejecutar el comando [dotnet-counters](dotnet-counters.md).</span><span class="sxs-lookup"><span data-stu-id="806df-132">Now, rerun the [dotnet-counters](dotnet-counters.md) command.</span></span> <span data-ttu-id="806df-133">Para supervisar solo `cpu-usage`, especifique `System.Runtime[cpu-usage]` como parte del comando.</span><span class="sxs-lookup"><span data-stu-id="806df-133">To monitor just the `cpu-usage`, specify `System.Runtime[cpu-usage]` as part of the command.</span></span>

```dotnetcli
dotnet-counters monitor --counters System.Runtime[cpu-usage] -p 22884 --refresh-interval 1
```

<span data-ttu-id="806df-134">Debería ver un aumento en el uso de CPU, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="806df-134">You should see an increase in CPU usage as shown below:</span></span>

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[System.Runtime]
    CPU Usage (%)                                         25
```

<span data-ttu-id="806df-135">Durante toda la solicitud, el uso de CPU rondará en torno al 25 %.</span><span class="sxs-lookup"><span data-stu-id="806df-135">Throughout the duration of the request, the CPU usage will hover around 25% .</span></span> <span data-ttu-id="806df-136">En función del equipo host, se espera un uso de CPU variable.</span><span class="sxs-lookup"><span data-stu-id="806df-136">Depending on the host machine, expect varying CPU usage.</span></span>

> [!TIP]
> <span data-ttu-id="806df-137">Para visualizar un uso de CPU incluso mayor, puede ejecutar este punto de conexión simultáneamente en varias pestañas del explorador.</span><span class="sxs-lookup"><span data-stu-id="806df-137">To visualize an even higher CPU usage, you can exercise this endpoint in multiple browser tabs simultaneously.</span></span>

<span data-ttu-id="806df-138">En este momento, puede afirmar con seguridad que el uso de CPU es mayor del esperado.</span><span class="sxs-lookup"><span data-stu-id="806df-138">At this point, you can safely say the CPU is running higher than you expect.</span></span>

## <a name="trace-generation"></a><span data-ttu-id="806df-139">Generación de seguimiento</span><span class="sxs-lookup"><span data-stu-id="806df-139">Trace generation</span></span>

<span data-ttu-id="806df-140">Al analizar una solicitud lenta, necesita una herramienta de diagnóstico que pueda proporcionar información sobre lo que hace el código.</span><span class="sxs-lookup"><span data-stu-id="806df-140">When analyzing a slow request, you need a diagnostics tool that can provide insights into what the code is doing.</span></span> <span data-ttu-id="806df-141">Lo habitual es optar por un generador de perfiles. Existen diferentes opciones de generador de perfiles entre las que elegir.</span><span class="sxs-lookup"><span data-stu-id="806df-141">The usual choice is a profiler, and there are different profiler options to choose from.</span></span>

### <a name="linux"></a>[<span data-ttu-id="806df-142">Linux</span><span class="sxs-lookup"><span data-stu-id="806df-142">Linux</span></span>](#tab/linux)

<span data-ttu-id="806df-143">La herramienta `perf` se puede usar para generar perfiles de aplicaciones .NET Core.</span><span class="sxs-lookup"><span data-stu-id="806df-143">The `perf` tool can be used to generate .NET Core app profiles.</span></span> <span data-ttu-id="806df-144">Salga de la instancia anterior del [destino de depuración de ejemplo](/samples/dotnet/samples/diagnostic-scenarios).</span><span class="sxs-lookup"><span data-stu-id="806df-144">Exit the previous instance of the [sample debug target](/samples/dotnet/samples/diagnostic-scenarios).</span></span>

<span data-ttu-id="806df-145">Establezca la variable de entorno `COMPlus_PerfMapEnabled` para que la aplicación .NET Core cree un archivo `map` en el directorio `/tmp`.</span><span class="sxs-lookup"><span data-stu-id="806df-145">Set the `COMPlus_PerfMapEnabled` environment variable to cause the .NET Core app to create a `map` file in the `/tmp` directory.</span></span> <span data-ttu-id="806df-146">`perf` usa este archivo `map` para asignar la dirección de CPU a las funciones generadas por JIT por nombre.</span><span class="sxs-lookup"><span data-stu-id="806df-146">This `map` file is used by `perf` to map CPU address to JIT-generated functions by name.</span></span> <span data-ttu-id="806df-147">Para obtener más información, consulte [Escritura del mapa de rendimiento](../run-time-config/debugging-profiling.md#write-perf-map).</span><span class="sxs-lookup"><span data-stu-id="806df-147">For more information, see [Write perf map](../run-time-config/debugging-profiling.md#write-perf-map).</span></span>

<span data-ttu-id="806df-148">Ejecute el [destino de depuración de ejemplo](/samples/dotnet/samples/diagnostic-scenarios) en la misma sesión de terminal.</span><span class="sxs-lookup"><span data-stu-id="806df-148">Run the [sample debug target](/samples/dotnet/samples/diagnostic-scenarios) in the same terminal session.</span></span>

```dotnetcli
export COMPlus_PerfMapEnabled=1
dotnet run
```

<span data-ttu-id="806df-149">Ejecute de nuevo el punto de conexión de la API de uso elevado de CPU (`https://localhost:5001/api/diagscenario/highcpu/60000`).</span><span class="sxs-lookup"><span data-stu-id="806df-149">Exercise the high CPU API endpoint (`https://localhost:5001/api/diagscenario/highcpu/60000`) again.</span></span> <span data-ttu-id="806df-150">Mientras se ejecuta en la solicitud de 1 minuto, ejecute el comando `perf` con el identificador de proceso:</span><span class="sxs-lookup"><span data-stu-id="806df-150">While it's running within the 1-minute request, run the `perf` command with your process ID:</span></span>

```bash
sudo perf record -p 2266 -g
```

<span data-ttu-id="806df-151">El comando `perf` inicia el proceso de recopilación de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="806df-151">The `perf` command starts the performance collection process.</span></span> <span data-ttu-id="806df-152">Deje que se ejecute durante unos 20 o 30 segundos y, luego, presione <kbd>Ctrl+C</kbd> para salir del proceso de recopilación.</span><span class="sxs-lookup"><span data-stu-id="806df-152">Let it run for about 20-30 seconds, then press <kbd>Ctrl+C</kbd> to exit the collection process.</span></span> <span data-ttu-id="806df-153">Puede usar el mismo comando `perf` para ver la salida del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="806df-153">You can use the same `perf` command to see the output of the trace.</span></span>

```bash
sudo perf report -f
```

<span data-ttu-id="806df-154">También puede generar un _gráfico de llamas_ mediante los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="806df-154">You can also generate a _flame-graph_ by using the following commands:</span></span>

```bash
git clone --depth=1 https://github.com/BrendanGregg/FlameGraph
sudo perf script | FlameGraph/stackcollapse-perf.pl | FlameGraph/flamegraph.pl > flamegraph.svg
```

<span data-ttu-id="806df-155">Este comando genera un archivo `flamegraph.svg` que puede ver en el explorador para investigar el problema de rendimiento:</span><span class="sxs-lookup"><span data-stu-id="806df-155">This command generates a `flamegraph.svg` that you can view in the browser to investigate the performance problem:</span></span>

<span data-ttu-id="806df-156">[![Imagen SVG del gráfico de llamas](media/flamegraph.jpg)](media/flamegraph.jpg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="806df-156">[![Flame graph SVG image](media/flamegraph.jpg)](media/flamegraph.jpg#lightbox)</span></span>

### <a name="windows"></a>[<span data-ttu-id="806df-157">Windows</span><span class="sxs-lookup"><span data-stu-id="806df-157">Windows</span></span>](#tab/windows)

<span data-ttu-id="806df-158">En Windows, puede usar la herramienta [dotnet-trace](dotnet-trace.md) como generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="806df-158">On Windows, you can use the [dotnet-trace](dotnet-trace.md) tool as a profiler.</span></span> <span data-ttu-id="806df-159">Con el anterior [destino de depuración de ejemplo](/samples/dotnet/samples/diagnostic-scenarios), ejecute de nuevo el punto de conexión de uso elevado de CPU (`https://localhost:5001/api/diagscenario/highcpu/60000`).</span><span class="sxs-lookup"><span data-stu-id="806df-159">Using the previous [sample debug target](/samples/dotnet/samples/diagnostic-scenarios), exercise the high CPU endpoint (`https://localhost:5001/api/diagscenario/highcpu/60000`) again.</span></span> <span data-ttu-id="806df-160">Mientras se ejecuta en la solicitud de 1 minuto, ejecute el comando `collect` como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="806df-160">While it's running within the 1-minute request, use the `collect` command as follows:</span></span>

```dotnetcli
dotnet-trace collect -p 22884 --providers Microsoft-DotNETCore-SampleProfiler
```

<span data-ttu-id="806df-161">Deje que [dotnet-trace](dotnet-trace.md) se ejecute durante unos 20 o 30 segundos y, luego, presione la tecla <kbd>ENTRAR</kbd> para salir de la recopilación.</span><span class="sxs-lookup"><span data-stu-id="806df-161">Let [dotnet-trace](dotnet-trace.md) run for about 20-30 seconds, and then press the <kbd>Enter</kbd> to exit the collection.</span></span> <span data-ttu-id="806df-162">El resultado es un archivo `nettrace` ubicado en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="806df-162">The result is a `nettrace` file located in the same folder.</span></span> <span data-ttu-id="806df-163">Los archivos `nettrace` son una excelente manera de usar las herramientas de análisis existentes en Windows.</span><span class="sxs-lookup"><span data-stu-id="806df-163">The `nettrace` files are a great way to use existing analysis tools on Windows.</span></span>

<span data-ttu-id="806df-164">Abra `nettrace` con [`PerfView`](https://github.com/microsoft/perfview/blob/master/documentation/Downloading.md) como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="806df-164">Open the `nettrace` with [`PerfView`](https://github.com/microsoft/perfview/blob/master/documentation/Downloading.md) as shown below.</span></span>

<span data-ttu-id="806df-165">[![Imagen de PerfView](media/perfview.jpg)](media/perfview.jpg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="806df-165">[![PerfView image](media/perfview.jpg)](media/perfview.jpg#lightbox)</span></span>

---

## <a name="see-also"></a><span data-ttu-id="806df-166">Consulte también</span><span class="sxs-lookup"><span data-stu-id="806df-166">See also</span></span>

- <span data-ttu-id="806df-167">[dotnet-trace](dotnet-trace.md) para mostrar procesos</span><span class="sxs-lookup"><span data-stu-id="806df-167">[dotnet-trace](dotnet-trace.md) to list processes</span></span>
- <span data-ttu-id="806df-168">[dotnet-counters](dotnet-counters.md) para comprobar el uso de memoria administrada</span><span class="sxs-lookup"><span data-stu-id="806df-168">[dotnet-counters](dotnet-counters.md) to check managed memory usage</span></span>
- <span data-ttu-id="806df-169">[dotnet-dump](dotnet-dump.md) para recopilar y analizar un archivo de volcado de memoria</span><span class="sxs-lookup"><span data-stu-id="806df-169">[dotnet-dump](dotnet-dump.md) to collect and analyze a dump file</span></span>
- [<span data-ttu-id="806df-170">dotnet/diagnostics</span><span class="sxs-lookup"><span data-stu-id="806df-170">dotnet/diagnostics</span></span>](https://github.com/dotnet/diagnostics/tree/main/documentation/tutorial)

## <a name="next-steps"></a><span data-ttu-id="806df-171">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="806df-171">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="806df-172">Depuración de un interbloqueo en .NET Core</span><span class="sxs-lookup"><span data-stu-id="806df-172">Debug a deadlock in .NET Core</span></span>](debug-deadlock.md)
