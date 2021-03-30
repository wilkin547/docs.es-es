---
title: 'Depuración de un interbloqueo: .NET Core'
description: Tutorial del proceso de depuración de un problema de bloqueo en .NET Core.
ms.topic: tutorial
ms.date: 07/20/2020
ms.openlocfilehash: a268884740ff38d7975303a5a5e5f2c24f16778d
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104874281"
---
# <a name="debug-a-deadlock-in-net-core"></a><span data-ttu-id="c5a54-103">Depuración de un interbloqueo en .NET Core</span><span class="sxs-lookup"><span data-stu-id="c5a54-103">Debug a deadlock in .NET Core</span></span>

<span data-ttu-id="c5a54-104">**Este artículo se aplica a: ✔️** SDK de .NET Core 3.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="c5a54-104">**This article applies to: ✔️** .NET Core 3.1 SDK and later versions</span></span>

<span data-ttu-id="c5a54-105">En este tutorial se explica cómo depurar un escenario de interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="c5a54-105">In this tutorial, you'll learn how to debug a deadlock scenario.</span></span> <span data-ttu-id="c5a54-106">Con el repositorio de código fuente de ejemplo proporcionado, [Aplicación web de ASP.NET Core](/samples/dotnet/samples/diagnostic-scenarios), puede provocar un interbloqueo de forma intencionada.</span><span class="sxs-lookup"><span data-stu-id="c5a54-106">Using the provided example [ASP.NET Core web app](/samples/dotnet/samples/diagnostic-scenarios) source code repository, you can cause a deadlock intentionally.</span></span> <span data-ttu-id="c5a54-107">El punto de conexión experimentará un bloqueo y una acumulación de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="c5a54-107">The endpoint will experience a hang and thread accumulation.</span></span> <span data-ttu-id="c5a54-108">Así, aprenderá a usar diversas herramientas para analizar el problema, como los volcados de núcleo, el análisis de volcados de núcleo y el seguimiento de procesos.</span><span class="sxs-lookup"><span data-stu-id="c5a54-108">You'll learn how you can use various tools to analyze the problem, such as core dumps, core dump analysis, and process tracing.</span></span>

<span data-ttu-id="c5a54-109">En este tutorial va a:</span><span class="sxs-lookup"><span data-stu-id="c5a54-109">In this tutorial, you will:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="c5a54-110">Investigar el bloqueo de una aplicación</span><span class="sxs-lookup"><span data-stu-id="c5a54-110">Investigate an app hang</span></span>
> - <span data-ttu-id="c5a54-111">Generar un archivo de volcado de núcleo</span><span class="sxs-lookup"><span data-stu-id="c5a54-111">Generate a core dump file</span></span>
> - <span data-ttu-id="c5a54-112">Analizar los subprocesos del proceso en el archivo de volcado de memoria</span><span class="sxs-lookup"><span data-stu-id="c5a54-112">Analyze process threads in the dump file</span></span>
> - <span data-ttu-id="c5a54-113">Analizar pilas de llamadas y bloques de sincronización</span><span class="sxs-lookup"><span data-stu-id="c5a54-113">Analyze callstacks and sync blocks</span></span>
> - <span data-ttu-id="c5a54-114">Diagnosticar y solucionar un interbloqueo</span><span class="sxs-lookup"><span data-stu-id="c5a54-114">Diagnose and solve a deadlock</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c5a54-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c5a54-115">Prerequisites</span></span>

<span data-ttu-id="c5a54-116">En el tutorial se usa:</span><span class="sxs-lookup"><span data-stu-id="c5a54-116">The tutorial uses:</span></span>

- <span data-ttu-id="c5a54-117">[SDK de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet) o una versión posterior</span><span class="sxs-lookup"><span data-stu-id="c5a54-117">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet) or a later version</span></span>
- <span data-ttu-id="c5a54-118">[Destino de depuración de ejemplo: aplicación web](/samples/dotnet/samples/diagnostic-scenarios) para desencadenar el escenario</span><span class="sxs-lookup"><span data-stu-id="c5a54-118">[Sample debug target - web app](/samples/dotnet/samples/diagnostic-scenarios) to trigger the scenario</span></span>
- <span data-ttu-id="c5a54-119">[dotnet-trace](dotnet-trace.md) para mostrar procesos</span><span class="sxs-lookup"><span data-stu-id="c5a54-119">[dotnet-trace](dotnet-trace.md) to list processes</span></span>
- <span data-ttu-id="c5a54-120">[dotnet-dump](dotnet-dump.md) para recopilar y analizar un archivo de volcado de memoria</span><span class="sxs-lookup"><span data-stu-id="c5a54-120">[dotnet-dump](dotnet-dump.md) to collect, and analyze a dump file</span></span>

## <a name="core-dump-generation"></a><span data-ttu-id="c5a54-121">Generación de volcado de núcleo</span><span class="sxs-lookup"><span data-stu-id="c5a54-121">Core dump generation</span></span>

<span data-ttu-id="c5a54-122">A la hora de investigar la falta de respuesta de una aplicación, un volcado de núcleo o memoria permite inspeccionar el estado de sus subprocesos y cualquier posible bloqueo que pueda tener problemas de contención.</span><span class="sxs-lookup"><span data-stu-id="c5a54-122">To investigate application unresponsiveness, a core dump or memory dump allows you to inspect the state of its threads and any possible locks that may have contention issues.</span></span> <span data-ttu-id="c5a54-123">Ejecute la aplicación de [depuración de ejemplo](/samples/dotnet/samples/diagnostic-scenarios) mediante el siguiente comando desde el directorio raíz de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c5a54-123">Run the [sample debug](/samples/dotnet/samples/diagnostic-scenarios) application using the following command from the sample root directory:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="c5a54-124">Para encontrar el identificador de proceso, use el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="c5a54-124">To find the process ID, use the following command:</span></span>

```dotnetcli
dotnet-trace ps
```

<span data-ttu-id="c5a54-125">Anote el identificador de proceso de la salida del comando.</span><span class="sxs-lookup"><span data-stu-id="c5a54-125">Take note of the process ID from your command output.</span></span> <span data-ttu-id="c5a54-126">El identificador de proceso era `4807`, pero el suyo será diferente.</span><span class="sxs-lookup"><span data-stu-id="c5a54-126">Our process ID was `4807`, but yours will be different.</span></span> <span data-ttu-id="c5a54-127">Vaya a la siguiente dirección URL, que es un punto de conexión de API en el sitio de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c5a54-127">Navigate to the following URL, which is an API endpoint on the sample site:</span></span>

`https://localhost:5001/api/diagscenario/deadlock`

<span data-ttu-id="c5a54-128">La solicitud de API al sitio se bloquea y no responde.</span><span class="sxs-lookup"><span data-stu-id="c5a54-128">The API request to the site will hang and not respond.</span></span> <span data-ttu-id="c5a54-129">Deje que la solicitud se ejecute durante unos 10 o 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="c5a54-129">Let the request run for about 10-15 seconds.</span></span> <span data-ttu-id="c5a54-130">Luego, cree el volcado de núcleo mediante el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c5a54-130">Then create the core dump using the following command:</span></span>

### <a name="linux"></a>[<span data-ttu-id="c5a54-131">Linux</span><span class="sxs-lookup"><span data-stu-id="c5a54-131">Linux</span></span>](#tab/linux)

```bash
sudo dotnet-dump collect -p 4807
```

### <a name="windows"></a>[<span data-ttu-id="c5a54-132">Windows</span><span class="sxs-lookup"><span data-stu-id="c5a54-132">Windows</span></span>](#tab/windows)

```console
dotnet-dump collect -p 4807
```

---

## <a name="analyze-the-core-dump"></a><span data-ttu-id="c5a54-133">Análisis del volcado de memoria principal</span><span class="sxs-lookup"><span data-stu-id="c5a54-133">Analyze the core dump</span></span>

<span data-ttu-id="c5a54-134">Para iniciar el análisis de volcado de núcleo, ábralo con el siguiente comando `dotnet-dump analyze`.</span><span class="sxs-lookup"><span data-stu-id="c5a54-134">To start the core dump analysis, open the core dump using the following `dotnet-dump analyze` command.</span></span> <span data-ttu-id="c5a54-135">El argumento es la ruta de acceso al archivo de volcado de núcleo recopilado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c5a54-135">The argument is the path to the core dump file that was collected earlier.</span></span>

```dotnetcli
dotnet-dump analyze  ~/.dotnet/tools/core_20190513_143916
```

<span data-ttu-id="c5a54-136">Puesto que está examinando un posible bloqueo, quiere obtener una idea general de la actividad de los subprocesos del proceso.</span><span class="sxs-lookup"><span data-stu-id="c5a54-136">Since you're looking at a potential hang, you want an overall feel for the thread activity in the process.</span></span> <span data-ttu-id="c5a54-137">Puede usar el comando `threads` como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="c5a54-137">You can use the `threads` command as shown below:</span></span>

```console
> threads
*0 0x1DBFF (121855)
 1 0x1DC01 (121857)
 2 0x1DC02 (121858)
 3 0x1DC03 (121859)
 4 0x1DC04 (121860)
 5 0x1DC05 (121861)
 6 0x1DC06 (121862)
 7 0x1DC07 (121863)
 8 0x1DC08 (121864)
 9 0x1DC09 (121865)
 10 0x1DC0A (121866)
 11 0x1DC0D (121869)
 12 0x1DC0E (121870)
 13 0x1DC10 (121872)
 14 0x1DC11 (121873)
 15 0x1DC12 (121874)
 16 0x1DC13 (121875)
 17 0x1DC14 (121876)
 18 0x1DC15 (121877)
 19 0x1DC1C (121884)
 20 0x1DC1D (121885)
 21 0x1DC1E (121886)
 22 0x1DC21 (121889)
 23 0x1DC22 (121890)
 24 0x1DC23 (121891)
 25 0x1DC24 (121892)
 26 0x1DC25 (121893)
...
...
 317 0x1DD48 (122184)
 318 0x1DD49 (122185)
 319 0x1DD4A (122186)
 320 0x1DD4B (122187)
 321 0x1DD4C (122188)
 ```

<span data-ttu-id="c5a54-138">La salida muestra todos los subprocesos que se están ejecutando en el proceso con su identificador de subproceso de depurador asociado y su identificador de subproceso de sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c5a54-138">The output shows all the threads currently running in the process with their associated debugger thread ID and operating system thread ID.</span></span> <span data-ttu-id="c5a54-139">Hay más de 300 subprocesos en función de la salida.</span><span class="sxs-lookup"><span data-stu-id="c5a54-139">Based on the output, there are over 300 threads.</span></span>

<span data-ttu-id="c5a54-140">El siguiente paso es entender mejor lo que los subprocesos están haciendo mediante la obtención de la pila de llamadas de cada subproceso.</span><span class="sxs-lookup"><span data-stu-id="c5a54-140">The next step is to get a better understanding of what the threads are currently doing by getting each thread's callstack.</span></span> <span data-ttu-id="c5a54-141">El comando `clrstack` se puede usar para generar pilas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c5a54-141">The `clrstack` command can be used to output callstacks.</span></span> <span data-ttu-id="c5a54-142">Puede generar una sola pila de llamadas o todas.</span><span class="sxs-lookup"><span data-stu-id="c5a54-142">It can either output a single callstack or all the callstacks.</span></span> <span data-ttu-id="c5a54-143">Use el siguiente comando para generar todas las pilas de llamadas de todos los subprocesos del proceso:</span><span class="sxs-lookup"><span data-stu-id="c5a54-143">Use the following command to output all the callstacks for all the threads in the process:</span></span>

```console
clrstack -all
```

<span data-ttu-id="c5a54-144">Una parte representativa de la salida tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="c5a54-144">A representative portion of the output looks like:</span></span>

```console
  ...
  ...
  ...
        Child SP               IP Call Site
00007F2AE37B5680 00007f305abc6360 [GCFrame: 00007f2ae37b5680]
00007F2AE37B5770 00007f305abc6360 [GCFrame: 00007f2ae37b5770]
00007F2AE37B57D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae37b57d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE37B5920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE37B5950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE37B5CA0 00007f30593044af [GCFrame: 00007f2ae37b5ca0]
00007F2AE37B5D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae37b5d70]
OS Thread Id: 0x1dc82
        Child SP               IP Call Site
00007F2AE2FB4680 00007f305abc6360 [GCFrame: 00007f2ae2fb4680]
00007F2AE2FB4770 00007f305abc6360 [GCFrame: 00007f2ae2fb4770]
00007F2AE2FB47D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae2fb47d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE2FB4920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE2FB4950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE2FB4CA0 00007f30593044af [GCFrame: 00007f2ae2fb4ca0]
00007F2AE2FB4D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae2fb4d70]
OS Thread Id: 0x1dc83
        Child SP               IP Call Site
00007F2AE27B3680 00007f305abc6360 [GCFrame: 00007f2ae27b3680]
00007F2AE27B3770 00007f305abc6360 [GCFrame: 00007f2ae27b3770]
00007F2AE27B37D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae27b37d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE27B3920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE27B3950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE27B3CA0 00007f30593044af [GCFrame: 00007f2ae27b3ca0]
00007F2AE27B3D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae27b3d70]
OS Thread Id: 0x1dc84
        Child SP               IP Call Site
00007F2AE1FB2680 00007f305abc6360 [GCFrame: 00007f2ae1fb2680]
00007F2AE1FB2770 00007f305abc6360 [GCFrame: 00007f2ae1fb2770]
00007F2AE1FB27D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae1fb27d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE1FB2920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE1FB2950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE1FB2CA0 00007f30593044af [GCFrame: 00007f2ae1fb2ca0]
00007F2AE1FB2D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae1fb2d70]
OS Thread Id: 0x1dc85
        Child SP               IP Call Site
00007F2AE17B1680 00007f305abc6360 [GCFrame: 00007f2ae17b1680]
00007F2AE17B1770 00007f305abc6360 [GCFrame: 00007f2ae17b1770]
00007F2AE17B17D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae17b17d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE17B1920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE17B1950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE17B1CA0 00007f30593044af [GCFrame: 00007f2ae17b1ca0]
00007F2AE17B1D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae17b1d70]
OS Thread Id: 0x1dc86
        Child SP               IP Call Site
00007F2AE0FB0680 00007f305abc6360 [GCFrame: 00007f2ae0fb0680]
00007F2AE0FB0770 00007f305abc6360 [GCFrame: 00007f2ae0fb0770]
00007F2AE0FB07D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae0fb07d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE0FB0920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE0FB0950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE0FB0CA0 00007f30593044af [GCFrame: 00007f2ae0fb0ca0]
00007F2AE0FB0D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae0fb0d70]
OS Thread Id: 0x1dc87
        Child SP               IP Call Site
00007F2AE07AF680 00007f305abc6360 [GCFrame: 00007f2ae07af680]
00007F2AE07AF770 00007f305abc6360 [GCFrame: 00007f2ae07af770]
00007F2AE07AF7D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae07af7d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE07AF920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE07AF950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE07AFCA0 00007f30593044af [GCFrame: 00007f2ae07afca0]
00007F2AE07AFD70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae07afd70]
OS Thread Id: 0x1dc88
        Child SP               IP Call Site
00007F2ADFFAE680 00007f305abc6360 [GCFrame: 00007f2adffae680]
00007F2ADFFAE770 00007f305abc6360 [GCFrame: 00007f2adffae770]
00007F2ADFFAE7D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2adffae7d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2ADFFAE920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2ADFFAE950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2ADFFAECA0 00007f30593044af [GCFrame: 00007f2adffaeca0]
00007F2ADFFAED70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2adffaed70]
...
...
```

<span data-ttu-id="c5a54-145">Si se observan las pilas de llamadas de los más de 300 subprocesos, se muestra un patrón en el que una mayoría de los subprocesos comparten una pila de llamadas común:</span><span class="sxs-lookup"><span data-stu-id="c5a54-145">Observing the callstacks for all 300+ threads shows a pattern where a majority of the threads share a common callstack:</span></span>

```console
OS Thread Id: 0x1dc88
        Child SP               IP Call Site
00007F2ADFFAE680 00007f305abc6360 [GCFrame: 00007f2adffae680]
00007F2ADFFAE770 00007f305abc6360 [GCFrame: 00007f2adffae770]
00007F2ADFFAE7D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2adffae7d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2ADFFAE920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2ADFFAE950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2ADFFAECA0 00007f30593044af [GCFrame: 00007f2adffaeca0]
00007F2ADFFAED70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2adffaed70]
```

<span data-ttu-id="c5a54-146">La pila de llamadas parece mostrar que la solicitud ha llegado en el método de interbloqueo que, a su vez, realiza una llamada a `Monitor.ReliableEnter`.</span><span class="sxs-lookup"><span data-stu-id="c5a54-146">The callstack seems to show that the request arrived in our deadlock method that in turn makes a call to `Monitor.ReliableEnter`.</span></span> <span data-ttu-id="c5a54-147">Este método indica que los subprocesos están intentando especificar un bloqueo de monitor.</span><span class="sxs-lookup"><span data-stu-id="c5a54-147">This method indicates that the threads are trying to enter a monitor lock.</span></span> <span data-ttu-id="c5a54-148">Están esperando a que el bloqueo esté disponible.</span><span class="sxs-lookup"><span data-stu-id="c5a54-148">They're waiting on the availability of the lock.</span></span> <span data-ttu-id="c5a54-149">Probablemente otro subproceso lo haya bloqueado.</span><span class="sxs-lookup"><span data-stu-id="c5a54-149">It's likely locked by a different thread.</span></span>

<span data-ttu-id="c5a54-150">El siguiente paso es averiguar qué subproceso está manteniendo realmente el bloqueo de monitor.</span><span class="sxs-lookup"><span data-stu-id="c5a54-150">The next step then is to find out which thread is actually holding the monitor lock.</span></span> <span data-ttu-id="c5a54-151">Como los monitores normalmente almacenan información de bloqueo en la tabla de bloques de sincronización, se puede usar el comando `syncblk` para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="c5a54-151">Since monitors typically store lock information in the sync block table, we can use the `syncblk` command to get more information:</span></span>

```console
> syncblk
Index         SyncBlock MonitorHeld Recursion Owning Thread Info          SyncBlock Owner
   43 00000246E51268B8          603         1 0000024B713F4E30 5634  28   00000249654b14c0 System.Object
   44 00000246E5126908            3         1 0000024B713F47E0 51d4  29   00000249654b14d8 System.Object
-----------------------------
Total           344
CCW             1
RCW             2
ComClassFactory 0
Free            0
```

<span data-ttu-id="c5a54-152">Las dos columnas que interesan son **MonitorHeld** y **Owning Thread Info**.</span><span class="sxs-lookup"><span data-stu-id="c5a54-152">The two interesting columns are **MonitorHeld** and **Owning Thread Info**.</span></span> <span data-ttu-id="c5a54-153">La columna **MonitorHeld** muestra si un subproceso ha adquirido un bloqueo de monitor y el número de subprocesos en espera.</span><span class="sxs-lookup"><span data-stu-id="c5a54-153">The **MonitorHeld** column shows whether a monitor lock is acquired by a thread and the number of waiting threads.</span></span> <span data-ttu-id="c5a54-154">La columna **Owning Thread Info** muestra el subproceso que posee actualmente el bloqueo de monitor.</span><span class="sxs-lookup"><span data-stu-id="c5a54-154">The **Owning Thread Info** column shows which thread currently owns the monitor lock.</span></span> <span data-ttu-id="c5a54-155">La información del subproceso tiene tres subcolumnas diferentes.</span><span class="sxs-lookup"><span data-stu-id="c5a54-155">The thread info has three different subcolumns.</span></span> <span data-ttu-id="c5a54-156">La segunda subcolumna muestra el identificador de subproceso de sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c5a54-156">The second subcolumn shows operating system thread ID.</span></span>

<span data-ttu-id="c5a54-157">En este punto, se sabe que dos subprocesos diferentes (0x5634 y 0x51d4) mantienen un bloqueo de monitor.</span><span class="sxs-lookup"><span data-stu-id="c5a54-157">At this point, we know two different threads (0x5634 and 0x51d4) hold a monitor lock.</span></span> <span data-ttu-id="c5a54-158">El siguiente paso consiste en echar un vistazo a lo que están haciendo esos subprocesos.</span><span class="sxs-lookup"><span data-stu-id="c5a54-158">The next step is to take a look at what those threads are doing.</span></span> <span data-ttu-id="c5a54-159">Hay que comprobar si mantienen el bloqueo indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="c5a54-159">We need to check if they're stuck indefinitely holding the lock.</span></span> <span data-ttu-id="c5a54-160">Vamos a usar los comandos `setthread` y `clrstack` para alternar entre cada uno de los subprocesos y mostrar las pilas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c5a54-160">Let's use the `setthread` and `clrstack` commands to switch to each of the threads and display the callstacks.</span></span>

<span data-ttu-id="c5a54-161">Para ver el primer subproceso, ejecute el comando `setthread` y busque el índice del subproceso 0x5634 (el índice era 28).</span><span class="sxs-lookup"><span data-stu-id="c5a54-161">To look at the first thread, run the `setthread` command, and find the index of the 0x5634 thread (our index was 28).</span></span> <span data-ttu-id="c5a54-162">La función de interbloqueo está esperando a adquirir un bloqueo, pero ya posee dicho bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c5a54-162">The deadlock function is waiting to acquire a lock, but it already owns the lock.</span></span> <span data-ttu-id="c5a54-163">Está en interbloqueo, a la espera del bloqueo que ya mantiene.</span><span class="sxs-lookup"><span data-stu-id="c5a54-163">It's in deadlock waiting for the lock it already holds.</span></span>

```console
> setthread 28
> clrstack
OS Thread Id: 0x5634 (28)
        Child SP               IP Call Site
0000004E46AFEAA8 00007fff43a5cbc4 [GCFrame: 0000004e46afeaa8]
0000004E46AFEC18 00007fff43a5cbc4 [GCFrame: 0000004e46afec18]
0000004E46AFEC68 00007fff43a5cbc4 [HelperMethodFrame_1OBJ: 0000004e46afec68] System.Threading.Monitor.Enter(System.Object)
0000004E46AFEDC0 00007FFE5EAF9C80 testwebapi.Controllers.DiagScenarioController.DeadlockFunc() [C:\Users\dapine\Downloads\Diagnostic_scenarios_sample_debug_target\Controllers\DiagnosticScenarios.cs @ 58]
0000004E46AFEE30 00007FFE5EAF9B8C testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_0() [C:\Users\dapine\Downloads\Diagnostic_scenarios_sample_debug_target\Controllers\DiagnosticScenarios.cs @ 26]
0000004E46AFEE80 00007FFEBB251A5B System.Threading.ThreadHelper.ThreadStart_Context(System.Object) [/_/src/System.Private.CoreLib/src/System/Threading/Thread.CoreCLR.cs @ 44]
0000004E46AFEEB0 00007FFE5EAEEEEC System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/_/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
0000004E46AFEF20 00007FFEBB234EAB System.Threading.ThreadHelper.ThreadStart() [/_/src/System.Private.CoreLib/src/System/Threading/Thread.CoreCLR.cs @ 93]
0000004E46AFF138 00007ffebdcc6b63 [GCFrame: 0000004e46aff138]
0000004E46AFF3A0 00007ffebdcc6b63 [DebuggerU2MCatchHandlerFrame: 0000004e46aff3a0]
```

<span data-ttu-id="c5a54-164">El segundo subproceso es similar.</span><span class="sxs-lookup"><span data-stu-id="c5a54-164">The second thread is similar.</span></span> <span data-ttu-id="c5a54-165">También está intentando adquirir un bloqueo que ya posee.</span><span class="sxs-lookup"><span data-stu-id="c5a54-165">It's also trying to acquire a lock that it already owns.</span></span> <span data-ttu-id="c5a54-166">Lo más probable es que los más de 300 subprocesos restantes en espera estén esperando también a uno de los bloqueos que han causado el interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="c5a54-166">The remaining 300+ threads that are all waiting are most likely also waiting on one of the locks that caused the deadlock.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5a54-167">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c5a54-167">See also</span></span>

- <span data-ttu-id="c5a54-168">[dotnet-trace](dotnet-trace.md) para mostrar procesos</span><span class="sxs-lookup"><span data-stu-id="c5a54-168">[dotnet-trace](dotnet-trace.md) to list processes</span></span>
- <span data-ttu-id="c5a54-169">[dotnet-counters](dotnet-counters.md) para comprobar el uso de memoria administrada</span><span class="sxs-lookup"><span data-stu-id="c5a54-169">[dotnet-counters](dotnet-counters.md) to check managed memory usage</span></span>
- <span data-ttu-id="c5a54-170">[dotnet-dump](dotnet-dump.md) para recopilar y analizar un archivo de volcado de memoria</span><span class="sxs-lookup"><span data-stu-id="c5a54-170">[dotnet-dump](dotnet-dump.md) to collect and analyze a dump file</span></span>
- [<span data-ttu-id="c5a54-171">dotnet/diagnostics</span><span class="sxs-lookup"><span data-stu-id="c5a54-171">dotnet/diagnostics</span></span>](https://github.com/dotnet/diagnostics/tree/main/documentation/tutorial)

## <a name="next-steps"></a><span data-ttu-id="c5a54-172">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c5a54-172">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c5a54-173">¿Qué herramientas de diagnóstico están disponibles en .NET Core?</span><span class="sxs-lookup"><span data-stu-id="c5a54-173">What diagnostic tools are available in .NET Core</span></span>](index.md)
