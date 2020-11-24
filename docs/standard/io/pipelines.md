---
title: 'Canalizaciones de E/S: .NET'
description: Obtenga información sobre cómo usar de forma eficiente las canalizaciones de E/S en .NET y evitar problemas en el código.
ms.date: 08/27/2020
helpviewer_keywords:
- Pipelines
- Pipelines I/O
- I/O [.NET], Pipelines
author: rick-anderson
ms.author: riande
ms.openlocfilehash: 508ae0e2b854f81ee639a63063a8f6d73ae84863
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830641"
---
# <a name="systemiopipelines-in-net"></a><span data-ttu-id="c2428-103">System.IO.Pipelines en .NET</span><span class="sxs-lookup"><span data-stu-id="c2428-103">System.IO.Pipelines in .NET</span></span>

<span data-ttu-id="c2428-104"><xref:System.IO.Pipelines> es una biblioteca nueva que se ha diseñado para facilitar la entrada y salida de alto rendimiento en .NET.</span><span class="sxs-lookup"><span data-stu-id="c2428-104"><xref:System.IO.Pipelines> is a new library that is designed to make it easier to do high-performance I/O in .NET.</span></span> <span data-ttu-id="c2428-105">Se trata de una biblioteca que tiene como destino .NET Standard y que funciona en todas las implementaciones de .NET.</span><span class="sxs-lookup"><span data-stu-id="c2428-105">It's a library targeting .NET Standard that works on all .NET implementations.</span></span>

<a name="solve"></a>

## <a name="what-problem-does-systemiopipelines-solve"></a><span data-ttu-id="c2428-106">¿Qué problema resuelve System.IO.Pipelines?</span><span class="sxs-lookup"><span data-stu-id="c2428-106">What problem does System.IO.Pipelines solve</span></span>

<!-- corner case doesn't MT (machine translate)   -->
<span data-ttu-id="c2428-107">Las aplicaciones que analizan datos de streaming se componen de código reutilizable que cuenta con muchos flujos de código especializados e inusuales.</span><span class="sxs-lookup"><span data-stu-id="c2428-107">Apps that parse streaming data are composed of boilerplate code having many specialized and unusual code flows.</span></span> <span data-ttu-id="c2428-108">El código reutilizable y especial del caso es complejo y difícil de mantener.</span><span class="sxs-lookup"><span data-stu-id="c2428-108">The boilerplate and special case code is complex and difficult to maintain.</span></span>

<span data-ttu-id="c2428-109">`System.IO.Pipelines` se ha diseñado para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c2428-109">`System.IO.Pipelines` was architected to:</span></span>

* <span data-ttu-id="c2428-110">Disponer de un alto rendimiento al analizar datos de streaming.</span><span class="sxs-lookup"><span data-stu-id="c2428-110">Have high performance parsing streaming data.</span></span>
* <span data-ttu-id="c2428-111">Reducir la complejidad del código.</span><span class="sxs-lookup"><span data-stu-id="c2428-111">Reduce code complexity.</span></span>

<span data-ttu-id="c2428-112">El código siguiente es habitual para un servidor TCP que recibe mensajes delimitados por línea (delimitados por `'\n'`) de un cliente:</span><span class="sxs-lookup"><span data-stu-id="c2428-112">The following code is typical for a TCP server that receives line-delimited messages (delimited by `'\n'`) from a client:</span></span>

```csharp
async Task ProcessLinesAsync(NetworkStream stream)
{
    var buffer = new byte[1024];
    await stream.ReadAsync(buffer, 0, buffer.Length);

    // Process a single line from the buffer
    ProcessLine(buffer);
}
```

<span data-ttu-id="c2428-113">El código anterior tiene varios problemas:</span><span class="sxs-lookup"><span data-stu-id="c2428-113">The preceding code has several problems:</span></span>

* <span data-ttu-id="c2428-114">Es posible que el mensaje completo (final de la línea) no se reciba en una sola llamada a `ReadAsync`.</span><span class="sxs-lookup"><span data-stu-id="c2428-114">The entire message (end of line) might not be received in a single call to `ReadAsync`.</span></span>
* <span data-ttu-id="c2428-115">Se omite el resultado de `stream.ReadAsync`.</span><span class="sxs-lookup"><span data-stu-id="c2428-115">It's ignoring the result of `stream.ReadAsync`.</span></span> <span data-ttu-id="c2428-116">`stream.ReadAsync` devuelve la cantidad de datos que se han leído.</span><span class="sxs-lookup"><span data-stu-id="c2428-116">`stream.ReadAsync` returns how much data was read.</span></span>
* <span data-ttu-id="c2428-117">No controla el caso en el que se leen varias líneas en una sola llamada a `ReadAsync`.</span><span class="sxs-lookup"><span data-stu-id="c2428-117">It doesn't handle the case where multiple lines are read in a single `ReadAsync` call.</span></span>
* <span data-ttu-id="c2428-118">Asigna una matriz `byte` con cada lectura.</span><span class="sxs-lookup"><span data-stu-id="c2428-118">It allocates a `byte` array with each read.</span></span>

<span data-ttu-id="c2428-119">Para solucionar los problemas anteriores, es necesario realizar los siguientes cambios:</span><span class="sxs-lookup"><span data-stu-id="c2428-119">To fix the preceding problems, the following changes are required:</span></span>

* <span data-ttu-id="c2428-120">Almacenar en búfer los datos entrantes hasta que se encuentre una línea nueva.</span><span class="sxs-lookup"><span data-stu-id="c2428-120">Buffer the incoming data until a new line is found.</span></span>
* <span data-ttu-id="c2428-121">Analizar todas las líneas devueltas en el búfer.</span><span class="sxs-lookup"><span data-stu-id="c2428-121">Parse all the lines returned in the buffer.</span></span>
* <span data-ttu-id="c2428-122">Es posible que la línea tenga un tamaño superior a 1 KB (1024 bytes).</span><span class="sxs-lookup"><span data-stu-id="c2428-122">It's possible that the line is bigger than 1 KB (1024 bytes).</span></span> <span data-ttu-id="c2428-123">El código debe cambiar el tamaño del búfer de entrada hasta que se encuentre el delimitador para ajustarse a la línea completa dentro del búfer.</span><span class="sxs-lookup"><span data-stu-id="c2428-123">The code needs to resize the input buffer until the delimiter is found in order to fit the complete line inside the buffer.</span></span>

  * <span data-ttu-id="c2428-124">Si se cambia el tamaño del búfer, se realizan más copias de búfer a medida que aparecen líneas más largas en la entrada.</span><span class="sxs-lookup"><span data-stu-id="c2428-124">If the buffer is resized, more buffer copies are made as longer lines appear in the input.</span></span>
  * <span data-ttu-id="c2428-125">Para reducir el espacio desaprovechado, compacte el búfer usado para las líneas de lectura.</span><span class="sxs-lookup"><span data-stu-id="c2428-125">To reduce wasted space, compact the buffer used for reading lines.</span></span>

* <span data-ttu-id="c2428-126">Considere la posibilidad de usar la agrupación de búferes para evitar asignar memoria de forma repetida.</span><span class="sxs-lookup"><span data-stu-id="c2428-126">Consider using buffer pooling to avoid allocating memory repeatedly.</span></span>
* <span data-ttu-id="c2428-127">En el código siguiente se abordan algunos de estos problemas:</span><span class="sxs-lookup"><span data-stu-id="c2428-127">The following code addresses some of these problems:</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/ProcessLinesAsync.cs" id="snippet":::

<span data-ttu-id="c2428-128">El código anterior es complejo y no aborda todos los problemas identificados.</span><span class="sxs-lookup"><span data-stu-id="c2428-128">The previous code is complex and doesn't address all the problems identified.</span></span> <span data-ttu-id="c2428-129">Las redes de alto rendimiento normalmente implican la escritura de código muy complejo para maximizar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c2428-129">High-performance networking usually means writing very complex code to maximize performance.</span></span> <span data-ttu-id="c2428-130">`System.IO.Pipelines` se ha diseñado para facilitar la escritura de este tipo de código.</span><span class="sxs-lookup"><span data-stu-id="c2428-130">`System.IO.Pipelines` was designed to make writing this type of code easier.</span></span>

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="pipe"></a><span data-ttu-id="c2428-131">Canalización (|).</span><span class="sxs-lookup"><span data-stu-id="c2428-131">Pipe</span></span>

<span data-ttu-id="c2428-132">La clase <xref:System.IO.Pipelines.Pipe> se puede usar para crear un par de `PipeWriter/PipeReader`.</span><span class="sxs-lookup"><span data-stu-id="c2428-132">The <xref:System.IO.Pipelines.Pipe> class can be used to create a `PipeWriter/PipeReader` pair.</span></span> <span data-ttu-id="c2428-133">Todos los datos escritos en `PipeWriter` están disponibles en `PipeReader`:</span><span class="sxs-lookup"><span data-stu-id="c2428-133">All data written into the `PipeWriter` is available in the `PipeReader`:</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/Pipe.cs" id="snippet2":::

<a name="pbu"></a>

### <a name="pipe-basic-usage"></a><span data-ttu-id="c2428-134">Uso básico de la canalización</span><span class="sxs-lookup"><span data-stu-id="c2428-134">Pipe basic usage</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/Pipe.cs" id="snippet":::

<span data-ttu-id="c2428-135">Hay dos bucles:</span><span class="sxs-lookup"><span data-stu-id="c2428-135">There are two loops:</span></span>

* <span data-ttu-id="c2428-136">`FillPipeAsync` lee de `Socket` y escribe en `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="c2428-136">`FillPipeAsync` reads from the `Socket` and writes to the `PipeWriter`.</span></span>
* <span data-ttu-id="c2428-137">`ReadPipeAsync` lee de `PipeReader` y analiza las líneas de entrada.</span><span class="sxs-lookup"><span data-stu-id="c2428-137">`ReadPipeAsync` reads from the `PipeReader` and parses incoming lines.</span></span>

<span data-ttu-id="c2428-138">No existe ningún búfer explícito asignado.</span><span class="sxs-lookup"><span data-stu-id="c2428-138">There are no explicit buffers allocated.</span></span> <span data-ttu-id="c2428-139">Toda la administración del búfer se delega en las implementaciones de `PipeReader` y `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="c2428-139">All buffer management is delegated to the `PipeReader` and `PipeWriter` implementations.</span></span> <span data-ttu-id="c2428-140">La delegación de la administración del búfer facilita el consumo de código para centrarse únicamente en la lógica de negocios.</span><span class="sxs-lookup"><span data-stu-id="c2428-140">Delegating buffer management makes it easier for consuming code to focus solely on the business logic.</span></span>

<span data-ttu-id="c2428-141">En el primer bucle:</span><span class="sxs-lookup"><span data-stu-id="c2428-141">In the first loop:</span></span>

* <span data-ttu-id="c2428-142">Se llama a <xref:System.IO.Pipelines.PipeWriter.GetMemory(System.Int32)?displayProperty=nameWithType> para obtener la memoria del escritor subyacente.</span><span class="sxs-lookup"><span data-stu-id="c2428-142"><xref:System.IO.Pipelines.PipeWriter.GetMemory(System.Int32)?displayProperty=nameWithType> is called to get memory from the underlying writer.</span></span>
* <span data-ttu-id="c2428-143">Se llama a <xref:System.IO.Pipelines.PipeWriter.Advance(System.Int32)?displayProperty=nameWithType> para indicar a `PipeWriter` la cantidad de datos que se han escrito en el búfer.</span><span class="sxs-lookup"><span data-stu-id="c2428-143"><xref:System.IO.Pipelines.PipeWriter.Advance(System.Int32)?displayProperty=nameWithType> is called to tell the `PipeWriter` how much data was written to the buffer.</span></span>
* <span data-ttu-id="c2428-144">Se llama a <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType> para hacer que los datos estén disponibles en `PipeReader`.</span><span class="sxs-lookup"><span data-stu-id="c2428-144"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType> is called to make the data available to the `PipeReader`.</span></span>

<span data-ttu-id="c2428-145">En el segundo bucle, `PipeReader` consume los búferes que ha escrito `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="c2428-145">In the second loop, the `PipeReader` consumes the buffers written by `PipeWriter`.</span></span> <span data-ttu-id="c2428-146">Los búferes proceden del socket.</span><span class="sxs-lookup"><span data-stu-id="c2428-146">The buffers come from the socket.</span></span> <span data-ttu-id="c2428-147">La llamada a `PipeReader.ReadAsync`:</span><span class="sxs-lookup"><span data-stu-id="c2428-147">The call to `PipeReader.ReadAsync`:</span></span>

* <span data-ttu-id="c2428-148">Devuelve un elemento <xref:System.IO.Pipelines.ReadResult> que contiene dos fragmentos de información importantes:</span><span class="sxs-lookup"><span data-stu-id="c2428-148">Returns a <xref:System.IO.Pipelines.ReadResult> that contains two important pieces of information:</span></span>

  * <span data-ttu-id="c2428-149">Los datos que se han leído en forma de `ReadOnlySequence<byte>`.</span><span class="sxs-lookup"><span data-stu-id="c2428-149">The data that was read in the form of `ReadOnlySequence<byte>`.</span></span>
  * <span data-ttu-id="c2428-150">Un valor booleano `IsCompleted` que indica si se ha alcanzado el final de los datos (EOD).</span><span class="sxs-lookup"><span data-stu-id="c2428-150">A boolean `IsCompleted` that indicates if the end of data (EOF) has been reached.</span></span>

<span data-ttu-id="c2428-151">Después de buscar el delimitador de final de línea (EOL) y analizar la línea ocurre lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c2428-151">After finding the end of line (EOL) delimiter and parsing the line:</span></span>

* <span data-ttu-id="c2428-152">La lógica procesa el búfer para omitir lo que ya se ha procesado.</span><span class="sxs-lookup"><span data-stu-id="c2428-152">The logic processes the buffer to skip what's already processed.</span></span>
* <span data-ttu-id="c2428-153">Se llama a `PipeReader.AdvanceTo` para indicar a `PipeReader` la cantidad de datos que se han consumido y examinado.</span><span class="sxs-lookup"><span data-stu-id="c2428-153">`PipeReader.AdvanceTo` is called to tell the `PipeReader` how much data has been consumed and examined.</span></span>

<span data-ttu-id="c2428-154">Los bucles de lectura y escritura finalizan con una llamada a `Complete`.</span><span class="sxs-lookup"><span data-stu-id="c2428-154">The reader and writer loops end by calling `Complete`.</span></span> <span data-ttu-id="c2428-155">`Complete` permite liberar la memoria que ha asignado la canalización subyacente.</span><span class="sxs-lookup"><span data-stu-id="c2428-155">`Complete` lets the underlying Pipe release the memory it allocated.</span></span>

### <a name="backpressure-and-flow-control"></a><span data-ttu-id="c2428-156">Contrapresión y control de flujo</span><span class="sxs-lookup"><span data-stu-id="c2428-156">Backpressure and flow control</span></span>

<span data-ttu-id="c2428-157">Idealmente, la lectura y el análisis funcionan juntos:</span><span class="sxs-lookup"><span data-stu-id="c2428-157">Ideally, reading and parsing work together:</span></span>

* <span data-ttu-id="c2428-158">El subproceso de escritura consume datos de la red y los coloca en los búferes.</span><span class="sxs-lookup"><span data-stu-id="c2428-158">The writing thread consumes data from the network and puts it in buffers.</span></span>
* <span data-ttu-id="c2428-159">El subproceso de análisis se encarga de construir las estructuras de datos adecuadas.</span><span class="sxs-lookup"><span data-stu-id="c2428-159">The parsing thread is responsible for constructing the appropriate data structures.</span></span>

<span data-ttu-id="c2428-160">Normalmente, el análisis tarda más tiempo en realizarse que simplemente copiar bloques de datos de la red:</span><span class="sxs-lookup"><span data-stu-id="c2428-160">Typically, parsing takes more time than just copying blocks of data from the network:</span></span>

* <span data-ttu-id="c2428-161">El subproceso de lectura se obtiene antes del subproceso de análisis.</span><span class="sxs-lookup"><span data-stu-id="c2428-161">The reading thread gets ahead of the parsing thread.</span></span>
* <span data-ttu-id="c2428-162">El subproceso de lectura tiene que ralentizar o asignar más memoria para almacenar los datos para el subproceso de análisis.</span><span class="sxs-lookup"><span data-stu-id="c2428-162">The reading thread has to either slow down or allocate more memory to store the data for the parsing thread.</span></span>

<span data-ttu-id="c2428-163">Para obtener un rendimiento óptimo, existe un equilibrio entre las pausas frecuentes y la asignación de más memoria.</span><span class="sxs-lookup"><span data-stu-id="c2428-163">For optimal performance, there's a balance between frequent pauses and allocating more memory.</span></span>

<span data-ttu-id="c2428-164">Para resolver el problema anterior, `Pipe` tiene dos opciones de configuración para controlar el flujo de datos:</span><span class="sxs-lookup"><span data-stu-id="c2428-164">To solve the preceding problem, the `Pipe` has two settings to control the flow of data:</span></span>

* <span data-ttu-id="c2428-165"><xref:System.IO.Pipelines.PipeOptions.PauseWriterThreshold>: determina la cantidad de datos que se deben almacenar en búfer antes de que se pausen las llamadas a <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2428-165"><xref:System.IO.Pipelines.PipeOptions.PauseWriterThreshold>: Determines how much data should be buffered before calls to <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> pause.</span></span>
* <span data-ttu-id="c2428-166"><xref:System.IO.Pipelines.PipeOptions.ResumeWriterThreshold>: determina la cantidad de datos que debe observar el lector antes de que se reanuden las llamadas a `PipeWriter.FlushAsync`.</span><span class="sxs-lookup"><span data-stu-id="c2428-166"><xref:System.IO.Pipelines.PipeOptions.ResumeWriterThreshold>: Determines how much data the reader has to observe before calls to `PipeWriter.FlushAsync` resume.</span></span>

![Diagrama con ResumeWriterThreshold y PauseWriterThreshold.](media/pipelines/resume-pause.png)

<span data-ttu-id="c2428-168"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="c2428-168"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>:</span></span>

* <span data-ttu-id="c2428-169">Devuelve un `ValueTask<FlushResult>` incompleto cuando la cantidad de datos de `Pipe` cruza `PauseWriterThreshold`.</span><span class="sxs-lookup"><span data-stu-id="c2428-169">Returns an incomplete `ValueTask<FlushResult>` when the amount of data in the `Pipe` crosses `PauseWriterThreshold`.</span></span>
* <span data-ttu-id="c2428-170">Completa `ValueTask<FlushResult>` cuando se vuelve menor que `ResumeWriterThreshold`.</span><span class="sxs-lookup"><span data-stu-id="c2428-170">Completes `ValueTask<FlushResult>` when it becomes lower than `ResumeWriterThreshold`.</span></span>

<span data-ttu-id="c2428-171">Se usan dos valores para evitar ciclos rápidos, que pueden producirse si solo se usa un valor.</span><span class="sxs-lookup"><span data-stu-id="c2428-171">Two values are used to prevent rapid cycling, which can occur if one value is used.</span></span>

### <a name="examples"></a><span data-ttu-id="c2428-172">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c2428-172">Examples</span></span>

```csharp
// The Pipe will start returning incomplete tasks from FlushAsync until
// the reader examines at least 5 bytes.
var options = new PipeOptions(pauseWriterThreshold: 10, resumeWriterThreshold: 5);
var pipe = new Pipe(options);
```

### <a name="pipescheduler"></a><span data-ttu-id="c2428-173">PipeScheduler</span><span class="sxs-lookup"><span data-stu-id="c2428-173">PipeScheduler</span></span>

<span data-ttu-id="c2428-174">Normalmente, cuando se usa `async` y `await`, el código asincrónico se reanuda en un elemento <xref:System.Threading.Tasks.TaskScheduler> o en el elemento <xref:System.Threading.SynchronizationContext> actual.</span><span class="sxs-lookup"><span data-stu-id="c2428-174">Typically when using `async` and `await`, asynchronous code resumes on either on a <xref:System.Threading.Tasks.TaskScheduler> or on the current <xref:System.Threading.SynchronizationContext>.</span></span>

<span data-ttu-id="c2428-175">Al realizar operaciones de E/S, es importante tener un control específico sobre dónde se realizan estas operaciones.</span><span class="sxs-lookup"><span data-stu-id="c2428-175">When doing I/O, it's important to have fine-grained control over where the I/O is performed.</span></span> <span data-ttu-id="c2428-176">Este control permite sacar provecho de las cachés de CPU de manera eficiente.</span><span class="sxs-lookup"><span data-stu-id="c2428-176">This control allows taking advantage of CPU caches effectively.</span></span> <span data-ttu-id="c2428-177">Para las aplicaciones de alto rendimiento, como los servidores web, disponer de un almacenamiento en caché eficiente resulta fundamental.</span><span class="sxs-lookup"><span data-stu-id="c2428-177">Efficient caching is critical for high-performance apps like web servers.</span></span> <span data-ttu-id="c2428-178"><xref:System.IO.Pipelines.PipeScheduler> proporciona control sobre dónde se ejecutan las devoluciones de llamada asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="c2428-178"><xref:System.IO.Pipelines.PipeScheduler> provides control over where asynchronous callbacks run.</span></span> <span data-ttu-id="c2428-179">De manera predeterminada:</span><span class="sxs-lookup"><span data-stu-id="c2428-179">By default:</span></span>

* <span data-ttu-id="c2428-180">Se usa el elemento <xref:System.Threading.SynchronizationContext> actual.</span><span class="sxs-lookup"><span data-stu-id="c2428-180">The current <xref:System.Threading.SynchronizationContext> is used.</span></span>
* <span data-ttu-id="c2428-181">Si no hay ningún elemento `SynchronizationContext`, se usa el grupo de subprocesos para ejecutar las devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="c2428-181">If there's no `SynchronizationContext`, it uses the thread pool to run callbacks.</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/Program.cs" id="snippet":::

<span data-ttu-id="c2428-182">[PipeScheduler.ThreadPool](xref:System.IO.Pipelines.PipeScheduler.ThreadPool) es la implementación de <xref:System.IO.Pipelines.PipeScheduler> que pone en cola las devoluciones de llamada en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="c2428-182">[PipeScheduler.ThreadPool](xref:System.IO.Pipelines.PipeScheduler.ThreadPool) is the <xref:System.IO.Pipelines.PipeScheduler> implementation that queues callbacks to the thread pool.</span></span> <span data-ttu-id="c2428-183">`PipeScheduler.ThreadPool` es el valor predeterminado y, por lo general, la mejor opción.</span><span class="sxs-lookup"><span data-stu-id="c2428-183">`PipeScheduler.ThreadPool` is the default and generally the best choice.</span></span> <span data-ttu-id="c2428-184">[PipeScheduler.Inline](xref:System.IO.Pipelines.PipeScheduler.Inline) puede producir consecuencias no intencionadas, como interbloqueos.</span><span class="sxs-lookup"><span data-stu-id="c2428-184">[PipeScheduler.Inline](xref:System.IO.Pipelines.PipeScheduler.Inline) can cause unintended consequences such as deadlocks.</span></span>

### <a name="pipe-reset"></a><span data-ttu-id="c2428-185">Restablecimiento de la canalización</span><span class="sxs-lookup"><span data-stu-id="c2428-185">Pipe reset</span></span>

<span data-ttu-id="c2428-186">A menudo, es eficiente la reutilización del objeto `Pipe`.</span><span class="sxs-lookup"><span data-stu-id="c2428-186">It's frequently efficient to reuse the `Pipe` object.</span></span> <span data-ttu-id="c2428-187">Para restablecer la canalización, llame a <xref:System.IO.Pipelines.PipeReader> <xref:System.IO.Pipelines.Pipe.Reset%2A> cuando se hayan completado los elementos `PipeReader` y `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="c2428-187">To reset the pipe, call <xref:System.IO.Pipelines.PipeReader> <xref:System.IO.Pipelines.Pipe.Reset%2A> when both the `PipeReader` and `PipeWriter` are complete.</span></span>

## <a name="pipereader"></a><span data-ttu-id="c2428-188">PipeReader</span><span class="sxs-lookup"><span data-stu-id="c2428-188">PipeReader</span></span>

<span data-ttu-id="c2428-189"><xref:System.IO.Pipelines.PipeReader> administra la memoria en nombre del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c2428-189"><xref:System.IO.Pipelines.PipeReader> manages memory on the caller's behalf.</span></span> <span data-ttu-id="c2428-190">Llame a <xref:System.IO.Pipelines.PipeReader.AdvanceTo%2A?displayProperty=nameWithType>**siempre** después de llamar a <xref:System.IO.Pipelines.PipeReader.ReadAsync%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c2428-190">**Always** call <xref:System.IO.Pipelines.PipeReader.AdvanceTo%2A?displayProperty=nameWithType> after calling <xref:System.IO.Pipelines.PipeReader.ReadAsync%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c2428-191">Esto permite que `PipeReader` sepa cuándo ha acabado con la memoria el autor de la llamada, de tal modo que se le pueda realizar un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c2428-191">This lets the `PipeReader` know when the caller is done with the memory so that it can be tracked.</span></span> <span data-ttu-id="c2428-192">El elemento `ReadOnlySequence<byte>` que devuelve `PipeReader.ReadAsync` solo es válido hasta que se llame a `PipeReader.AdvanceTo`.</span><span class="sxs-lookup"><span data-stu-id="c2428-192">The `ReadOnlySequence<byte>` returned from `PipeReader.ReadAsync` is only valid until the call the `PipeReader.AdvanceTo`.</span></span> <span data-ttu-id="c2428-193">No es válido usar `ReadOnlySequence<byte>` después de llamar a `PipeReader.AdvanceTo`.</span><span class="sxs-lookup"><span data-stu-id="c2428-193">It's illegal to use `ReadOnlySequence<byte>` after calling `PipeReader.AdvanceTo`.</span></span>

<span data-ttu-id="c2428-194">`PipeReader.AdvanceTo` toma dos argumentos <xref:System.SequencePosition>:</span><span class="sxs-lookup"><span data-stu-id="c2428-194">`PipeReader.AdvanceTo` takes two <xref:System.SequencePosition> arguments:</span></span>

* <span data-ttu-id="c2428-195">El primer argumento determina la cantidad de memoria consumida.</span><span class="sxs-lookup"><span data-stu-id="c2428-195">The first argument determines how much memory was consumed.</span></span>
* <span data-ttu-id="c2428-196">El segundo argumento determina la cantidad de búfer observado.</span><span class="sxs-lookup"><span data-stu-id="c2428-196">The second argument determines how much of the buffer was observed.</span></span>

<span data-ttu-id="c2428-197">Marcar los datos como consumidos significa que la canalización puede devolver la memoria al grupo de búferes subyacente.</span><span class="sxs-lookup"><span data-stu-id="c2428-197">Marking data as consumed means that the pipe can return the memory to the underlying buffer pool.</span></span> <span data-ttu-id="c2428-198">Cuando se marcan los datos como observados, estos controlan lo que hace la siguiente llamada a `PipeReader.ReadAsync`.</span><span class="sxs-lookup"><span data-stu-id="c2428-198">Marking data as observed controls what the next call to `PipeReader.ReadAsync` does.</span></span> <span data-ttu-id="c2428-199">Marcar todo como observado significa que la siguiente llamada a `PipeReader.ReadAsync` no se devolverá hasta que haya más datos escritos en la canalización.</span><span class="sxs-lookup"><span data-stu-id="c2428-199">Marking everything as observed means that the next call to `PipeReader.ReadAsync` won't return until there's more data written to the pipe.</span></span> <span data-ttu-id="c2428-200">Cualquier otro valor hará que la siguiente llamada a `PipeReader.ReadAsync` se devuelva de inmediato con los datos observados *y* los no observados, pero no con los que ya se han consumido.</span><span class="sxs-lookup"><span data-stu-id="c2428-200">Any other value will make the next call to `PipeReader.ReadAsync` return immediately with the observed *and* unobserved data, but not data that has already been consumed.</span></span>

### <a name="read-streaming-data-scenarios"></a><span data-ttu-id="c2428-201">Escenarios de lectura de datos de streaming</span><span class="sxs-lookup"><span data-stu-id="c2428-201">Read streaming data scenarios</span></span>

<span data-ttu-id="c2428-202">Hay un par de patrones típicos que surgen al intentar leer datos de streaming:</span><span class="sxs-lookup"><span data-stu-id="c2428-202">There are a couple of typical patterns that emerge when trying to read streaming data:</span></span>

* <span data-ttu-id="c2428-203">Dada una secuencia de datos, analizar un solo mensaje.</span><span class="sxs-lookup"><span data-stu-id="c2428-203">Given a stream of data, parse a single message.</span></span>
* <span data-ttu-id="c2428-204">Dada una secuencia de datos, analizar todos los mensajes disponibles.</span><span class="sxs-lookup"><span data-stu-id="c2428-204">Given a stream of data, parse all available messages.</span></span>

<span data-ttu-id="c2428-205">En los ejemplos siguientes se usa el método `TryParseMessage` para analizar los mensajes que proceden de un elemento `ReadOnlySequence<byte>`.</span><span class="sxs-lookup"><span data-stu-id="c2428-205">The following examples use the `TryParseMessage` method for parsing messages from a `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="c2428-206">`TryParseMessage` analiza un solo mensaje y actualiza el búfer de entrada para recortar el mensaje analizado del búfer.</span><span class="sxs-lookup"><span data-stu-id="c2428-206">`TryParseMessage` parses a single message and update the input buffer to trim the parsed message from the buffer.</span></span> <span data-ttu-id="c2428-207">`TryParseMessage` no forma parte de .NET, es un método de usuario escrito que se usa en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="c2428-207">`TryParseMessage` is not part of .NET, it's a user written method used in the following sections.</span></span>

```csharp
bool TryParseMessage(ref ReadOnlySequence<byte> buffer, out Message message);
```

### <a name="read-a-single-message"></a><span data-ttu-id="c2428-208">Lectura de un único mensaje</span><span class="sxs-lookup"><span data-stu-id="c2428-208">Read a single message</span></span>

<span data-ttu-id="c2428-209">En el código siguiente se lee un único mensaje de un elemento `PipeReader` y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c2428-209">The following code reads a single message from a `PipeReader` and returns it to the caller.</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/ReadSingleMsg.cs" id="snippet":::

<span data-ttu-id="c2428-210">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="c2428-210">The preceding code:</span></span>

* <span data-ttu-id="c2428-211">Analiza un único mensaje.</span><span class="sxs-lookup"><span data-stu-id="c2428-211">Parses a single message.</span></span>
* <span data-ttu-id="c2428-212">Actualiza el elemento `SequencePosition` consumido y el elemento `SequencePosition` examinado para que apunte al principio del búfer recortado de entrada.</span><span class="sxs-lookup"><span data-stu-id="c2428-212">Updates the consumed `SequencePosition` and examined `SequencePosition` to point to the start of the trimmed input buffer.</span></span>

<span data-ttu-id="c2428-213">Los dos argumentos `SequencePosition` se actualizan porque `TryParseMessage` quita el mensaje analizado del búfer de entrada.</span><span class="sxs-lookup"><span data-stu-id="c2428-213">The two `SequencePosition` arguments are updated because `TryParseMessage` removes the parsed message from the input buffer.</span></span> <span data-ttu-id="c2428-214">Por lo general, al analizar un solo mensaje del búfer, la posición examinada debe ser una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="c2428-214">Generally, when parsing a single message from the buffer, the examined position should be one of the following:</span></span>

* <span data-ttu-id="c2428-215">El final del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c2428-215">The end of the message.</span></span>
* <span data-ttu-id="c2428-216">El final del búfer recibido si no se ha encontrado ningún mensaje.</span><span class="sxs-lookup"><span data-stu-id="c2428-216">The end of the received buffer if no message was found.</span></span>

<span data-ttu-id="c2428-217">El caso de mensaje único tiene la probabilidad más alta de producir errores.</span><span class="sxs-lookup"><span data-stu-id="c2428-217">The single message case has the most potential for errors.</span></span> <span data-ttu-id="c2428-218">Si se pasan valores incorrectos a *examinados*, se puede producir una excepción de memoria insuficiente o un bucle infinito.</span><span class="sxs-lookup"><span data-stu-id="c2428-218">Passing the wrong values to *examined* can result in an out of memory exception or an infinite loop.</span></span> <span data-ttu-id="c2428-219">Para obtener más información, vea la sección [Problemas comunes de PipeReader](#gotchas).</span><span class="sxs-lookup"><span data-stu-id="c2428-219">For more information, see the [PipeReader common problems](#gotchas) section in this article.</span></span>

### <a name="reading-multiple-messages"></a><span data-ttu-id="c2428-220">Lectura de varios mensajes</span><span class="sxs-lookup"><span data-stu-id="c2428-220">Reading multiple messages</span></span>

<span data-ttu-id="c2428-221">En el código siguiente se leen todos los mensajes de un elemento `PipeReader` y se llama a `ProcessMessageAsync` en cada uno de estos.</span><span class="sxs-lookup"><span data-stu-id="c2428-221">The following code reads all messages from a `PipeReader` and calls `ProcessMessageAsync` on each.</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyConnection1.cs" id="snippet":::

### <a name="cancellation"></a><span data-ttu-id="c2428-222">Cancelación</span><span class="sxs-lookup"><span data-stu-id="c2428-222">Cancellation</span></span>

<span data-ttu-id="c2428-223">`PipeReader.ReadAsync`:</span><span class="sxs-lookup"><span data-stu-id="c2428-223">`PipeReader.ReadAsync`:</span></span>

* <span data-ttu-id="c2428-224">Admite pasar un elemento <xref:System.Threading.CancellationToken>.</span><span class="sxs-lookup"><span data-stu-id="c2428-224">Supports passing a <xref:System.Threading.CancellationToken>.</span></span>
* <span data-ttu-id="c2428-225">Produce un elemento <xref:System.OperationCanceledException> si se cancela `CancellationToken` mientras haya una lectura pendiente.</span><span class="sxs-lookup"><span data-stu-id="c2428-225">Throws an <xref:System.OperationCanceledException> if the `CancellationToken` is canceled while there's a read pending.</span></span>
* <span data-ttu-id="c2428-226">Admite una manera de cancelar la operación de lectura actual mediante <xref:System.IO.Pipelines.PipeReader.CancelPendingRead%2A?displayProperty=nameWithType>, lo que evita que se produzca una excepción.</span><span class="sxs-lookup"><span data-stu-id="c2428-226">Supports a way to cancel the current read operation via <xref:System.IO.Pipelines.PipeReader.CancelPendingRead%2A?displayProperty=nameWithType>, which avoids raising an exception.</span></span> <span data-ttu-id="c2428-227">La llamada a `PipeReader.CancelPendingRead` provoca que la llamada actual a `PipeReader.ReadAsync`, o la siguiente, devuelva un elemento <xref:System.IO.Pipelines.ReadResult> con `IsCanceled` establecido en `true`.</span><span class="sxs-lookup"><span data-stu-id="c2428-227">Calling `PipeReader.CancelPendingRead` causes the current or next call to `PipeReader.ReadAsync` to return a <xref:System.IO.Pipelines.ReadResult> with `IsCanceled` set to `true`.</span></span> <span data-ttu-id="c2428-228">Esto puede ser útil para detener el bucle de lectura existente de forma no destructiva y no excepcional.</span><span class="sxs-lookup"><span data-stu-id="c2428-228">This can be useful for halting the existing read loop in a non-destructive and non-exceptional way.</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyConnection.cs" id="snippet":::

<a name="gotchas"></a>

### <a name="pipereader-common-problems"></a><span data-ttu-id="c2428-229">Problemas comunes de PipeReader</span><span class="sxs-lookup"><span data-stu-id="c2428-229">PipeReader common problems</span></span>

* <span data-ttu-id="c2428-230">Si se pasan valores incorrectos a `consumed` o `examined`, es posible que se lean datos ya leídos.</span><span class="sxs-lookup"><span data-stu-id="c2428-230">Passing the wrong values to `consumed` or `examined` may result in reading already read data.</span></span>
* <span data-ttu-id="c2428-231">Si se pasa `buffer.End` como examinado, es posible que se produzca lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c2428-231">Passing `buffer.End` as examined may result in:</span></span>

  * <span data-ttu-id="c2428-232">Datos detenidos</span><span class="sxs-lookup"><span data-stu-id="c2428-232">Stalled data</span></span>
  * <span data-ttu-id="c2428-233">Es posible que se produzca una excepción de memoria insuficiente (OOM) si no se consumen los datos.</span><span class="sxs-lookup"><span data-stu-id="c2428-233">Possibly an eventual Out of Memory (OOM) exception if data isn't consumed.</span></span> <span data-ttu-id="c2428-234">Por ejemplo, `PipeReader.AdvanceTo(position, buffer.End)` cuando se procesa un único mensaje a la vez desde el búfer.</span><span class="sxs-lookup"><span data-stu-id="c2428-234">For example, `PipeReader.AdvanceTo(position, buffer.End)` when processing a single message at a time from the buffer.</span></span>

* <span data-ttu-id="c2428-235">Si se pasan valores incorrectos a `consumed` o `examined`, es posible que se produzca un bucle infinito.</span><span class="sxs-lookup"><span data-stu-id="c2428-235">Passing the wrong values to `consumed` or `examined` may result in an infinite loop.</span></span> <span data-ttu-id="c2428-236">Por ejemplo, `PipeReader.AdvanceTo(buffer.Start)`, si `buffer.Start` no ha cambiado, hará que la siguiente llamada a `PipeReader.ReadAsync` se devuelva inmediatamente antes de que lleguen datos nuevos.</span><span class="sxs-lookup"><span data-stu-id="c2428-236">For example, `PipeReader.AdvanceTo(buffer.Start)` if `buffer.Start` hasn't changed will cause the next call to `PipeReader.ReadAsync` to return immediately before new data arrives.</span></span>
* <span data-ttu-id="c2428-237">Si se pasan valores incorrectos a `consumed` o `examined`, es posible que se produzca un almacenamiento en búfer infinito (posible OOM).</span><span class="sxs-lookup"><span data-stu-id="c2428-237">Passing the wrong values to `consumed` or `examined` may result in infinite buffering (eventual OOM).</span></span>
* <span data-ttu-id="c2428-238">El uso de `ReadOnlySequence<byte>` después de llamar a `PipeReader.AdvanceTo` puede producir daños en la memoria (se usa después de liberar).</span><span class="sxs-lookup"><span data-stu-id="c2428-238">Using the `ReadOnlySequence<byte>` after calling `PipeReader.AdvanceTo` may result in memory corruption (use after free).</span></span>
* <span data-ttu-id="c2428-239">Si se produce un error al llamar a `PipeReader.Complete/CompleteAsync`, puede dar como resultado una fuga de memoria.</span><span class="sxs-lookup"><span data-stu-id="c2428-239">Failing to call `PipeReader.Complete/CompleteAsync` may result in a memory leak.</span></span>
* <span data-ttu-id="c2428-240">Al comprobar <xref:System.IO.Pipelines.ReadResult.IsCompleted?displayProperty=nameWithType> y salir de la lógica de lectura antes de procesar el búfer, se produce una pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="c2428-240">Checking <xref:System.IO.Pipelines.ReadResult.IsCompleted?displayProperty=nameWithType> and exiting the reading logic before processing the buffer results in data loss.</span></span> <span data-ttu-id="c2428-241">La condición de salida del bucle debe basarse en `ReadResult.Buffer.IsEmpty` y `ReadResult.IsCompleted`.</span><span class="sxs-lookup"><span data-stu-id="c2428-241">The loop exit condition should be based on `ReadResult.Buffer.IsEmpty` and `ReadResult.IsCompleted`.</span></span> <span data-ttu-id="c2428-242">Si esto se hace incorrectamente, podría producirse un bucle infinito.</span><span class="sxs-lookup"><span data-stu-id="c2428-242">Doing this incorrectly could result in an infinite loop.</span></span>

#### <a name="problematic-code"></a><span data-ttu-id="c2428-243">Código problemático</span><span class="sxs-lookup"><span data-stu-id="c2428-243">Problematic code</span></span>

<span data-ttu-id="c2428-244">❌ **Pérdida de datos**</span><span class="sxs-lookup"><span data-stu-id="c2428-244">❌ **Data loss**</span></span>

<span data-ttu-id="c2428-245">`ReadResult` puede devolver el segmento final de los datos cuando `IsCompleted` está establecido en `true`.</span><span class="sxs-lookup"><span data-stu-id="c2428-245">The `ReadResult` can return the final segment of data when `IsCompleted` is set to `true`.</span></span> <span data-ttu-id="c2428-246">Si no se leen los datos antes de salir del bucle de lectura, se producirá una pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="c2428-246">Not reading that data before exiting the read loop will result in data loss.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="c2428-247">❌ **Bucle infinito**</span><span class="sxs-lookup"><span data-stu-id="c2428-247">❌ **Infinite loop**</span></span>

<span data-ttu-id="c2428-248">La lógica siguiente puede producir un bucle infinito si `Result.IsCompleted` es `true`, pero nunca hay un mensaje completo en el búfer.</span><span class="sxs-lookup"><span data-stu-id="c2428-248">The following logic may result in an infinite loop if the `Result.IsCompleted` is `true` but there's never a complete message in the buffer.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet2":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="c2428-249">Este es otro fragmento de código con el mismo problema.</span><span class="sxs-lookup"><span data-stu-id="c2428-249">Here's another piece of code with the same problem.</span></span> <span data-ttu-id="c2428-250">Está comprobando si hay un búfer no vacío antes de comprobar `ReadResult.IsCompleted`.</span><span class="sxs-lookup"><span data-stu-id="c2428-250">It's checking for a non-empty buffer before checking `ReadResult.IsCompleted`.</span></span> <span data-ttu-id="c2428-251">Dado que está en un elemento `else if`, se ejecutará en bucle para siempre si en el búfer no hay nunca un mensaje completo.</span><span class="sxs-lookup"><span data-stu-id="c2428-251">Because it's in an `else if`, it will loop forever if there's never a complete message in the buffer.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet3":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="c2428-252">❌ **Bloqueo inesperado**</span><span class="sxs-lookup"><span data-stu-id="c2428-252">❌ **Unexpected Hang**</span></span>

<span data-ttu-id="c2428-253">La llamada incondicional a `PipeReader.AdvanceTo`, con `buffer.End` en la posición `examined`, puede dar lugar a bloqueos al analizar un solo mensaje.</span><span class="sxs-lookup"><span data-stu-id="c2428-253">Unconditionally calling `PipeReader.AdvanceTo` with `buffer.End` in the `examined` position may result in hangs when parsing a single message.</span></span> <span data-ttu-id="c2428-254">La siguiente llamada a `PipeReader.AdvanceTo` no se devolverá hasta que:</span><span class="sxs-lookup"><span data-stu-id="c2428-254">The next call to `PipeReader.AdvanceTo` won't return until:</span></span>

* <span data-ttu-id="c2428-255">Haya más datos escritos en la canalización.</span><span class="sxs-lookup"><span data-stu-id="c2428-255">There's more data written to the pipe.</span></span>
* <span data-ttu-id="c2428-256">Y los nuevos datos no se hayan examinado previamente.</span><span class="sxs-lookup"><span data-stu-id="c2428-256">And the new data wasn't previously examined.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet4":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="c2428-257">❌ **Memoria insuficiente (OOM)**</span><span class="sxs-lookup"><span data-stu-id="c2428-257">❌ **Out of Memory (OOM)**</span></span>

<span data-ttu-id="c2428-258">Con las condiciones siguientes, el código siguiente mantiene el almacenamiento en búfer hasta que se produce <xref:System.OutOfMemoryException>:</span><span class="sxs-lookup"><span data-stu-id="c2428-258">With the following conditions, the following code keeps buffering until an <xref:System.OutOfMemoryException> occurs:</span></span>

* <span data-ttu-id="c2428-259">No hay tamaño máximo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c2428-259">There's no maximum message size.</span></span>
* <span data-ttu-id="c2428-260">Los datos que devuelve `PipeReader` no representan un mensaje completo.</span><span class="sxs-lookup"><span data-stu-id="c2428-260">The data returned from the `PipeReader` doesn't make a complete message.</span></span> <span data-ttu-id="c2428-261">Por ejemplo, no representa un mensaje completo porque el otro lado está escribiendo un mensaje de gran tamaño (por ejemplo, un mensaje de 4 GB).</span><span class="sxs-lookup"><span data-stu-id="c2428-261">For example, it doesn't make a complete message because the other side is writing a large message (For example, a 4-GB message).</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet5":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="c2428-262">❌ **Daño en la memoria**</span><span class="sxs-lookup"><span data-stu-id="c2428-262">❌ **Memory Corruption**</span></span>

<span data-ttu-id="c2428-263">Al escribir asistentes que lean el búfer, se debe copiar cualquier carga devuelta antes de llamar a `Advance`.</span><span class="sxs-lookup"><span data-stu-id="c2428-263">When writing helpers that read the buffer, any returned payload should be copied before calling `Advance`.</span></span> <span data-ttu-id="c2428-264">En el ejemplo siguiente se devolverá la memoria que ha descartado `Pipe` y se puede volver a usar para la siguiente operación (lectura/escritura).</span><span class="sxs-lookup"><span data-stu-id="c2428-264">The following example will return memory that the `Pipe` has discarded and may reuse it for the next operation (read/write).</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippetMessage":::

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet6":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

## <a name="pipewriter"></a><span data-ttu-id="c2428-265">PipeWriter</span><span class="sxs-lookup"><span data-stu-id="c2428-265">PipeWriter</span></span>

<span data-ttu-id="c2428-266"><xref:System.IO.Pipelines.PipeWriter> administra los búferes para escribir en nombre del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c2428-266">The <xref:System.IO.Pipelines.PipeWriter> manages buffers for writing on the caller's behalf.</span></span> <span data-ttu-id="c2428-267">`PipeWriter` implementa [`IBufferWriter<byte>`](xref:System.Buffers.IBufferWriter%601).</span><span class="sxs-lookup"><span data-stu-id="c2428-267">`PipeWriter` implements [`IBufferWriter<byte>`](xref:System.Buffers.IBufferWriter%601).</span></span> <span data-ttu-id="c2428-268">`IBufferWriter<byte>` permite obtener acceso a los búferes para realizar escrituras sin necesidad de tener copias de búfer adicionales.</span><span class="sxs-lookup"><span data-stu-id="c2428-268">`IBufferWriter<byte>` makes it possible to get access to buffers to perform writes without additional buffer copies.</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyPipeWriter.cs" id="snippet":::

<span data-ttu-id="c2428-269">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="c2428-269">The previous code:</span></span>

* <span data-ttu-id="c2428-270">Solicita un búfer de al menos 5 bytes de `PipeWriter` mediante <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2428-270">Requests a buffer of at least 5 bytes from the `PipeWriter` using <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A>.</span></span>
* <span data-ttu-id="c2428-271">Escribe bytes para la cadena ASCII `"Hello"` en el elemento devuelto `Memory<byte>`.</span><span class="sxs-lookup"><span data-stu-id="c2428-271">Writes bytes for the ASCII string `"Hello"` to the returned `Memory<byte>`.</span></span>
* <span data-ttu-id="c2428-272">Llama a <xref:System.IO.Pipelines.PipeWriter.Advance%2A> para indicar el número de bytes que se han escrito en el búfer.</span><span class="sxs-lookup"><span data-stu-id="c2428-272">Calls <xref:System.IO.Pipelines.PipeWriter.Advance%2A> to indicate how many bytes were written to the buffer.</span></span>
* <span data-ttu-id="c2428-273">Vacía `PipeWriter`, que envía los bytes al dispositivo subyacente.</span><span class="sxs-lookup"><span data-stu-id="c2428-273">Flushes the `PipeWriter`, which sends the bytes to the underlying device.</span></span>

<span data-ttu-id="c2428-274">El método de escritura anterior utiliza los búferes que proporciona `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="c2428-274">The previous method of writing uses the buffers provided by the `PipeWriter`.</span></span> <span data-ttu-id="c2428-275">O bien, <xref:System.IO.Pipelines.PipeWriter.WriteAsync%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="c2428-275">Alternatively, <xref:System.IO.Pipelines.PipeWriter.WriteAsync%2A?displayProperty=nameWithType>:</span></span>

* <span data-ttu-id="c2428-276">Copia el búfer existente en `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="c2428-276">Copies the existing buffer to the `PipeWriter`.</span></span>
* <span data-ttu-id="c2428-277">Llama a `GetSpan` o `Advance`, según corresponda, y llama a <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2428-277">Calls `GetSpan`, `Advance` as appropriate and calls <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A>.</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyPipeWriter.cs" id="snippet2":::

### <a name="cancellation"></a><span data-ttu-id="c2428-278">Cancelación</span><span class="sxs-lookup"><span data-stu-id="c2428-278">Cancellation</span></span>

<span data-ttu-id="c2428-279"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> admite pasar un elemento <xref:System.Threading.CancellationToken>.</span><span class="sxs-lookup"><span data-stu-id="c2428-279"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> supports passing a <xref:System.Threading.CancellationToken>.</span></span> <span data-ttu-id="c2428-280">Al pasar un elemento `CancellationToken`, se produce un elemento `OperationCanceledException` si el token se cancela mientras haya una operación de vaciado pendiente.</span><span class="sxs-lookup"><span data-stu-id="c2428-280">Passing a `CancellationToken` results in an `OperationCanceledException` if the token is canceled while there's a flush pending.</span></span> <span data-ttu-id="c2428-281">`PipeWriter.FlushAsync` admite una manera de cancelar la operación de vaciado actual a través de <xref:System.IO.Pipelines.PipeWriter.CancelPendingFlush%2A?displayProperty=nameWithType> sin que se produzca una excepción.</span><span class="sxs-lookup"><span data-stu-id="c2428-281">`PipeWriter.FlushAsync` supports a way to cancel the current flush operation via <xref:System.IO.Pipelines.PipeWriter.CancelPendingFlush%2A?displayProperty=nameWithType> without raising an exception.</span></span> <span data-ttu-id="c2428-282">La llamada a `PipeWriter.CancelPendingFlush` provoca que la llamada actual a `PipeWriter.FlushAsync` o a `PipeWriter.WriteAsync`, devuelva un elemento <xref:System.IO.Pipelines.FlushResult> con `IsCanceled` establecido en `true`.</span><span class="sxs-lookup"><span data-stu-id="c2428-282">Calling `PipeWriter.CancelPendingFlush` causes the current or next call to `PipeWriter.FlushAsync` or `PipeWriter.WriteAsync` to return a <xref:System.IO.Pipelines.FlushResult> with `IsCanceled` set to `true`.</span></span> <span data-ttu-id="c2428-283">Esto puede ser útil para detener el vaciado de retención de forma no destructiva y no excepcional.</span><span class="sxs-lookup"><span data-stu-id="c2428-283">This can be useful for halting the yielding flush in a non-destructive and non-exceptional way.</span></span>

<a name="pwcp"></a>

### <a name="pipewriter-common-problems"></a><span data-ttu-id="c2428-284">Problemas comunes de PipeWriter</span><span class="sxs-lookup"><span data-stu-id="c2428-284">PipeWriter common problems</span></span>

* <span data-ttu-id="c2428-285"><xref:System.IO.Pipelines.PipeWriter.GetSpan%2A> y <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> devuelven un búfer con, al menos, la cantidad de memoria solicitada.</span><span class="sxs-lookup"><span data-stu-id="c2428-285"><xref:System.IO.Pipelines.PipeWriter.GetSpan%2A> and <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> return a buffer with at least the requested amount of memory.</span></span> <span data-ttu-id="c2428-286">**No** asume tamaños de búfer exactos.</span><span class="sxs-lookup"><span data-stu-id="c2428-286">**Don't** assume exact buffer sizes.</span></span>
* <span data-ttu-id="c2428-287">No existe ninguna garantía de que las llamadas sucesivas devuelvan el mismo búfer o el mismo tamaño del búfer.</span><span class="sxs-lookup"><span data-stu-id="c2428-287">There's no guarantee that successive calls will return the same buffer or the same-sized buffer.</span></span>
* <span data-ttu-id="c2428-288">Se debe solicitar un nuevo búfer después de llamar a <xref:System.IO.Pipelines.PipeWriter.Advance%2A> para seguir escribiendo más datos.</span><span class="sxs-lookup"><span data-stu-id="c2428-288">A new buffer must be requested after calling <xref:System.IO.Pipelines.PipeWriter.Advance%2A> to continue writing more data.</span></span> <span data-ttu-id="c2428-289">No se puede escribir en el búfer adquirido previamente.</span><span class="sxs-lookup"><span data-stu-id="c2428-289">The previously acquired buffer can't be written to.</span></span>
* <span data-ttu-id="c2428-290">La llamada a `GetMemory` o a `GetSpan` no es segura mientras haya una llamada incompleta a `FlushAsync`.</span><span class="sxs-lookup"><span data-stu-id="c2428-290">Calling `GetMemory` or `GetSpan` while there's an incomplete call to `FlushAsync` isn't safe.</span></span>
* <span data-ttu-id="c2428-291">La llamada a `Complete` o a `CompleteAsync` puede provocar daños en la memoria mientras haya datos no vaciados.</span><span class="sxs-lookup"><span data-stu-id="c2428-291">Calling `Complete` or `CompleteAsync` while there's unflushed data can result in memory corruption.</span></span>

## <a name="iduplexpipe"></a><span data-ttu-id="c2428-292">IDuplexPipe</span><span class="sxs-lookup"><span data-stu-id="c2428-292">IDuplexPipe</span></span>

<span data-ttu-id="c2428-293"><xref:System.IO.Pipelines.IDuplexPipe> es un contrato para los tipos que admiten la lectura y la escritura.</span><span class="sxs-lookup"><span data-stu-id="c2428-293">The <xref:System.IO.Pipelines.IDuplexPipe> is a contract for types that support both reading and writing.</span></span> <span data-ttu-id="c2428-294">Por ejemplo, una conexión de red se representará mediante un elemento `IDuplexPipe`.</span><span class="sxs-lookup"><span data-stu-id="c2428-294">For example, a network connection would be represented by an `IDuplexPipe`.</span></span>

 <span data-ttu-id="c2428-295">A diferencia de `Pipe`, que contiene un elemento `PipeReader` y otro elemento `PipeWriter`, `IDuplexPipe` representa un solo lado de una conexión de dúplex completo.</span><span class="sxs-lookup"><span data-stu-id="c2428-295">Unlike `Pipe`, which contains a `PipeReader` and a `PipeWriter`, `IDuplexPipe` represents a single side of a full duplex connection.</span></span> <span data-ttu-id="c2428-296">Esto significa que lo que se escribe en `PipeWriter` no se leerá desde `PipeReader`.</span><span class="sxs-lookup"><span data-stu-id="c2428-296">That means what is written to the `PipeWriter` will not be read from the `PipeReader`.</span></span>

## <a name="streams"></a><span data-ttu-id="c2428-297">Secuencias</span><span class="sxs-lookup"><span data-stu-id="c2428-297">Streams</span></span>

<span data-ttu-id="c2428-298">Al leer o escribir datos de secuencia, normalmente se leen los datos mediante un deserializador y se escriben mediante un serializador.</span><span class="sxs-lookup"><span data-stu-id="c2428-298">When reading or writing stream data, you typically read data using a de-serializer and write data using a serializer.</span></span> <span data-ttu-id="c2428-299">La mayoría de estas API de secuencias de lectura y escritura tienen un parámetro `Stream`.</span><span class="sxs-lookup"><span data-stu-id="c2428-299">Most of these read and write stream APIs have a `Stream` parameter.</span></span> <span data-ttu-id="c2428-300">Para facilitar la integración con estas API existentes, `PipeReader` y `PipeWriter` exponen un método <xref:System.IO.Pipelines.PipeReader.AsStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2428-300">To make it easier to integrate with these existing APIs, `PipeReader` and `PipeWriter` expose an <xref:System.IO.Pipelines.PipeReader.AsStream%2A> method.</span></span> <span data-ttu-id="c2428-301"><xref:System.IO.Pipelines.PipeWriter.AsStream%2A> devuelve una implementación de `Stream` en torno a `PipeReader` o `PipeWriter`.</span><span class="sxs-lookup"><span data-stu-id="c2428-301"><xref:System.IO.Pipelines.PipeWriter.AsStream%2A> returns a `Stream` implementation around the `PipeReader` or `PipeWriter`.</span></span>

### <a name="stream-example"></a><span data-ttu-id="c2428-302">Ejemplos de secuencias</span><span class="sxs-lookup"><span data-stu-id="c2428-302">Stream example</span></span>

<span data-ttu-id="c2428-303">Las instancias de `PipeReader` y `PipeWriter` se pueden crear mediante los métodos `Create` estáticos dado un objeto <xref:System.IO.Stream> y las opciones de creación correspondientes.</span><span class="sxs-lookup"><span data-stu-id="c2428-303">`PipeReader` and `PipeWriter` instances can be created using the static `Create` methods given a <xref:System.IO.Stream> object and optional corresponding creation options.</span></span>

<span data-ttu-id="c2428-304"><xref:System.IO.Pipelines.StreamPipeReaderOptions> permite el control sobre la creación de la instancia de `PipeReader` con los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="c2428-304">The <xref:System.IO.Pipelines.StreamPipeReaderOptions> allow for control over the creation of the `PipeReader` instance with the following parameters:</span></span>

- <span data-ttu-id="c2428-305"><xref:System.IO.Pipelines.StreamPipeReaderOptions.BufferSize?displayProperty=nameWithType> es el tamaño de búfer mínimo en bytes que se usa al alquilar memoria del grupo y su valor predeterminado es `4096`.</span><span class="sxs-lookup"><span data-stu-id="c2428-305"><xref:System.IO.Pipelines.StreamPipeReaderOptions.BufferSize?displayProperty=nameWithType> is the minimum buffer size in bytes used when renting memory from the pool, and defaults to `4096`.</span></span>
- <span data-ttu-id="c2428-306">La marca <xref:System.IO.Pipelines.StreamPipeReaderOptions.LeaveOpen?displayProperty=nameWithType> determina si el flujo subyacente se deja abierto una vez finalizada la instancia de `PipeReader` y se establece de forma predeterminada en `false`.</span><span class="sxs-lookup"><span data-stu-id="c2428-306"><xref:System.IO.Pipelines.StreamPipeReaderOptions.LeaveOpen?displayProperty=nameWithType> flag determines whether or not the underlying stream is left open after the `PipeReader` completes, and defaults to `false`.</span></span>
- <span data-ttu-id="c2428-307"><xref:System.IO.Pipelines.StreamPipeReaderOptions.MinimumReadSize?displayProperty=nameWithType> representa el umbral de bytes restantes en el búfer antes de que se asigne un nuevo búfer y su valor predeterminado es `1024`.</span><span class="sxs-lookup"><span data-stu-id="c2428-307"><xref:System.IO.Pipelines.StreamPipeReaderOptions.MinimumReadSize?displayProperty=nameWithType> represents the threshold of remaining bytes in the buffer before a new buffer is allocated, and defaults to `1024`.</span></span>
- <span data-ttu-id="c2428-308"><xref:System.IO.Pipelines.StreamPipeReaderOptions.Pool?displayProperty=nameWithType> es el elemento `MemoryPool<byte>` que se usa al asignar memoria y el valor predeterminado es `null`.</span><span class="sxs-lookup"><span data-stu-id="c2428-308"><xref:System.IO.Pipelines.StreamPipeReaderOptions.Pool?displayProperty=nameWithType> is the `MemoryPool<byte>` used when allocating memory, and defaults to `null`.</span></span>

<span data-ttu-id="c2428-309"><xref:System.IO.Pipelines.StreamPipeWriterOptions> permite el control sobre la creación de la instancia de `PipeWriter` con los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="c2428-309">The <xref:System.IO.Pipelines.StreamPipeWriterOptions> allow for control over the creation of the `PipeWriter` instance with the following parameters:</span></span>

- <span data-ttu-id="c2428-310">La marca <xref:System.IO.Pipelines.StreamPipeWriterOptions.LeaveOpen?displayProperty=nameWithType> determina si el flujo subyacente se deja abierto una vez finalizada la instancia de `PipeWriter` y se establece de forma predeterminada en `false`.</span><span class="sxs-lookup"><span data-stu-id="c2428-310"><xref:System.IO.Pipelines.StreamPipeWriterOptions.LeaveOpen?displayProperty=nameWithType> flag determines whether or not the underlying stream is left open after the `PipeWriter` completes, and defaults to `false`.</span></span>
- <span data-ttu-id="c2428-311"><xref:System.IO.Pipelines.StreamPipeWriterOptions.MinimumBufferSize?displayProperty=nameWithType> representa el tamaño de búfer mínimo que se va a usar al alquilar memoria de <xref:System.IO.Pipelines.StreamPipeWriterOptions.Pool> y su valor predeterminado es `4096`.</span><span class="sxs-lookup"><span data-stu-id="c2428-311"><xref:System.IO.Pipelines.StreamPipeWriterOptions.MinimumBufferSize?displayProperty=nameWithType> represents the minimum buffer size to use when renting memory from the <xref:System.IO.Pipelines.StreamPipeWriterOptions.Pool>, and defaults to `4096`.</span></span>
- <span data-ttu-id="c2428-312"><xref:System.IO.Pipelines.StreamPipeWriterOptions.Pool?displayProperty=nameWithType> es el elemento `MemoryPool<byte>` que se usa al asignar memoria y el valor predeterminado es `null`.</span><span class="sxs-lookup"><span data-stu-id="c2428-312"><xref:System.IO.Pipelines.StreamPipeWriterOptions.Pool?displayProperty=nameWithType> is the `MemoryPool<byte>` used when allocating memory, and defaults to `null`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2428-313">Al crear instancias de `PipeReader` y `PipeWriter` mediante los métodos `Create`, debe tener en cuenta la duración del objeto `Stream`.</span><span class="sxs-lookup"><span data-stu-id="c2428-313">When creating `PipeReader` and `PipeWriter` instances using the `Create` methods, you need to consider the `Stream` object lifetime.</span></span> <span data-ttu-id="c2428-314">Si necesita tener acceso al flujo después de que el lector o el escritor hayan terminado con él, debe establecer la marca `LeaveOpen` en `true` en las opciones de creación.</span><span class="sxs-lookup"><span data-stu-id="c2428-314">If you need access to the stream after the reader or writer is done with it, you'll need to set the `LeaveOpen` flag to `true` on the creation options.</span></span> <span data-ttu-id="c2428-315">De lo contrario, el flujo se cerrará.</span><span class="sxs-lookup"><span data-stu-id="c2428-315">Otherwise, the stream will be closed.</span></span>

<span data-ttu-id="c2428-316">En el código siguiente se muestra la creación de instancias de `PipeReader` y `PipeWriter` mediante los métodos `Create` de un flujo.</span><span class="sxs-lookup"><span data-stu-id="c2428-316">The following code demonstrates the creation of `PipeReader` and `PipeWriter` instances using the `Create` methods from a stream.</span></span>

:::code language="csharp" source="snippets/pipelines/Program.cs":::

<span data-ttu-id="c2428-317">La aplicación utiliza un elemento <xref:System.IO.StreamReader> para leer el archivo *lorem-ipsum.txt* como un flujo.</span><span class="sxs-lookup"><span data-stu-id="c2428-317">The application uses a <xref:System.IO.StreamReader> to read the *lorem-ipsum.txt* file as a stream.</span></span> <span data-ttu-id="c2428-318"><xref:System.IO.FileStream> se pasa a <xref:System.IO.Pipelines.PipeReader.Create%2A?displayProperty=nameWithType>, que crea una instancia de un objeto `PipeReader`.</span><span class="sxs-lookup"><span data-stu-id="c2428-318">The <xref:System.IO.FileStream> is passed to <xref:System.IO.Pipelines.PipeReader.Create%2A?displayProperty=nameWithType>, which instantiates a `PipeReader` object.</span></span> <span data-ttu-id="c2428-319">Después, la aplicación de consola pasa su flujo de salida estándar a <xref:System.IO.Pipelines.PipeWriter.Create%2A?displayProperty=nameWithType> mediante <xref:System.Console.OpenStandardOutput?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c2428-319">The console application then passes its standard output stream to <xref:System.IO.Pipelines.PipeWriter.Create%2A?displayProperty=nameWithType> using <xref:System.Console.OpenStandardOutput?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c2428-320">El ejemplo admite la [cancelación](#cancellation).</span><span class="sxs-lookup"><span data-stu-id="c2428-320">The example supports [cancellation](#cancellation).</span></span>
