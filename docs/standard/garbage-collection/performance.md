---
title: Recolección de elementos no utilizados y rendimiento
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- garbage collection, troubleshooting
- garbage collection, performance
ms.assetid: c203467b-e95c-4ccf-b30b-953eb3463134
ms.openlocfilehash: 72cf742aae26f9441229b355dc6e70da7a5fc9cd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "75900583"
---
# <a name="garbage-collection-and-performance"></a><span data-ttu-id="b820b-102">Recolección de elementos no utilizados y rendimiento</span><span class="sxs-lookup"><span data-stu-id="b820b-102">Garbage Collection and Performance</span></span>

<span data-ttu-id="b820b-103">En este tema se describen problemas relacionados con la recolección de elementos no utilizados y el uso de memoria.</span><span class="sxs-lookup"><span data-stu-id="b820b-103">This topic describes issues related to garbage collection and memory usage.</span></span> <span data-ttu-id="b820b-104">Se tratan problemas relativos al montón administrado y se explica cómo minimizar el efecto de la recolección de elementos no utilizados en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b820b-104">It addresses issues that pertain to the managed heap and explains how to minimize the effect of garbage collection on your applications.</span></span> <span data-ttu-id="b820b-105">Cada problema contiene vínculos a procedimientos que puede emplear para investigar los problemas.</span><span class="sxs-lookup"><span data-stu-id="b820b-105">Each issue has links to procedures that you can use to investigate problems.</span></span>

## <a name="performance-analysis-tools"></a><span data-ttu-id="b820b-106">Herramientas de análisis de rendimiento</span><span class="sxs-lookup"><span data-stu-id="b820b-106">Performance Analysis Tools</span></span>

<span data-ttu-id="b820b-107">En las próximas siguientes se describen las herramientas disponibles para investigar los problemas de uso de memoria y de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-107">The following sections describe the tools that are available for investigating memory usage and garbage collection issues.</span></span> <span data-ttu-id="b820b-108">Los [procedimientos](#performance-check-procedures) que se muestran más adelante en este tema hacen referencia a estas herramientas.</span><span class="sxs-lookup"><span data-stu-id="b820b-108">The [procedures](#performance-check-procedures) provided later in this topic refer to these tools.</span></span>

### <a name="memory-performance-counters"></a><span data-ttu-id="b820b-109">Contadores de rendimiento de memoria</span><span class="sxs-lookup"><span data-stu-id="b820b-109">Memory Performance Counters</span></span>

<span data-ttu-id="b820b-110">Puede usar contadores de rendimiento para recopilar datos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b820b-110">You can use performance counters to gather performance data.</span></span> <span data-ttu-id="b820b-111">Para obtener instrucciones, vea [Generar perfiles en tiempo de ejecución](../../../docs/framework/debug-trace-profile/runtime-profiling.md).</span><span class="sxs-lookup"><span data-stu-id="b820b-111">For instructions, see [Runtime Profiling](../../../docs/framework/debug-trace-profile/runtime-profiling.md).</span></span> <span data-ttu-id="b820b-112">La categoría CLR Memory de contadores de rendimiento de .NET, tal y como se describe en [Contadores de rendimiento en .NET Framework](../../../docs/framework/debug-trace-profile/performance-counters.md), ofrece información sobre el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-112">The .NET CLR Memory category of performance counters, as described in [Performance Counters in the .NET Framework](../../../docs/framework/debug-trace-profile/performance-counters.md), provides information about the garbage collector.</span></span>

### <a name="debugging-with-sos"></a><span data-ttu-id="b820b-113">Depurar con SOS</span><span class="sxs-lookup"><span data-stu-id="b820b-113">Debugging with SOS</span></span>

<span data-ttu-id="b820b-114">Puede usar el [depurador de Windows (WinDbg)](/windows-hardware/drivers/debugger/index) para inspeccionar objetos del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b820b-114">You can use the [Windows Debugger (WinDbg)](/windows-hardware/drivers/debugger/index) to inspect objects on the managed heap.</span></span>

<span data-ttu-id="b820b-115">Para instalar WinDbg, instale las Herramientas de depuración para Windows desde la página [Download Debugging Tools for Windows](/windows-hardware/drivers/debugger/debugger-download-tools) (Descarga de Herramientas de depuración para Windows).</span><span class="sxs-lookup"><span data-stu-id="b820b-115">To install WinDbg, install Debugging Tools for Windows from the [Download Debugging Tools for Windows](/windows-hardware/drivers/debugger/debugger-download-tools) page.</span></span>

### <a name="garbage-collection-etw-events"></a><span data-ttu-id="b820b-116">Eventos ETW de recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="b820b-116">Garbage Collection ETW Events</span></span>

<span data-ttu-id="b820b-117">El seguimiento de eventos para Windows (ETW) es un sistema de traza que complementa la compatibilidad con generación de perfiles y depuración proporcionada por .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b820b-117">Event tracing for Windows (ETW) is a tracing system that supplements the profiling and debugging support provided by the .NET Framework.</span></span> <span data-ttu-id="b820b-118">A partir de .NET Framework 4, los [eventos ETW de recolección de elementos no utilizados](../../../docs/framework/performance/garbage-collection-etw-events.md) capturan información útil para analizar el montón administrado desde un punto de vista estadístico.</span><span class="sxs-lookup"><span data-stu-id="b820b-118">Starting with the .NET Framework 4, [garbage collection ETW events](../../../docs/framework/performance/garbage-collection-etw-events.md) capture useful information for analyzing the managed heap from a statistical point of view.</span></span> <span data-ttu-id="b820b-119">Por ejemplo, el evento `GCStart_V1`, que se genera cuando está a punto de producirse una recolección de elementos no utilizados, proporciona la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="b820b-119">For example, the `GCStart_V1` event, which is raised when a garbage collection is about to occur, provides the following information:</span></span>

- <span data-ttu-id="b820b-120">La generación de objetos que se recolecta.</span><span class="sxs-lookup"><span data-stu-id="b820b-120">Which generation of objects is being collected.</span></span>

- <span data-ttu-id="b820b-121">Lo que desencadenó la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-121">What triggered the garbage collection.</span></span>

- <span data-ttu-id="b820b-122">Tipo de recolección de elementos no utilizados (simultánea o no simultánea).</span><span class="sxs-lookup"><span data-stu-id="b820b-122">Type of garbage collection (concurrent or not concurrent).</span></span>

<span data-ttu-id="b820b-123">El registro de eventos ETW es eficaz y no enmascara ningún problema de rendimiento asociado a la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-123">ETW event logging is efficient and will not mask any performance problems associated with garbage collection.</span></span> <span data-ttu-id="b820b-124">Un proceso puede proporcionar sus propios eventos junto con los eventos ETW.</span><span class="sxs-lookup"><span data-stu-id="b820b-124">A process can provide its own events in conjunction with ETW events.</span></span> <span data-ttu-id="b820b-125">Cuando se registran, tanto los eventos de la aplicación como los eventos de la recolección de elementos no utilizados se pueden poner en correlación para determinar cómo y cuándo se producen problemas de pila.</span><span class="sxs-lookup"><span data-stu-id="b820b-125">When logged, both the application's events and the garbage collection events can be correlated to determine how and when heap problems occur.</span></span> <span data-ttu-id="b820b-126">Por ejemplo, una aplicación de servidor puede proporcionar eventos al comienzo y al final de una solicitud de cliente.</span><span class="sxs-lookup"><span data-stu-id="b820b-126">For example, a server application could provide events at the start and end of a client request.</span></span>

### <a name="the-profiling-api"></a><span data-ttu-id="b820b-127">La API de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="b820b-127">The Profiling API</span></span>

<span data-ttu-id="b820b-128">Las interfaces de generación de perfiles de Common Language Runtime (CLR) proporcionan información detallada sobre los objetos que se vieron afectados durante la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-128">The common language runtime (CLR) profiling interfaces provide detailed information about the objects that were affected during garbage collection.</span></span> <span data-ttu-id="b820b-129">Un generador de perfiles puede recibir una notificación cuando se inicia y finaliza una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-129">A profiler can be notified when a garbage collection starts and ends.</span></span> <span data-ttu-id="b820b-130">Puede proporcionar informes sobre los objetos del montón administrado, incluida una identificación de los objetos de cada generación.</span><span class="sxs-lookup"><span data-stu-id="b820b-130">It can provide reports about the objects on the managed heap, including an identification of objects in each generation.</span></span> <span data-ttu-id="b820b-131">Para más información, consulte [Información general sobre la generación de perfiles](../../../docs/framework/unmanaged-api/profiling/profiling-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b820b-131">For more information, see [Profiling Overview](../../../docs/framework/unmanaged-api/profiling/profiling-overview.md).</span></span>

<span data-ttu-id="b820b-132">Los generadores de perfiles pueden proporcionar información completa.</span><span class="sxs-lookup"><span data-stu-id="b820b-132">Profilers can provide comprehensive information.</span></span> <span data-ttu-id="b820b-133">Sin embargo, los generadores de perfiles complejos pueden modificar el comportamiento de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="b820b-133">However, complex profilers can potentially modify an application's behavior.</span></span>

### <a name="application-domain-resource-monitoring"></a><span data-ttu-id="b820b-134">Supervisión de recursos de dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="b820b-134">Application Domain Resource Monitoring</span></span>

<span data-ttu-id="b820b-135">A partir de .NET Framework 4, la supervisión de recursos de dominio de aplicación (ARM) permite a los anfitriones supervisar el uso de la CPU y la memoria por parte del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b820b-135">Starting with the .NET Framework 4, Application domain resource monitoring (ARM) enables hosts to monitor CPU and memory usage by application domain.</span></span> <span data-ttu-id="b820b-136">Para más información, consulte [Supervisión de recursos de dominio de aplicación](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md).</span><span class="sxs-lookup"><span data-stu-id="b820b-136">For more information, see [Application Domain Resource Monitoring](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md).</span></span>

## <a name="troubleshooting-performance-issues"></a><span data-ttu-id="b820b-137">Solucionar problemas de rendimiento</span><span class="sxs-lookup"><span data-stu-id="b820b-137">Troubleshooting Performance Issues</span></span>

<span data-ttu-id="b820b-138">El primer paso consiste en [determinar si el problema es realmente la recolección de elementos no utilizados](#IsGC).</span><span class="sxs-lookup"><span data-stu-id="b820b-138">The first step is to [determine whether the issue is actually garbage collection](#IsGC).</span></span> <span data-ttu-id="b820b-139">Si determina que lo es, seleccione un elemento de la lista siguiente para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="b820b-139">If you determine that it is, select from the following list to troubleshoot the problem.</span></span>

- [<span data-ttu-id="b820b-140">Se inicia una excepción de memoria insuficiente</span><span class="sxs-lookup"><span data-stu-id="b820b-140">An out-of-memory exception is thrown</span></span>](#Issue_OOM)

- [<span data-ttu-id="b820b-141">El proceso usa demasiada memoria</span><span class="sxs-lookup"><span data-stu-id="b820b-141">The process uses too much memory</span></span>](#Issue_TooMuchMemory)

- [<span data-ttu-id="b820b-142">El recolector de elementos no utilizados no recupera los objetos con la rapidez suficiente</span><span class="sxs-lookup"><span data-stu-id="b820b-142">The garbage collector does not reclaim objects fast enough</span></span>](#Issue_NotFastEnough)

- [<span data-ttu-id="b820b-143">El montón administrado está demasiado fragmentado</span><span class="sxs-lookup"><span data-stu-id="b820b-143">The managed heap is too fragmented</span></span>](#Issue_Fragmentation)

- [<span data-ttu-id="b820b-144">Las pausas de la recolección de elementos no utilizados son demasiado largas</span><span class="sxs-lookup"><span data-stu-id="b820b-144">Garbage collection pauses are too long</span></span>](#Issue_LongPauses)

- [<span data-ttu-id="b820b-145">La generación 0 es demasiado grande</span><span class="sxs-lookup"><span data-stu-id="b820b-145">Generation 0 is too big</span></span>](#Issue_Gen0)

- [<span data-ttu-id="b820b-146">El uso de CPU durante una recolección de elementos no utilizados es demasiado alto</span><span class="sxs-lookup"><span data-stu-id="b820b-146">CPU usage during a garbage collection is too high</span></span>](#Issue_HighCPU)

<a name="Issue_OOM"></a>

### <a name="issue-an-out-of-memory-exception-is-thrown"></a><span data-ttu-id="b820b-147">Problema: Se inicia una excepción de memoria insuficiente</span><span class="sxs-lookup"><span data-stu-id="b820b-147">Issue: An Out-of-Memory Exception Is Thrown</span></span>

<span data-ttu-id="b820b-148">Hay dos casos justificados para que se produzca una excepción <xref:System.OutOfMemoryException> administrada:</span><span class="sxs-lookup"><span data-stu-id="b820b-148">There are two legitimate cases for a managed <xref:System.OutOfMemoryException> to be thrown:</span></span>

- <span data-ttu-id="b820b-149">La escasez de memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="b820b-149">Running out of virtual memory.</span></span>

  <span data-ttu-id="b820b-150">El recolector de elementos no utilizados asigna memoria del sistema en segmentos de un tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b820b-150">The garbage collector allocates memory from the system in segments of a pre-determined size.</span></span> <span data-ttu-id="b820b-151">Si una asignación necesita un segmento adicional, pero no queda ningún bloque libre contiguo en el espacio de memoria virtual del proceso, se producirá un error en la asignación del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b820b-151">If an allocation requires an additional segment, but there is no contiguous free block left in the process's virtual memory space, the allocation for the managed heap will fail.</span></span>

- <span data-ttu-id="b820b-152">No tener suficiente memoria física para asignar.</span><span class="sxs-lookup"><span data-stu-id="b820b-152">Not having enough physical memory to allocate.</span></span>

|<span data-ttu-id="b820b-153">Comprobaciones de rendimiento</span><span class="sxs-lookup"><span data-stu-id="b820b-153">Performance checks</span></span>|
|------------------------|
|[<span data-ttu-id="b820b-154">Determine si la excepción de memoria insuficiente está administrada.</span><span class="sxs-lookup"><span data-stu-id="b820b-154">Determine whether the out-of-memory exception is managed.</span></span>](#OOMIsManaged)<br /><br /> [<span data-ttu-id="b820b-155">Determine cuánta memoria virtual se puede reservar.</span><span class="sxs-lookup"><span data-stu-id="b820b-155">Determine how much virtual memory can be reserved.</span></span>](#GetVM)<br /><br /> [<span data-ttu-id="b820b-156">Determine si hay suficiente memoria física.</span><span class="sxs-lookup"><span data-stu-id="b820b-156">Determine whether there is enough physical memory.</span></span>](#Physical)|

<span data-ttu-id="b820b-157">Si determina que la excepción no es legítima, póngase en contacto con el servicio de atención al cliente y soporte técnico de Microsoft, y proporcione la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="b820b-157">If you determine that the exception is not legitimate, contact Microsoft Customer Service and Support with the following information:</span></span>

- <span data-ttu-id="b820b-158">La pila con la excepción administrada de memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="b820b-158">The stack with the managed out-of-memory exception.</span></span>

- <span data-ttu-id="b820b-159">Un volcado de memoria completo.</span><span class="sxs-lookup"><span data-stu-id="b820b-159">Full memory dump.</span></span>

- <span data-ttu-id="b820b-160">Los datos que demuestran que no es una excepción legítima de memoria insuficiente, incluidos los datos que muestran que la memoria virtual o la memoria física no supone ningún problema.</span><span class="sxs-lookup"><span data-stu-id="b820b-160">Data that proves that it is not a legitimate out-of-memory exception, including data that shows that virtual or physical memory is not an issue.</span></span>

<a name="Issue_TooMuchMemory"></a>

### <a name="issue-the-process-uses-too-much-memory"></a><span data-ttu-id="b820b-161">Problema: El proceso usa demasiada memoria</span><span class="sxs-lookup"><span data-stu-id="b820b-161">Issue: The Process Uses Too Much Memory</span></span>

<span data-ttu-id="b820b-162">Un supuesto común es que el uso de memoria que aparece en la pestaña **Rendimiento** del Administrador de tareas de Windows puede indicar cuándo se está usando demasiada memoria.</span><span class="sxs-lookup"><span data-stu-id="b820b-162">A common assumption is that the memory usage display on the **Performance** tab of Windows Task Manager can indicate when too much memory is being used.</span></span> <span data-ttu-id="b820b-163">Sin embargo, esa información pertenece al espacio de trabajo; no proporciona información sobre el uso de memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="b820b-163">However, that display pertains to the working set; it does not provide information about virtual memory usage.</span></span>

<span data-ttu-id="b820b-164">Si determina que el problema está provocado por el montón administrado, debe medir el montón administrado a lo largo del tiempo para determinar cualquier patrón.</span><span class="sxs-lookup"><span data-stu-id="b820b-164">If you determine that the issue is caused by the managed heap, you must measure the managed heap over time to determine any patterns.</span></span>

<span data-ttu-id="b820b-165">Si determina que el problema no está provocado por el montón administrado, debe usar la depuración nativa.</span><span class="sxs-lookup"><span data-stu-id="b820b-165">If you determine that the problem is not caused by the managed heap, you must use native debugging.</span></span>

|<span data-ttu-id="b820b-166">Comprobaciones de rendimiento</span><span class="sxs-lookup"><span data-stu-id="b820b-166">Performance checks</span></span>|
|------------------------|
|[<span data-ttu-id="b820b-167">Determine cuánta memoria virtual se puede reservar.</span><span class="sxs-lookup"><span data-stu-id="b820b-167">Determine how much virtual memory can be reserved.</span></span>](#GetVM)<br /><br /> [<span data-ttu-id="b820b-168">Determine cuánta memoria está confirmando el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b820b-168">Determine how much memory the managed heap is committing.</span></span>](#ManagedHeapCommit)<br /><br /> [<span data-ttu-id="b820b-169">Determine cuánta memoria reserva el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b820b-169">Determine how much memory the managed heap reserves.</span></span>](#ManagedHeapReserve)<br /><br /> [<span data-ttu-id="b820b-170">Determine los objetos grandes de la generación 2.</span><span class="sxs-lookup"><span data-stu-id="b820b-170">Determine large objects in generation 2.</span></span>](#ExamineGen2)<br /><br /> [<span data-ttu-id="b820b-171">Determine las referencias a objetos.</span><span class="sxs-lookup"><span data-stu-id="b820b-171">Determine references to objects.</span></span>](#ObjRef)|

<a name="Issue_NotFastEnough"></a>

### <a name="issue-the-garbage-collector-does-not-reclaim-objects-fast-enough"></a><span data-ttu-id="b820b-172">Problema: El recolector de elementos no utilizados no recupera los objetos con la rapidez suficiente</span><span class="sxs-lookup"><span data-stu-id="b820b-172">Issue: The Garbage Collector Does Not Reclaim Objects Fast Enough</span></span>

<span data-ttu-id="b820b-173">Cuando parezca que la recolección de elementos no utilizados no está recuperando los objetos según lo esperado, debe determinar si hay alguna referencia segura a esos objetos.</span><span class="sxs-lookup"><span data-stu-id="b820b-173">When it appears as if objects are not being reclaimed as expected for garbage collection, you must determine if there are any strong references to those objects.</span></span>

<span data-ttu-id="b820b-174">También puede encontrar este problema si no se ha producido ninguna recolección de elementos no utilizados para la generación que contiene un objeto muerto, lo que indica que el finalizador del objeto muerto no se ha ejecutado.</span><span class="sxs-lookup"><span data-stu-id="b820b-174">You may also encounter this issue if there has been no garbage collection for the generation that contains a dead object, which indicates that the finalizer for the dead object has not been run.</span></span> <span data-ttu-id="b820b-175">Por ejemplo, esto puede ocurrir cuando se ejecuta una aplicación de contenedor uniproceso (STA) y el subproceso que atiende a la cola del finalizador no la puede llamar.</span><span class="sxs-lookup"><span data-stu-id="b820b-175">For example, this is possible when you are running a single-threaded apartment (STA) application and the thread that services the finalizer queue cannot call into it.</span></span>

|<span data-ttu-id="b820b-176">Comprobaciones de rendimiento</span><span class="sxs-lookup"><span data-stu-id="b820b-176">Performance checks</span></span>|
|------------------------|
|[<span data-ttu-id="b820b-177">Compruebe las referencias a objetos.</span><span class="sxs-lookup"><span data-stu-id="b820b-177">Check references to objects.</span></span>](#ObjRef)<br /><br /> [<span data-ttu-id="b820b-178">Determine si se ha ejecutado un finalizador.</span><span class="sxs-lookup"><span data-stu-id="b820b-178">Determine whether a finalizer has been run.</span></span>](#Induce)<br /><br /> [<span data-ttu-id="b820b-179">Determine si hay objetos en espera de finalización.</span><span class="sxs-lookup"><span data-stu-id="b820b-179">Determine whether there are objects waiting to be finalized.</span></span>](#Finalize)|

<a name="Issue_Fragmentation"></a>

### <a name="issue-the-managed-heap-is-too-fragmented"></a><span data-ttu-id="b820b-180">Problema: El montón administrado está demasiado fragmentado</span><span class="sxs-lookup"><span data-stu-id="b820b-180">Issue: The Managed Heap Is Too fragmented</span></span>

<span data-ttu-id="b820b-181">El nivel de fragmentación se calcula como la proporción de espacio disponible con respecto a la memoria total asignada para la generación.</span><span class="sxs-lookup"><span data-stu-id="b820b-181">The fragmentation level is calculated as the ratio of free space over the total allocated memory for the generation.</span></span> <span data-ttu-id="b820b-182">Para la generación 2, un nivel aceptable de fragmentación es inferior al 20%.</span><span class="sxs-lookup"><span data-stu-id="b820b-182">For generation 2, an acceptable level of fragmentation is no more than 20%.</span></span> <span data-ttu-id="b820b-183">Puesto que la generación 2 puede llegar a ser muy grande, la proporción de fragmentación es más importante que el valor absoluto.</span><span class="sxs-lookup"><span data-stu-id="b820b-183">Because generation 2 can get very big, the ratio of fragmentation is more important than the absolute value.</span></span>

<span data-ttu-id="b820b-184">El hecho de tener mucho espacio disponible en la generación 0 no supone ningún problema porque esta es la generación donde se asignan nuevos objetos.</span><span class="sxs-lookup"><span data-stu-id="b820b-184">Having lots of free space in generation 0 is not a problem because this is the generation where new objects are allocated.</span></span>

<span data-ttu-id="b820b-185">Siempre se produce fragmentación en el montón de objetos grandes porque no se compacta.</span><span class="sxs-lookup"><span data-stu-id="b820b-185">Fragmentation always occurs in the large object heap because it is not compacted.</span></span> <span data-ttu-id="b820b-186">Los objetos libres adyacentes se contraen de forma natural en un único espacio para satisfacer las solicitudes de asignación de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="b820b-186">Free objects that are adjacent are naturally collapsed into a single space to satisfy large object allocation requests.</span></span>

<span data-ttu-id="b820b-187">La fragmentación puede convertirse en un problema en las generaciones 1 y 2.</span><span class="sxs-lookup"><span data-stu-id="b820b-187">Fragmentation can become a problem in generation 1 and generation 2.</span></span> <span data-ttu-id="b820b-188">Si estas generaciones tienen una gran cantidad de espacio disponible después de una recolección de elementos no utilizados, el uso de objetos de una aplicación puede necesitar modificaciones y debe considerar la posibilidad de volver a evaluar la duración de los objetos de larga duración.</span><span class="sxs-lookup"><span data-stu-id="b820b-188">If these generations have a large amount of free space after a garbage collection, an application's object usage may need modification, and you should consider re-evaluating the lifetime of long-term objects.</span></span>

<span data-ttu-id="b820b-189">El anclaje excesivo de objetos puede aumentar la fragmentación.</span><span class="sxs-lookup"><span data-stu-id="b820b-189">Excessive pinning of objects can increase fragmentation.</span></span> <span data-ttu-id="b820b-190">Si la fragmentación es elevada, puede que haya demasiados objetos anclados.</span><span class="sxs-lookup"><span data-stu-id="b820b-190">If fragmentation is high, too many objects could have been pinned.</span></span>

<span data-ttu-id="b820b-191">Si la fragmentación de la memoria virtual está impidiendo que el recolector de elementos no utilizados agregue segmentos, puede deberse a una de las causas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b820b-191">If fragmentation of virtual memory is preventing the garbage collector from adding segments, the causes could be one of the following:</span></span>

- <span data-ttu-id="b820b-192">Carga y descarga frecuentes de muchos ensamblados pequeños.</span><span class="sxs-lookup"><span data-stu-id="b820b-192">Frequent loading and unloading of many small assemblies.</span></span>

- <span data-ttu-id="b820b-193">Almacenamiento de demasiadas referencias a objetos COM al interoperar con código no administrado.</span><span class="sxs-lookup"><span data-stu-id="b820b-193">Holding too many references to COM objects when interoperating with unmanaged code.</span></span>

- <span data-ttu-id="b820b-194">Creación de objetos grandes transitorios, lo que hace que el montón de objetos grandes asigne y libere segmentos del montón con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="b820b-194">Creation of large transient objects, which causes the large object heap to allocate and free heap segments frequently.</span></span>

  <span data-ttu-id="b820b-195">Al hospedar el CLR, una aplicación puede solicitar que el recolector de elementos no utilizados conserve sus segmentos.</span><span class="sxs-lookup"><span data-stu-id="b820b-195">When hosting the CLR, an application can request that the garbage collector retain its segments.</span></span> <span data-ttu-id="b820b-196">Esto reduce la frecuencia de las asignaciones de segmentos.</span><span class="sxs-lookup"><span data-stu-id="b820b-196">This reduces the frequency of segment allocations.</span></span> <span data-ttu-id="b820b-197">Para ello se emplea la marca STARTUP_HOARD_GC_VM en la [enumeración STARTUP_FLAGS](../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="b820b-197">This is accomplished by using the STARTUP_HOARD_GC_VM flag in the [STARTUP_FLAGS Enumeration](../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).</span></span>

|<span data-ttu-id="b820b-198">Comprobaciones de rendimiento</span><span class="sxs-lookup"><span data-stu-id="b820b-198">Performance checks</span></span>|
|------------------------|
|[<span data-ttu-id="b820b-199">Determine la cantidad de espacio disponible en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b820b-199">Determine the amount of free space in the managed heap.</span></span>](#Fragmented)<br /><br /> [<span data-ttu-id="b820b-200">Determine el número de objetos anclados.</span><span class="sxs-lookup"><span data-stu-id="b820b-200">Determine the number of pinned objects.</span></span>](#Pinned)|

<span data-ttu-id="b820b-201">Si cree que no hay ninguna causa que justifique la fragmentación, póngase en contacto con el servicio de atención al cliente y soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b820b-201">If you think that there is no legitimate cause for the fragmentation, contact Microsoft Customer Service and Support.</span></span>

<a name="Issue_LongPauses"></a>

### <a name="issue-garbage-collection-pauses-are-too-long"></a><span data-ttu-id="b820b-202">Problema: Las pausas de la recolección de elementos no utilizados son demasiado largas</span><span class="sxs-lookup"><span data-stu-id="b820b-202">Issue: Garbage Collection Pauses Are Too Long</span></span>

<span data-ttu-id="b820b-203">La recolección de elementos no utilizados funciona en tiempo real flexible, por lo que una aplicación debe poder tolerar algunas pausas.</span><span class="sxs-lookup"><span data-stu-id="b820b-203">Garbage collection operates in soft real time, so an application must be able to tolerate some pauses.</span></span> <span data-ttu-id="b820b-204">Un criterio para el tiempo real flexible es que el 95% de las operaciones debe finalizar a tiempo.</span><span class="sxs-lookup"><span data-stu-id="b820b-204">A criterion for soft real time is that 95% of the operations must finish on time.</span></span>

<span data-ttu-id="b820b-205">En la recolección de elementos no utilizados simultánea, se permite la ejecución de subprocesos administrados durante una recolección, lo que significa que las pausas son mínimas.</span><span class="sxs-lookup"><span data-stu-id="b820b-205">In concurrent garbage collection, managed threads are allowed to run during a collection, which means that pauses are very minimal.</span></span>

<span data-ttu-id="b820b-206">Las recolecciones de elementos no utilizados efímeras (las generaciones 0 y 1) solo duran algunos milisegundos, por lo que no suele ser viable reducir las pausas.</span><span class="sxs-lookup"><span data-stu-id="b820b-206">Ephemeral garbage collections (generations 0 and 1) last only a few milliseconds, so decreasing pauses is usually not feasible.</span></span> <span data-ttu-id="b820b-207">Sin embargo, puede reducir las pausas en las recolecciones de la generación 2 cambiando el modelo de las solicitudes de asignación de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="b820b-207">However, you can decrease the pauses in generation 2 collections by changing the pattern of allocation requests by an application.</span></span>

<span data-ttu-id="b820b-208">Otro método más preciso consiste en usar [eventos ETW de recolección de elementos no utilizados](../../../docs/framework/performance/garbage-collection-etw-events.md).</span><span class="sxs-lookup"><span data-stu-id="b820b-208">Another, more accurate, method is to use [garbage collection ETW events](../../../docs/framework/performance/garbage-collection-etw-events.md).</span></span> <span data-ttu-id="b820b-209">Puede averiguar los controles de tiempo para las recolecciones si suma las diferencias de marca de tiempo para una secuencia de eventos.</span><span class="sxs-lookup"><span data-stu-id="b820b-209">You can find the timings for collections by adding the time stamp differences for a sequence of events.</span></span> <span data-ttu-id="b820b-210">La secuencia de recolección completa incluye la suspensión del motor de ejecución, la recolección de elementos no utilizados propiamente dicha y la reanudación del motor de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b820b-210">The whole collection sequence includes suspension of the execution engine, the garbage collection itself, and the resumption of the execution engine.</span></span>

<span data-ttu-id="b820b-211">Puede usar [notificaciones de recolección de elementos no utilizados](../../../docs/standard/garbage-collection/notifications.md) para determinar si se va a realizar una recolección de generación 2 en un servidor y si redirigir las solicitudes a otro servidor podría solucionar los problemas de las pausas.</span><span class="sxs-lookup"><span data-stu-id="b820b-211">You can use [Garbage Collection Notifications](../../../docs/standard/garbage-collection/notifications.md) to determine whether a server is about to have a generation 2 collection, and whether rerouting requests to another server could ease any problems with pauses.</span></span>

|<span data-ttu-id="b820b-212">Comprobaciones de rendimiento</span><span class="sxs-lookup"><span data-stu-id="b820b-212">Performance checks</span></span>|
|------------------------|
|[<span data-ttu-id="b820b-213">Determine la duración de una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-213">Determine the length of time in a garbage collection.</span></span>](#TimeInGC)<br /><br /> [<span data-ttu-id="b820b-214">Determine lo que desencadenó una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-214">Determine what caused a garbage collection.</span></span>](#Triggered)|

<a name="Issue_Gen0"></a>

### <a name="issue-generation-0-is-too-big"></a><span data-ttu-id="b820b-215">Problema: La generación 0 es demasiado grande</span><span class="sxs-lookup"><span data-stu-id="b820b-215">Issue: Generation 0 Is Too Big</span></span>

<span data-ttu-id="b820b-216">Es probable que la generación 0 tenga un número mayor de objetos en un sistema de 64 bits, sobre todo cuando se usa la recolección de elementos no utilizados de servidor en lugar de la de estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b820b-216">Generation 0 is likely to have a larger number of objects on a 64-bit system, especially when you use server garbage collection instead of workstation garbage collection.</span></span> <span data-ttu-id="b820b-217">Esto se debe a que el umbral para desencadenar una recolección de elementos no utilizados de generación 0 es más alto en estos entornos y las recolecciones de generación 0 pueden llegar a ser mucho mayores.</span><span class="sxs-lookup"><span data-stu-id="b820b-217">This is because the threshold to trigger a generation 0 garbage collection is higher in these environments, and generation 0 collections can get much bigger.</span></span> <span data-ttu-id="b820b-218">El rendimiento mejora cuando una aplicación asigna más memoria antes de que se desencadene una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-218">Performance is improved when an application allocates more memory before a garbage collection is triggered.</span></span>

<a name="Issue_HighCPU"></a>

### <a name="issue-cpu-usage-during-a-garbage-collection-is-too-high"></a><span data-ttu-id="b820b-219">Problema: El uso de CPU durante una recolección de elementos no utilizados es demasiado alto</span><span class="sxs-lookup"><span data-stu-id="b820b-219">Issue: CPU Usage During a Garbage Collection Is Too High</span></span>

<span data-ttu-id="b820b-220">El uso de CPU será elevado durante una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-220">CPU usage will be high during a garbage collection.</span></span> <span data-ttu-id="b820b-221">Si se dedica una cantidad significativa de tiempo de proceso a una recolección de elementos no utilizados, el número de recolecciones es demasiado frecuente o la recolección está durando demasiado.</span><span class="sxs-lookup"><span data-stu-id="b820b-221">If a significant amount of process time is spent in a garbage collection, the number of collections is too frequent or the collection is lasting too long.</span></span> <span data-ttu-id="b820b-222">Una proporción de asignación de objetos mayor en el montón administrado hace que la recolección de elementos no utilizados se realice con más frecuencia.</span><span class="sxs-lookup"><span data-stu-id="b820b-222">An increased allocation rate of objects on the managed heap causes garbage collection to occur more frequently.</span></span> <span data-ttu-id="b820b-223">Al disminuir la proporción de asignación se reduce la frecuencia de las recolecciones de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-223">Decreasing the allocation rate reduces the frequency of garbage collections.</span></span>

<span data-ttu-id="b820b-224">Puede supervisar las proporciones de asignación mediante el contador de rendimiento `Allocated Bytes/second`.</span><span class="sxs-lookup"><span data-stu-id="b820b-224">You can monitor allocation rates by using the `Allocated Bytes/second` performance counter.</span></span> <span data-ttu-id="b820b-225">Para más información, consulte [Contadores de rendimiento en .NET Framework](../../../docs/framework/debug-trace-profile/performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="b820b-225">For more information, see [Performance Counters in the .NET Framework](../../../docs/framework/debug-trace-profile/performance-counters.md).</span></span>

<span data-ttu-id="b820b-226">La duración de una recolección suele depender del número de objetos que sobrevivan después de la asignación.</span><span class="sxs-lookup"><span data-stu-id="b820b-226">The duration of a collection is primarily a factor of the number of objects that survive after allocation.</span></span> <span data-ttu-id="b820b-227">El recolector de elementos no utilizados debe pasar por una gran cantidad de memoria si hay que recolectar muchos objetos.</span><span class="sxs-lookup"><span data-stu-id="b820b-227">The garbage collector must go through a large amount of memory if many objects remain to be collected.</span></span> <span data-ttu-id="b820b-228">El trabajo para compactar los supervivientes lleva mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="b820b-228">The work to compact the survivors is time-consuming.</span></span> <span data-ttu-id="b820b-229">Para determinar cuántos objetos se controlaron durante una recolección, establezca un punto de interrupción en el depurador al final de una recolección de elementos no utilizados para una generación especificada.</span><span class="sxs-lookup"><span data-stu-id="b820b-229">To determine how many objects were handled during a collection, set a breakpoint in the debugger at the end of a garbage collection for a specified generation.</span></span>

|<span data-ttu-id="b820b-230">Comprobaciones de rendimiento</span><span class="sxs-lookup"><span data-stu-id="b820b-230">Performance checks</span></span>|
|------------------------|
|[<span data-ttu-id="b820b-231">Determine si el uso elevado de CPU está provocado por la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-231">Determine if high CPU usage is caused by garbage collection.</span></span>](#HighCPU)<br /><br /> [<span data-ttu-id="b820b-232">Establezca un punto de interrupción al final de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-232">Set a breakpoint at the end of garbage collection.</span></span>](#GenBreak)|

## <a name="troubleshooting-guidelines"></a><span data-ttu-id="b820b-233">Instrucciones para la solución de problemas</span><span class="sxs-lookup"><span data-stu-id="b820b-233">Troubleshooting Guidelines</span></span>

<span data-ttu-id="b820b-234">En esta sección se describen instrucciones debe tener en cuenta cuando empiece las investigaciones.</span><span class="sxs-lookup"><span data-stu-id="b820b-234">This section describes guidelines that you should consider as you begin your investigations.</span></span>

### <a name="workstation-or-server-garbage-collection"></a><span data-ttu-id="b820b-235">Recolección de elementos no utilizados de estación de trabajo o de servidor</span><span class="sxs-lookup"><span data-stu-id="b820b-235">Workstation or Server Garbage Collection</span></span>

<span data-ttu-id="b820b-236">Determine si está usando el tipo correcto de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-236">Determine if you are using the correct type of garbage collection.</span></span> <span data-ttu-id="b820b-237">Si la aplicación emplea varios subprocesos e instancias de objeto, use la recolección de elementos no utilizados de servidor en lugar de la de estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b820b-237">If your application uses multiple threads and object instances, use server garbage collection instead of workstation garbage collection.</span></span> <span data-ttu-id="b820b-238">La recolección de elementos no utilizados de servidor funciona en varios subprocesos, mientras que la de estación de trabajo necesita que varias instancias de una aplicación ejecuten sus propios subprocesos de recolección de elementos no utilizados y compitan por el tiempo de CPU.</span><span class="sxs-lookup"><span data-stu-id="b820b-238">Server garbage collection operates on multiple threads, whereas workstation garbage collection requires multiple instances of an application to run their own garbage collection threads and compete for CPU time.</span></span>

<span data-ttu-id="b820b-239">Una aplicación que tenga una carga baja y realice tareas con poca frecuencia en segundo plano, como un servicio, puede usar la recolección de elementos no utilizados de estación de trabajo con la recolección simultánea de elementos no utilizados deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="b820b-239">An application that has a low load and that performs tasks infrequently in the background, such as a service, could use workstation garbage collection with concurrent garbage collection disabled.</span></span>

### <a name="when-to-measure-the-managed-heap-size"></a><span data-ttu-id="b820b-240">Cuándo medir el tamaño del montón administrado</span><span class="sxs-lookup"><span data-stu-id="b820b-240">When to Measure the Managed Heap Size</span></span>

<span data-ttu-id="b820b-241">A menos que esté usando un generador de perfiles, tendrá que establecer un modelo de medida coherente para diagnosticar eficazmente los problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b820b-241">Unless you are using a profiler, you will have to establish a consistent measuring pattern to effectively diagnose performance issues.</span></span> <span data-ttu-id="b820b-242">Tenga en cuenta lo siguiente a la hora de establecer una programación:</span><span class="sxs-lookup"><span data-stu-id="b820b-242">Consider the following points to establish a schedule:</span></span>

- <span data-ttu-id="b820b-243">Si mide después de una recolección de elementos no utilizados de generación 2, todo el montón administrado estará libre de elementos no utilizados (objetos muertos).</span><span class="sxs-lookup"><span data-stu-id="b820b-243">If you measure after a generation 2 garbage collection, the entire managed heap will be free of garbage (dead objects).</span></span>

- <span data-ttu-id="b820b-244">Si mide inmediatamente después de una recolección de elementos no utilizados de generación 0, los objetos de las generaciones 1 y 2 no se recolectarán todavía.</span><span class="sxs-lookup"><span data-stu-id="b820b-244">If you measure immediately after a generation 0 garbage collection, the objects in generations 1 and 2 will not be collected yet.</span></span>

- <span data-ttu-id="b820b-245">Si mide inmediatamente antes de una recolección de elementos no utilizados, se medirá toda la asignación posible antes de que comience dicha recolección.</span><span class="sxs-lookup"><span data-stu-id="b820b-245">If you measure immediately before a garbage collection, you will measure as much allocation as possible before the garbage collection starts.</span></span>

- <span data-ttu-id="b820b-246">La medición durante una recolección de elementos no utilizados es problemática, ya que las estructuras de datos del recolector de elementos no utilizados no están en un estado válido para el cruce seguro y quizás no se obtengan resultados completos.</span><span class="sxs-lookup"><span data-stu-id="b820b-246">Measuring during a garbage collection is problematic, because the garbage collector data structures are not in a valid state for traversal and may not be able to give you the complete results.</span></span> <span data-ttu-id="b820b-247">Esto es intencionado.</span><span class="sxs-lookup"><span data-stu-id="b820b-247">This is by design.</span></span>

- <span data-ttu-id="b820b-248">Cuando se usa la recolección de elementos no utilizados de estación de trabajo con la recolección simultánea de elementos no utilizados, los objetos recuperados no se compactan, por lo que el tamaño del montón puede ser igual o mayor (la fragmentación puede hacer que parezca mayor).</span><span class="sxs-lookup"><span data-stu-id="b820b-248">When you are using workstation garbage collection with concurrent garbage collection, the reclaimed objects are not compacted, so the heap size can be the same or larger (fragmentation can make it appear to be larger).</span></span>

- <span data-ttu-id="b820b-249">La recolección de elementos no utilizados simultánea en la generación 2 se retrasa cuando la carga de memoria física es demasiado alta.</span><span class="sxs-lookup"><span data-stu-id="b820b-249">Concurrent garbage collection on generation 2 is delayed when the physical memory load is too high.</span></span>

<span data-ttu-id="b820b-250">En el procedimiento siguiente se describe cómo establecer un punto de interrupción para que pueda medir el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b820b-250">The following procedure describes how to set a breakpoint so that you can measure the managed heap.</span></span>

<a name="GenBreak"></a>

#### <a name="to-set-a-breakpoint-at-the-end-of-garbage-collection"></a><span data-ttu-id="b820b-251">Para establecer un punto de interrupción al final de la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="b820b-251">To set a breakpoint at the end of garbage collection</span></span>

- <span data-ttu-id="b820b-252">En WinDbg con la extensión del depurador de SOS cargada, escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="b820b-252">In WinDbg with the SOS debugger extension loaded, type the following command:</span></span>

  <span data-ttu-id="b820b-253">**bp mscorwks!WKS::GCHeap::RestartEE "j (dwo(mscorwks!WKS::GCHeap::GcCondemnedGeneration)==2) 'kb';'g'"**</span><span class="sxs-lookup"><span data-stu-id="b820b-253">**bp mscorwks!WKS::GCHeap::RestartEE "j (dwo(mscorwks!WKS::GCHeap::GcCondemnedGeneration)==2) 'kb';'g'"**</span></span>

  <span data-ttu-id="b820b-254">donde **GcCondemnedGeneration** se establece en la generación que se prefiera.</span><span class="sxs-lookup"><span data-stu-id="b820b-254">where **GcCondemnedGeneration** is set to the desired generation.</span></span> <span data-ttu-id="b820b-255">Este comando necesita símbolos privados.</span><span class="sxs-lookup"><span data-stu-id="b820b-255">This command requires private symbols.</span></span>

  <span data-ttu-id="b820b-256">Este comando fuerza una interrupción si **RestartEE** se ejecuta una vez recuperados los objetos de generación 2 para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-256">This command forces a break if **RestartEE** is executed after generation 2 objects have been reclaimed for garbage collection.</span></span>

  <span data-ttu-id="b820b-257">En la recolección de elementos no utilizados de servidor, solo un subproceso llama a **RestartEE**, por lo que el punto de interrupción solo se producirá una vez durante una recolección de elementos no utilizados de generación 2.</span><span class="sxs-lookup"><span data-stu-id="b820b-257">In server garbage collection, only one thread calls **RestartEE**, so the breakpoint will occur only once during a generation 2 garbage collection.</span></span>

## <a name="performance-check-procedures"></a><span data-ttu-id="b820b-258">Procedimientos para comprobar el rendimiento</span><span class="sxs-lookup"><span data-stu-id="b820b-258">Performance Check Procedures</span></span>

<span data-ttu-id="b820b-259">En esta sección se describen los procedimientos siguientes para aislar la causa del problema de rendimiento:</span><span class="sxs-lookup"><span data-stu-id="b820b-259">This section describes the following procedures to isolate the cause of your performance issue:</span></span>

- [<span data-ttu-id="b820b-260">Determine si el problema está provocado por la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-260">Determine whether the problem is caused by garbage collection.</span></span>](#IsGC)

- [<span data-ttu-id="b820b-261">Determine si la excepción de memoria insuficiente está administrada.</span><span class="sxs-lookup"><span data-stu-id="b820b-261">Determine whether the out-of-memory exception is managed.</span></span>](#OOMIsManaged)

- [<span data-ttu-id="b820b-262">Determine cuánta memoria virtual se puede reservar.</span><span class="sxs-lookup"><span data-stu-id="b820b-262">Determine how much virtual memory can be reserved.</span></span>](#GetVM)

- [<span data-ttu-id="b820b-263">Determine si hay suficiente memoria física.</span><span class="sxs-lookup"><span data-stu-id="b820b-263">Determine whether there is enough physical memory.</span></span>](#Physical)

- [<span data-ttu-id="b820b-264">Determine cuánta memoria está confirmando el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b820b-264">Determine how much memory the managed heap is committing.</span></span>](#ManagedHeapCommit)

- [<span data-ttu-id="b820b-265">Determine cuánta memoria reserva el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b820b-265">Determine how much memory the managed heap reserves.</span></span>](#ManagedHeapReserve)

- [<span data-ttu-id="b820b-266">Determine los objetos grandes de la generación 2.</span><span class="sxs-lookup"><span data-stu-id="b820b-266">Determine large objects in generation 2.</span></span>](#ExamineGen2)

- [<span data-ttu-id="b820b-267">Determine las referencias a objetos.</span><span class="sxs-lookup"><span data-stu-id="b820b-267">Determine references to objects.</span></span>](#ObjRef)

- [<span data-ttu-id="b820b-268">Determine si se ha ejecutado un finalizador.</span><span class="sxs-lookup"><span data-stu-id="b820b-268">Determine whether a finalizer has been run.</span></span>](#Induce)

- [<span data-ttu-id="b820b-269">Determine si hay objetos en espera de finalización.</span><span class="sxs-lookup"><span data-stu-id="b820b-269">Determine whether there are objects waiting to be finalized.</span></span>](#Finalize)

- [<span data-ttu-id="b820b-270">Determine la cantidad de espacio disponible en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b820b-270">Determine the amount of free space in the managed heap.</span></span>](#Fragmented)

- [<span data-ttu-id="b820b-271">Determine el número de objetos anclados.</span><span class="sxs-lookup"><span data-stu-id="b820b-271">Determine the number of pinned objects.</span></span>](#Pinned)

- [<span data-ttu-id="b820b-272">Determine la duración de una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-272">Determine the length of time in a garbage collection.</span></span>](#TimeInGC)

- [<span data-ttu-id="b820b-273">Determine lo que desencadenó una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-273">Determine what triggered a garbage collection.</span></span>](#Triggered)

- [<span data-ttu-id="b820b-274">Determine si el uso elevado de CPU está provocado por la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-274">Determine whether high CPU usage is caused by garbage collection.</span></span>](#HighCPU)

<a name="IsGC"></a>

### <a name="to-determine-whether-the-problem-is-caused-by-garbage-collection"></a><span data-ttu-id="b820b-275">Para determinar si el problema está provocado por la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="b820b-275">To determine whether the problem is caused by garbage collection</span></span>

- <span data-ttu-id="b820b-276">Examine los dos contadores de rendimiento de memoria siguientes:</span><span class="sxs-lookup"><span data-stu-id="b820b-276">Examine the following two memory performance counters:</span></span>

  - <span data-ttu-id="b820b-277">**% de tiempo de la GC**.</span><span class="sxs-lookup"><span data-stu-id="b820b-277">**% Time in GC**.</span></span> <span data-ttu-id="b820b-278">Muestra el porcentaje de tiempo transcurrido que se dedicó a realizar una recolección de elementos no utilizados después del último ciclo de recolección.</span><span class="sxs-lookup"><span data-stu-id="b820b-278">Displays the percentage of elapsed time that was spent performing a garbage collection after the last garbage collection cycle.</span></span> <span data-ttu-id="b820b-279">Use este contador para determinar si el recolector de elementos no utilizados está dedicando demasiado tiempo a hacer que haya espacio disponible en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b820b-279">Use this counter to determine whether the garbage collector is spending too much time to make managed heap space available.</span></span> <span data-ttu-id="b820b-280">Si el tiempo dedicado a la recolección de elementos no utilizados es relativamente bajo, podría indicar un problema de recursos fuera del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b820b-280">If the time spent in garbage collection is relatively low, that could indicate a resource problem outside the managed heap.</span></span> <span data-ttu-id="b820b-281">Puede que este contador no sea exacto cuando se invoca una recolección de elementos no utilizados simultánea o en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="b820b-281">This counter may not be accurate when concurrent or background garbage collection is involved.</span></span>

  - <span data-ttu-id="b820b-282">**Número de bytes totales confirmados**.</span><span class="sxs-lookup"><span data-stu-id="b820b-282">**# Total committed Bytes**.</span></span> <span data-ttu-id="b820b-283">Muestra la cantidad de memoria virtual confirmada actualmente por el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-283">Displays the amount of virtual memory currently committed by the garbage collector.</span></span> <span data-ttu-id="b820b-284">Use este contador para determinar si la memoria usada por el recolector de elementos no utilizados es una parte excesiva de la memoria que su aplicación emplea.</span><span class="sxs-lookup"><span data-stu-id="b820b-284">Use this counter to determine whether the memory consumed by the garbage collector is an excessive portion of the memory that your application uses.</span></span>

  <span data-ttu-id="b820b-285">La mayoría de los contadores de rendimiento de memoria se actualizan al final de cada recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-285">Most of the memory performance counters are updated at the end of each garbage collection.</span></span> <span data-ttu-id="b820b-286">Por tanto, puede que no reflejen las condiciones actuales sobre las que desea obtener información.</span><span class="sxs-lookup"><span data-stu-id="b820b-286">Therefore, they may not reflect the current conditions that you want information about.</span></span>

<a name="OOMIsManaged"></a>

### <a name="to-determine-whether-the-out-of-memory-exception-is-managed"></a><span data-ttu-id="b820b-287">Para determinar si la excepción de memoria insuficiente está administrada</span><span class="sxs-lookup"><span data-stu-id="b820b-287">To determine whether the out-of-memory exception is managed</span></span>

1. <span data-ttu-id="b820b-288">En WinDbg o en el depurador de Visual Studio con la extensión del depurador de SOS cargada, escriba el comando de impresión de excepciones (**pe**):</span><span class="sxs-lookup"><span data-stu-id="b820b-288">In the WinDbg or Visual Studio debugger with the SOS debugger extension loaded, type the print exception (**pe**) command:</span></span>

    <span data-ttu-id="b820b-289">**!pe**</span><span class="sxs-lookup"><span data-stu-id="b820b-289">**!pe**</span></span>

    <span data-ttu-id="b820b-290">Si la excepción es administrada, se mostrará <xref:System.OutOfMemoryException> como el tipo de excepción, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b820b-290">If the exception is managed, <xref:System.OutOfMemoryException> is displayed as the exception type, as shown in the following example.</span></span>

    ```console
    Exception object: 39594518
    Exception type: System.OutOfMemoryException
    Message: <none>
    InnerException: <none>
    StackTrace (generated):
    ```

2. <span data-ttu-id="b820b-291">Si el resultado no especifica ninguna excepción, tiene que determinar de qué subproceso procede la excepción de memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="b820b-291">If the output does not specify an exception, you have to determine which thread the out-of-memory exception is from.</span></span> <span data-ttu-id="b820b-292">Escriba el comando siguiente en el depurador para mostrar todos los subprocesos con sus pilas de llamadas:</span><span class="sxs-lookup"><span data-stu-id="b820b-292">Type the following command in the debugger to show all the threads with their call stacks:</span></span>

    <span data-ttu-id="b820b-293">**~\*KB**</span><span class="sxs-lookup"><span data-stu-id="b820b-293">**~\*kb**</span></span>

    <span data-ttu-id="b820b-294">El argumento `RaiseTheException` indica el subproceso con la pila que tiene llamadas de excepción.</span><span class="sxs-lookup"><span data-stu-id="b820b-294">The thread with the stack that has exception calls is indicated by the `RaiseTheException` argument.</span></span> <span data-ttu-id="b820b-295">Este es el objeto de excepción administrado.</span><span class="sxs-lookup"><span data-stu-id="b820b-295">This is the managed exception object.</span></span>

    ```console
    28adfb44 7923918f 5b61f2b4 00000000 5b61f2b4 mscorwks!RaiseTheException+0xa0
    ```

3. <span data-ttu-id="b820b-296">Puede usar el comando siguiente para volcar las excepciones anidadas.</span><span class="sxs-lookup"><span data-stu-id="b820b-296">You can use the following command to dump nested exceptions.</span></span>

    <span data-ttu-id="b820b-297">**!pe -nested**</span><span class="sxs-lookup"><span data-stu-id="b820b-297">**!pe -nested**</span></span>

    <span data-ttu-id="b820b-298">Si no encuentra ninguna excepción, la excepción de memoria insuficiente se originó desde código no administrado.</span><span class="sxs-lookup"><span data-stu-id="b820b-298">If you do not find any exceptions, the out-of-memory exception originated from unmanaged code.</span></span>

<a name="GetVM"></a>

### <a name="to-determine-how-much-virtual-memory-can-be-reserved"></a><span data-ttu-id="b820b-299">Para determinar cuánta memoria virtual se puede reservar</span><span class="sxs-lookup"><span data-stu-id="b820b-299">To determine how much virtual memory can be reserved</span></span>

- <span data-ttu-id="b820b-300">En WinDbg con la extensión del depurador de SOS cargada, escriba el comando siguiente para obtener la mayor región disponible:</span><span class="sxs-lookup"><span data-stu-id="b820b-300">In WinDbg with the SOS debugger extension loaded, type the following command to get the largest free region:</span></span>

  <span data-ttu-id="b820b-301">**!address -summary**</span><span class="sxs-lookup"><span data-stu-id="b820b-301">**!address -summary**</span></span>

  <span data-ttu-id="b820b-302">La mayor región disponible se muestra como en el resultado siguiente.</span><span class="sxs-lookup"><span data-stu-id="b820b-302">The largest free region is displayed as shown in the following output.</span></span>

  ```console
  Largest free region: Base 54000000 - Size 0003A980
  ```

  <span data-ttu-id="b820b-303">En este ejemplo, el tamaño de la mayor región disponible es de aproximadamente 24000 KB (3A980 en hexadecimal).</span><span class="sxs-lookup"><span data-stu-id="b820b-303">In this example, the size of the largest free region is approximately 24000 KB (3A980 in hexadecimal).</span></span> <span data-ttu-id="b820b-304">Esta región es mucho menor que cuando el recolector de elementos no utilizados necesita un segmento.</span><span class="sxs-lookup"><span data-stu-id="b820b-304">This region is much smaller than what the garbage collector needs for a segment.</span></span>

  <span data-ttu-id="b820b-305">o bien</span><span class="sxs-lookup"><span data-stu-id="b820b-305">-or-</span></span>

- <span data-ttu-id="b820b-306">Use el comando **vmstat**:</span><span class="sxs-lookup"><span data-stu-id="b820b-306">Use the **vmstat** command:</span></span>

  <span data-ttu-id="b820b-307">**!vmstat**</span><span class="sxs-lookup"><span data-stu-id="b820b-307">**!vmstat**</span></span>

  <span data-ttu-id="b820b-308">La mayor región disponible es el valor mayor de la columna MAXIMUM, como se muestra en el resultado siguiente.</span><span class="sxs-lookup"><span data-stu-id="b820b-308">The largest free region is the largest value in the MAXIMUM column, as shown in the following output.</span></span>

  ```console
  TYPE        MINIMUM   MAXIMUM     AVERAGE   BLK COUNT   TOTAL
  ~~~~        ~~~~~~~   ~~~~~~~     ~~~~~~~   ~~~~~~~~~~  ~~~~
  Free:
  Small       8K        64K         46K       36          1,671K
  Medium      80K       864K        349K      3           1,047K
  Large       1,384K    1,278,848K  151,834K  12          1,822,015K
  Summary     8K        1,278,848K  35,779K   51          1,824,735K
  ```

<a name="Physical"></a>

### <a name="to-determine-whether-there-is-enough-physical-memory"></a><span data-ttu-id="b820b-309">Para determinar si hay suficiente memoria física</span><span class="sxs-lookup"><span data-stu-id="b820b-309">To determine whether there is enough physical memory</span></span>

1. <span data-ttu-id="b820b-310">Inicie el Administrador de tareas de Windows.</span><span class="sxs-lookup"><span data-stu-id="b820b-310">Start Windows Task Manager.</span></span>

2. <span data-ttu-id="b820b-311">En la pestaña **Rendimiento**, busque el valor confirmado.</span><span class="sxs-lookup"><span data-stu-id="b820b-311">On the **Performance** tab, look at the committed value.</span></span> <span data-ttu-id="b820b-312">(En Windows 7, busque **Asignación (KB)** en el grupo **Sistema**).</span><span class="sxs-lookup"><span data-stu-id="b820b-312">(In Windows 7, look at **Commit (KB)** in the **System group**.)</span></span>

    <span data-ttu-id="b820b-313">Si el **Total** se aproxima al **Límite** hay poca memoria física.</span><span class="sxs-lookup"><span data-stu-id="b820b-313">If the **Total** is close to the **Limit**, you are running low on physical memory.</span></span>

<a name="ManagedHeapCommit"></a>

### <a name="to-determine-how-much-memory-the-managed-heap-is-committing"></a><span data-ttu-id="b820b-314">Para determinar cuánta memoria está confirmando el montón administrado</span><span class="sxs-lookup"><span data-stu-id="b820b-314">To determine how much memory the managed heap is committing</span></span>

- <span data-ttu-id="b820b-315">Use el contador de rendimiento de memoria `# Total committed bytes` para obtener el número de bytes que el montón administrado está confirmando.</span><span class="sxs-lookup"><span data-stu-id="b820b-315">Use the `# Total committed bytes` memory performance counter to get the number of bytes that the managed heap is committing.</span></span> <span data-ttu-id="b820b-316">El recolector de elementos no utilizados confirma fragmentos de un segmento a medida que son necesarios, no todos al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="b820b-316">The garbage collector commits chunks on a segment as needed, not all at the same time.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b820b-317">No use el contador de rendimiento `# Bytes in all Heaps`, ya que no representa el uso de memoria real por parte del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b820b-317">Do not use the `# Bytes in all Heaps` performance counter, because it does not represent actual memory usage by the managed heap.</span></span> <span data-ttu-id="b820b-318">En este valor se incluye el tamaño de una generación y es realmente su tamaño umbral; es decir, el tamaño que induce una recolección de elementos no utilizados si la generación se llena de objetos.</span><span class="sxs-lookup"><span data-stu-id="b820b-318">The size of a generation is included in this value and is actually its threshold size, that is, the size that induces a garbage collection if the generation is filled with objects.</span></span> <span data-ttu-id="b820b-319">Por tanto, este valor suele ser cero.</span><span class="sxs-lookup"><span data-stu-id="b820b-319">Therefore, this value is usually zero.</span></span>

<a name="ManagedHeapReserve"></a>

### <a name="to-determine-how-much-memory-the-managed-heap-reserves"></a><span data-ttu-id="b820b-320">Para determinar cuánta memoria reserva el montón administrado</span><span class="sxs-lookup"><span data-stu-id="b820b-320">To determine how much memory the managed heap reserves</span></span>

- <span data-ttu-id="b820b-321">Use el contador de rendimiento de memoria `# Total reserved bytes`.</span><span class="sxs-lookup"><span data-stu-id="b820b-321">Use the `# Total reserved bytes` memory performance counter.</span></span>

  <span data-ttu-id="b820b-322">El recolector de elementos no utilizados reserva memoria en segmentos y puede determinar dónde comienza un segmento mediante el comando **eeheap**.</span><span class="sxs-lookup"><span data-stu-id="b820b-322">The garbage collector reserves memory in segments, and you can determine where a segment starts by using the **eeheap** command.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="b820b-323">Aunque puede determinar la cantidad de memoria que el recolector de elementos no utilizados asigna a cada segmento, el tamaño del segmento es específico de la implementación y está sujeto a cambios en cualquier momento, incluso en las actualizaciones periódicas.</span><span class="sxs-lookup"><span data-stu-id="b820b-323">Although you can determine the amount of memory the garbage collector allocates for each segment, segment size is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="b820b-324">La aplicación nunca debe realizar suposiciones sobre el tamaño de un sector determinado ni depender de él, y tampoco debe intentar configurar la cantidad de memoria disponible para las asignaciones de segmentos.</span><span class="sxs-lookup"><span data-stu-id="b820b-324">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

- <span data-ttu-id="b820b-325">En WinDbg o en el depurador de Visual Studio con la extensión del depurador de SOS cargada, escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="b820b-325">In the WinDbg or Visual Studio debugger with the SOS debugger extension loaded, type the following command:</span></span>

  <span data-ttu-id="b820b-326">**!eeheap -gc**</span><span class="sxs-lookup"><span data-stu-id="b820b-326">**!eeheap -gc**</span></span>

  <span data-ttu-id="b820b-327">El resultado es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="b820b-327">The result is as follows.</span></span>

  ```console
  Number of GC Heaps: 2
  ------------------------------
  Heap 0 (002db550)
  generation 0 starts at 0x02abe29c
  generation 1 starts at 0x02abdd08
  generation 2 starts at 0x02ab0038
  ephemeral segment allocation context: none
    segment    begin allocated     size
  02ab0000 02ab0038  02aceff4 0x0001efbc(126908)
  Large object heap starts at 0x0aab0038
    segment    begin allocated     size
  0aab0000 0aab0038  0aab2278 0x00002240(8768)
  Heap Size   0x211fc(135676)
  ------------------------------
  Heap 1 (002dc958)
  generation 0 starts at 0x06ab1bd8
  generation 1 starts at 0x06ab1bcc
  generation 2 starts at 0x06ab0038
  ephemeral segment allocation context: none
    segment    begin allocated     size
  06ab0000 06ab0038  06ab3be4 0x00003bac(15276)
  Large object heap starts at 0x0cab0038
    segment    begin allocated     size
  0cab0000 0cab0038  0cab0048 0x00000010(16)
  Heap Size    0x3bbc(15292)
  ------------------------------
  GC Heap Size   0x24db8(150968)
  ```

  <span data-ttu-id="b820b-328">Las direcciones indicadas por "segment" son las direcciones iniciales de los segmentos.</span><span class="sxs-lookup"><span data-stu-id="b820b-328">The addresses indicated by "segment" are the starting addresses of the segments.</span></span>

<a name="ExamineGen2"></a>

### <a name="to-determine-large-objects-in-generation-2"></a><span data-ttu-id="b820b-329">Para determinar los objetos grandes de la generación 2</span><span class="sxs-lookup"><span data-stu-id="b820b-329">To determine large objects in generation 2</span></span>

- <span data-ttu-id="b820b-330">En WinDbg o en el depurador de Visual Studio con la extensión del depurador de SOS cargada, escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="b820b-330">In the WinDbg or Visual Studio debugger with the SOS debugger extension loaded, type the following command:</span></span>

  <span data-ttu-id="b820b-331">**!dumpheap –stat**</span><span class="sxs-lookup"><span data-stu-id="b820b-331">**!dumpheap –stat**</span></span>

  <span data-ttu-id="b820b-332">Si el montón administrado es grande, **dumpheap** puede tardar bastante en finalizar.</span><span class="sxs-lookup"><span data-stu-id="b820b-332">If the managed heap is big, **dumpheap** may take a while to finish.</span></span>

  <span data-ttu-id="b820b-333">Puede empezar el análisis por las últimas líneas del resultado, ya que muestran los objetos que usan la mayor parte del espacio.</span><span class="sxs-lookup"><span data-stu-id="b820b-333">You can start analyzing from the last few lines of the output, because they list the objects that use the most space.</span></span> <span data-ttu-id="b820b-334">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b820b-334">For example:</span></span>

  ```console
  2c6108d4   173712     14591808 DevExpress.XtraGrid.Views.Grid.ViewInfo.GridCellInfo
  00155f80      533     15216804      Free
  7a747c78   791070     15821400 System.Collections.Specialized.ListDictionary+DictionaryNode
  7a747bac   700930     19626040 System.Collections.Specialized.ListDictionary
  2c64e36c    78644     20762016 DevExpress.XtraEditors.ViewInfo.TextEditViewInfo
  79124228   121143     29064120 System.Object[]
  035f0ee4    81626     35588936 Toolkit.TlkOrder
  00fcae40     6193     44911636 WaveBasedStrategy.Tick_Snap[]
  791242ec    40182     90664128 System.Collections.Hashtable+bucket[]
  790fa3e0  3154024    137881448 System.String
  Total 8454945 objects
  ```

  <span data-ttu-id="b820b-335">El último objeto mostrado es una cadena y es el que ocupa más espacio.</span><span class="sxs-lookup"><span data-stu-id="b820b-335">The last object listed is a string and occupies the most space.</span></span> <span data-ttu-id="b820b-336">Puede examinar la aplicación para ver cómo se pueden optimizar los objetos de cadena.</span><span class="sxs-lookup"><span data-stu-id="b820b-336">You can examine your application to see how your string objects can be optimized.</span></span> <span data-ttu-id="b820b-337">Para ver las cadenas comprendidas entre 150 y 200 bytes, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b820b-337">To see strings that are between 150 and 200 bytes, type the following:</span></span>

  <span data-ttu-id="b820b-338">**!dumpheap -type System.String -min 150 -max 200**</span><span class="sxs-lookup"><span data-stu-id="b820b-338">**!dumpheap -type System.String -min 150 -max 200**</span></span>

  <span data-ttu-id="b820b-339">A continuación se muestra un ejemplo de los resultados.</span><span class="sxs-lookup"><span data-stu-id="b820b-339">An example of the results is as follows.</span></span>

  ```console
  Address  MT           Size  Gen
  1875d2c0 790fa3e0      152    2 System.String HighlightNullStyle_Blotter_PendingOrder-11_Blotter_PendingOrder-11
  …
  ```

  <span data-ttu-id="b820b-340">Puede ser más eficaz usar un entero en lugar de una cadena para un identificador.</span><span class="sxs-lookup"><span data-stu-id="b820b-340">Using an integer instead of a string for an ID can be more efficient.</span></span> <span data-ttu-id="b820b-341">Si la misma cadena se está repitiendo miles de veces, considere la posibilidad de asignación al grupo interno de cadenas.</span><span class="sxs-lookup"><span data-stu-id="b820b-341">If the same string is being repeated thousands of times, consider string interning.</span></span> <span data-ttu-id="b820b-342">Para obtener más información sobre la asignación al grupo interno de cadenas, vea el tema de referencia sobre el método <xref:System.String.Intern%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b820b-342">For more information about string interning, see the reference topic for the <xref:System.String.Intern%2A?displayProperty=nameWithType> method.</span></span>

<a name="ObjRef"></a>

### <a name="to-determine-references-to-objects"></a><span data-ttu-id="b820b-343">Para determinar las referencias a objetos</span><span class="sxs-lookup"><span data-stu-id="b820b-343">To determine references to objects</span></span>

- <span data-ttu-id="b820b-344">En WinDbg con la extensión del depurador de SOS cargada, escriba el comando siguiente para mostrar las referencias a objetos:</span><span class="sxs-lookup"><span data-stu-id="b820b-344">In WinDbg with the SOS debugger extension loaded, type the following command to list references to objects:</span></span>

  <span data-ttu-id="b820b-345">**!gcroot**</span><span class="sxs-lookup"><span data-stu-id="b820b-345">**!gcroot**</span></span>

  `-or-`

- <span data-ttu-id="b820b-346">Para determinar las referencias para un objeto concreto, incluya la dirección:</span><span class="sxs-lookup"><span data-stu-id="b820b-346">To determine the references for a specific object, include the address:</span></span>

  <span data-ttu-id="b820b-347">**!gcroot 1c37b2ac**</span><span class="sxs-lookup"><span data-stu-id="b820b-347">**!gcroot 1c37b2ac**</span></span>

  <span data-ttu-id="b820b-348">Las raíces encontradas en pilas pueden ser falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="b820b-348">Roots found on stacks may be false positives.</span></span> <span data-ttu-id="b820b-349">Para obtener más información, use el comando `!help gcroot`.</span><span class="sxs-lookup"><span data-stu-id="b820b-349">For more information, use the command `!help gcroot`.</span></span>

  ```console
  ebx:Root:19011c5c(System.Windows.Forms.Application+ThreadContext)->
  19010b78(DemoApp.FormDemoApp)->
  19011158(System.Windows.Forms.PropertyStore)->
  … [omitted]
  1c3745ec(System.Data.DataTable)->
  1c3747a8(System.Data.DataColumnCollection)->
  1c3747f8(System.Collections.Hashtable)->
  1c376590(System.Collections.Hashtable+bucket[])->
  1c376c98(System.Data.DataColumn)->
  1c37b270(System.Data.Common.DoubleStorage)->
  1c37b2ac(System.Double[])
  Scan Thread 0 OSTHread 99c
  Scan Thread 6 OSTHread 484
  ```

  <span data-ttu-id="b820b-350">El comando **gcroot** puede tardar mucho en finalizar.</span><span class="sxs-lookup"><span data-stu-id="b820b-350">The **gcroot** command can take a long time to finish.</span></span> <span data-ttu-id="b820b-351">Todo objeto no reclamado en la recolección de elementos no utilizados es un objeto activo.</span><span class="sxs-lookup"><span data-stu-id="b820b-351">Any object that is not reclaimed by garbage collection is a live object.</span></span> <span data-ttu-id="b820b-352">Esto implica que alguna raíz se almacena directa o indirectamente en el objeto, por lo que **gcroot** debe devolver información de ruta de acceso al objeto.</span><span class="sxs-lookup"><span data-stu-id="b820b-352">This means that some root is directly or indirectly holding onto the object, so **gcroot** should return path information to the object.</span></span> <span data-ttu-id="b820b-353">Debe examinar los gráficos devueltos y ver por qué todavía se hace referencia a estos objetos.</span><span class="sxs-lookup"><span data-stu-id="b820b-353">You should examine the graphs returned and see why these objects are still referenced.</span></span>

<a name="Induce"></a>

### <a name="to-determine-whether-a-finalizer-has-been-run"></a><span data-ttu-id="b820b-354">Para determinar si se ha ejecutado un finalizador</span><span class="sxs-lookup"><span data-stu-id="b820b-354">To determine whether a finalizer has been run</span></span>

- <span data-ttu-id="b820b-355">Ejecute un programa de prueba que contenga el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b820b-355">Run a test program that contains the following code:</span></span>

  ```csharp
  GC.Collect();
  GC.WaitForPendingFinalizers();
  GC.Collect();
  ```

  <span data-ttu-id="b820b-356">Si la prueba resuelve el problema, significa que el recolector de elementos no utilizados no estaba recuperando objetos porque los finalizadores de esos objetos se habían suspendido.</span><span class="sxs-lookup"><span data-stu-id="b820b-356">If the test resolves the problem, this means that the garbage collector was not reclaiming objects, because the finalizers for those objects had been suspended.</span></span> <span data-ttu-id="b820b-357">El método <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> permite que los finalizadores completen sus tareas y corrige el problema.</span><span class="sxs-lookup"><span data-stu-id="b820b-357">The <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> method enables the finalizers to complete their tasks, and fixes the problem.</span></span>

<a name="Finalize"></a>

### <a name="to-determine-whether-there-are-objects-waiting-to-be-finalized"></a><span data-ttu-id="b820b-358">Para determinar si hay objetos en espera de finalización</span><span class="sxs-lookup"><span data-stu-id="b820b-358">To determine whether there are objects waiting to be finalized</span></span>

1. <span data-ttu-id="b820b-359">En WinDbg o en el depurador de Visual Studio con la extensión del depurador de SOS cargada, escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="b820b-359">In the WinDbg or Visual Studio debugger with the SOS debugger extension loaded, type the following command:</span></span>

    <span data-ttu-id="b820b-360">**!finalizequeue**</span><span class="sxs-lookup"><span data-stu-id="b820b-360">**!finalizequeue**</span></span>

    <span data-ttu-id="b820b-361">Observe el número de objetos que están listos para la finalización.</span><span class="sxs-lookup"><span data-stu-id="b820b-361">Look at the number of objects that are ready for finalization.</span></span> <span data-ttu-id="b820b-362">Si el número es elevado, debe examinar por qué estos finalizadores no pueden progresar en absoluto o con la rapidez suficiente.</span><span class="sxs-lookup"><span data-stu-id="b820b-362">If the number is high, you must examine why these finalizers cannot progress at all or cannot progress fast enough.</span></span>

2. <span data-ttu-id="b820b-363">Para obtener un resultado de subprocesos, escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="b820b-363">To get an output of threads, type the following command:</span></span>

    <span data-ttu-id="b820b-364">**threads -special**</span><span class="sxs-lookup"><span data-stu-id="b820b-364">**threads -special**</span></span>

    <span data-ttu-id="b820b-365">Este comando proporciona resultados como el siguiente.</span><span class="sxs-lookup"><span data-stu-id="b820b-365">This command provides output such as the following.</span></span>

    ```console
       OSID     Special thread type
    2    cd0    DbgHelper
    3    c18    Finalizer
    4    df0    GC SuspendEE
    ```

    <span data-ttu-id="b820b-366">El subproceso finalizador indica qué finalizador, si hay alguno, se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="b820b-366">The finalizer thread indicates which finalizer, if any, is currently being run.</span></span> <span data-ttu-id="b820b-367">Cuando un subproceso finalizador no está ejecutando ningún finalizador, está esperando un evento para indicarle que haga su trabajo.</span><span class="sxs-lookup"><span data-stu-id="b820b-367">When a finalizer thread is not running any finalizers, it is waiting for an event to tell it to do its work.</span></span> <span data-ttu-id="b820b-368">La mayoría de las veces verá el subproceso finalizador en este estado porque se ejecuta en THREAD_HIGHEST_PRIORITY y se presupone que termina de ejecutar los finalizadores, si hay alguno, muy rápidamente.</span><span class="sxs-lookup"><span data-stu-id="b820b-368">Most of the time you will see the finalizer thread in this state because it runs at THREAD_HIGHEST_PRIORITY and is supposed to finish running finalizers, if any, very quickly.</span></span>

<a name="Fragmented"></a>

### <a name="to-determine-the-amount-of-free-space-in-the-managed-heap"></a><span data-ttu-id="b820b-369">Para determinar la cantidad de espacio disponible en el montón administrado</span><span class="sxs-lookup"><span data-stu-id="b820b-369">To determine the amount of free space in the managed heap</span></span>

- <span data-ttu-id="b820b-370">En WinDbg o en el depurador de Visual Studio con la extensión del depurador de SOS cargada, escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="b820b-370">In the WinDbg or Visual Studio debugger with the SOS debugger extension loaded, type the following command:</span></span>

  <span data-ttu-id="b820b-371">**!dumpheap -type Free -stat**</span><span class="sxs-lookup"><span data-stu-id="b820b-371">**!dumpheap -type Free -stat**</span></span>

  <span data-ttu-id="b820b-372">Este comando muestra el tamaño total de todos los objetos disponibles en el montón administrado, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b820b-372">This command displays the total size of all the free objects on the managed heap, as shown in the following example.</span></span>

  ```console
  total 230 objects
  Statistics:
        MT    Count    TotalSize Class Name
  00152b18      230     40958584      Free
  Total 230 objects
  ```

- <span data-ttu-id="b820b-373">Para determinar el espacio disponible en la generación 0, escriba el comando siguiente para obtener información sobre el consumo de memoria por generación:</span><span class="sxs-lookup"><span data-stu-id="b820b-373">To determine the free space in generation 0, type the following command for memory consumption information by generation:</span></span>

  <span data-ttu-id="b820b-374">**!eeheap -gc**</span><span class="sxs-lookup"><span data-stu-id="b820b-374">**!eeheap -gc**</span></span>

  <span data-ttu-id="b820b-375">Este comando muestra un resultado similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="b820b-375">This command displays output similar to the following.</span></span> <span data-ttu-id="b820b-376">La última línea muestra el segmento efímero.</span><span class="sxs-lookup"><span data-stu-id="b820b-376">The last line shows the ephemeral segment.</span></span>

  ```console
  Heap 0 (0015ad08)
  generation 0 starts at 0x49521f8c
  generation 1 starts at 0x494d7f64
  generation 2 starts at 0x007f0038
  ephemeral segment allocation context: none
  segment  begin     allocated  size
  00178250 7a80d84c  7a82f1cc   0x00021980(137600)
  00161918 78c50e40  78c7056c   0x0001f72c(128812)
  007f0000 007f0038  047eed28   0x03ffecf0(67103984)
  3a120000 3a120038  3a3e84f8   0x002c84c0(2917568)
  46120000 46120038  49e05d04   0x03ce5ccc(63855820)
  ```

- <span data-ttu-id="b820b-377">Calcule el espacio usado por la generación 0:</span><span class="sxs-lookup"><span data-stu-id="b820b-377">Calculate the space used by generation 0:</span></span>

  <span data-ttu-id="b820b-378">**? 49e05d04-0x49521f8c**</span><span class="sxs-lookup"><span data-stu-id="b820b-378">**? 49e05d04-0x49521f8c**</span></span>

  <span data-ttu-id="b820b-379">El resultado es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="b820b-379">The result is as follows.</span></span> <span data-ttu-id="b820b-380">La generación 0 ocupa aproximadamente 9 MB.</span><span class="sxs-lookup"><span data-stu-id="b820b-380">Generation 0 is approximately 9 MB.</span></span>

  ```console
  Evaluate expression: 9321848 = 008e3d78
  ```

- <span data-ttu-id="b820b-381">El comando siguiente vuelca el espacio disponible dentro del intervalo de la generación 0:</span><span class="sxs-lookup"><span data-stu-id="b820b-381">The following command dumps the free space within the generation 0 range:</span></span>

  <span data-ttu-id="b820b-382">**!dumpheap -type Free -stat 0x49521f8c 49e05d04**</span><span class="sxs-lookup"><span data-stu-id="b820b-382">**!dumpheap -type Free -stat 0x49521f8c 49e05d04**</span></span>

  <span data-ttu-id="b820b-383">El resultado es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="b820b-383">The result is as follows.</span></span>

  ```console
  ------------------------------
  Heap 0
  total 409 objects
  ------------------------------
  Heap 1
  total 0 objects
  ------------------------------
  Heap 2
  total 0 objects
  ------------------------------
  Heap 3
  total 0 objects
  ------------------------------
  total 409 objects
  Statistics:
        MT    Count TotalSize Class Name
  0015a498      409   7296540      Free
  Total 409 objects
  ```

  <span data-ttu-id="b820b-384">Este resultado muestra que la parte de la generación 0 del montón está usando 9 MB de espacio para los objetos y tiene 7 MB disponibles.</span><span class="sxs-lookup"><span data-stu-id="b820b-384">This output shows that the generation 0 portion of the heap is using 9 MB of space for objects and has 7 MB free.</span></span> <span data-ttu-id="b820b-385">Este análisis muestra hasta qué punto la generación 0 contribuye a la fragmentación.</span><span class="sxs-lookup"><span data-stu-id="b820b-385">This analysis shows the extent to which generation 0 contributes to fragmentation.</span></span> <span data-ttu-id="b820b-386">Esta cantidad de uso del montón se debe descontar de la cantidad total como la causa de fragmentación por parte de los objetos de larga duración.</span><span class="sxs-lookup"><span data-stu-id="b820b-386">This amount of heap usage should be discounted from the total amount as the cause of fragmentation by long-term objects.</span></span>

<a name="Pinned"></a>

### <a name="to-determine-the-number-of-pinned-objects"></a><span data-ttu-id="b820b-387">Para determinar el número de objetos anclados</span><span class="sxs-lookup"><span data-stu-id="b820b-387">To determine the number of pinned objects</span></span>

- <span data-ttu-id="b820b-388">En WinDbg o en el depurador de Visual Studio con la extensión del depurador de SOS cargada, escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="b820b-388">In the WinDbg or Visual Studio debugger with the SOS debugger extension loaded, type the following command:</span></span>

  <span data-ttu-id="b820b-389">**!gchandles**</span><span class="sxs-lookup"><span data-stu-id="b820b-389">**!gchandles**</span></span>

  <span data-ttu-id="b820b-390">Las estadísticas mostradas incluyen el número de identificadores anclados, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b820b-390">The statistics displayed includes the number of pinned handles, as the following example shows.</span></span>

  ```console
  GC Handle Statistics:
  Strong Handles:      29
  Pinned Handles:      10
  ```

<a name="TimeInGC"></a>

### <a name="to-determine-the-length-of-time-in-a-garbage-collection"></a><span data-ttu-id="b820b-391">Para determinar la duración de una recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="b820b-391">To determine the length of time in a garbage collection</span></span>

- <span data-ttu-id="b820b-392">Examine el contador de rendimiento de memoria `% Time in GC`.</span><span class="sxs-lookup"><span data-stu-id="b820b-392">Examine the `% Time in GC` memory performance counter.</span></span>

  <span data-ttu-id="b820b-393">El valor se calcula usando un tiempo de intervalo de muestra.</span><span class="sxs-lookup"><span data-stu-id="b820b-393">The value is calculated by using a sample interval time.</span></span> <span data-ttu-id="b820b-394">Como los contadores se actualizan al final de cada recolección de elementos no utilizados, el ejemplo actual tendrá el mismo valor que el ejemplo anterior si no se realizó ninguna recolección durante el intervalo.</span><span class="sxs-lookup"><span data-stu-id="b820b-394">Because the counters are updated at the end of each garbage collection, the current sample will have the same value as the previous sample if no collections occurred during the interval.</span></span>

  <span data-ttu-id="b820b-395">Tiempo de recolección se obtiene multiplicando el tiempo de intervalo de muestra por el valor de porcentaje.</span><span class="sxs-lookup"><span data-stu-id="b820b-395">Collection time is obtained by multiplying the sample interval time with the percentage value.</span></span>

  <span data-ttu-id="b820b-396">Los datos siguientes muestran cuatro intervalos de muestreo de dos segundos para un estudio de 8 segundos.</span><span class="sxs-lookup"><span data-stu-id="b820b-396">The following data shows four sampling intervals of two seconds, for an 8-second study.</span></span> <span data-ttu-id="b820b-397">Las columnas `Gen0`, `Gen1` y `Gen2` muestran el número de recolecciones de elementos no utilizados que se produjeron durante ese intervalo para esa generación.</span><span class="sxs-lookup"><span data-stu-id="b820b-397">The `Gen0`, `Gen1`, and `Gen2` columns show the number of garbage collections that occurred during that interval for that generation.</span></span>

  ```console
  Interval    Gen0    Gen1    Gen2    % Time in GC
          1       9       3       1              10
          2      10       3       1               1
          3      11       3       1               3
          4      11       3       1               3
  ```

  <span data-ttu-id="b820b-398">Esta información no indica cuándo se produjo la recolección de elementos no utilizados, pero puede determinar el número de recolecciones de elementos no utilizados que se produjeron en un intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="b820b-398">This information does not show when the garbage collection occurred, but you can determine the number of garbage collections that occurred in an interval of time.</span></span> <span data-ttu-id="b820b-399">Suponiendo el caso peor, la décima recolección de elementos no utilizados de generación 0 terminó al principio del segundo intervalo y la undécima recolección de elementos no utilizados de generación 0 terminó al final del quinto intervalo.</span><span class="sxs-lookup"><span data-stu-id="b820b-399">Assuming the worst case, the tenth generation 0 garbage collection finished at the start of the second interval, and the eleventh generation 0 garbage collection finished at the end of the fifth interval.</span></span> <span data-ttu-id="b820b-400">El tiempo transcurrido entre el final de la décima recolección de elementos no utilizados y el final de la undécima recolección de elementos no utilizados es de aproximadamente 2 segundos y el contador de rendimiento muestra un 3%, por lo que la duración de la undécima recolección de elementos no utilizados de generación 0 fue de (2 segundos \* 3% = 60 ms).</span><span class="sxs-lookup"><span data-stu-id="b820b-400">The time between the end of the tenth and the end of the eleventh garbage collection is about 2 seconds, and the performance counter shows 3%, so the duration of the eleventh generation 0 garbage collection was (2 seconds \* 3% = 60ms).</span></span>

  <span data-ttu-id="b820b-401">En este ejemplo, hay 5 periodos.</span><span class="sxs-lookup"><span data-stu-id="b820b-401">In this example, there are 5 periods.</span></span>

  ```console
  Interval    Gen0    Gen1    Gen2     % Time in GC
          1       9       3       1                3
          2      10       3       1                1
          3      11       4       2                1
          4      11       4       2                1
          5      11       4       2               20
  ```

  <span data-ttu-id="b820b-402">La segunda recolección de elementos no utilizados de generación 2 se inició durante el tercer intervalo y terminó en el quinto intervalo.</span><span class="sxs-lookup"><span data-stu-id="b820b-402">The second generation 2 garbage collection started during the third interval and finished at the fifth interval.</span></span> <span data-ttu-id="b820b-403">Suponiendo el caso peor, la última recolección de elementos no utilizados fue de una generación 0 que terminó al principio del segundo intervalo y la recolección de elementos no utilizados de generación 2 terminó al final del quinto intervalo.</span><span class="sxs-lookup"><span data-stu-id="b820b-403">Assuming the worst case, the last garbage collection was for a generation 0 collection that finished at the start of the second interval, and the generation 2 garbage collection finished at the end of the fifth interval.</span></span> <span data-ttu-id="b820b-404">Por tanto, el tiempo transcurrido entre el final de la recolección de elementos no utilizados de generación 0 y el final de la recolección de elementos no utilizados de generación 2 es de 4 segundos.</span><span class="sxs-lookup"><span data-stu-id="b820b-404">Therefore, the time between the end of the generation 0 garbage collection and the end of the generation 2 garbage collection is 4 seconds.</span></span> <span data-ttu-id="b820b-405">Puesto que el contador `% Time in GC` muestra un 20%, el tiempo máximo que la recolección de elementos no utilizados de generación 2 podría haber tardado es (4 segundos \* 20% = 800 ms).</span><span class="sxs-lookup"><span data-stu-id="b820b-405">Because the `% Time in GC` counter is 20%, the maximum amount of time the generation 2 garbage collection could have taken is (4 seconds \* 20% = 800ms).</span></span>

- <span data-ttu-id="b820b-406">También puede determinar la duración de una recolección de elementos no utilizados mediante [eventos ETW de recolección de elementos no utilizados](../../../docs/framework/performance/garbage-collection-etw-events.md) y analizar la información para averiguar la duración de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-406">Alternatively, you can determine the length of a garbage collection by using [garbage collection ETW events](../../../docs/framework/performance/garbage-collection-etw-events.md), and analyze the information to determine the duration of garbage collection.</span></span>

  <span data-ttu-id="b820b-407">Por ejemplo, los datos siguiente muestran una secuencia de eventos que se produjo durante una recolección de elementos no utilizados no simultánea.</span><span class="sxs-lookup"><span data-stu-id="b820b-407">For example, the following data shows an event sequence that occurred during a non-concurrent garbage collection.</span></span>

  ```console
  Timestamp    Event name
  513052        GCSuspendEEBegin_V1
  513078        GCSuspendEEEnd
  513090        GCStart_V1
  517890        GCEnd_V1
  517894        GCHeapStats
  517897        GCRestartEEBegin
  517918        GCRestartEEEnd
  ```

  <span data-ttu-id="b820b-408">La suspensión del subproceso administrado tardó 26 us (`GCSuspendEEEnd` – `GCSuspendEEBegin_V1`).</span><span class="sxs-lookup"><span data-stu-id="b820b-408">Suspending the managed thread took 26us (`GCSuspendEEEnd` – `GCSuspendEEBegin_V1`).</span></span>

  <span data-ttu-id="b820b-409">La recolección de elementos no utilizados real tardó 4,8 ms (`GCEnd_V1` – `GCStart_V1`).</span><span class="sxs-lookup"><span data-stu-id="b820b-409">The actual garbage collection took 4.8ms (`GCEnd_V1` – `GCStart_V1`).</span></span>

  <span data-ttu-id="b820b-410">La reanudación de los subprocesos administrados tardó 21 us (`GCRestartEEEnd` – `GCRestartEEBegin`).</span><span class="sxs-lookup"><span data-stu-id="b820b-410">Resuming the managed threads took 21us (`GCRestartEEEnd` – `GCRestartEEBegin`).</span></span>

  <span data-ttu-id="b820b-411">El resultado siguiente proporciona un ejemplo de recolección de elementos no utilizados en segundo plano, e incluye los campos de proceso, subproceso y evento.</span><span class="sxs-lookup"><span data-stu-id="b820b-411">The following output provides an example for background garbage collection, and includes the process, thread, and event fields.</span></span> <span data-ttu-id="b820b-412">(No se muestra todos los datos.)</span><span class="sxs-lookup"><span data-stu-id="b820b-412">(Not all data is shown.)</span></span>

  ```console
  timestamp(us)    event name            process    thread    event field
  42504385        GCSuspendEEBegin_V1    Test.exe    4372             1
  42504648        GCSuspendEEEnd         Test.exe    4372
  42504816        GCStart_V1             Test.exe    4372        102019
  42504907        GCStart_V1             Test.exe    4372        102020
  42514170        GCEnd_V1               Test.exe    4372
  42514204        GCHeapStats            Test.exe    4372        102020
  42832052        GCRestartEEBegin       Test.exe    4372
  42832136        GCRestartEEEnd         Test.exe    4372
  63685394        GCSuspendEEBegin_V1    Test.exe    4744             6
  63686347        GCSuspendEEEnd         Test.exe    4744
  63784294        GCRestartEEBegin       Test.exe    4744
  63784407        GCRestartEEEnd         Test.exe    4744
  89931423        GCEnd_V1               Test.exe    4372        102019
  89931464        GCHeapStats            Test.exe    4372
  ```

  <span data-ttu-id="b820b-413">El evento `GCStart_V1` en 42504816 indica que se trata de una recolección de elementos no utilizados en segundo plano, ya que el último campo es `1`.</span><span class="sxs-lookup"><span data-stu-id="b820b-413">The `GCStart_V1` event at 42504816 indicates that this is a background garbage collection, because the last field is `1`.</span></span> <span data-ttu-id="b820b-414">Esta se convierte en la recolección de elementos no utilizados número</span><span class="sxs-lookup"><span data-stu-id="b820b-414">This becomes garbage collection No.</span></span> <span data-ttu-id="b820b-415">102019.</span><span class="sxs-lookup"><span data-stu-id="b820b-415">102019.</span></span>

  <span data-ttu-id="b820b-416">El evento `GCStart` se produce porque se necesita una recolección de elementos no utilizados efímera antes de iniciar una recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="b820b-416">The `GCStart` event occurs because there is a need for an ephemeral garbage collection before you start a background garbage collection.</span></span> <span data-ttu-id="b820b-417">Esta se convierte en la recolección de elementos no utilizados número</span><span class="sxs-lookup"><span data-stu-id="b820b-417">This becomes garbage collection No.</span></span> <span data-ttu-id="b820b-418">102020.</span><span class="sxs-lookup"><span data-stu-id="b820b-418">102020.</span></span>

  <span data-ttu-id="b820b-419">En 42514170, la recolección de elementos no utilizados número</span><span class="sxs-lookup"><span data-stu-id="b820b-419">At 42514170, garbage collection No.</span></span> <span data-ttu-id="b820b-420">102020 finaliza.</span><span class="sxs-lookup"><span data-stu-id="b820b-420">102020 finishes.</span></span> <span data-ttu-id="b820b-421">Los subprocesos administrados se reinician en este momento.</span><span class="sxs-lookup"><span data-stu-id="b820b-421">The managed threads are restarted at this point.</span></span> <span data-ttu-id="b820b-422">Esto se completa en el subproceso 4372, que desencadenó esta recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="b820b-422">This is completed on thread 4372, which triggered this background garbage collection.</span></span>

  <span data-ttu-id="b820b-423">En el subproceso 4744, se produce una suspensión.</span><span class="sxs-lookup"><span data-stu-id="b820b-423">On thread 4744, a suspension occurs.</span></span> <span data-ttu-id="b820b-424">Esta es la última vez que la recolección de elementos no utilizados en segundo plano tiene que suspender subprocesos administrados.</span><span class="sxs-lookup"><span data-stu-id="b820b-424">This is the only time at which the background garbage collection has to suspend managed threads.</span></span> <span data-ttu-id="b820b-425">Esta duración es de aproximadamente 99 ms ((63784407-63685394)/1000).</span><span class="sxs-lookup"><span data-stu-id="b820b-425">This duration is approximately 99ms ((63784407-63685394)/1000).</span></span>

  <span data-ttu-id="b820b-426">El evento `GCEnd` para la recolección de elementos no utilizados en segundo plano está en 89931423.</span><span class="sxs-lookup"><span data-stu-id="b820b-426">The `GCEnd` event for the background garbage collection is at 89931423.</span></span> <span data-ttu-id="b820b-427">Esto significa que la recolección de elementos no utilizados en segundo plano duró alrededor de 47 segundos ((89931423-42504816)/1000).</span><span class="sxs-lookup"><span data-stu-id="b820b-427">This means that the background garbage collection lasted for about 47seconds ((89931423-42504816)/1000).</span></span>

  <span data-ttu-id="b820b-428">Mientras los subprocesos administrados se están ejecutando, puede producirse cualquier número de recolecciones de elementos no utilizados efímeras.</span><span class="sxs-lookup"><span data-stu-id="b820b-428">While the managed threads are running, you can see any number of ephemeral garbage collections occurring.</span></span>

<a name="Triggered"></a>

### <a name="to-determine-what-triggered-a-garbage-collection"></a><span data-ttu-id="b820b-429">Para determinar qué desencadenó una recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="b820b-429">To determine what triggered a garbage collection</span></span>

- <span data-ttu-id="b820b-430">En WinDbg o en el depurador de Visual Studio con la extensión del depurador de SOS cargada, escriba el comando siguiente para mostrar todos los subprocesos con sus pilas de llamadas:</span><span class="sxs-lookup"><span data-stu-id="b820b-430">In the WinDbg or Visual Studio debugger with the SOS debugger extension loaded, type the following command to show all the threads with their call stacks:</span></span>

  <span data-ttu-id="b820b-431">**~\*KB**</span><span class="sxs-lookup"><span data-stu-id="b820b-431">**~\*kb**</span></span>

  <span data-ttu-id="b820b-432">Este comando muestra un resultado similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="b820b-432">This command displays output similar to the following.</span></span>

  ```console
  0012f3b0 79ff0bf8 mscorwks!WKS::GCHeap::GarbageCollect
  0012f454 30002894 mscorwks!GCInterface::CollectGeneration+0xa4
  0012f490 79fa22bd fragment_ni!request.Main(System.String[])+0x48
  ```

  <span data-ttu-id="b820b-433">Si la recolección de elementos no utilizados se produjo por una notificación de memoria insuficiente del sistema operativo, la pila de llamadas es similar, salvo que el subproceso es el subproceso finalizador.</span><span class="sxs-lookup"><span data-stu-id="b820b-433">If the garbage collection was caused by a low memory notification from the operating system, the call stack is similar, except that the thread is the finalizer thread.</span></span> <span data-ttu-id="b820b-434">El subproceso finalizador obtiene una notificación asincrónica de memoria insuficiente e induce la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b820b-434">The finalizer thread gets an asynchronous low memory notification and induces the garbage collection.</span></span>

  <span data-ttu-id="b820b-435">Si la recolección de elementos no utilizados se produjo por la asignación de memoria, la pila aparece de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="b820b-435">If the garbage collection was caused by memory allocation, the stack appears as follows:</span></span>

  ```console
  0012f230 7a07c551 mscorwks!WKS::GCHeap::GarbageCollectGeneration
  0012f2b8 7a07cba8 mscorwks!WKS::gc_heap::try_allocate_more_space+0x1a1
  0012f2d4 7a07cefb mscorwks!WKS::gc_heap::allocate_more_space+0x18
  0012f2f4 7a02a51b mscorwks!WKS::GCHeap::Alloc+0x4b
  0012f310 7a02ae4c mscorwks!Alloc+0x60
  0012f364 7a030e46 mscorwks!FastAllocatePrimitiveArray+0xbd
  0012f424 300027f4 mscorwks!JIT_NewArr1+0x148
  000af70f 3000299f fragment_ni!request..ctor(Int32, Single)+0x20c
  0000002a 79fa22bd fragment_ni!request.Main(System.String[])+0x153
  ```

  <span data-ttu-id="b820b-436">Un asistente Just-In-Time (`JIT_New*`) llama finalmente a `GCHeap::GarbageCollectGeneration`.</span><span class="sxs-lookup"><span data-stu-id="b820b-436">A just-in-time helper (`JIT_New*`) eventually calls `GCHeap::GarbageCollectGeneration`.</span></span> <span data-ttu-id="b820b-437">Si determina que las recolecciones de elementos no utilizados de generación 2 se deben a asignaciones, debe averiguar qué objetos recolecta una recolección de elementos no utilizados de generación 2 y cómo evitarlas.</span><span class="sxs-lookup"><span data-stu-id="b820b-437">If you determine that generation 2 garbage collections are caused by allocations, you must determine which objects are collected by a generation 2 garbage collection and how to avoid them.</span></span> <span data-ttu-id="b820b-438">Es decir, debe determinar la diferencia entre el inicio y el final de una recolección de elementos no utilizados de generación 2 y los objetos que causaron la recolección de generación 2.</span><span class="sxs-lookup"><span data-stu-id="b820b-438">That is, you want to determine the difference between the start and the end of a generation 2 garbage collection, and the objects that caused the generation 2 collection.</span></span>

  <span data-ttu-id="b820b-439">Por ejemplo, escriba el comando siguiente en el depurador para mostrar el comienzo de una recolección de generación 2:</span><span class="sxs-lookup"><span data-stu-id="b820b-439">For example, type the following command in the debugger to show the beginning of a generation 2 collection:</span></span>

  <span data-ttu-id="b820b-440">**!dumpheap –stat**</span><span class="sxs-lookup"><span data-stu-id="b820b-440">**!dumpheap –stat**</span></span>

  <span data-ttu-id="b820b-441">Resultado de ejemplo (abreviado para mostrar los objetos que usan más espacio):</span><span class="sxs-lookup"><span data-stu-id="b820b-441">Example output (abridged to show the objects that use the most space):</span></span>

  ```console
  79124228    31857      9862328 System.Object[]
  035f0384    25668     11601936 Toolkit.TlkPosition
  00155f80    21248     12256296      Free
  79103b6c   297003     13068132 System.Threading.ReaderWriterLock
  7a747ad4   708732     14174640 System.Collections.Specialized.HybridDictionary
  7a747c78   786498     15729960 System.Collections.Specialized.ListDictionary+DictionaryNode
  7a747bac   700298     19608344 System.Collections.Specialized.ListDictionary
  035f0ee4    89192     38887712 Toolkit.TlkOrder
  00fcae40     6193     44911636 WaveBasedStrategy.Tick_Snap[]
  7912c444    91616     71887080 System.Double[]
  791242ec    32451     82462728 System.Collections.Hashtable+bucket[]
  790fa3e0  2459154    112128436 System.String
  Total 6471774 objects
  ```

  <span data-ttu-id="b820b-442">Repita el comando al final de la generación 2:</span><span class="sxs-lookup"><span data-stu-id="b820b-442">Repeat the command at the end of generation 2:</span></span>

  <span data-ttu-id="b820b-443">**!dumpheap –stat**</span><span class="sxs-lookup"><span data-stu-id="b820b-443">**!dumpheap –stat**</span></span>

  <span data-ttu-id="b820b-444">Resultado de ejemplo (abreviado para mostrar los objetos que usan más espacio):</span><span class="sxs-lookup"><span data-stu-id="b820b-444">Example output (abridged to show the objects that use the most space):</span></span>

  ```console
  79124228    26648      9314256 System.Object[]
  035f0384    25668     11601936 Toolkit.TlkPosition
  79103b6c   296770     13057880 System.Threading.ReaderWriterLock
  7a747ad4   708730     14174600 System.Collections.Specialized.HybridDictionary
  7a747c78   786497     15729940 System.Collections.Specialized.ListDictionary+DictionaryNode
  7a747bac   700298     19608344 System.Collections.Specialized.ListDictionary
  00155f80    13806     34007212      Free
  035f0ee4    89187     38885532 Toolkit.TlkOrder
  00fcae40     6193     44911636 WaveBasedStrategy.Tick_Snap[]
  791242ec    32370     82359768 System.Collections.Hashtable+bucket[]
  790fa3e0  2440020    111341808 System.String
  Total 6417525 objects
  ```

  <span data-ttu-id="b820b-445">Los objetos `double[]` desaparecieron del final del resultado, lo que significa que se recopilaron.</span><span class="sxs-lookup"><span data-stu-id="b820b-445">The `double[]` objects disappeared from the end of the output, which means that they were collected.</span></span> <span data-ttu-id="b820b-446">Estos objetos ocupan aproximadamente 70 MB.</span><span class="sxs-lookup"><span data-stu-id="b820b-446">These objects account for approximately 70 MB.</span></span> <span data-ttu-id="b820b-447">Los objetos restantes no cambiaron mucho.</span><span class="sxs-lookup"><span data-stu-id="b820b-447">The remaining objects did not change much.</span></span> <span data-ttu-id="b820b-448">Por tanto, estos objetos `double[]` eran la razón por la que se produjo esta recolección de elementos no utilizados de generación 2.</span><span class="sxs-lookup"><span data-stu-id="b820b-448">Therefore, these `double[]` objects were the reason why this generation 2 garbage collection occurred.</span></span> <span data-ttu-id="b820b-449">El paso siguiente consiste en determinar por qué están allí los objetos `double[]` y por qué murieron.</span><span class="sxs-lookup"><span data-stu-id="b820b-449">Your next step is to determine why the `double[]` objects are there and why they died.</span></span> <span data-ttu-id="b820b-450">Puede preguntar al desarrollador del código la procedencia de estos objetos o puede usar el comando **gcroot**.</span><span class="sxs-lookup"><span data-stu-id="b820b-450">You can ask the code developer where these objects came from, or you can use the **gcroot** command.</span></span>

<a name="HighCPU"></a>

### <a name="to-determine-whether-high-cpu-usage-is-caused-by-garbage-collection"></a><span data-ttu-id="b820b-451">Para determinar si el uso elevado de CPU está provocado por la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="b820b-451">To determine whether high CPU usage is caused by garbage collection</span></span>

- <span data-ttu-id="b820b-452">Correlacione el valor del contador de rendimiento de memoria `% Time in GC` con el tiempo de proceso.</span><span class="sxs-lookup"><span data-stu-id="b820b-452">Correlate the `% Time in GC` memory performance counter value with the process time.</span></span>

  <span data-ttu-id="b820b-453">Si el valor de `% Time in GC` tiene un pico a la vez que el tiempo de proceso, la recolección de elementos no utilizados está provocando un uso de CPU elevado.</span><span class="sxs-lookup"><span data-stu-id="b820b-453">If the `% Time in GC` value spikes at the same time as process time, garbage collection is causing a high CPU usage.</span></span> <span data-ttu-id="b820b-454">De lo contrario, genere un perfil de la aplicación para averiguar dónde se está produciendo el uso elevado.</span><span class="sxs-lookup"><span data-stu-id="b820b-454">Otherwise, profile the application to find where the high usage is occurring.</span></span>

## <a name="see-also"></a><span data-ttu-id="b820b-455">Vea también</span><span class="sxs-lookup"><span data-stu-id="b820b-455">See also</span></span>

- [<span data-ttu-id="b820b-456">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="b820b-456">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
