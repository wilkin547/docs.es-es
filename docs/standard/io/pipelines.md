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
# <a name="systemiopipelines-in-net"></a>System.IO.Pipelines en .NET

<xref:System.IO.Pipelines> es una biblioteca nueva que se ha diseñado para facilitar la entrada y salida de alto rendimiento en .NET. Se trata de una biblioteca que tiene como destino .NET Standard y que funciona en todas las implementaciones de .NET.

<a name="solve"></a>

## <a name="what-problem-does-systemiopipelines-solve"></a>¿Qué problema resuelve System.IO.Pipelines?

<!-- corner case doesn't MT (machine translate)   -->
Las aplicaciones que analizan datos de streaming se componen de código reutilizable que cuenta con muchos flujos de código especializados e inusuales. El código reutilizable y especial del caso es complejo y difícil de mantener.

`System.IO.Pipelines` se ha diseñado para lo siguiente:

* Disponer de un alto rendimiento al analizar datos de streaming.
* Reducir la complejidad del código.

El código siguiente es habitual para un servidor TCP que recibe mensajes delimitados por línea (delimitados por `'\n'`) de un cliente:

```csharp
async Task ProcessLinesAsync(NetworkStream stream)
{
    var buffer = new byte[1024];
    await stream.ReadAsync(buffer, 0, buffer.Length);

    // Process a single line from the buffer
    ProcessLine(buffer);
}
```

El código anterior tiene varios problemas:

* Es posible que el mensaje completo (final de la línea) no se reciba en una sola llamada a `ReadAsync`.
* Se omite el resultado de `stream.ReadAsync`. `stream.ReadAsync` devuelve la cantidad de datos que se han leído.
* No controla el caso en el que se leen varias líneas en una sola llamada a `ReadAsync`.
* Asigna una matriz `byte` con cada lectura.

Para solucionar los problemas anteriores, es necesario realizar los siguientes cambios:

* Almacenar en búfer los datos entrantes hasta que se encuentre una línea nueva.
* Analizar todas las líneas devueltas en el búfer.
* Es posible que la línea tenga un tamaño superior a 1 KB (1024 bytes). El código debe cambiar el tamaño del búfer de entrada hasta que se encuentre el delimitador para ajustarse a la línea completa dentro del búfer.

  * Si se cambia el tamaño del búfer, se realizan más copias de búfer a medida que aparecen líneas más largas en la entrada.
  * Para reducir el espacio desaprovechado, compacte el búfer usado para las líneas de lectura.

* Considere la posibilidad de usar la agrupación de búferes para evitar asignar memoria de forma repetida.
* En el código siguiente se abordan algunos de estos problemas:

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/ProcessLinesAsync.cs" id="snippet":::

El código anterior es complejo y no aborda todos los problemas identificados. Las redes de alto rendimiento normalmente implican la escritura de código muy complejo para maximizar el rendimiento. `System.IO.Pipelines` se ha diseñado para facilitar la escritura de este tipo de código.

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="pipe"></a>Canalización (|).

La clase <xref:System.IO.Pipelines.Pipe> se puede usar para crear un par de `PipeWriter/PipeReader`. Todos los datos escritos en `PipeWriter` están disponibles en `PipeReader`:

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/Pipe.cs" id="snippet2":::

<a name="pbu"></a>

### <a name="pipe-basic-usage"></a>Uso básico de la canalización

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/Pipe.cs" id="snippet":::

Hay dos bucles:

* `FillPipeAsync` lee de `Socket` y escribe en `PipeWriter`.
* `ReadPipeAsync` lee de `PipeReader` y analiza las líneas de entrada.

No existe ningún búfer explícito asignado. Toda la administración del búfer se delega en las implementaciones de `PipeReader` y `PipeWriter`. La delegación de la administración del búfer facilita el consumo de código para centrarse únicamente en la lógica de negocios.

En el primer bucle:

* Se llama a <xref:System.IO.Pipelines.PipeWriter.GetMemory(System.Int32)?displayProperty=nameWithType> para obtener la memoria del escritor subyacente.
* Se llama a <xref:System.IO.Pipelines.PipeWriter.Advance(System.Int32)?displayProperty=nameWithType> para indicar a `PipeWriter` la cantidad de datos que se han escrito en el búfer.
* Se llama a <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType> para hacer que los datos estén disponibles en `PipeReader`.

En el segundo bucle, `PipeReader` consume los búferes que ha escrito `PipeWriter`. Los búferes proceden del socket. La llamada a `PipeReader.ReadAsync`:

* Devuelve un elemento <xref:System.IO.Pipelines.ReadResult> que contiene dos fragmentos de información importantes:

  * Los datos que se han leído en forma de `ReadOnlySequence<byte>`.
  * Un valor booleano `IsCompleted` que indica si se ha alcanzado el final de los datos (EOD).

Después de buscar el delimitador de final de línea (EOL) y analizar la línea ocurre lo siguiente:

* La lógica procesa el búfer para omitir lo que ya se ha procesado.
* Se llama a `PipeReader.AdvanceTo` para indicar a `PipeReader` la cantidad de datos que se han consumido y examinado.

Los bucles de lectura y escritura finalizan con una llamada a `Complete`. `Complete` permite liberar la memoria que ha asignado la canalización subyacente.

### <a name="backpressure-and-flow-control"></a>Contrapresión y control de flujo

Idealmente, la lectura y el análisis funcionan juntos:

* El subproceso de escritura consume datos de la red y los coloca en los búferes.
* El subproceso de análisis se encarga de construir las estructuras de datos adecuadas.

Normalmente, el análisis tarda más tiempo en realizarse que simplemente copiar bloques de datos de la red:

* El subproceso de lectura se obtiene antes del subproceso de análisis.
* El subproceso de lectura tiene que ralentizar o asignar más memoria para almacenar los datos para el subproceso de análisis.

Para obtener un rendimiento óptimo, existe un equilibrio entre las pausas frecuentes y la asignación de más memoria.

Para resolver el problema anterior, `Pipe` tiene dos opciones de configuración para controlar el flujo de datos:

* <xref:System.IO.Pipelines.PipeOptions.PauseWriterThreshold>: determina la cantidad de datos que se deben almacenar en búfer antes de que se pausen las llamadas a <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A>.
* <xref:System.IO.Pipelines.PipeOptions.ResumeWriterThreshold>: determina la cantidad de datos que debe observar el lector antes de que se reanuden las llamadas a `PipeWriter.FlushAsync`.

![Diagrama con ResumeWriterThreshold y PauseWriterThreshold.](media/pipelines/resume-pause.png)

<xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>:

* Devuelve un `ValueTask<FlushResult>` incompleto cuando la cantidad de datos de `Pipe` cruza `PauseWriterThreshold`.
* Completa `ValueTask<FlushResult>` cuando se vuelve menor que `ResumeWriterThreshold`.

Se usan dos valores para evitar ciclos rápidos, que pueden producirse si solo se usa un valor.

### <a name="examples"></a>Ejemplos

```csharp
// The Pipe will start returning incomplete tasks from FlushAsync until
// the reader examines at least 5 bytes.
var options = new PipeOptions(pauseWriterThreshold: 10, resumeWriterThreshold: 5);
var pipe = new Pipe(options);
```

### <a name="pipescheduler"></a>PipeScheduler

Normalmente, cuando se usa `async` y `await`, el código asincrónico se reanuda en un elemento <xref:System.Threading.Tasks.TaskScheduler> o en el elemento <xref:System.Threading.SynchronizationContext> actual.

Al realizar operaciones de E/S, es importante tener un control específico sobre dónde se realizan estas operaciones. Este control permite sacar provecho de las cachés de CPU de manera eficiente. Para las aplicaciones de alto rendimiento, como los servidores web, disponer de un almacenamiento en caché eficiente resulta fundamental. <xref:System.IO.Pipelines.PipeScheduler> proporciona control sobre dónde se ejecutan las devoluciones de llamada asincrónicas. De manera predeterminada:

* Se usa el elemento <xref:System.Threading.SynchronizationContext> actual.
* Si no hay ningún elemento `SynchronizationContext`, se usa el grupo de subprocesos para ejecutar las devoluciones de llamada.

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/Program.cs" id="snippet":::

[PipeScheduler.ThreadPool](xref:System.IO.Pipelines.PipeScheduler.ThreadPool) es la implementación de <xref:System.IO.Pipelines.PipeScheduler> que pone en cola las devoluciones de llamada en el grupo de subprocesos. `PipeScheduler.ThreadPool` es el valor predeterminado y, por lo general, la mejor opción. [PipeScheduler.Inline](xref:System.IO.Pipelines.PipeScheduler.Inline) puede producir consecuencias no intencionadas, como interbloqueos.

### <a name="pipe-reset"></a>Restablecimiento de la canalización

A menudo, es eficiente la reutilización del objeto `Pipe`. Para restablecer la canalización, llame a <xref:System.IO.Pipelines.PipeReader> <xref:System.IO.Pipelines.Pipe.Reset%2A> cuando se hayan completado los elementos `PipeReader` y `PipeWriter`.

## <a name="pipereader"></a>PipeReader

<xref:System.IO.Pipelines.PipeReader> administra la memoria en nombre del autor de la llamada. Llame a <xref:System.IO.Pipelines.PipeReader.AdvanceTo%2A?displayProperty=nameWithType>**siempre** después de llamar a <xref:System.IO.Pipelines.PipeReader.ReadAsync%2A?displayProperty=nameWithType>. Esto permite que `PipeReader` sepa cuándo ha acabado con la memoria el autor de la llamada, de tal modo que se le pueda realizar un seguimiento. El elemento `ReadOnlySequence<byte>` que devuelve `PipeReader.ReadAsync` solo es válido hasta que se llame a `PipeReader.AdvanceTo`. No es válido usar `ReadOnlySequence<byte>` después de llamar a `PipeReader.AdvanceTo`.

`PipeReader.AdvanceTo` toma dos argumentos <xref:System.SequencePosition>:

* El primer argumento determina la cantidad de memoria consumida.
* El segundo argumento determina la cantidad de búfer observado.

Marcar los datos como consumidos significa que la canalización puede devolver la memoria al grupo de búferes subyacente. Cuando se marcan los datos como observados, estos controlan lo que hace la siguiente llamada a `PipeReader.ReadAsync`. Marcar todo como observado significa que la siguiente llamada a `PipeReader.ReadAsync` no se devolverá hasta que haya más datos escritos en la canalización. Cualquier otro valor hará que la siguiente llamada a `PipeReader.ReadAsync` se devuelva de inmediato con los datos observados *y* los no observados, pero no con los que ya se han consumido.

### <a name="read-streaming-data-scenarios"></a>Escenarios de lectura de datos de streaming

Hay un par de patrones típicos que surgen al intentar leer datos de streaming:

* Dada una secuencia de datos, analizar un solo mensaje.
* Dada una secuencia de datos, analizar todos los mensajes disponibles.

En los ejemplos siguientes se usa el método `TryParseMessage` para analizar los mensajes que proceden de un elemento `ReadOnlySequence<byte>`. `TryParseMessage` analiza un solo mensaje y actualiza el búfer de entrada para recortar el mensaje analizado del búfer. `TryParseMessage` no forma parte de .NET, es un método de usuario escrito que se usa en las secciones siguientes.

```csharp
bool TryParseMessage(ref ReadOnlySequence<byte> buffer, out Message message);
```

### <a name="read-a-single-message"></a>Lectura de un único mensaje

En el código siguiente se lee un único mensaje de un elemento `PipeReader` y se devuelve al autor de la llamada.

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/ReadSingleMsg.cs" id="snippet":::

El código anterior:

* Analiza un único mensaje.
* Actualiza el elemento `SequencePosition` consumido y el elemento `SequencePosition` examinado para que apunte al principio del búfer recortado de entrada.

Los dos argumentos `SequencePosition` se actualizan porque `TryParseMessage` quita el mensaje analizado del búfer de entrada. Por lo general, al analizar un solo mensaje del búfer, la posición examinada debe ser una de las siguientes:

* El final del mensaje.
* El final del búfer recibido si no se ha encontrado ningún mensaje.

El caso de mensaje único tiene la probabilidad más alta de producir errores. Si se pasan valores incorrectos a *examinados*, se puede producir una excepción de memoria insuficiente o un bucle infinito. Para obtener más información, vea la sección [Problemas comunes de PipeReader](#gotchas).

### <a name="reading-multiple-messages"></a>Lectura de varios mensajes

En el código siguiente se leen todos los mensajes de un elemento `PipeReader` y se llama a `ProcessMessageAsync` en cada uno de estos.

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyConnection1.cs" id="snippet":::

### <a name="cancellation"></a>Cancelación

`PipeReader.ReadAsync`:

* Admite pasar un elemento <xref:System.Threading.CancellationToken>.
* Produce un elemento <xref:System.OperationCanceledException> si se cancela `CancellationToken` mientras haya una lectura pendiente.
* Admite una manera de cancelar la operación de lectura actual mediante <xref:System.IO.Pipelines.PipeReader.CancelPendingRead%2A?displayProperty=nameWithType>, lo que evita que se produzca una excepción. La llamada a `PipeReader.CancelPendingRead` provoca que la llamada actual a `PipeReader.ReadAsync`, o la siguiente, devuelva un elemento <xref:System.IO.Pipelines.ReadResult> con `IsCanceled` establecido en `true`. Esto puede ser útil para detener el bucle de lectura existente de forma no destructiva y no excepcional.

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyConnection.cs" id="snippet":::

<a name="gotchas"></a>

### <a name="pipereader-common-problems"></a>Problemas comunes de PipeReader

* Si se pasan valores incorrectos a `consumed` o `examined`, es posible que se lean datos ya leídos.
* Si se pasa `buffer.End` como examinado, es posible que se produzca lo siguiente:

  * Datos detenidos
  * Es posible que se produzca una excepción de memoria insuficiente (OOM) si no se consumen los datos. Por ejemplo, `PipeReader.AdvanceTo(position, buffer.End)` cuando se procesa un único mensaje a la vez desde el búfer.

* Si se pasan valores incorrectos a `consumed` o `examined`, es posible que se produzca un bucle infinito. Por ejemplo, `PipeReader.AdvanceTo(buffer.Start)`, si `buffer.Start` no ha cambiado, hará que la siguiente llamada a `PipeReader.ReadAsync` se devuelva inmediatamente antes de que lleguen datos nuevos.
* Si se pasan valores incorrectos a `consumed` o `examined`, es posible que se produzca un almacenamiento en búfer infinito (posible OOM).
* El uso de `ReadOnlySequence<byte>` después de llamar a `PipeReader.AdvanceTo` puede producir daños en la memoria (se usa después de liberar).
* Si se produce un error al llamar a `PipeReader.Complete/CompleteAsync`, puede dar como resultado una fuga de memoria.
* Al comprobar <xref:System.IO.Pipelines.ReadResult.IsCompleted?displayProperty=nameWithType> y salir de la lógica de lectura antes de procesar el búfer, se produce una pérdida de datos. La condición de salida del bucle debe basarse en `ReadResult.Buffer.IsEmpty` y `ReadResult.IsCompleted`. Si esto se hace incorrectamente, podría producirse un bucle infinito.

#### <a name="problematic-code"></a>Código problemático

❌ **Pérdida de datos**

`ReadResult` puede devolver el segmento final de los datos cuando `IsCompleted` está establecido en `true`. Si no se leen los datos antes de salir del bucle de lectura, se producirá una pérdida de datos.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

❌ **Bucle infinito**

La lógica siguiente puede producir un bucle infinito si `Result.IsCompleted` es `true`, pero nunca hay un mensaje completo en el búfer.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet2":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

Este es otro fragmento de código con el mismo problema. Está comprobando si hay un búfer no vacío antes de comprobar `ReadResult.IsCompleted`. Dado que está en un elemento `else if`, se ejecutará en bucle para siempre si en el búfer no hay nunca un mensaje completo.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet3":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

❌ **Bloqueo inesperado**

La llamada incondicional a `PipeReader.AdvanceTo`, con `buffer.End` en la posición `examined`, puede dar lugar a bloqueos al analizar un solo mensaje. La siguiente llamada a `PipeReader.AdvanceTo` no se devolverá hasta que:

* Haya más datos escritos en la canalización.
* Y los nuevos datos no se hayan examinado previamente.

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet4":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

❌ **Memoria insuficiente (OOM)**

Con las condiciones siguientes, el código siguiente mantiene el almacenamiento en búfer hasta que se produce <xref:System.OutOfMemoryException>:

* No hay tamaño máximo del mensaje.
* Los datos que devuelve `PipeReader` no representan un mensaje completo. Por ejemplo, no representa un mensaje completo porque el otro lado está escribiendo un mensaje de gran tamaño (por ejemplo, un mensaje de 4 GB).

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet5":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

❌ **Daño en la memoria**

Al escribir asistentes que lean el búfer, se debe copiar cualquier carga devuelta antes de llamar a `Advance`. En el ejemplo siguiente se devolverá la memoria que ha descartado `Pipe` y se puede volver a usar para la siguiente operación (lectura/escritura).

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippetMessage":::

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet6":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

## <a name="pipewriter"></a>PipeWriter

<xref:System.IO.Pipelines.PipeWriter> administra los búferes para escribir en nombre del autor de la llamada. `PipeWriter` implementa [`IBufferWriter<byte>`](xref:System.Buffers.IBufferWriter%601). `IBufferWriter<byte>` permite obtener acceso a los búferes para realizar escrituras sin necesidad de tener copias de búfer adicionales.

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyPipeWriter.cs" id="snippet":::

El código anterior:

* Solicita un búfer de al menos 5 bytes de `PipeWriter` mediante <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A>.
* Escribe bytes para la cadena ASCII `"Hello"` en el elemento devuelto `Memory<byte>`.
* Llama a <xref:System.IO.Pipelines.PipeWriter.Advance%2A> para indicar el número de bytes que se han escrito en el búfer.
* Vacía `PipeWriter`, que envía los bytes al dispositivo subyacente.

El método de escritura anterior utiliza los búferes que proporciona `PipeWriter`. O bien, <xref:System.IO.Pipelines.PipeWriter.WriteAsync%2A?displayProperty=nameWithType>:

* Copia el búfer existente en `PipeWriter`.
* Llama a `GetSpan` o `Advance`, según corresponda, y llama a <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A>.

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyPipeWriter.cs" id="snippet2":::

### <a name="cancellation"></a>Cancelación

<xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> admite pasar un elemento <xref:System.Threading.CancellationToken>. Al pasar un elemento `CancellationToken`, se produce un elemento `OperationCanceledException` si el token se cancela mientras haya una operación de vaciado pendiente. `PipeWriter.FlushAsync` admite una manera de cancelar la operación de vaciado actual a través de <xref:System.IO.Pipelines.PipeWriter.CancelPendingFlush%2A?displayProperty=nameWithType> sin que se produzca una excepción. La llamada a `PipeWriter.CancelPendingFlush` provoca que la llamada actual a `PipeWriter.FlushAsync` o a `PipeWriter.WriteAsync`, devuelva un elemento <xref:System.IO.Pipelines.FlushResult> con `IsCanceled` establecido en `true`. Esto puede ser útil para detener el vaciado de retención de forma no destructiva y no excepcional.

<a name="pwcp"></a>

### <a name="pipewriter-common-problems"></a>Problemas comunes de PipeWriter

* <xref:System.IO.Pipelines.PipeWriter.GetSpan%2A> y <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> devuelven un búfer con, al menos, la cantidad de memoria solicitada. **No** asume tamaños de búfer exactos.
* No existe ninguna garantía de que las llamadas sucesivas devuelvan el mismo búfer o el mismo tamaño del búfer.
* Se debe solicitar un nuevo búfer después de llamar a <xref:System.IO.Pipelines.PipeWriter.Advance%2A> para seguir escribiendo más datos. No se puede escribir en el búfer adquirido previamente.
* La llamada a `GetMemory` o a `GetSpan` no es segura mientras haya una llamada incompleta a `FlushAsync`.
* La llamada a `Complete` o a `CompleteAsync` puede provocar daños en la memoria mientras haya datos no vaciados.

## <a name="iduplexpipe"></a>IDuplexPipe

<xref:System.IO.Pipelines.IDuplexPipe> es un contrato para los tipos que admiten la lectura y la escritura. Por ejemplo, una conexión de red se representará mediante un elemento `IDuplexPipe`.

 A diferencia de `Pipe`, que contiene un elemento `PipeReader` y otro elemento `PipeWriter`, `IDuplexPipe` representa un solo lado de una conexión de dúplex completo. Esto significa que lo que se escribe en `PipeWriter` no se leerá desde `PipeReader`.

## <a name="streams"></a>Secuencias

Al leer o escribir datos de secuencia, normalmente se leen los datos mediante un deserializador y se escriben mediante un serializador. La mayoría de estas API de secuencias de lectura y escritura tienen un parámetro `Stream`. Para facilitar la integración con estas API existentes, `PipeReader` y `PipeWriter` exponen un método <xref:System.IO.Pipelines.PipeReader.AsStream%2A>. <xref:System.IO.Pipelines.PipeWriter.AsStream%2A> devuelve una implementación de `Stream` en torno a `PipeReader` o `PipeWriter`.

### <a name="stream-example"></a>Ejemplos de secuencias

Las instancias de `PipeReader` y `PipeWriter` se pueden crear mediante los métodos `Create` estáticos dado un objeto <xref:System.IO.Stream> y las opciones de creación correspondientes.

<xref:System.IO.Pipelines.StreamPipeReaderOptions> permite el control sobre la creación de la instancia de `PipeReader` con los parámetros siguientes:

- <xref:System.IO.Pipelines.StreamPipeReaderOptions.BufferSize?displayProperty=nameWithType> es el tamaño de búfer mínimo en bytes que se usa al alquilar memoria del grupo y su valor predeterminado es `4096`.
- La marca <xref:System.IO.Pipelines.StreamPipeReaderOptions.LeaveOpen?displayProperty=nameWithType> determina si el flujo subyacente se deja abierto una vez finalizada la instancia de `PipeReader` y se establece de forma predeterminada en `false`.
- <xref:System.IO.Pipelines.StreamPipeReaderOptions.MinimumReadSize?displayProperty=nameWithType> representa el umbral de bytes restantes en el búfer antes de que se asigne un nuevo búfer y su valor predeterminado es `1024`.
- <xref:System.IO.Pipelines.StreamPipeReaderOptions.Pool?displayProperty=nameWithType> es el elemento `MemoryPool<byte>` que se usa al asignar memoria y el valor predeterminado es `null`.

<xref:System.IO.Pipelines.StreamPipeWriterOptions> permite el control sobre la creación de la instancia de `PipeWriter` con los parámetros siguientes:

- La marca <xref:System.IO.Pipelines.StreamPipeWriterOptions.LeaveOpen?displayProperty=nameWithType> determina si el flujo subyacente se deja abierto una vez finalizada la instancia de `PipeWriter` y se establece de forma predeterminada en `false`.
- <xref:System.IO.Pipelines.StreamPipeWriterOptions.MinimumBufferSize?displayProperty=nameWithType> representa el tamaño de búfer mínimo que se va a usar al alquilar memoria de <xref:System.IO.Pipelines.StreamPipeWriterOptions.Pool> y su valor predeterminado es `4096`.
- <xref:System.IO.Pipelines.StreamPipeWriterOptions.Pool?displayProperty=nameWithType> es el elemento `MemoryPool<byte>` que se usa al asignar memoria y el valor predeterminado es `null`.

> [!IMPORTANT]
> Al crear instancias de `PipeReader` y `PipeWriter` mediante los métodos `Create`, debe tener en cuenta la duración del objeto `Stream`. Si necesita tener acceso al flujo después de que el lector o el escritor hayan terminado con él, debe establecer la marca `LeaveOpen` en `true` en las opciones de creación. De lo contrario, el flujo se cerrará.

En el código siguiente se muestra la creación de instancias de `PipeReader` y `PipeWriter` mediante los métodos `Create` de un flujo.

:::code language="csharp" source="snippets/pipelines/Program.cs":::

La aplicación utiliza un elemento <xref:System.IO.StreamReader> para leer el archivo *lorem-ipsum.txt* como un flujo. <xref:System.IO.FileStream> se pasa a <xref:System.IO.Pipelines.PipeReader.Create%2A?displayProperty=nameWithType>, que crea una instancia de un objeto `PipeReader`. Después, la aplicación de consola pasa su flujo de salida estándar a <xref:System.IO.Pipelines.PipeWriter.Create%2A?displayProperty=nameWithType> mediante <xref:System.Console.OpenStandardOutput?displayProperty=nameWithType>. El ejemplo admite la [cancelación](#cancellation).
