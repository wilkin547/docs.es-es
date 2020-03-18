---
title: 'System.Buffers: .NET'
ms.date: 12/05/2019
ms.technology: dotnet-standard
helpviewer_keywords:
- buffers [.NET]
- I/O [.NET], buffers
author: rick-anderson
ms.author: riande
ms.openlocfilehash: f939164cd56b2fb2feeeb171236b0e1171327e19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160123"
---
# <a name="work-with-buffers-in-net"></a>Trabajo con búferes en .NET

En este artículo se proporciona información general sobre los tipos que ayudan a leer datos que se ejecutan en varios búferes. Se usan principalmente para la compatibilidad con objetos <xref:System.IO.Pipelines.PipeReader>.

## <a name="ibufferwritert"></a>IBufferWriter\<T\>

<xref:System.Buffers.IBufferWriter%601?displayProperty=fullName> es un contrato para la escritura sincrónica en búfer. En el nivel más bajo, la interfaz:

- Es básica y fácil de usar.
- Permite el acceso a <xref:System.Memory%601> o <xref:System.Span%601>. Es posible escribir en `Memory<T>` o `Span<T>` y se puede determinar cuántos elementos `T` se escribieron.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet)]

El método anterior:

- Solicita un búfer de al menos 5 bytes de `IBufferWriter<byte>` mediante `GetSpan(5)`.
- Escribe los bytes de la cadena ASCII "Hola" en el elemento `Span<byte>` devuelto.
- Llama a <xref:System.Buffers.IBufferWriter%601> para indicar el número de bytes que se escribieron en el búfer.

Este método de escritura usa el búfer `Memory<T>`/`Span<T>` proporcionado por `IBufferWriter<T>`. Como alternativa, se puede usar el método de extensión <xref:System.Buffers.BuffersExtensions.Write%2A> para copiar un búfer existente en `IBufferWriter<T>`. `Write` realiza el trabajo de llamar a `GetSpan`/`Advance` según sea necesario, por lo que no hace falta llamar a `Advance` después de escribir:

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet2)]

<xref:System.Buffers.ArrayBufferWriter%601> es una implementación de `IBufferWriter<T>` cuya memoria auxiliar es una sola matriz contigua.

### <a name="ibufferwriter-common-problems"></a>Problemas comunes de IBufferWriter

- `GetSpan` y `GetMemory` devuelven un búfer con, al menos, la cantidad de memoria solicitada. No asume tamaños de búfer exactos.
- No existe ninguna garantía de que las llamadas sucesivas devuelvan el mismo búfer o el mismo tamaño del búfer.
- Se debe solicitar un nuevo búfer después de llamar a `Advance` para seguir escribiendo más datos. No se puede escribir en un búfer adquirido previamente después de llamar a `Advance`.

## <a name="readonlysequencet"></a>ReadOnlySequence\<T\>

![ReadOnlySequence que muestra la memoria de la canalización y debajo la posición de esa secuencia de memoria de solo lectura](media/buffers/ro-sequence.png)

<xref:System.Buffers.ReadOnlySequence%601> es una estructura que puede representar una secuencia de `T` contigua o no contigua. Se puede construir a partir de:

1. `T[]`.
1. `ReadOnlyMemory<T>`.
1. Un par de nodos de lista vinculados <xref:System.Buffers.ReadOnlySequenceSegment%601> y el índice para representar la posición inicial y final de la secuencia.

La tercera representación es la más interesante, ya que tiene implicaciones para el rendimiento en varias operaciones en `ReadOnlySequence<T>`:

|Representación|Operación|Complejidad|
---|---|---|
|`T[]`/`ReadOnlyMemory<T>`|`Length`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`GetPosition(long)`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`Slice(int, int)`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`Slice(SequencePostion,  SequencePostion)`|`O(1)`|
|`ReadOnlySequenceSegment<T>`|`Length`|`O(1)`|
|`ReadOnlySequenceSegment<T>`|`GetPosition(long)`|`O(number of segments)`|
|`ReadOnlySequenceSegment<T>`|`Slice(int, int)`|`O(number of segments)`|
|`ReadOnlySequenceSegment<T>`|`Slice(SequencePostion, SequencePostion)`|`O(1)`|

Debido a esta representación mixta, `ReadOnlySequence<T>` expone los índices como `SequencePosition` en lugar de un entero. `SequencePosition`:

- es un valor opaco que representa un índice en la estructura `ReadOnlySequence<T>` donde se originó.
- Consta de dos partes: un entero y un objeto. Estos dos valores representan que están asociados a la implementación de `ReadOnlySequence<T>`.

### <a name="access-data"></a>Acceder a datos

`ReadOnlySequence<T>` expone los datos como un valor enumerable de `ReadOnlyMemory<T>`. La enumeración de cada uno de los segmentos puede realizarse mediante una instrucción foreach básica:

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet3)]

El método anterior busca un byte específico en cada segmento. Si necesita realizar un seguimiento del valor `SequencePosition` de cada segmento, es más adecuado <xref:System.Buffers.ReadOnlySequence%601.TryGet%2A?displayProperty=nameWithType>. En el ejemplo siguiente se cambia el código anterior para devolver `SequencePosition` en lugar de un entero. Devolver `SequencePosition` tiene la ventaja de permitir que el autor de la llamada evite un segundo examen para obtener los datos en un índice específico.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet4)]

La combinación de `SequencePosition` y `TryGet` actúa como enumerador. El campo de posición se modifica al principio de cada iteración para que sea el inicio de cada segmento dentro de `ReadOnlySequence<T>`.

El método anterior existe como método de extensión en `ReadOnlySequence<T>`. <xref:System.Buffers.BuffersExtensions.PositionOf%2A> se puede usar para simplificar el código anterior:

```csharp
SequencePosition? FindIndexOf(in ReadOnlySequence<byte> buffer, byte data) => buffer.PositionOf(data);
```

#### <a name="process-a-readonlysequencet"></a>Procesamiento de ReadOnlySequence\<T\>

El procesamiento de `ReadOnlySequence<T>` puede ser difícil, dado que los datos podrían estar divididos en varios segmentos dentro de la secuencia. Para obtener el mejor rendimiento, divida el código en dos rutas de acceso:

- Una ruta de acceso rápida que se ocupa del caso de un único segmento.
- Una ruta de acceso lenta que se ocupa de la división de los datos entre segmentos.

Existen varios enfoques que se pueden usar para procesar datos en secuencias de varios segmentos:

- Usar [`SequenceReader<T>`](#sequencereadert).
- Analizar el segmento de datos por segmento y mantener el seguimiento de `SequencePosition` y del índice dentro del segmento analizado. De esta forma, se evitan asignaciones innecesarias, aunque puede ser ineficaz, especialmente en el caso de búferes pequeños.
- Copiar `ReadOnlySequence<T>` en una matriz contigua y tratarla como un solo búfer:
  - Si el tamaño de `ReadOnlySequence<T>` es pequeño, puede ser razonable copiar los datos en un búfer asignado por la pila mediante el operador [stackalloc](../../csharp/language-reference/operators/stackalloc.md).
  - Copie `ReadOnlySequence<T>` en una matriz agrupada mediante <xref:System.Buffers.ArrayPool%601.Shared%2A?displayProperty=nameWithType>.
  - Utilice [`ReadOnlySequence<T>.ToArray()`](xref:System.Buffers.BuffersExtensions.ToArray%2A). Este método no se recomienda en las rutas de acceso activas, ya que asigna un nuevo elemento `T[]` en el montón.

En los siguientes ejemplos se muestran algunos casos comunes de procesamiento de `ReadOnlySequence<byte>`:

##### <a name="process-binary-data"></a>Procesamiento de datos binarios

En el siguiente ejemplo se analiza una longitud de entero bid endian de 4 bytes desde el inicio de `ReadOnlySequence<byte>`.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet5)]

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

##### <a name="process-text-data"></a>Procesamiento de datos de texto

En el ejemplo siguiente:

- Encuentra la primera línea nueva (`\r\n`) en `ReadOnlySequence<byte>` y la devuelve mediante el parámetro "line" de salida.
- Recorta esa línea, sin incluir `\r\n` del búfer de entrada.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet6)]

##### <a name="empty-segments"></a>Segmentos vacíos

Es válido almacenar segmentos vacíos dentro de `ReadOnlySequence<T>`. Pueden aparecer segmentos vacíos mientras se enumeran los segmentos de manera explícita:

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet7)]

El código anterior crea una estructura `ReadOnlySequence<byte>` con segmentos vacíos y muestra cómo afectan estos a las distintas API:

- `ReadOnlySequence<T>.Slice` con un valor `SequencePosition` que apunta a un segmento vacío conserva ese segmento.
- `ReadOnlySequence<T>.Slice` con un valor entero omite los segmentos vacíos.
- Al enumerar `ReadOnlySequence<T>`, se enumeran los segmentos vacíos.

### <a name="potential-problems-with-readonlysequencet-and-sequenceposition"></a>Posibles problemas con ReadOnlySequence\<T > y SequencePosition

Hay varios resultados inusuales cuando se trabaja con `ReadOnlySequence<T>`/`SequencePosition` frente a una representación `ReadOnlySpan<T>`normal /`ReadOnlyMemory<T>`/`T[]`/`int`:

- `SequencePosition` es un marcador de posición para una estructura `ReadOnlySequence<T>` específica, no una posición absoluta. Dado que es relativo a una estructura `ReadOnlySequence<T>` específica, no tiene ningún significado si se usa fuera de la estructura `ReadOnlySequence<T>` donde se origina.
- No se pueden realizar operaciones aritméticas en `SequencePosition` sin `ReadOnlySequence<T>`. Eso significa que hacer cosas básicas, como `position++`, se escribe `ReadOnlySequence<T>.GetPosition(position, 1)`.
- `GetPosition(long)`**no** admite índices negativos. Esto significa que es imposible obtener del segundo al último carácter sin recorrer todos los segmentos.
- No se pueden comparar dos valores `SequencePosition`, lo que dificulta:
  - Saber si una posición es mayor o menor que otra.
  - Escribir algunos algoritmos de análisis.
- `ReadOnlySequence<T>` es mayor que una referencia de objeto y debe pasarse mediante [in](../../csharp/language-reference/keywords/in-parameter-modifier.md) o [ref](../../csharp/language-reference/keywords/ref.md) siempre que sea posible. Pasar `ReadOnlySequence<T>` mediante `in` o `ref` reduce las copias de la [estructura](../../csharp/language-reference/builtin-types/struct.md).
- Segmentos vacíos:
  - Son válidos dentro de `ReadOnlySequence<T>`.
  - Pueden aparecer cuando se recorre en iteración mediante el método `ReadOnlySequence<T>.TryGet`.
  - Pueden aparecer segmentando la secuencia mediante el método `ReadOnlySequence<T>.Slice()` con objetos `SequencePosition`.

## <a name="sequencereadert"></a>SequenceReader\<T\>

<xref:System.Buffers.SequenceReader%601>:

- Es un nuevo tipo que se presentó en .NET Core 3.0 para simplificar el procesamiento de `ReadOnlySequence<T>`.
- Unifica las diferencias entre un solo segmento `ReadOnlySequence<T>` y varios segmentos `ReadOnlySequence<T>`.
- Proporciona asistentes para leer datos binarios y de texto (`byte` y `char`) que podrían estar o no divididos entre segmentos.

Existen métodos integrados que se ocupan del procesamiento de datos binarios y delimitados. En la siguiente sección se muestra el aspecto de esos mismos métodos con `SequenceReader<T>`:

### <a name="access-data"></a>Acceder a datos

`SequenceReader<T>` tiene métodos para enumerar datos dentro de `ReadOnlySequence<T>` directamente. El código siguiente es un ejemplo de procesamiento de `ReadOnlySequence<byte>` un `byte` cada vez:

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet8)]

`CurrentSpan` expone el valor `Span` del segmento actual, que es similar a lo que se hizo en el método manualmente.

### <a name="use-position"></a>Uso de la posición

El código siguiente es un ejemplo de implementación de `FindIndexOf` mediante `SequenceReader<T>`.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet9)]

### <a name="process-binary-data"></a>Procesamiento de datos binarios

En el siguiente ejemplo se analiza una longitud de entero bid endian de 4 bytes desde el inicio de `ReadOnlySequence<byte>`.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet11)]

### <a name="process-text-data"></a>Procesamiento de datos de texto

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet10)]

### <a name="sequencereadert-common-problems"></a>Problemas comunes de SequenceReader\<T\>

- Dado que `SequenceReader<T>` es una estructura mutable, siempre debe pasarse mediante una [referencia](../../csharp/language-reference/keywords/ref.md).
- `SequenceReader<T>` es una [estructura de referencia](../../csharp/language-reference/keywords/ref.md#ref-struct-types), de modo que solo se puede usar en métodos sincrónicos y no se puede almacenar en campos. Para más información, consulte [Escritura de código C# seguro y eficaz](../../csharp/write-safe-efficient-code.md).
- `SequenceReader<T>` está optimizado para su uso como lector de solo avance. `Rewind` está destinado a copias de seguridad pequeñas que no se pueden abordar mediante otras API de `Read`, `Peek` y `IsNext`.
