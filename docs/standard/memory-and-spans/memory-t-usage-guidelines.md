---
title: Instrucciones de uso de Memory<T> y Span<T>
description: En este artículo se describen Memory<T> y Span<T>, que son búferes de datos estructurados en .NET Core que se pueden usar en las canalizaciones.
ms.date: 10/01/2018
helpviewer_keywords:
- Memory&lt;T&gt; and Span&lt;T&gt; best practices
- using Memory&lt;T&gt; and Span&lt;T&gt;
ms.openlocfilehash: b9405d746c141308c7d984dac9da0d65d1048d1e
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380014"
---
# <a name="memoryt-and-spant-usage-guidelines"></a><span data-ttu-id="d57b1-103">Instrucciones de uso de Memory\<T> y Span\<T></span><span class="sxs-lookup"><span data-stu-id="d57b1-103">Memory\<T> and Span\<T> usage guidelines</span></span>

<span data-ttu-id="d57b1-104">.NET Core incluye una serie de tipos que representan una región contigua y arbitraria de memoria.</span><span class="sxs-lookup"><span data-stu-id="d57b1-104">.NET Core includes a number of types that represent an arbitrary contiguous region of memory.</span></span> <span data-ttu-id="d57b1-105">.NET Core 2.0 introdujo <xref:System.Span%601> y <xref:System.ReadOnlySpan%601>, que son búferes de memoria ligera que se puede respaldar por la memoria administrada o no administrada.</span><span class="sxs-lookup"><span data-stu-id="d57b1-105">.NET Core 2.0 introduced <xref:System.Span%601> and <xref:System.ReadOnlySpan%601>, which are lightweight memory buffers that can be backed by managed or unmanaged memory.</span></span> <span data-ttu-id="d57b1-106">Dado que estos tipos solo se pueden almacenar en la pila, no son aptos para una serie de escenarios, incluidas las llamadas de método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="d57b1-106">Because these types can only be stored on the stack, they are unsuitable for a number of scenarios, including asynchronous method calls.</span></span> <span data-ttu-id="d57b1-107">.NET Core 2.1 agrega numerosos tipos adicionales, incluidos <xref:System.Memory%601>, <xref:System.ReadOnlyMemory%601>, <xref:System.Buffers.IMemoryOwner%601> y <xref:System.Buffers.MemoryPool%601>.</span><span class="sxs-lookup"><span data-stu-id="d57b1-107">.NET Core 2.1 adds a number of additional types, including <xref:System.Memory%601>, <xref:System.ReadOnlyMemory%601>, <xref:System.Buffers.IMemoryOwner%601>, and <xref:System.Buffers.MemoryPool%601>.</span></span> <span data-ttu-id="d57b1-108">Al igual que <xref:System.Span%601>, <xref:System.Memory%601> y sus tipos relacionados pueden estar respaldados por la memoria administrada y no administrada.</span><span class="sxs-lookup"><span data-stu-id="d57b1-108">Like <xref:System.Span%601>, <xref:System.Memory%601> and its related types can be backed by both managed and unmanaged memory.</span></span> <span data-ttu-id="d57b1-109">A diferencia de <xref:System.Span%601>, <xref:System.Memory%601> se puede almacenar en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="d57b1-109">Unlike <xref:System.Span%601>, <xref:System.Memory%601> can be stored on the managed heap.</span></span>

<span data-ttu-id="d57b1-110"><xref:System.Span%601> y <xref:System.Memory%601> son los búferes de datos estructurados que se pueden usar en las canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="d57b1-110">Both <xref:System.Span%601> and <xref:System.Memory%601> are buffers of structured data that can be used in pipelines.</span></span> <span data-ttu-id="d57b1-111">Es decir, están diseñados para que parte de los datos, o todos, se pueda pasar de forma eficaz a los componentes de la canalización, que puede procesarlos y, opcionalmente, modifique el búfer.</span><span class="sxs-lookup"><span data-stu-id="d57b1-111">That is, they are designed so that some or all of the data can be efficiently passed to components in the pipeline, which can process them and optionally modify the buffer.</span></span> <span data-ttu-id="d57b1-112">Como varios componentes o subprocesos pueden acceder a <xref:System.Memory%601> y sus tipos relacionados, es importante que los desarrolladores sigan algunas directrices de uso estándar para crear código sólido.</span><span class="sxs-lookup"><span data-stu-id="d57b1-112">Because <xref:System.Memory%601> and its related types can be accessed by multiple components or by multiple threads, it's important that developers follow some standard usage guidelines to produce robust code.</span></span>

## <a name="owners-consumers-and-lifetime-management"></a><span data-ttu-id="d57b1-113">Propietarios, consumidores y administración de la duración</span><span class="sxs-lookup"><span data-stu-id="d57b1-113">Owners, consumers, and lifetime management</span></span>

<span data-ttu-id="d57b1-114">Puesto que los búferes se pueden pasar entre las API, y que se, a veces, se puede acceder a los búferes desde varios subprocesos, es importante tener en cuenta la administración de la duración.</span><span class="sxs-lookup"><span data-stu-id="d57b1-114">Since buffers can be passed around between APIs, and since buffers can sometimes be accessed from multiple threads, it's important to consider lifetime management.</span></span> <span data-ttu-id="d57b1-115">Hay tres conceptos principales:</span><span class="sxs-lookup"><span data-stu-id="d57b1-115">There are three core concepts:</span></span>

- <span data-ttu-id="d57b1-116">**Propiedad**.</span><span class="sxs-lookup"><span data-stu-id="d57b1-116">**Ownership**.</span></span> <span data-ttu-id="d57b1-117">El propietario de una instancia de búfer es responsable de la administración de la duración, por ejemplo, destruir el búfer cuando ya no se use.</span><span class="sxs-lookup"><span data-stu-id="d57b1-117">The owner of a buffer instance is responsible for lifetime management, including destroying the buffer when it's no longer in use.</span></span> <span data-ttu-id="d57b1-118">Todos los búferes tienen un único propietario.</span><span class="sxs-lookup"><span data-stu-id="d57b1-118">All buffers have a single owner.</span></span> <span data-ttu-id="d57b1-119">Por lo general, el propietario es el componente que creó el búfer o que recibió el búfer de una fábrica.</span><span class="sxs-lookup"><span data-stu-id="d57b1-119">Generally the owner is the component that created the buffer or that received the buffer from a factory.</span></span> <span data-ttu-id="d57b1-120">También se puede transferir la propiedad; **Component-A** puede ceder el control del búfer a **Component-B**, momento en que **Component-A** ya no puede usar más el búfer, y **Component-B** pasa a ser responsable de destruir el búfer cuando ya no se usa.</span><span class="sxs-lookup"><span data-stu-id="d57b1-120">Ownership can also be transferred; **Component-A** can relinquish control of the buffer to **Component-B**, at which point **Component-A** may no longer use the buffer, and **Component-B** becomes responsible for destroying the buffer when it's no longer in use.</span></span>

- <span data-ttu-id="d57b1-121">**Consumo**.</span><span class="sxs-lookup"><span data-stu-id="d57b1-121">**Consumption**.</span></span> <span data-ttu-id="d57b1-122">El consumidor de una instancia de búfer puede usar la instancia de búfer leyéndolo y, posiblemente, escribir en él.</span><span class="sxs-lookup"><span data-stu-id="d57b1-122">The consumer of a buffer instance is allowed to use the buffer instance by reading from it and possibly writing to it.</span></span> <span data-ttu-id="d57b1-123">Los búferes pueden tener un consumidor a la vez, a menos que se proporcione algún mecanismo de sincronización externo.</span><span class="sxs-lookup"><span data-stu-id="d57b1-123">Buffers can have one consumer at a time unless some external synchronization mechanism is provided.</span></span> <span data-ttu-id="d57b1-124">El consumidor activo de un búfer no es necesariamente el propietario del búfer.</span><span class="sxs-lookup"><span data-stu-id="d57b1-124">The active consumer of a buffer isn't necessarily the buffer's owner.</span></span>

- <span data-ttu-id="d57b1-125">**Concesión**.</span><span class="sxs-lookup"><span data-stu-id="d57b1-125">**Lease**.</span></span> <span data-ttu-id="d57b1-126">La concesión es el período durante el cual un componente concreto puede ser el consumidor del búfer.</span><span class="sxs-lookup"><span data-stu-id="d57b1-126">The lease is the length of time that a particular component is allowed to be the consumer of the buffer.</span></span>

<span data-ttu-id="d57b1-127">En el ejemplo de pseudocódigo siguiente se muestran estos tres conceptos.</span><span class="sxs-lookup"><span data-stu-id="d57b1-127">The following pseudo-code example illustrates these three concepts.</span></span> <span data-ttu-id="d57b1-128">Incluye un método `Main` que crea una instancia de un búfer <xref:System.Memory%601> de tipo <xref:System.Char>, llama al método `WriteInt32ToBuffer` para escribir la representación de cadena de un entero en el búfer y, después, llama al método `DisplayBufferToConsole` para mostrar el valor del búfer.</span><span class="sxs-lookup"><span data-stu-id="d57b1-128">It includes a `Main` method that instantiates a <xref:System.Memory%601> buffer of type <xref:System.Char>, calls the `WriteInt32ToBuffer` method to write the string representation of an integer to the buffer, and then calls the `DisplayBufferToConsole` method to display the value of the buffer.</span></span>

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

<span data-ttu-id="d57b1-129">El método `Main` crea el búfer (en este caso, una instancia de <xref:System.Span%601>); el propietario.</span><span class="sxs-lookup"><span data-stu-id="d57b1-129">The `Main` method creates the buffer (in this case an <xref:System.Span%601> instance) and so is its owner.</span></span> <span data-ttu-id="d57b1-130">Por lo tanto, `Main` es responsable de destruir el búfer cuando ya no se usa.</span><span class="sxs-lookup"><span data-stu-id="d57b1-130">Therefore, `Main` is responsible for destroying the buffer when it's no longer in use.</span></span> <span data-ttu-id="d57b1-131">Esto se hace llamando al método <xref:System.Span%601.Clear?displayProperty=nameWithType> del búfer.</span><span class="sxs-lookup"><span data-stu-id="d57b1-131">It does this by calling the buffer's <xref:System.Span%601.Clear?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d57b1-132">El método <xref:System.Span%601.Clear> realmente borra la memoria del búfer; la estructura <xref:System.Span%601> no tiene en realidad un método que destruya el búfer.</span><span class="sxs-lookup"><span data-stu-id="d57b1-132">(The <xref:System.Span%601.Clear> method here actually clears the buffer's memory; the <xref:System.Span%601> structure doesn't actually have a method that destroys the buffer.)</span></span>

<span data-ttu-id="d57b1-133">El búfer tiene dos consumidores, `WriteInt32ToBuffer` y `DisplayBufferToConsole`.</span><span class="sxs-lookup"><span data-stu-id="d57b1-133">The buffer has two consumers, `WriteInt32ToBuffer` and `DisplayBufferToConsole`.</span></span> <span data-ttu-id="d57b1-134">Hay solo un consumidor a la vez (primero `WriteInt32ToBuffer` y, luego, `DisplayBufferToConsole`), y ninguno de los consumidores posee el búfer.</span><span class="sxs-lookup"><span data-stu-id="d57b1-134">There is only one consumer at a time (first `WriteInt32ToBuffer`, then `DisplayBufferToConsole`), and neither of the consumers owns the buffer.</span></span> <span data-ttu-id="d57b1-135">Tenga en cuenta también que "consumidor" en este contexto no implica una vista de solo lectura del búfer; los consumidores pueden modificar el contenido del búfer, como `WriteInt32ToBuffer`, si se proporciona una vista de lectura/escritura del búfer.</span><span class="sxs-lookup"><span data-stu-id="d57b1-135">Note also that "consumer" in this context doesn't imply a read-only view of the buffer; consumers can modify the buffer's contents, as `WriteInt32ToBuffer` does, if given a read/write view of the buffer.</span></span>

<span data-ttu-id="d57b1-136">El método `WriteInt32ToBuffer` tiene una concesión (pueden consumir) sobre el búfer entre el inicio de la llamada al método y el momento en que se devuelve el método.</span><span class="sxs-lookup"><span data-stu-id="d57b1-136">The `WriteInt32ToBuffer` method has a lease on (can consume) the buffer between the start of the method call and the time the method returns.</span></span> <span data-ttu-id="d57b1-137">De forma similar, `DisplayBufferToConsole` tiene una concesión sobre el búfer mientras se ejecuta, y se libera cuando se desenreda el método.</span><span class="sxs-lookup"><span data-stu-id="d57b1-137">Similarly, `DisplayBufferToConsole` has a lease on the buffer while it's executing, and the lease is released when the method unwinds.</span></span> <span data-ttu-id="d57b1-138">No hay ninguna API para administrar concesiones; la "concesión" es una cuestión conceptual.</span><span class="sxs-lookup"><span data-stu-id="d57b1-138">(There is no API for lease management; a "lease" is a conceptual matter.)</span></span>

## <a name="memoryt-and-the-ownerconsumer-model"></a><span data-ttu-id="d57b1-139">Memory\<T> y el modelo de consumidor y propietario</span><span class="sxs-lookup"><span data-stu-id="d57b1-139">Memory\<T> and the owner/consumer model</span></span>

<span data-ttu-id="d57b1-140">Como se indica en la sección [Propietarios, consumidores y administración de la duración](#owners-consumers-and-lifetime-management), un búfer siempre tiene un propietario.</span><span class="sxs-lookup"><span data-stu-id="d57b1-140">As the [Owners, consumers, and lifetime management](#owners-consumers-and-lifetime-management) section notes, a buffer always has an owner.</span></span> <span data-ttu-id="d57b1-141">.NET Core admite dos modelos de propiedad:</span><span class="sxs-lookup"><span data-stu-id="d57b1-141">.NET Core supports two ownership models:</span></span>

- <span data-ttu-id="d57b1-142">Un modelo que admite la propiedad única.</span><span class="sxs-lookup"><span data-stu-id="d57b1-142">A model that supports single ownership.</span></span> <span data-ttu-id="d57b1-143">Un búfer tiene un propietario único para toda su duración.</span><span class="sxs-lookup"><span data-stu-id="d57b1-143">A buffer has a single owner for its entire lifetime.</span></span>

- <span data-ttu-id="d57b1-144">Un modelo que admite la transferencia de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="d57b1-144">A model that supports ownership transfer.</span></span> <span data-ttu-id="d57b1-145">La propiedad de un búfer se puede transferir desde el propietario original (su creador) a otro componente, que, luego, pasa a ser responsable de la administración de la duración del búfer.</span><span class="sxs-lookup"><span data-stu-id="d57b1-145">Ownership of a buffer can be transferred from its original owner (its creator) to another component, which then becomes responsible for the buffer's lifetime management.</span></span> <span data-ttu-id="d57b1-146">Ese propietario, a su vez, puede transferir la propiedad a otro componente, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="d57b1-146">That owner can in turn transfer ownership to another component, and so on.</span></span>

<span data-ttu-id="d57b1-147">Usa la interfaz <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType> para administrar explícitamente la propiedad de un búfer.</span><span class="sxs-lookup"><span data-stu-id="d57b1-147">You use the <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType> interface to explicitly manage the ownership of a buffer.</span></span> <span data-ttu-id="d57b1-148"><xref:System.Buffers.IMemoryOwner%601> es compatible con ambos modelos de propiedad.</span><span class="sxs-lookup"><span data-stu-id="d57b1-148"><xref:System.Buffers.IMemoryOwner%601> supports both ownership models.</span></span> <span data-ttu-id="d57b1-149">El componente que tiene una referencia de <xref:System.Buffers.IMemoryOwner%601> posee el búfer.</span><span class="sxs-lookup"><span data-stu-id="d57b1-149">The component that has an <xref:System.Buffers.IMemoryOwner%601> reference owns the buffer.</span></span> <span data-ttu-id="d57b1-150">En el ejemplo siguiente se usa una instancia de <xref:System.Buffers.IMemoryOwner%601?> para reflejar la propiedad de un búfer de <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="d57b1-150">The following example uses an <xref:System.Buffers.IMemoryOwner%601?> instance to reflect the ownership of an <xref:System.Memory%601> buffer.</span></span>

[!code-csharp[ownership](~/samples/snippets/standard/buffers/memory-t/owner/owner.cs)]

<span data-ttu-id="d57b1-151">También podemos escribir este ejemplo con [`using`](../../csharp/language-reference/keywords/using-statement.md):</span><span class="sxs-lookup"><span data-stu-id="d57b1-151">We can also write this example with the [`using`](../../csharp/language-reference/keywords/using-statement.md):</span></span>

[!code-csharp[ownership-using](~/samples/snippets/standard/buffers/memory-t/owner-using/owner-using.cs)]

<span data-ttu-id="d57b1-152">En este código:</span><span class="sxs-lookup"><span data-stu-id="d57b1-152">In this code:</span></span>

- <span data-ttu-id="d57b1-153">El método `Main` contiene la referencia a la instancia de <xref:System.Buffers.IMemoryOwner%601>, por lo que el método `Main` es el propietario del búfer.</span><span class="sxs-lookup"><span data-stu-id="d57b1-153">The `Main` method holds the reference to the <xref:System.Buffers.IMemoryOwner%601> instance, so the `Main` method is the owner of the buffer.</span></span>

- <span data-ttu-id="d57b1-154">Los métodos `WriteInt32ToBuffer` y `DisplayBufferToConsole` aceptan <xref:System.Memory%601> como API pública.</span><span class="sxs-lookup"><span data-stu-id="d57b1-154">The `WriteInt32ToBuffer` and `DisplayBufferToConsole` methods accept <xref:System.Memory%601> as a public API.</span></span> <span data-ttu-id="d57b1-155">Por lo tanto, son consumidores del búfer.</span><span class="sxs-lookup"><span data-stu-id="d57b1-155">Therefore, they are consumers of the buffer.</span></span> <span data-ttu-id="d57b1-156">Y solo lo consumen de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="d57b1-156">And they only consume it one at a time.</span></span>

<span data-ttu-id="d57b1-157">Aunque el método `WriteInt32ToBuffer` está diseñado para escribir un valor en el búfer, el método`DisplayBufferToConsole`, no.</span><span class="sxs-lookup"><span data-stu-id="d57b1-157">Although the `WriteInt32ToBuffer` method is intended to write a value to the buffer, the `DisplayBufferToConsole` method isn't.</span></span> <span data-ttu-id="d57b1-158">Para reflejar esto, podría haber aceptado un argumento de tipo <xref:System.ReadOnlyMemory%601>.</span><span class="sxs-lookup"><span data-stu-id="d57b1-158">To reflect this, it could have accepted an argument of type <xref:System.ReadOnlyMemory%601>.</span></span> <span data-ttu-id="d57b1-159">Para más información sobre <xref:System.ReadOnlyMemory%601>, vea [Regla 2: Use ReadOnlySpan\<T> o ReadOnlyMemory\<T> si el búfer debe ser de solo lectura](#rule-2).</span><span class="sxs-lookup"><span data-stu-id="d57b1-159">For more information on <xref:System.ReadOnlyMemory%601>, see [Rule #2: Use ReadOnlySpan\<T> or ReadOnlyMemory\<T> if the buffer should be read-only](#rule-2).</span></span>

### <a name="ownerless-memoryt-instances"></a><span data-ttu-id="d57b1-160">Instancias de Memory\<T> "sin propietario"</span><span class="sxs-lookup"><span data-stu-id="d57b1-160">"Ownerless" Memory\<T> instances</span></span>

<span data-ttu-id="d57b1-161">Puede crear una instancia de <xref:System.Memory%601> sin usar <xref:System.Buffers.IMemoryOwner%601>.</span><span class="sxs-lookup"><span data-stu-id="d57b1-161">You can create a <xref:System.Memory%601> instance without using <xref:System.Buffers.IMemoryOwner%601>.</span></span> <span data-ttu-id="d57b1-162">En este caso, la propiedad del búfer está implícita en lugar de explícita, y solo se admite el modelo de propietario único.</span><span class="sxs-lookup"><span data-stu-id="d57b1-162">In this case, ownership of the buffer is implicit rather than explicit, and only the single-owner model is supported.</span></span> <span data-ttu-id="d57b1-163">Puede hacerlo de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="d57b1-163">You can do this by:</span></span>

- <span data-ttu-id="d57b1-164">Llamar a uno de los constructores <xref:System.Memory%601> directamente, pasando un búfer `T[]`, como en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d57b1-164">Calling one of the  <xref:System.Memory%601> constructors directly, passing in a `T[]`, as the following example does.</span></span>

- <span data-ttu-id="d57b1-165">Llamar al método de extensión [String.AsMemory](xref:System.MemoryExtensions.AsMemory(System.String)) para generar una instancia de `ReadOnlyMemory<char>`.</span><span class="sxs-lookup"><span data-stu-id="d57b1-165">Calling the [String.AsMemory](xref:System.MemoryExtensions.AsMemory(System.String)) extension method to produce a `ReadOnlyMemory<char>` instance.</span></span>

[!code-csharp[ownerless-memory](~/samples/snippets/standard/buffers/memory-t/ownerless/ownerless.cs)]

<span data-ttu-id="d57b1-166">El método que crea inicialmente la instancia de <xref:System.Memory%601> es el propietario implícito del búfer.</span><span class="sxs-lookup"><span data-stu-id="d57b1-166">The method that initially creates the <xref:System.Memory%601> instance is the implicit owner of the buffer.</span></span> <span data-ttu-id="d57b1-167">No se puede transferir la propiedad a cualquier otro componente porque no hay ninguna instancia de <xref:System.Buffers.IMemoryOwner%601> que facilite la transferencia.</span><span class="sxs-lookup"><span data-stu-id="d57b1-167">Ownership cannot be transferred to any other component because there is no <xref:System.Buffers.IMemoryOwner%601> instance to facilitate the transfer.</span></span> <span data-ttu-id="d57b1-168">Como alternativa, puede también imaginarse que el recolector de elementos no utilizados del entorno de ejecución contiene el búfer, y todos los métodos simplemente consumen el búfer.</span><span class="sxs-lookup"><span data-stu-id="d57b1-168">(As an alternative, you can also imagine that the runtime's garbage collector owns the buffer, and all methods just consume the buffer.)</span></span>

## <a name="usage-guidelines"></a><span data-ttu-id="d57b1-169">Instrucciones de uso</span><span class="sxs-lookup"><span data-stu-id="d57b1-169">Usage guidelines</span></span>

<span data-ttu-id="d57b1-170">Dado que un bloque de memoria tiene un propietario, pero está diseñado para pasarse a varios componentes, algunos de los cuales pueden funcionar en un bloque de memoria específica al mismo tiempo, es importante establecer instrucciones para usar <xref:System.Memory%601> y <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="d57b1-170">Because a memory block is owned but is intended to be passed to multiple components, some of which may operate upon a particular memory block simultaneously, it is important to establish guidelines for using both <xref:System.Memory%601> and <xref:System.Span%601>.</span></span>  <span data-ttu-id="d57b1-171">Estas instrucciones son necesarias por los siguientes motivos:</span><span class="sxs-lookup"><span data-stu-id="d57b1-171">Guidelines are necessary because:</span></span>

- <span data-ttu-id="d57b1-172">Es posible que un componente conserve una referencia a un bloque de memoria después de que su propietario lo haya liberado.</span><span class="sxs-lookup"><span data-stu-id="d57b1-172">It is possible for a component to retain a reference to a memory block after its owner has released it.</span></span>

- <span data-ttu-id="d57b1-173">Un componente puede estar funcionando en un búfer al mismo tiempo que otro componente está operando en el proceso, con lo que se dañan los datos del búfer.</span><span class="sxs-lookup"><span data-stu-id="d57b1-173">It is possible for a component to operate on a buffer at the same time that another component is operating on it, in the process corrupting the data in the buffer.</span></span>

- <span data-ttu-id="d57b1-174">Si bien la naturaleza asignada a la pila de <xref:System.Span%601> optimiza el rendimiento y convierte a <xref:System.Span%601> en el tipo preferido para funcionar en un bloque de memoria, también somete a <xref:System.Span%601> a algunas restricciones principales.</span><span class="sxs-lookup"><span data-stu-id="d57b1-174">While the stack-allocated nature of <xref:System.Span%601> optimizes performance and makes <xref:System.Span%601> the preferred type for operating on a memory block, it also subjects <xref:System.Span%601> to some major restrictions.</span></span> <span data-ttu-id="d57b1-175">Es importante saber cuándo usar <xref:System.Span%601> y <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="d57b1-175">It is important to know when to use a <xref:System.Span%601> and when to use <xref:System.Memory%601>.</span></span>

<span data-ttu-id="d57b1-176">A continuación, se muestran recomendaciones para usar correctamente <xref:System.Memory%601> y sus tipos relacionados.</span><span class="sxs-lookup"><span data-stu-id="d57b1-176">The following are our recommendations for successfully using <xref:System.Memory%601> and its related types.</span></span> <span data-ttu-id="d57b1-177">Las instrucciones que se aplican a <xref:System.Memory%601> y a <xref:System.Span%601> son válidas también para <xref:System.ReadOnlyMemory%601> y <xref:System.ReadOnlySpan%601>, a menos que se indique expresamente lo contrario.</span><span class="sxs-lookup"><span data-stu-id="d57b1-177">Guidance that applies to <xref:System.Memory%601> and <xref:System.Span%601> also applies to <xref:System.ReadOnlyMemory%601> and <xref:System.ReadOnlySpan%601> unless we explicitly note otherwise.</span></span>

<span data-ttu-id="d57b1-178">**Regla 1: Para una API sincrónica, use Span\<T> en lugar de Memory\<T> como un parámetro si es posible.**</span><span class="sxs-lookup"><span data-stu-id="d57b1-178">**Rule #1: For a synchronous API, use Span\<T> instead of Memory\<T> as a parameter if possible.**</span></span>

<span data-ttu-id="d57b1-179"><xref:System.Span%601> es más versátil que <xref:System.Memory%601> y puede representar una amplia variedad de búferes de memoria contigua.</span><span class="sxs-lookup"><span data-stu-id="d57b1-179"><xref:System.Span%601> is more versatile than <xref:System.Memory%601> and can represent a wider variety of contiguous memory buffers.</span></span> <span data-ttu-id="d57b1-180"><xref:System.Span%601> también ofrece mayor rendimiento que <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="d57b1-180"><xref:System.Span%601> also offers better performance than <xref:System.Memory%601>.</span></span> <span data-ttu-id="d57b1-181">Finalmente, puede usar la propiedad <xref:System.Memory%601.Span?displayProperty=nameWithType> para convertir una instancia de <xref:System.Memory%601> a <xref:System.Span%601>, aunque la conversión de Span\<T> a Memory \<T> no se puede realizar.</span><span class="sxs-lookup"><span data-stu-id="d57b1-181">Finally, you can use the <xref:System.Memory%601.Span?displayProperty=nameWithType> property to convert a <xref:System.Memory%601> instance to a <xref:System.Span%601>, although Span\<T>-to-Memory\<T> conversion isn't possible.</span></span> <span data-ttu-id="d57b1-182">Por tanto, si los autores de llamada tienen una instancia de <xref:System.Memory%601>, pueden llamar a los métodos con parámetros <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="d57b1-182">So if your callers happen to have a <xref:System.Memory%601> instance, they'll be able to call your methods with <xref:System.Span%601> parameters anyway.</span></span>

<span data-ttu-id="d57b1-183">Usar un parámetro de tipo <xref:System.Span%601> en lugar de tipo <xref:System.Memory%601> también ayuda a escribir una implementación de método de consumo correcta.</span><span class="sxs-lookup"><span data-stu-id="d57b1-183">Using a parameter of type <xref:System.Span%601> instead of type <xref:System.Memory%601> also helps you write a correct consuming method implementation.</span></span> <span data-ttu-id="d57b1-184">Obtendrá automáticamente comprobaciones en tiempo de compilación para asegurarse de que no está tratando de acceder al búfer más allá de la concesión del método (encontrará más información sobre esto más adelante).</span><span class="sxs-lookup"><span data-stu-id="d57b1-184">You'll automatically get compile-time checks to ensure that you're not attempting to access the buffer beyond your method's lease (more on this later).</span></span>

<span data-ttu-id="d57b1-185">En ocasiones, tendrá que usar un parámetro <xref:System.Memory%601> en lugar de <xref:System.Span%601>, aunque sea un método completamente sincrónico.</span><span class="sxs-lookup"><span data-stu-id="d57b1-185">Sometimes, you'll have to use a <xref:System.Memory%601> parameter instead of a <xref:System.Span%601> parameter, even if you're fully synchronous.</span></span> <span data-ttu-id="d57b1-186">Quizás, una API de la que depende solo acepta argumentos <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="d57b1-186">Perhaps an API that you depend accepts only <xref:System.Memory%601> arguments.</span></span> <span data-ttu-id="d57b1-187">Aunque es correcto, debe ser consciente de los inconvenientes que implica usar <xref:System.Memory%601> sincrónicamente.</span><span class="sxs-lookup"><span data-stu-id="d57b1-187">This is fine, but be aware of the tradeoffs involved when using <xref:System.Memory%601> synchronously.</span></span>

<a name="rule-2" />

<span data-ttu-id="d57b1-188">**Regla 2: Use ReadOnlySpan\<T> o ReadOnlyMemory\<T> si el búfer debe ser de solo lectura.**</span><span class="sxs-lookup"><span data-stu-id="d57b1-188">**Rule #2: Use ReadOnlySpan\<T> or ReadOnlyMemory\<T> if the buffer should be read-only.**</span></span>

<span data-ttu-id="d57b1-189">En los ejemplos anteriores, el método `DisplayBufferToConsole` solo lee del búfer, no modifica su contenido.</span><span class="sxs-lookup"><span data-stu-id="d57b1-189">In the earlier examples, the `DisplayBufferToConsole` method only reads from the buffer; it doesn't modify the contents of the buffer.</span></span> <span data-ttu-id="d57b1-190">La firma del método se debe cambiar a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="d57b1-190">The method signature should be changed to the following.</span></span>

```csharp
void DisplayBufferToConsole(ReadOnlyMemory<char> buffer);
```

<span data-ttu-id="d57b1-191">De hecho, si se combinan esta regla y la 1, podemos hacerlo incluso mejor y reescribir la firma del método como sigue:</span><span class="sxs-lookup"><span data-stu-id="d57b1-191">In fact, if we combine this rule and Rule #1, we can do even better and rewrite the method signature as follows:</span></span>

```csharp
void DisplayBufferToConsole(ReadOnlySpan<char> buffer);
```

<span data-ttu-id="d57b1-192">El método `DisplayBufferToConsole` ahora funciona con prácticamente cualquier tipo de búfer imaginable: `T[]`, almacenamiento asignable con [stackalloc](../../csharp/language-reference/operators/stackalloc.md) y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="d57b1-192">The `DisplayBufferToConsole` method now works with virtually every buffer type imaginable: `T[]`, storage allocated with [stackalloc](../../csharp/language-reference/operators/stackalloc.md), and so on.</span></span> <span data-ttu-id="d57b1-193">Incluso puede pasar una clase <xref:System.String> directamente.</span><span class="sxs-lookup"><span data-stu-id="d57b1-193">You can even pass a <xref:System.String> directly into it!</span></span>

<span data-ttu-id="d57b1-194">**Regla 3: Si el método acepta Memory\<T> y devuelve `void`, no debe usar la instancia de Memory\<T> después de que se devuelva el método.**</span><span class="sxs-lookup"><span data-stu-id="d57b1-194">**Rule #3: If your method accepts Memory\<T> and returns `void`, you must not use the Memory\<T> instance after your method returns.**</span></span>

<span data-ttu-id="d57b1-195">Esto se relaciona con el concepto de "concesión" mencionado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d57b1-195">This relates to the "lease" concept mentioned earlier.</span></span> <span data-ttu-id="d57b1-196">La concesión de un método que no devuelve valores sobre la instancia de <xref:System.Memory%601> comienza cuando se especifica el método y termina cuando finaliza.</span><span class="sxs-lookup"><span data-stu-id="d57b1-196">A void-returning method's lease on the <xref:System.Memory%601> instance begins when the method is entered, and it ends when the method exits.</span></span> <span data-ttu-id="d57b1-197">Observe el ejemplo siguiente, que llama a `Log` en un bucle basado en lo especificado desde la consola.</span><span class="sxs-lookup"><span data-stu-id="d57b1-197">Consider the following example, which calls `Log` in a loop based on input from the console.</span></span>

[!code-csharp[void-returning](~/samples/snippets/standard/buffers/memory-t/void-returning/void-returning.cs#1)]

<span data-ttu-id="d57b1-198">Si `Log` es un método completamente sincrónico, este código se comportará según lo esperado porque solo hay un consumidor activo de la instancia de la memoria en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="d57b1-198">If `Log` is a fully synchronous method, this code will behave as expected because there is only one active consumer of the memory instance at any given time.</span></span>
<span data-ttu-id="d57b1-199">Pero, en lugar de esto, imagine que `Log` tiene esta implementación.</span><span class="sxs-lookup"><span data-stu-id="d57b1-199">But imagine instead that `Log` has this implementation.</span></span>

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

<span data-ttu-id="d57b1-200">En esta implementación, `Log` infringe su concesión porque sigue tratando de utilizar la instancia de <xref:System.Memory%601> en segundo plano después de que se haya devuelto el método original.</span><span class="sxs-lookup"><span data-stu-id="d57b1-200">In this implementation, `Log` violates its lease because it still attempts to use the <xref:System.Memory%601> instance in the background after the original method has returned.</span></span> <span data-ttu-id="d57b1-201">El método `Main` podría modificar el búfer mientras `Log` intenta leer desde él, lo que podría provocar daños en los datos.</span><span class="sxs-lookup"><span data-stu-id="d57b1-201">The `Main` method could mutate the buffer while `Log` attempts to read from it, which could result in data corruption.</span></span>

<span data-ttu-id="d57b1-202">Hay varias formas de solucionar esto:</span><span class="sxs-lookup"><span data-stu-id="d57b1-202">There are several ways to resolve this:</span></span>

- <span data-ttu-id="d57b1-203">El método `Log` puede devolver una clase <xref:System.Threading.Tasks.Task> en lugar de `void`, como hace la siguiente implementación del método `Log`.</span><span class="sxs-lookup"><span data-stu-id="d57b1-203">The `Log` method can return a <xref:System.Threading.Tasks.Task> instead of `void`, as the following implementation of the `Log` method does.</span></span>

   [!code-csharp[task-returning](~/samples/snippets/standard/buffers/memory-t/task-returning2/task-returning2.cs#1)]

- <span data-ttu-id="d57b1-204">`Log` se puede implementar de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="d57b1-204">`Log` can instead be implemented as follows:</span></span>

   [!code-csharp[defensive-copy](~/samples/snippets/standard/buffers/memory-t/task-returning/task-returning.cs#1)]

<span data-ttu-id="d57b1-205">**Regla 4: Si el método acepta Memory\<T> y devuelve una clase Task, no debe usar la instancia de Memory\<T> después de las transiciones de Task a un estado terminal.**</span><span class="sxs-lookup"><span data-stu-id="d57b1-205">**Rule #4: If your method accepts a Memory\<T> and returns a Task, you must not use the Memory\<T> instance after the Task transitions to a terminal state.**</span></span>

<span data-ttu-id="d57b1-206">Se trata de la variante asincrónica de la regla 3.</span><span class="sxs-lookup"><span data-stu-id="d57b1-206">This is just the async variant of Rule #3.</span></span> <span data-ttu-id="d57b1-207">El método `Log` del ejemplo anterior puede escribirse como sigue para cumplir con esta regla:</span><span class="sxs-lookup"><span data-stu-id="d57b1-207">The `Log` method from the earlier example can be written as follows to comply with this rule:</span></span>

[!code-csharp[task-returning-async](~/samples/snippets/standard/buffers/memory-t/void-returning-async/void-returning-async.cs#1)]

<span data-ttu-id="d57b1-208">En este caso, "estado terminal" significa que Task cambia a un estado completado, con errores o cancelado.</span><span class="sxs-lookup"><span data-stu-id="d57b1-208">Here, "terminal state" means that the task transitions to a completed, faulted, or canceled state.</span></span> <span data-ttu-id="d57b1-209">Es decir, "estado terminal" significa "todo lo que provocaría esperar a que se inicie o continuar la ejecución".</span><span class="sxs-lookup"><span data-stu-id="d57b1-209">In other words, "terminal state" means "anything that would cause await to throw or to continue execution."</span></span>

<span data-ttu-id="d57b1-210">Esta guía se aplica a los métodos que devuelven <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask%601> o cualquier tipo similar.</span><span class="sxs-lookup"><span data-stu-id="d57b1-210">This guidance applies to methods that return <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask%601>, or any similar type.</span></span>

<span data-ttu-id="d57b1-211">**Regla 5: Si el constructor acepta Memory\<T> como un parámetro, se da por sentado que los métodos de instancia del objeto construido son los consumidores de la instancia de Memory\<T>.**</span><span class="sxs-lookup"><span data-stu-id="d57b1-211">**Rule #5: If your constructor accepts Memory\<T> as a parameter, instance methods on the constructed object are assumed to be consumers of the Memory\<T> instance.**</span></span>

<span data-ttu-id="d57b1-212">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d57b1-212">Consider the following example:</span></span>

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

<span data-ttu-id="d57b1-213">En este caso, el constructor `OddValueExtractor` acepta `ReadOnlyMemory<int>` como un parámetro de constructor, por lo que el propio constructor es un consumidor de la instancia de `ReadOnlyMemory<int>` y todos los métodos de instancia del valor devuelto también son los consumidores de la instancia de `ReadOnlyMemory<int>` original.</span><span class="sxs-lookup"><span data-stu-id="d57b1-213">Here, the `OddValueExtractor` constructor accepts a `ReadOnlyMemory<int>` as a constructor parameter, so the constructor itself is a consumer of the `ReadOnlyMemory<int>` instance, and all instance methods on the returned value are also consumers of the original `ReadOnlyMemory<int>` instance.</span></span> <span data-ttu-id="d57b1-214">Esto significa que `TryReadNextOddValue` consume la instancia de `ReadOnlyMemory<int>`, aunque no se pasa directamente al método `TryReadNextOddValue`.</span><span class="sxs-lookup"><span data-stu-id="d57b1-214">This means that `TryReadNextOddValue` consumes the `ReadOnlyMemory<int>` instance, even though the instance isn't passed directly to the `TryReadNextOddValue` method.</span></span>

<span data-ttu-id="d57b1-215">**Regla 6: Si tiene una propiedad con el tipo Memory\<T> configurable (o un método de instancia equivalente) en su tipo, se da por sentado que los métodos de instancia de ese objeto son los consumidores de la instancia de Memory\<T>.**</span><span class="sxs-lookup"><span data-stu-id="d57b1-215">**Rule #6: If you have a settable Memory\<T>-typed property (or an equivalent instance method) on your type, instance methods on that object are assumed to be consumers of the Memory\<T> instance.**</span></span>

<span data-ttu-id="d57b1-216">Se trata simplemente una variante de la regla 5.</span><span class="sxs-lookup"><span data-stu-id="d57b1-216">This is really just a variant of Rule #5.</span></span> <span data-ttu-id="d57b1-217">Esta regla existe porque se supone que los establecedores de propiedades o métodos equivalentes capturan y conservan sus entradas, por lo que los métodos de instancia del mismo objeto pueden utilizar el estado capturado.</span><span class="sxs-lookup"><span data-stu-id="d57b1-217">This rule exists because property setters or equivalent methods are assumed to capture and persist their inputs, so instance methods on the same object may utilize the captured state.</span></span>

<span data-ttu-id="d57b1-218">En el ejemplo siguiente se infringe esta regla:</span><span class="sxs-lookup"><span data-stu-id="d57b1-218">The following example triggers this rule:</span></span>

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

<span data-ttu-id="d57b1-219">**Regla 7: Si tiene una referencia de IMemoryOwner\<T>, en algún punto, debe eliminarla o transferir su propiedad (pero no ambas cosas).**</span><span class="sxs-lookup"><span data-stu-id="d57b1-219">**Rule #7: If you have an IMemoryOwner\<T> reference, you must at some point dispose of it or transfer its ownership (but not both).**</span></span>

<span data-ttu-id="d57b1-220">Puesto que una instancia de <xref:System.Memory%601> puede estar respaldada por la memoria administrada o no administrada, el propietario debe llamar a <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> cuando se completa el trabajo realizado en la instancia de <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="d57b1-220">Since a <xref:System.Memory%601> instance may be backed by either managed or unmanaged memory, the owner must call <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> when work performed on the <xref:System.Memory%601> instance is complete.</span></span> <span data-ttu-id="d57b1-221">Como alternativa, el propietario puede transferir la propiedad de la instancia de <xref:System.Buffers.IMemoryOwner%601> a un componente diferente, momento en que el componente de adquisición pasa a ser responsable de llamar a <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> en el momento adecuado (se ofrece más información sobre esto más adelante).</span><span class="sxs-lookup"><span data-stu-id="d57b1-221">Alternatively, the owner may transfer ownership of the <xref:System.Buffers.IMemoryOwner%601> instance to a different component, at which point the acquiring component becomes responsible for calling <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> at the appropriate time (more on this later).</span></span>

<span data-ttu-id="d57b1-222">Si no se llama al método <xref:System.Buffers.MemoryPool%601.Dispose%2A> correctamente, se pueden producir fugas de memoria no administrada u otra degradación del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d57b1-222">Failure to call the <xref:System.Buffers.MemoryPool%601.Dispose%2A> method may lead to unmanaged memory leaks or other performance degradation.</span></span>

<span data-ttu-id="d57b1-223">Esta regla también se aplica al código que llama a métodos de fábrica como <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d57b1-223">This rule also applies to code that calls factory methods like <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d57b1-224">El autor de llamada pasa a ser el propietario de la instancia de <xref:System.Buffers.IMemoryOwner%601> devuelta y es responsable de la eliminación de dicha instancia cuando se termina.</span><span class="sxs-lookup"><span data-stu-id="d57b1-224">The caller becomes the owner of the returned <xref:System.Buffers.IMemoryOwner%601> and is responsible for disposing of the instance when finished.</span></span>

<span data-ttu-id="d57b1-225">**Regla 8: Si tiene un parámetro IMemoryOwner\<T> en la superficie de API, implica la aceptación de la propiedad de esa instancia.**</span><span class="sxs-lookup"><span data-stu-id="d57b1-225">**Rule #8: If you have an IMemoryOwner\<T> parameter in your API surface, you are accepting ownership of that instance.**</span></span>

<span data-ttu-id="d57b1-226">Aceptar una instancia de este tipo indica que el componente intenta tomar posesión de esta instancia.</span><span class="sxs-lookup"><span data-stu-id="d57b1-226">Accepting an instance of this type signals that your component intends to take ownership of this instance.</span></span> <span data-ttu-id="d57b1-227">El componente pasa a ser responsable de la correcta eliminación según la regla 7.</span><span class="sxs-lookup"><span data-stu-id="d57b1-227">Your component becomes responsible for proper disposal according to Rule #7.</span></span>

<span data-ttu-id="d57b1-228">Cualquier componente que transfiere la propiedad de la instancia de <xref:System.Buffers.IMemoryOwner%601> a un componente diferente ya no debe utilizar esa instancia una vez finalizada la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="d57b1-228">Any component that transfers ownership of the <xref:System.Buffers.IMemoryOwner%601> instance to a different component should no longer use that instance after the method call completes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d57b1-229">Si el constructor acepta <xref:System.Buffers.IMemoryOwner%601> como un parámetro, su tipo debe implementar <xref:System.IDisposable>y el método <xref:System.IDisposable.Dispose%2A> debe llamar a <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d57b1-229">If your constructor accepts <xref:System.Buffers.IMemoryOwner%601> as a parameter, its type should implement <xref:System.IDisposable>, and your <xref:System.IDisposable.Dispose%2A> method should call <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="d57b1-230">**Regla 9: Si está encapsulando un método p/invoke sincrónico, la API debe aceptar Span\<T> como parámetro.**</span><span class="sxs-lookup"><span data-stu-id="d57b1-230">**Rule #9: If you're wrapping a synchronous p/invoke method, your API should accept Span\<T> as a parameter.**</span></span>

<span data-ttu-id="d57b1-231">Según la regla 1, <xref:System.Span%601> es normalmente el tipo correcto que se usará para las API sincrónicas.</span><span class="sxs-lookup"><span data-stu-id="d57b1-231">According to Rule #1, <xref:System.Span%601> is generally the correct type to use for synchronous APIs.</span></span> <span data-ttu-id="d57b1-232">Puede anclar instancias de <xref:System.Span%601> a través de la palabra clave [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md), como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d57b1-232">You can pin <xref:System.Span%601> instances via the [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) keyword, as in the following example.</span></span>

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

<span data-ttu-id="d57b1-233">En el ejemplo anterior, `pbData` puede ser NULL si, por ejemplo, el intervalo de entrada está vacío.</span><span class="sxs-lookup"><span data-stu-id="d57b1-233">In the previous example, `pbData` can be null if, for example, the input span is empty.</span></span> <span data-ttu-id="d57b1-234">Si el método exportado requiera absolutamente que `pbData` tenga un valor distinto de NULL, aunque `cbData` sea 0, el método puede implementarse como sigue:</span><span class="sxs-lookup"><span data-stu-id="d57b1-234">If the exported method absolutely requires that `pbData` be non-null, even if `cbData` is 0, the method can be implemented as follows:</span></span>

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

<span data-ttu-id="d57b1-235">**Regla 10: Si está encapsulando un método p/invoke asincrónico, la API debe aceptar Memory\<T> como parámetro.**</span><span class="sxs-lookup"><span data-stu-id="d57b1-235">**Rule #10: If you're wrapping an asynchronous p/invoke method, your API should accept Memory\<T> as a parameter.**</span></span>

<span data-ttu-id="d57b1-236">Puesto que no se puede utilizar la palabra clave [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) en las operaciones asincrónicas, use el método <xref:System.Memory%601.Pin%2A?displayProperty=nameWithType> para anclar instancias de <xref:System.Memory%601>, independientemente del tipo de memoria contigua que represente la instancia.</span><span class="sxs-lookup"><span data-stu-id="d57b1-236">Since you cannot use the [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) keyword across asynchronous operations, you use the <xref:System.Memory%601.Pin%2A?displayProperty=nameWithType> method to pin <xref:System.Memory%601> instances, regardless of the kind of contiguous memory the instance represents.</span></span> <span data-ttu-id="d57b1-237">En el ejemplo siguiente se muestra cómo utilizar esta API para realizar una llamada p/invoke asincrónica.</span><span class="sxs-lookup"><span data-stu-id="d57b1-237">The following example shows how to use this API to perform an asynchronous p/invoke call.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d57b1-238">Vea también</span><span class="sxs-lookup"><span data-stu-id="d57b1-238">See also</span></span>

- <xref:System.Memory%601?displayProperty=nameWithType>
- <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>
- <xref:System.Span%601?displayProperty=nameWithType>
