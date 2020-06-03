---
title: 'System.Buffers: .NET'
ms.date: 12/05/2019
ms.technology: dotnet-standard
helpviewer_keywords:
- buffers [.NET]
- I/O [.NET], buffers
author: rick-anderson
ms.author: riande
ms.openlocfilehash: d113def0182dc6a5bcea6c18b2d0e4b475946e31
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739623"
---
# <a name="work-with-buffers-in-net"></a><span data-ttu-id="f9ef1-102">Trabajo con búferes en .NET</span><span class="sxs-lookup"><span data-stu-id="f9ef1-102">Work with Buffers in .NET</span></span>

<span data-ttu-id="f9ef1-103">En este artículo se proporciona información general sobre los tipos que ayudan a leer datos que se ejecutan en varios búferes.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-103">This article provides an overview of types that help read data that runs across multiple buffers.</span></span> <span data-ttu-id="f9ef1-104">Se usan principalmente para la compatibilidad con objetos <xref:System.IO.Pipelines.PipeReader>.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-104">They're primarily used to support <xref:System.IO.Pipelines.PipeReader> objects.</span></span>

## <a name="ibufferwritert"></a><span data-ttu-id="f9ef1-105">IBufferWriter\<T\></span><span class="sxs-lookup"><span data-stu-id="f9ef1-105">IBufferWriter\<T\></span></span>

<span data-ttu-id="f9ef1-106"><xref:System.Buffers.IBufferWriter%601?displayProperty=fullName> es un contrato para la escritura sincrónica en búfer.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-106"><xref:System.Buffers.IBufferWriter%601?displayProperty=fullName> is a contract for synchronous buffered writing.</span></span> <span data-ttu-id="f9ef1-107">En el nivel más bajo, la interfaz:</span><span class="sxs-lookup"><span data-stu-id="f9ef1-107">At the lowest level, the interface:</span></span>

- <span data-ttu-id="f9ef1-108">Es básica y fácil de usar.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-108">Is basic and not difficult to use.</span></span>
- <span data-ttu-id="f9ef1-109">Permite el acceso a <xref:System.Memory%601> o <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-109">Allows access to a <xref:System.Memory%601> or <xref:System.Span%601>.</span></span> <span data-ttu-id="f9ef1-110">Es posible escribir en `Memory<T>` o `Span<T>` y se puede determinar cuántos elementos `T` se escribieron.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-110">The `Memory<T>` or `Span<T>` can be written to and you can determine how many `T` items were written.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet)]

<span data-ttu-id="f9ef1-111">El método anterior:</span><span class="sxs-lookup"><span data-stu-id="f9ef1-111">The preceding method:</span></span>

- <span data-ttu-id="f9ef1-112">Solicita un búfer de al menos 5 bytes de `IBufferWriter<byte>` mediante `GetSpan(5)`.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-112">Requests a buffer of at least 5 bytes from the `IBufferWriter<byte>` using `GetSpan(5)`.</span></span>
- <span data-ttu-id="f9ef1-113">Escribe los bytes de la cadena ASCII "Hola" en el elemento `Span<byte>` devuelto.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-113">Writes bytes for the ASCII string "Hello" to the returned `Span<byte>`.</span></span>
- <span data-ttu-id="f9ef1-114">Llama a <xref:System.Buffers.IBufferWriter%601> para indicar el número de bytes que se escribieron en el búfer.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-114">Calls  <xref:System.Buffers.IBufferWriter%601> to indicate how many bytes were written to the buffer.</span></span>

<span data-ttu-id="f9ef1-115">Este método de escritura usa el búfer `Memory<T>`/`Span<T>` proporcionado por `IBufferWriter<T>`.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-115">This method of writing uses the `Memory<T>`/`Span<T>` buffer provided by the `IBufferWriter<T>`.</span></span> <span data-ttu-id="f9ef1-116">Como alternativa, se puede usar el método de extensión <xref:System.Buffers.BuffersExtensions.Write%2A> para copiar un búfer existente en `IBufferWriter<T>`.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-116">Alternatively, the <xref:System.Buffers.BuffersExtensions.Write%2A> extension method can be used to copy an existing buffer to the `IBufferWriter<T>`.</span></span> <span data-ttu-id="f9ef1-117">`Write` realiza el trabajo de llamar a `GetSpan`/`Advance` según sea necesario, por lo que no hace falta llamar a `Advance` después de escribir:</span><span class="sxs-lookup"><span data-stu-id="f9ef1-117">`Write` does the work of calling `GetSpan`/`Advance` as appropriate, so there's no need to call `Advance` after writing:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet2)]

<span data-ttu-id="f9ef1-118"><xref:System.Buffers.ArrayBufferWriter%601> es una implementación de `IBufferWriter<T>` cuya memoria auxiliar es una sola matriz contigua.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-118"><xref:System.Buffers.ArrayBufferWriter%601> is an implementation of `IBufferWriter<T>` whose backing store is a single contiguous array.</span></span>

### <a name="ibufferwriter-common-problems"></a><span data-ttu-id="f9ef1-119">Problemas comunes de IBufferWriter</span><span class="sxs-lookup"><span data-stu-id="f9ef1-119">IBufferWriter common problems</span></span>

- <span data-ttu-id="f9ef1-120">`GetSpan` y `GetMemory` devuelven un búfer con, al menos, la cantidad de memoria solicitada.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-120">`GetSpan` and `GetMemory` return a buffer with at least the requested amount of memory.</span></span> <span data-ttu-id="f9ef1-121">No asume tamaños de búfer exactos.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-121">Don't assume exact buffer sizes.</span></span>
- <span data-ttu-id="f9ef1-122">No existe ninguna garantía de que las llamadas sucesivas devuelvan el mismo búfer o el mismo tamaño del búfer.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-122">There's no guarantee that successive calls will return the same buffer or the same-sized buffer.</span></span>
- <span data-ttu-id="f9ef1-123">Se debe solicitar un nuevo búfer después de llamar a `Advance` para seguir escribiendo más datos.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-123">A new buffer must be requested after calling `Advance` to continue writing more data.</span></span> <span data-ttu-id="f9ef1-124">No se puede escribir en un búfer adquirido previamente después de llamar a `Advance`.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-124">A previously acquired buffer cannot be written to after `Advance` has been called.</span></span>

## <a name="readonlysequencet"></a><span data-ttu-id="f9ef1-125">ReadOnlySequence\<T\></span><span class="sxs-lookup"><span data-stu-id="f9ef1-125">ReadOnlySequence\<T\></span></span>

![ReadOnlySequence que muestra la memoria de la canalización y debajo la posición de esa secuencia de memoria de solo lectura](media/buffers/ro-sequence.png)

<span data-ttu-id="f9ef1-127"><xref:System.Buffers.ReadOnlySequence%601> es una estructura que puede representar una secuencia de `T` contigua o no contigua.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-127"><xref:System.Buffers.ReadOnlySequence%601> is a struct that can represent a contiguous or noncontiguous sequence of `T`.</span></span> <span data-ttu-id="f9ef1-128">Se puede construir a partir de:</span><span class="sxs-lookup"><span data-stu-id="f9ef1-128">It can be constructed from:</span></span>

1. <span data-ttu-id="f9ef1-129">`T[]`.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-129">A `T[]`</span></span>
1. <span data-ttu-id="f9ef1-130">`ReadOnlyMemory<T>`.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-130">A `ReadOnlyMemory<T>`</span></span>
1. <span data-ttu-id="f9ef1-131">Un par de nodos de lista vinculados <xref:System.Buffers.ReadOnlySequenceSegment%601> y el índice para representar la posición inicial y final de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-131">A pair of linked list node <xref:System.Buffers.ReadOnlySequenceSegment%601> and index to represent the start and end position of the sequence.</span></span>

<span data-ttu-id="f9ef1-132">La tercera representación es la más interesante, ya que tiene implicaciones para el rendimiento en varias operaciones en `ReadOnlySequence<T>`:</span><span class="sxs-lookup"><span data-stu-id="f9ef1-132">The third representation is the most interesting one as it has performance implications on various operations on the `ReadOnlySequence<T>`:</span></span>

|<span data-ttu-id="f9ef1-133">Representación</span><span class="sxs-lookup"><span data-stu-id="f9ef1-133">Representation</span></span>|<span data-ttu-id="f9ef1-134">Operación</span><span class="sxs-lookup"><span data-stu-id="f9ef1-134">Operation</span></span>|<span data-ttu-id="f9ef1-135">Complejidad</span><span class="sxs-lookup"><span data-stu-id="f9ef1-135">Complexity</span></span>|
---|---|---|
|`T[]`/`ReadOnlyMemory<T>`|`Length`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`GetPosition(long)`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`Slice(int, int)`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`Slice(SequencePostion,  SequencePostion)`|`O(1)`|
|`ReadOnlySequenceSegment<T>`|`Length`|`O(1)`|
|`ReadOnlySequenceSegment<T>`|`GetPosition(long)`|`O(number of segments)`|
|`ReadOnlySequenceSegment<T>`|`Slice(int, int)`|`O(number of segments)`|
|`ReadOnlySequenceSegment<T>`|`Slice(SequencePostion, SequencePostion)`|`O(1)`|

<span data-ttu-id="f9ef1-136">Debido a esta representación mixta, `ReadOnlySequence<T>` expone los índices como `SequencePosition` en lugar de un entero.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-136">Because of this mixed representation, the `ReadOnlySequence<T>` exposes indexes as `SequencePosition` instead of an integer.</span></span> <span data-ttu-id="f9ef1-137">`SequencePosition`:</span><span class="sxs-lookup"><span data-stu-id="f9ef1-137">A `SequencePosition`:</span></span>

- <span data-ttu-id="f9ef1-138">es un valor opaco que representa un índice en la estructura `ReadOnlySequence<T>` donde se originó.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-138">Is an opaque value that represents an index into the `ReadOnlySequence<T>` where it originated.</span></span>
- <span data-ttu-id="f9ef1-139">Consta de dos partes: un entero y un objeto.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-139">Consists of two parts, an integer and an object.</span></span> <span data-ttu-id="f9ef1-140">Estos dos valores representan que están asociados a la implementación de `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-140">What these two values represent are tied to the implementation of `ReadOnlySequence<T>`.</span></span>

### <a name="access-data"></a><span data-ttu-id="f9ef1-141">Acceder a datos</span><span class="sxs-lookup"><span data-stu-id="f9ef1-141">Access data</span></span>

<span data-ttu-id="f9ef1-142">`ReadOnlySequence<T>` expone los datos como un valor enumerable de `ReadOnlyMemory<T>`.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-142">The `ReadOnlySequence<T>` exposes data as an enumerable of `ReadOnlyMemory<T>`.</span></span> <span data-ttu-id="f9ef1-143">La enumeración de cada uno de los segmentos puede realizarse mediante una instrucción foreach básica:</span><span class="sxs-lookup"><span data-stu-id="f9ef1-143">Enumerating each of the segments can be done using a basic foreach:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet3)]

<span data-ttu-id="f9ef1-144">El método anterior busca un byte específico en cada segmento.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-144">The preceding method searches each segment for a specific byte.</span></span> <span data-ttu-id="f9ef1-145">Si necesita realizar un seguimiento del valor `SequencePosition` de cada segmento, es más adecuado <xref:System.Buffers.ReadOnlySequence%601.TryGet%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-145">If you need to keep track of each segment's `SequencePosition`, <xref:System.Buffers.ReadOnlySequence%601.TryGet%2A?displayProperty=nameWithType> is more appropriate.</span></span> <span data-ttu-id="f9ef1-146">En el ejemplo siguiente se cambia el código anterior para devolver `SequencePosition` en lugar de un entero.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-146">The next sample changes the preceding code to return a `SequencePosition` instead of an integer.</span></span> <span data-ttu-id="f9ef1-147">Devolver `SequencePosition` tiene la ventaja de permitir que el autor de la llamada evite un segundo examen para obtener los datos en un índice específico.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-147">Returning a `SequencePosition` has the benefit of allowing the caller to avoid a second scan to get the data at a specific index.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet4)]

<span data-ttu-id="f9ef1-148">La combinación de `SequencePosition` y `TryGet` actúa como enumerador.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-148">The combination of `SequencePosition` and `TryGet` acts like an enumerator.</span></span> <span data-ttu-id="f9ef1-149">El campo de posición se modifica al principio de cada iteración para que sea el inicio de cada segmento dentro de `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-149">The position field is modified at the start of each iteration to be start of each segment within the `ReadOnlySequence<T>`.</span></span>

<span data-ttu-id="f9ef1-150">El método anterior existe como método de extensión en `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-150">The preceding method exists as an extension method on `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="f9ef1-151"><xref:System.Buffers.BuffersExtensions.PositionOf%2A> se puede usar para simplificar el código anterior:</span><span class="sxs-lookup"><span data-stu-id="f9ef1-151"><xref:System.Buffers.BuffersExtensions.PositionOf%2A> can be used to simplify the preceding code:</span></span>

```csharp
SequencePosition? FindIndexOf(in ReadOnlySequence<byte> buffer, byte data) => buffer.PositionOf(data);
```

#### <a name="process-a-readonlysequencet"></a><span data-ttu-id="f9ef1-152">Procesamiento de ReadOnlySequence\<T\></span><span class="sxs-lookup"><span data-stu-id="f9ef1-152">Process a ReadOnlySequence\<T\></span></span>

<span data-ttu-id="f9ef1-153">El procesamiento de `ReadOnlySequence<T>` puede ser difícil, dado que los datos podrían estar divididos en varios segmentos dentro de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-153">Processing a `ReadOnlySequence<T>` can be challenging since data may be split across multiple segments within the sequence.</span></span> <span data-ttu-id="f9ef1-154">Para obtener el mejor rendimiento, divida el código en dos rutas de acceso:</span><span class="sxs-lookup"><span data-stu-id="f9ef1-154">For the best performance, split code into two paths:</span></span>

- <span data-ttu-id="f9ef1-155">Una ruta de acceso rápida que se ocupa del caso de un único segmento.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-155">A fast path that deals with the single segment case.</span></span>
- <span data-ttu-id="f9ef1-156">Una ruta de acceso lenta que se ocupa de la división de los datos entre segmentos.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-156">A slow path that deals with the data split across segments.</span></span>

<span data-ttu-id="f9ef1-157">Existen varios enfoques que se pueden usar para procesar datos en secuencias de varios segmentos:</span><span class="sxs-lookup"><span data-stu-id="f9ef1-157">There are a few approaches that can be used to process data in multi-segmented sequences:</span></span>

- <span data-ttu-id="f9ef1-158">Usar [`SequenceReader<T>`](#sequencereadert).</span><span class="sxs-lookup"><span data-stu-id="f9ef1-158">Use the [`SequenceReader<T>`](#sequencereadert).</span></span>
- <span data-ttu-id="f9ef1-159">Analizar el segmento de datos por segmento y mantener el seguimiento de `SequencePosition` y del índice dentro del segmento analizado.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-159">Parse data segment by segment, keeping track of the `SequencePosition` and index within the segment parsed.</span></span> <span data-ttu-id="f9ef1-160">De esta forma, se evitan asignaciones innecesarias, aunque puede ser ineficaz, especialmente en el caso de búferes pequeños.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-160">This avoids unnecessary allocations but may be inefficient, especially for small buffers.</span></span>
- <span data-ttu-id="f9ef1-161">Copiar `ReadOnlySequence<T>` en una matriz contigua y tratarla como un solo búfer:</span><span class="sxs-lookup"><span data-stu-id="f9ef1-161">Copy the `ReadOnlySequence<T>` to a contiguous array and treat it like a single buffer:</span></span>
  - <span data-ttu-id="f9ef1-162">Si el tamaño de `ReadOnlySequence<T>` es pequeño, puede ser razonable copiar los datos en un búfer asignado por la pila mediante el operador [stackalloc](../../csharp/language-reference/operators/stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="f9ef1-162">If the size of the `ReadOnlySequence<T>` is small, it may be reasonable to copy the data into a stack-allocated buffer using the [stackalloc](../../csharp/language-reference/operators/stackalloc.md) operator.</span></span>
  - <span data-ttu-id="f9ef1-163">Copie `ReadOnlySequence<T>` en una matriz agrupada mediante <xref:System.Buffers.ArrayPool%601.Shared%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-163">Copy the `ReadOnlySequence<T>` into a pooled array using <xref:System.Buffers.ArrayPool%601.Shared%2A?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="f9ef1-164">Utilice [`ReadOnlySequence<T>.ToArray()`](xref:System.Buffers.BuffersExtensions.ToArray%2A).</span><span class="sxs-lookup"><span data-stu-id="f9ef1-164">Use [`ReadOnlySequence<T>.ToArray()`](xref:System.Buffers.BuffersExtensions.ToArray%2A).</span></span> <span data-ttu-id="f9ef1-165">Este método no se recomienda en las rutas de acceso activas, ya que asigna un nuevo elemento `T[]` en el montón.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-165">This isn't recommended in hot paths as it allocates a new `T[]` on the heap.</span></span>

<span data-ttu-id="f9ef1-166">En los siguientes ejemplos se muestran algunos casos comunes de procesamiento de `ReadOnlySequence<byte>`:</span><span class="sxs-lookup"><span data-stu-id="f9ef1-166">The following examples demonstrate some common cases for processing `ReadOnlySequence<byte>`:</span></span>

##### <a name="process-binary-data"></a><span data-ttu-id="f9ef1-167">Procesamiento de datos binarios</span><span class="sxs-lookup"><span data-stu-id="f9ef1-167">Process binary data</span></span>

<span data-ttu-id="f9ef1-168">En el siguiente ejemplo se analiza una longitud de entero bid endian de 4 bytes desde el inicio de `ReadOnlySequence<byte>`.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-168">The following example parses a 4-byte big-endian integer length from the start of the `ReadOnlySequence<byte>`.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet5)]

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

##### <a name="process-text-data"></a><span data-ttu-id="f9ef1-169">Procesamiento de datos de texto</span><span class="sxs-lookup"><span data-stu-id="f9ef1-169">Process text data</span></span>

<span data-ttu-id="f9ef1-170">En el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f9ef1-170">The following example:</span></span>

- <span data-ttu-id="f9ef1-171">Encuentra la primera línea nueva (`\r\n`) en `ReadOnlySequence<byte>` y la devuelve mediante el parámetro "line" de salida.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-171">Finds the first newline (`\r\n`) in the `ReadOnlySequence<byte>` and returns it via the out 'line' parameter.</span></span>
- <span data-ttu-id="f9ef1-172">Recorta esa línea, sin incluir `\r\n` del búfer de entrada.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-172">Trims that line, excluding the `\r\n` from the input buffer.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet6)]

##### <a name="empty-segments"></a><span data-ttu-id="f9ef1-173">Segmentos vacíos</span><span class="sxs-lookup"><span data-stu-id="f9ef1-173">Empty segments</span></span>

<span data-ttu-id="f9ef1-174">Es válido almacenar segmentos vacíos dentro de `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-174">It's valid to store empty segments inside of a `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="f9ef1-175">Pueden aparecer segmentos vacíos mientras se enumeran los segmentos de manera explícita:</span><span class="sxs-lookup"><span data-stu-id="f9ef1-175">Empty segments may occur while enumerating segments explicitly:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet7)]

<span data-ttu-id="f9ef1-176">El código anterior crea una estructura `ReadOnlySequence<byte>` con segmentos vacíos y muestra cómo afectan estos a las distintas API:</span><span class="sxs-lookup"><span data-stu-id="f9ef1-176">The preceding code creates a `ReadOnlySequence<byte>` with empty segments and shows how those empty segments affect the various APIs:</span></span>

- <span data-ttu-id="f9ef1-177">`ReadOnlySequence<T>.Slice` con un valor `SequencePosition` que apunta a un segmento vacío conserva ese segmento.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-177">`ReadOnlySequence<T>.Slice` with a `SequencePosition` pointing to an empty segment preserves that segment.</span></span>
- <span data-ttu-id="f9ef1-178">`ReadOnlySequence<T>.Slice` con un valor entero omite los segmentos vacíos.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-178">`ReadOnlySequence<T>.Slice` with an int skips over the empty segments.</span></span>
- <span data-ttu-id="f9ef1-179">Al enumerar `ReadOnlySequence<T>`, se enumeran los segmentos vacíos.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-179">Enumerating the `ReadOnlySequence<T>` enumerates the empty segments.</span></span>

### <a name="potential-problems-with-readonlysequencet-and-sequenceposition"></a><span data-ttu-id="f9ef1-180">Posibles problemas con ReadOnlySequence\<T > y SequencePosition</span><span class="sxs-lookup"><span data-stu-id="f9ef1-180">Potential problems with ReadOnlySequence\<T> and SequencePosition</span></span>

<span data-ttu-id="f9ef1-181">Hay varios resultados inusuales cuando se trabaja con `ReadOnlySequence<T>`/`SequencePosition` frente a una representación `ReadOnlySpan<T>`normal /`ReadOnlyMemory<T>`/`T[]`/`int`:</span><span class="sxs-lookup"><span data-stu-id="f9ef1-181">There are several unusual outcomes when dealing with a `ReadOnlySequence<T>`/`SequencePosition` vs. a normal `ReadOnlySpan<T>`/`ReadOnlyMemory<T>`/`T[]`/`int`:</span></span>

- <span data-ttu-id="f9ef1-182">`SequencePosition` es un marcador de posición para una estructura `ReadOnlySequence<T>` específica, no una posición absoluta.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-182">`SequencePosition` is a position marker for a specific `ReadOnlySequence<T>`, not an absolute position.</span></span> <span data-ttu-id="f9ef1-183">Dado que es relativo a una estructura `ReadOnlySequence<T>` específica, no tiene ningún significado si se usa fuera de la estructura `ReadOnlySequence<T>` donde se origina.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-183">Because it's relative to a specific `ReadOnlySequence<T>`, it doesn't have meaning if used outside of the `ReadOnlySequence<T>` where it originated.</span></span>
- <span data-ttu-id="f9ef1-184">No se pueden realizar operaciones aritméticas en `SequencePosition` sin `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-184">Arithmetic can't be performed on `SequencePosition` without the `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="f9ef1-185">Eso significa que hacer cosas básicas, como `position++`, se escribe `ReadOnlySequence<T>.GetPosition(position, 1)`.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-185">That means doing basic things like `position++` is written `ReadOnlySequence<T>.GetPosition(position, 1)`.</span></span>
- <span data-ttu-id="f9ef1-186">`GetPosition(long)`**no** admite índices negativos.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-186">`GetPosition(long)` does **not** support negative indexes.</span></span> <span data-ttu-id="f9ef1-187">Esto significa que es imposible obtener del segundo al último carácter sin recorrer todos los segmentos.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-187">That means it's impossible to get the second to last character without walking all segments.</span></span>
- <span data-ttu-id="f9ef1-188">No se pueden comparar dos valores `SequencePosition`, lo que dificulta:</span><span class="sxs-lookup"><span data-stu-id="f9ef1-188">Two `SequencePosition` can't be compared, making it difficult to:</span></span>
  - <span data-ttu-id="f9ef1-189">Saber si una posición es mayor o menor que otra.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-189">Know if one position is greater than or less than another position.</span></span>
  - <span data-ttu-id="f9ef1-190">Escribir algunos algoritmos de análisis.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-190">Write some parsing algorithms.</span></span>
- <span data-ttu-id="f9ef1-191">`ReadOnlySequence<T>` es mayor que una referencia de objeto y debe pasarse mediante [in](../../csharp/language-reference/keywords/in-parameter-modifier.md) o [ref](../../csharp/language-reference/keywords/ref.md) siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-191">`ReadOnlySequence<T>` is bigger than an object reference and should be passed by [in](../../csharp/language-reference/keywords/in-parameter-modifier.md) or [ref](../../csharp/language-reference/keywords/ref.md) where possible.</span></span> <span data-ttu-id="f9ef1-192">Pasar `ReadOnlySequence<T>` mediante `in` o `ref` reduce las copias de la [estructura](../../csharp/language-reference/builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="f9ef1-192">Passing `ReadOnlySequence<T>` by `in` or `ref` reduces copies of the [struct](../../csharp/language-reference/builtin-types/struct.md).</span></span>
- <span data-ttu-id="f9ef1-193">Segmentos vacíos:</span><span class="sxs-lookup"><span data-stu-id="f9ef1-193">Empty segments:</span></span>
  - <span data-ttu-id="f9ef1-194">Son válidos dentro de `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-194">Are valid within a `ReadOnlySequence<T>`.</span></span>
  - <span data-ttu-id="f9ef1-195">Pueden aparecer cuando se recorre en iteración mediante el método `ReadOnlySequence<T>.TryGet`.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-195">Can appear when iterating using the `ReadOnlySequence<T>.TryGet` method.</span></span>
  - <span data-ttu-id="f9ef1-196">Pueden aparecer segmentando la secuencia mediante el método `ReadOnlySequence<T>.Slice()` con objetos `SequencePosition`.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-196">Can appear slicing the sequence using the `ReadOnlySequence<T>.Slice()` method with `SequencePosition` objects.</span></span>

## <a name="sequencereadert"></a><span data-ttu-id="f9ef1-197">SequenceReader\<T\></span><span class="sxs-lookup"><span data-stu-id="f9ef1-197">SequenceReader\<T\></span></span>

<span data-ttu-id="f9ef1-198"><xref:System.Buffers.SequenceReader%601>:</span><span class="sxs-lookup"><span data-stu-id="f9ef1-198"><xref:System.Buffers.SequenceReader%601>:</span></span>

- <span data-ttu-id="f9ef1-199">Es un nuevo tipo que se presentó en .NET Core 3.0 para simplificar el procesamiento de `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-199">Is a new type that was introduced in .NET Core 3.0 to simplify the processing of a `ReadOnlySequence<T>`.</span></span>
- <span data-ttu-id="f9ef1-200">Unifica las diferencias entre un solo segmento `ReadOnlySequence<T>` y varios segmentos `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-200">Unifies the differences between a single segment `ReadOnlySequence<T>` and multi-segment `ReadOnlySequence<T>`.</span></span>
- <span data-ttu-id="f9ef1-201">Proporciona asistentes para leer datos binarios y de texto (`byte` y `char`) que podrían estar o no divididos entre segmentos.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-201">Provides helpers for reading binary and text data (`byte` and `char`) that may or may not be split across segments.</span></span>

<span data-ttu-id="f9ef1-202">Existen métodos integrados que se ocupan del procesamiento de datos binarios y delimitados.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-202">There are built-in methods for dealing with processing both binary and delimited data.</span></span> <span data-ttu-id="f9ef1-203">En la siguiente sección se muestra el aspecto de esos mismos métodos con `SequenceReader<T>`:</span><span class="sxs-lookup"><span data-stu-id="f9ef1-203">The following section demonstrates what those same methods look like with the `SequenceReader<T>`:</span></span>

### <a name="access-data"></a><span data-ttu-id="f9ef1-204">Acceder a datos</span><span class="sxs-lookup"><span data-stu-id="f9ef1-204">Access data</span></span>

<span data-ttu-id="f9ef1-205">`SequenceReader<T>` tiene métodos para enumerar datos dentro de `ReadOnlySequence<T>` directamente.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-205">`SequenceReader<T>` has methods for enumerating data inside of the `ReadOnlySequence<T>` directly.</span></span> <span data-ttu-id="f9ef1-206">El código siguiente es un ejemplo de procesamiento de `ReadOnlySequence<byte>` un `byte` cada vez:</span><span class="sxs-lookup"><span data-stu-id="f9ef1-206">The following code is an example of processing a `ReadOnlySequence<byte>` a `byte` at a time:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet8)]

<span data-ttu-id="f9ef1-207">`CurrentSpan` expone el valor `Span` del segmento actual, que es similar a lo que se hizo en el método manualmente.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-207">The `CurrentSpan` exposes the current segment's `Span`, which is similar to what was done in the method manually.</span></span>

### <a name="use-position"></a><span data-ttu-id="f9ef1-208">Uso de la posición</span><span class="sxs-lookup"><span data-stu-id="f9ef1-208">Use position</span></span>

<span data-ttu-id="f9ef1-209">El código siguiente es un ejemplo de implementación de `FindIndexOf` mediante `SequenceReader<T>`.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-209">The following code is an example implementation of `FindIndexOf` using the `SequenceReader<T>`:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet9)]

### <a name="process-binary-data"></a><span data-ttu-id="f9ef1-210">Procesamiento de datos binarios</span><span class="sxs-lookup"><span data-stu-id="f9ef1-210">Process binary data</span></span>

<span data-ttu-id="f9ef1-211">En el siguiente ejemplo se analiza una longitud de entero bid endian de 4 bytes desde el inicio de `ReadOnlySequence<byte>`.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-211">The following example parses a 4-byte big-endian integer length from the start of the `ReadOnlySequence<byte>`.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet11)]

### <a name="process-text-data"></a><span data-ttu-id="f9ef1-212">Procesamiento de datos de texto</span><span class="sxs-lookup"><span data-stu-id="f9ef1-212">Process text data</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet10)]

### <a name="sequencereadert-common-problems"></a><span data-ttu-id="f9ef1-213">Problemas comunes de SequenceReader\<T\></span><span class="sxs-lookup"><span data-stu-id="f9ef1-213">SequenceReader\<T\> common problems</span></span>

- <span data-ttu-id="f9ef1-214">Dado que `SequenceReader<T>` es una estructura mutable, siempre debe pasarse mediante una [referencia](../../csharp/language-reference/keywords/ref.md).</span><span class="sxs-lookup"><span data-stu-id="f9ef1-214">Because `SequenceReader<T>` is a mutable struct, it should always be passed by [reference](../../csharp/language-reference/keywords/ref.md).</span></span>
- <span data-ttu-id="f9ef1-215">`SequenceReader<T>` es una [estructura de referencia](../../csharp/language-reference/builtin-types/struct.md#ref-struct), de modo que solo se puede usar en métodos sincrónicos y no se puede almacenar en campos.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-215">`SequenceReader<T>` is a [ref struct](../../csharp/language-reference/builtin-types/struct.md#ref-struct) so it can only be used in synchronous methods and can't be stored in fields.</span></span> <span data-ttu-id="f9ef1-216">Para más información, consulte [Escritura de código C# seguro y eficaz](../../csharp/write-safe-efficient-code.md).</span><span class="sxs-lookup"><span data-stu-id="f9ef1-216">For more information, see [Write safe and efficient C# code](../../csharp/write-safe-efficient-code.md).</span></span>
- <span data-ttu-id="f9ef1-217">`SequenceReader<T>` está optimizado para su uso como lector de solo avance.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-217">`SequenceReader<T>` is optimized for use as a forward-only reader.</span></span> <span data-ttu-id="f9ef1-218">`Rewind` está destinado a copias de seguridad pequeñas que no se pueden abordar mediante otras API de `Read`, `Peek` y `IsNext`.</span><span class="sxs-lookup"><span data-stu-id="f9ef1-218">`Rewind` is intended for small backups that can't be addressed utilizing other `Read`, `Peek`, and `IsNext` APIs.</span></span>
