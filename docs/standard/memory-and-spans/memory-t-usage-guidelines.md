---
title: Instrucciones de uso de Memory<T> y Span<T>
ms.date: 10/01/2018
helpviewer_keywords:
- Memory&lt;T&gt; and Span&lt;T&gt; best practices
- using Memory&lt;T&gt; and Span&lt;T&gt;
ms.openlocfilehash: b89969f212da6ac90d0fb0d1bf388626e136b92e
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158598"
---
# <a name="memoryt-and-spant-usage-guidelines"></a>Instrucciones de uso de Memory\<T> y Span\<T>

.NET Core incluye una serie de tipos que representan una región contigua y arbitraria de memoria. .NET Core 2.0 introdujo <xref:System.Span%601> y <xref:System.ReadOnlySpan%601>, que son búferes de memoria ligera que se puede respaldar por la memoria administrada o no administrada. Dado que estos tipos solo se pueden almacenar en la pila, no son aptos para una serie de escenarios, incluidas las llamadas de método asincrónico. .NET Core 2.1 agrega numerosos tipos adicionales, incluidos <xref:System.Memory%601>, <xref:System.ReadOnlyMemory%601>, <xref:System.Buffers.IMemoryOwner%601> y <xref:System.Buffers.MemoryPool%601>. Al igual que <xref:System.Span%601>, <xref:System.Memory%601> y sus tipos relacionados pueden estar respaldados por la memoria administrada y no administrada. A diferencia de <xref:System.Span%601>, <xref:System.Memory%601> se puede almacenar en el montón administrado.

<xref:System.Span%601> y <xref:System.Memory%601> son los búferes de datos estructurados que se pueden usar en las canalizaciones. Es decir, están diseñados para que parte de los datos, o todos, se pueda pasar de forma eficaz a los componentes de la canalización, que puede procesarlos y, opcionalmente, modifique el búfer. Como varios componentes o subprocesos pueden acceder a <xref:System.Memory%601> y sus tipos relacionados, es importante que los desarrolladores sigan algunas directrices de uso estándar para crear código sólido.

## <a name="owners-consumers-and-lifetime-management"></a>Propietarios, consumidores y administración de la duración

Puesto que los búferes se pueden pasar entre las API, y que se, a veces, se puede acceder a los búferes desde varios subprocesos, es importante tener en cuenta la administración de la duración. Hay tres conceptos principales:

- **Propiedad**. El propietario de una instancia de búfer es responsable de la administración de la duración, por ejemplo, destruir el búfer cuando ya no se use. Todos los búferes tienen un único propietario. Por lo general, el propietario es el componente que creó el búfer o que recibió el búfer de una fábrica. También se puede transferir la propiedad; **Component-A** puede ceder el control del búfer a **Component-B**, momento en que **Component-A** ya no puede usar más el búfer, y **Component-B** pasa a ser responsable de destruir el búfer cuando ya no se usa.

- **Consumo**. El consumidor de una instancia de búfer puede usar la instancia de búfer leyéndolo y, posiblemente, escribir en él. Los búferes pueden tener un consumidor a la vez, a menos que se proporcione algún mecanismo de sincronización externo. El consumidor activo de un búfer no es necesariamente el propietario del búfer.

- **Concesión**. La concesión es el período durante el cual un componente concreto puede ser el consumidor del búfer.

En el ejemplo de pseudocódigo siguiente se muestran estos tres conceptos. Incluye un método `Main` que crea una instancia de un búfer <xref:System.Memory%601> de tipo <xref:System.Char>, llama al método `WriteInt32ToBuffer` para escribir la representación de cadena de un entero en el búfer y, después, llama al método `DisplayBufferToConsole` para mostrar el valor del búfer.

```csharp
using System;

class Program
{
    // Write 'value' as a human-readable string to the output buffer.
    void WriteInt32ToBuffer(int value, Buffer buffer);

    // Display the contents of the buffer to the console.
    void DisplayBufferToConsole(Buffer buffer);

    // Application code
    static void Main()
    {
        var buffer = CreateBuffer();
        try
        {
            int value = Int32.Parse(Console.ReadLine());
            WriteInt32ToBuffer(value, buffer);
            DisplayBufferToConsole(buffer);
        }
        finally
        {
            buffer.Destroy();
        }
    }
}
```

El método `Main` crea el búfer (en este caso, una instancia de <xref:System.Span%601>); el propietario. Por lo tanto, `Main` es responsable de destruir el búfer cuando ya no se usa. Esto se hace llamando al método <xref:System.Span%601.Clear?displayProperty=nameWithType> del búfer. El método <xref:System.Span%601.Clear> realmente borra la memoria del búfer; la estructura <xref:System.Span%601> no tiene en realidad un método que destruya el búfer.

El búfer tiene dos consumidores, `WriteInt32ToBuffer` y `DisplayBufferToConsole`. Hay solo un consumidor a la vez (primero `WriteInt32ToBuffer` y, luego, `DisplayBufferToConsole`), y ninguno de los consumidores posee el búfer. Tenga en cuenta también que "consumidor" en este contexto no implica una vista de solo lectura del búfer; los consumidores pueden modificar el contenido del búfer, como `WriteInt32ToBuffer`, si se proporciona una vista de lectura/escritura del búfer.

El método `WriteInt32ToBuffer` tiene una concesión (pueden consumir) sobre el búfer entre el inicio de la llamada al método y el momento en que se devuelve el método. De forma similar, `DisplayBufferToConsole` tiene una concesión sobre el búfer mientras se ejecuta, y se libera cuando se desenreda el método. No hay ninguna API para administrar concesiones; la "concesión" es una cuestión conceptual.

## <a name="memoryt-and-the-ownerconsumer-model"></a>Memory\<T> y el modelo de consumidor y propietario

Como se indica en la sección [Propietarios, consumidores y administración de la duración](#owners-consumers-and-lifetime-management), un búfer siempre tiene un propietario. .NET Core admite dos modelos de propiedad:

- Un modelo que admite la propiedad única. Un búfer tiene un propietario único para toda su duración.

- Un modelo que admite la transferencia de la propiedad. La propiedad de un búfer se puede transferir desde el propietario original (su creador) a otro componente, que, luego, pasa a ser responsable de la administración de la duración del búfer. Ese propietario, a su vez, puede transferir la propiedad a otro componente, y así sucesivamente.

Usa la interfaz <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType> para administrar explícitamente la propiedad de un búfer. <xref:System.Buffers.IMemoryOwner%601> es compatible con ambos modelos de propiedad. El componente que tiene una referencia de <xref:System.Buffers.IMemoryOwner%601> posee el búfer. En el ejemplo siguiente se usa una instancia de <xref:System.Buffers.IMemoryOwner%601?> para reflejar la propiedad de un búfer de <xref:System.Memory%601>.

[!code-csharp[ownership](~/samples/snippets/standard/buffers/memory-t/owner/owner.cs)]

También podemos escribir este ejemplo con [`using`](../../csharp/language-reference/keywords/using-statement.md):

[!code-csharp[ownership-using](~/samples/snippets/standard/buffers/memory-t/owner-using/owner-using.cs)]

En este código:

- El método `Main` contiene la referencia a la instancia de <xref:System.Buffers.IMemoryOwner%601>, por lo que el método `Main` es el propietario del búfer.

- Los métodos `WriteInt32ToBuffer` y `DisplayBufferToConsole` aceptan <xref:System.Memory%601> como API pública. Por lo tanto, son consumidores del búfer. Y solo lo consumen de uno en uno.

Aunque el método `WriteInt32ToBuffer` está diseñado para escribir un valor en el búfer, el método`DisplayBufferToConsole`, no. Para reflejar esto, podría haber aceptado un argumento de tipo <xref:System.ReadOnlyMemory%601>. Para más información sobre <xref:System.ReadOnlyMemory%601>, vea [Regla 2: Use ReadOnlySpan\<T> o ReadOnlyMemory\<T> si el búfer debe ser de solo lectura](#rule-2).

### <a name="ownerless-memoryt-instances"></a>Instancias de Memory\<T> "sin propietario"

Puede crear una instancia de <xref:System.Memory%601> sin usar <xref:System.Buffers.IMemoryOwner%601>. En este caso, la propiedad del búfer está implícita en lugar de explícita, y solo se admite el modelo de propietario único. Puede hacerlo de la siguiente forma:

- Llamar a uno de los constructores <xref:System.Memory%601> directamente, pasando un búfer `T[]`, como en el siguiente ejemplo.

- Llamar al método de extensión [String.AsMemory](xref:System.MemoryExtensions.AsMemory(System.String)) para generar una instancia de `ReadOnlyMemory<char>`.

[!code-csharp[ownerless-memory](~/samples/snippets/standard/buffers/memory-t/ownerless/ownerless.cs)]

El método que crea inicialmente la instancia de <xref:System.Memory%601> es el propietario implícito del búfer. No se puede transferir la propiedad a cualquier otro componente porque no hay ninguna instancia de <xref:System.Buffers.IMemoryOwner%601> que facilite la transferencia. Como alternativa, puede también imaginarse que el recolector de elementos no utilizados del entorno de ejecución contiene el búfer, y todos los métodos simplemente consumen el búfer.

## <a name="usage-guidelines"></a>Instrucciones de uso

Dado que un bloque de memoria tiene un propietario, pero está diseñado para pasarse a varios componentes, algunos de los cuales pueden funcionar en un bloque de memoria específica al mismo tiempo, es importante establecer instrucciones para usar <xref:System.Memory%601> y <xref:System.Span%601>.  Estas instrucciones son necesarias por los siguientes motivos:

- Es posible que un componente conserve una referencia a un bloque de memoria después de que su propietario lo haya liberado.

- Un componente puede estar funcionando en un búfer al mismo tiempo que otro componente está operando en el proceso, con lo que se dañan los datos del búfer.

- Si bien la naturaleza asignada a la pila de <xref:System.Span%601> optimiza el rendimiento y convierte a <xref:System.Span%601> en el tipo preferido para funcionar en un bloque de memoria, también somete a <xref:System.Span%601> a algunas restricciones principales. Es importante saber cuándo usar <xref:System.Span%601> y <xref:System.Memory%601>.

A continuación, se muestran recomendaciones para usar correctamente <xref:System.Memory%601> y sus tipos relacionados. Las instrucciones que se aplican a <xref:System.Memory%601> y a <xref:System.Span%601> son válidas también para <xref:System.ReadOnlyMemory%601> y <xref:System.ReadOnlySpan%601>, a menos que se indique expresamente lo contrario.

**Regla 1: Para una API sincrónica, use Span\<T> en lugar de Memory\<T> como un parámetro si es posible.**

<xref:System.Span%601> es más versátil que <xref:System.Memory%601> y puede representar una amplia variedad de búferes de memoria contigua. <xref:System.Span%601> también ofrece mayor rendimiento que <xref:System.Memory%601>. Finalmente, puede usar la propiedad <xref:System.Memory%601.Span?displayProperty=nameWithType> para convertir una instancia de <xref:System.Memory%601> a <xref:System.Span%601>, aunque la conversión de Span\<T> a Memory \<T> no se puede realizar. Por tanto, si los autores de llamada tienen una instancia de <xref:System.Memory%601>, pueden llamar a los métodos con parámetros <xref:System.Span%601>.

Usar un parámetro de tipo <xref:System.Span%601> en lugar de tipo <xref:System.Memory%601> también ayuda a escribir una implementación de método de consumo correcta. Obtendrá automáticamente comprobaciones en tiempo de compilación para asegurarse de que no está tratando de acceder al búfer más allá de la concesión del método (encontrará más información sobre esto más adelante).

En ocasiones, tendrá que usar un parámetro <xref:System.Memory%601> en lugar de <xref:System.Span%601>, aunque sea un método completamente sincrónico. Quizás, una API de la que depende solo acepta argumentos <xref:System.Memory%601>. Aunque es correcto, debe ser consciente de los inconvenientes que implica usar <xref:System.Memory%601> sincrónicamente.

<a name="rule-2" />

**Regla 2: Use ReadOnlySpan\<T> o ReadOnlyMemory\<T> si el búfer debe ser de solo lectura.**

En los ejemplos anteriores, el método `DisplayBufferToConsole` solo lee del búfer, no modifica su contenido. La firma del método se debe cambiar a la siguiente.

```csharp
void DisplayBufferToConsole(ReadOnlyMemory<char> buffer);
```

De hecho, si se combinan esta regla y la 1, podemos hacerlo incluso mejor y reescribir la firma del método como sigue:

```csharp
void DisplayBufferToConsole(ReadOnlySpan<char> buffer);
```

El método `DisplayBufferToConsole` ahora funciona con prácticamente cualquier tipo de búfer imaginable: `T[]`, almacenamiento asignable con [stackalloc](../../csharp/language-reference/operators/stackalloc.md) y así sucesivamente. Incluso puede pasar una clase <xref:System.String> directamente.

**Regla 3: Si el método acepta Memory\<T> y devuelve `void`, no debe usar la instancia de Memory\<T> después de que se devuelva el método.**

Esto se relaciona con el concepto de "concesión" mencionado anteriormente. La concesión de un método que no devuelve valores sobre la instancia de <xref:System.Memory%601> comienza cuando se especifica el método y termina cuando finaliza. Observe el ejemplo siguiente, que llama a `Log` en un bucle basado en lo especificado desde la consola.

[!code-csharp[void-returning](~/samples/snippets/standard/buffers/memory-t/void-returning/void-returning.cs#1)]

Si `Log` es un método completamente sincrónico, este código se comportará según lo esperado porque solo hay un consumidor activo de la instancia de la memoria en un momento dado.
Pero, en lugar de esto, imagine que `Log` tiene esta implementación.

```csharp
// !!! INCORRECT IMPLEMENTATION !!!
static void Log(ReadOnlyMemory<char> message)
{
    // Run in background so that we don't block the main thread while performing IO.
    Task.Run(() =>
    {
        StreamWriter sw = File.AppendText(@".\input-numbers.dat");
        sw.WriteLine(message);
    });
}
```

En esta implementación, `Log` infringe su concesión porque sigue tratando de utilizar la instancia de <xref:System.Memory%601> en segundo plano después de que se haya devuelto el método original. El método `Main` podría modificar el búfer mientras `Log` intenta leer desde él, lo que podría provocar daños en los datos.

Hay varias formas de solucionar esto:

- El método `Log` puede devolver una clase <xref:System.Threading.Tasks.Task> en lugar de `void`, como hace la siguiente implementación del método `Log`.

   [!code-csharp[task-returning](~/samples/snippets/standard/buffers/memory-t/task-returning2/task-returning2.cs#1)]

- `Log` se puede implementar de la siguiente forma:

   [!code-csharp[defensive-copy](~/samples/snippets/standard/buffers/memory-t/task-returning/task-returning.cs#1)]

**Regla 4: Si el método acepta Memory\<T> y devuelve una clase Task, no debe usar la instancia de Memory\<T> después de las transiciones de Task a un estado terminal.**

Se trata de la variante asincrónica de la regla 3. El método `Log` del ejemplo anterior puede escribirse como sigue para cumplir con esta regla:

[!code-csharp[task-returning-async](~/samples/snippets/standard/buffers/memory-t/void-returning-async/void-returning-async.cs#1)]

En este caso, "estado terminal" significa que Task cambia a un estado completado, con errores o cancelado. Es decir, "estado terminal" significa "todo lo que provocaría esperar a que se inicie o continuar la ejecución".

Esta guía se aplica a los métodos que devuelven <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask%601> o cualquier tipo similar.

**Regla 5: Si el constructor acepta Memory\<T> como un parámetro, se da por sentado que los métodos de instancia del objeto construido son los consumidores de la instancia de Memory\<T>.**

Considere el ejemplo siguiente:

```csharp
class OddValueExtractor
{
    public OddValueExtractor(ReadOnlyMemory<int> input);
    public bool TryReadNextOddValue(out int value);
}

void PrintAllOddValues(ReadOnlyMemory<int> input)
{
    var extractor = new OddValueExtractor(input);
    while (extractor.TryReadNextOddValue(out int value))
    {
      Console.WriteLine(value);
    }
}
```

En este caso, el constructor `OddValueExtractor` acepta `ReadOnlyMemory<int>` como un parámetro de constructor, por lo que el propio constructor es un consumidor de la instancia de `ReadOnlyMemory<int>` y todos los métodos de instancia del valor devuelto también son los consumidores de la instancia de `ReadOnlyMemory<int>` original. Esto significa que `TryReadNextOddValue` consume la instancia de `ReadOnlyMemory<int>`, aunque no se pasa directamente al método `TryReadNextOddValue`.

**Regla 6: Si tiene una propiedad con el tipo Memory\<T> configurable (o un método de instancia equivalente) en su tipo, se da por sentado que los métodos de instancia de ese objeto son los consumidores de la instancia de Memory\<T>.**

Se trata simplemente una variante de la regla 5. Esta regla existe porque se supone que los establecedores de propiedades o métodos equivalentes capturan y conservan sus entradas, por lo que los métodos de instancia del mismo objeto pueden utilizar el estado capturado.

En el ejemplo siguiente se infringe esta regla:

```csharp
class Person
{
    // Settable property.
    public Memory<char> FirstName { get; set; }

    // alternatively, equivalent "setter" method
    public SetFirstName(Memory<char> value);

    // alternatively, a public settable field
    public Memory<char> FirstName;
}
```

**Regla 7: Si tiene una referencia de IMemoryOwner\<T>, en algún punto, debe eliminarla o transferir su propiedad (pero no ambas cosas).**

Puesto que una instancia de <xref:System.Memory%601> puede estar respaldada por la memoria administrada o no administrada, el propietario debe llamar a <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> cuando se completa el trabajo realizado en la instancia de <xref:System.Memory%601>. Como alternativa, el propietario puede transferir la propiedad de la instancia de <xref:System.Buffers.IMemoryOwner%601> a un componente diferente, momento en que el componente de adquisición pasa a ser responsable de llamar a <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> en el momento adecuado (se ofrece más información sobre esto más adelante).

Si no se llama al método <xref:System.Buffers.MemoryPool%601.Dispose%2A> correctamente, se pueden producir fugas de memoria no administrada u otra degradación del rendimiento.

Esta regla también se aplica al código que llama a métodos de fábrica como <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType>. El autor de llamada pasa a ser el propietario de la instancia de <xref:System.Buffers.IMemoryOwner%601> devuelta y es responsable de la eliminación de dicha instancia cuando se termina.

**Regla 8: Si tiene un parámetro IMemoryOwner\<T> en la superficie de API, implica la aceptación de la propiedad de esa instancia.**

Aceptar una instancia de este tipo indica que el componente intenta tomar posesión de esta instancia. El componente pasa a ser responsable de la correcta eliminación según la regla 7.

Cualquier componente que transfiere la propiedad de la instancia de <xref:System.Buffers.IMemoryOwner%601> a un componente diferente ya no debe utilizar esa instancia una vez finalizada la llamada al método.

> [!IMPORTANT]
> Si el constructor acepta <xref:System.Buffers.IMemoryOwner%601> como un parámetro, su tipo debe implementar <xref:System.IDisposable>y el método <xref:System.IDisposable.Dispose%2A> debe llamar a <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType>.

**Regla 9: Si está encapsulando un método p/invoke sincrónico, la API debe aceptar Span\<T> como parámetro.**

Según la regla 1, <xref:System.Span%601> es normalmente el tipo correcto que se usará para las API sincrónicas. Puede anclar instancias de <xref:System.Span%601> a través de la palabra clave [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md), como en el ejemplo siguiente.

```csharp
using System.Runtime.InteropServices;

[DllImport(...)]
private static extern unsafe int ExportedMethod(byte* pbData, int cbData);

public unsafe int ManagedWrapper(Span<byte> data)
{
    fixed (byte* pbData = &MemoryMarshal.GetReference(data))
    {
        int retVal = ExportedMethod(pbData, data.Length);

        /* error checking retVal goes here */

        return retVal;
    }
}
```

En el ejemplo anterior, `pbData` puede ser NULL si, por ejemplo, el intervalo de entrada está vacío. Si el método exportado requiera absolutamente que `pbData` tenga un valor distinto de NULL, aunque `cbData` sea 0, el método puede implementarse como sigue:

```csharp
public unsafe int ManagedWrapper(Span<byte> data)
{
    fixed (byte* pbData = &MemoryMarshal.GetReference(data))
    {
        byte dummy = 0;
        int retVal = ExportedMethod((pbData != null) ? pbData : &dummy, data.Length);

        /* error checking retVal goes here */

        return retVal;
    }
}
```

**Regla 10: Si está encapsulando un método p/invoke asincrónico, la API debe aceptar Memory\<T> como parámetro.**

Puesto que no se puede utilizar la palabra clave [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) en las operaciones asincrónicas, use el método <xref:System.Memory%601.Pin%2A?displayProperty=nameWithType> para anclar instancias de <xref:System.Memory%601>, independientemente del tipo de memoria contigua que represente la instancia. En el ejemplo siguiente se muestra cómo utilizar esta API para realizar una llamada p/invoke asincrónica.

```csharp
using System.Runtime.InteropServices;

[UnmanagedFunctionPointer(...)]
private delegate void OnCompletedCallback(IntPtr state, int result);

[DllImport(...)]
private static extern unsafe int ExportedAsyncMethod(byte* pbData, int cbData, IntPtr pState, IntPtr lpfnOnCompletedCallback);

private static readonly IntPtr _callbackPtr = GetCompletionCallbackPointer();

public unsafe Task<int> ManagedWrapperAsync(Memory<byte> data)
{
    // setup
    var tcs = new TaskCompletionSource<int>();
    var state = new MyCompletedCallbackState
    {
        Tcs = tcs
    };
    var pState = (IntPtr)GCHandle.Alloc(state);

    var memoryHandle = data.Pin();
    state.MemoryHandle = memoryHandle;

    // make the call
    int result;
    try
    {
        result = ExportedAsyncMethod((byte*)memoryHandle.Pointer, data.Length, pState, _callbackPtr);
    }
    catch
    {
        ((GCHandle)pState).Free(); // cleanup since callback won't be invoked
        memoryHandle.Dispose();
        throw;
    }

    if (result != PENDING)
    {
        // Operation completed synchronously; invoke callback manually
        // for result processing and cleanup.
        MyCompletedCallbackImplementation(pState, result);
    }

    return tcs.Task;
}

private static void MyCompletedCallbackImplementation(IntPtr state, int result)
{
    GCHandle handle = (GCHandle)state;
    var actualState = (MyCompletedCallbackState)(handle.Target);
    handle.Free();
    actualState.MemoryHandle.Dispose();

    /* error checking result goes here */

    if (error)
    {
        actualState.Tcs.SetException(...);
    }
    else
    {
        actualState.Tcs.SetResult(result);
    }
}

private static IntPtr GetCompletionCallbackPointer()
{
    OnCompletedCallback callback = MyCompletedCallbackImplementation;
    GCHandle.Alloc(callback); // keep alive for lifetime of application
    return Marshal.GetFunctionPointerForDelegate(callback);
}

private class MyCompletedCallbackState
{
    public TaskCompletionSource<int> Tcs;
    public MemoryHandle MemoryHandle;
}
```

## <a name="see-also"></a>Vea también

- <xref:System.Memory%601?displayProperty=nameWithType>
- <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>
- <xref:System.Span%601?displayProperty=nameWithType>
