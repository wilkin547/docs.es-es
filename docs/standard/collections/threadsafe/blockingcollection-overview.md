---
title: "Información general sobre BlockingCollection"
description: "Información general sobre BlockingCollection"
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: a1a867de-53c2-49ca-9a1a-e5770a942724
translationtype: Human Translation
ms.sourcegitcommit: e07788926a995b41571be276379ad9285747951d
ms.openlocfilehash: 64a01b5e21e012dfaae07a02f5fb27932be9cf98

---

# <a name="blockingcollection-overview"></a>Información general sobre BlockingCollection

[BlockingCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.BlockingCollection-1) es una clase de colección segura para subprocesos que proporciona las siguientes características:

*   Una implementación del patrón productor-consumidor.

*   Adición segura para subprocesos y eliminación de elementos de una colección.

*   Capacidad máxima opcional.

*   Operaciones de inserción y eliminación que se bloquean cuando la colección está vacía o completa.

*   Inserción y eliminación de operaciones "try" que no se bloquean o que se bloquean en un período de tiempo especificado.

*   Encapsula cualquier tipo de colección que implementa [IProducerConsumerCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.IProducerConsumerCollection-1).

*   Cancelación con tokens de cancelación.

*   Dos tipos de enumeraciones con `foreach`: 

    1. Enumeración de solo lectura.
    
    2. Enumeración que quita los elementos que se enumeran.
    
## <a name="bounding-and-blocking-support"></a>Compatibilidad con límites y bloqueos 

[BlockingCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.BlockingCollection-1) admite límites y bloqueos. Los límites implican que puede establecer la capacidad máxima de la colección. Los límites son importantes en ciertos escenarios, porque le permiten controlar el tamaño máximo de la colección en memoria y evitan que los subprocesos de producción vayan demasiado por delante de los subprocesos de consumo.

Varios subprocesos o tareas pueden agregar elementos a la colección de forma simultánea y, si la colección alcanza su capacidad máxima especificada, los subprocesos de producción se bloquearán hasta que se quite un elemento. Varios consumidores pueden quitar elementos de forma simultánea y, si la colección está vacía, los subprocesos de consumo se bloquearán hasta que un productor agregue un elemento. Un subproceso de producción puede llamar a `CompleteAdding` para indicar que no se agregarán más elementos. Los consumidores supervisan la propiedad `IsCompleted` para saber cuándo está vacía la colección y no se agregarán más elementos. En el ejemplo siguiente, se muestra una `BlockingCollection` sencilla con una capacidad limitada de 100. Una tarea de producción agrega elementos a la colección siempre que alguna condición externa sea true y después llama a `CompleteAdding`. La tarea de consumidor toma elementos hasta que la propiedad `IsCompleted` es true.

```csharp
// A bounded collection. It can hold no more 
// than 100 items at once.
BlockingCollection<Data> dataItems = new BlockingCollection<Data>(100);


// A simple blocking consumer with no cancellation.
Task.Run(() => 
{
    while (!dataItems.IsCompleted)
    {

        Data data = null;
        // Blocks if number.Count == 0
        // IOE means that Take() was called on a completed collection.
        // Some other thread can call CompleteAdding after we pass the
        // IsCompleted check but before we call Take. 
        // In this example, we can simply catch the exception since the 
        // loop will break on the next iteration.
        try
        {
            data = dataItems.Take();
        }
        catch (InvalidOperationException) { }

        if (data != null)
        {
            Process(data);
        }
    }
    Console.WriteLine("\r\nNo more items to take.");
});

// A simple blocking producer with no cancellation.
Task.Run(() =>
{
    while (moreItemsToAdd)
    {
        Data data = GetData();
        // Blocks if numbers.Count == dataItems.BoundedCapacity
        dataItems.Add(data);
    }
    // Let consumer know we are done.
    dataItems.CompleteAdding();
});
```

Para ver un ejemplo completo, consulte [Cómo: Agregar y tomar elementos de forma individual en una clase BlockingCollection](how-to-add-and-take-items.md).

## <a name="timed-blocking-operations"></a>Operaciones de bloqueo cronometradas

En las operaciones de bloqueo cronometradas `TryAdd` y `TryTake` en colecciones limitadas, el método intenta agregar o quitar un elemento. Si un elemento está disponible, se coloca en la variable que ha pasado la referencia y el método devuelve `true`. Si no se recupera ningún elemento después de un período de tiempo de espera especificado, el método devuelve `false`. El subproceso es libre para realizar otro trabajo útil antes de intentar acceder de nuevo a la colección. Para obtener un ejemplo de acceso de bloqueo cronometrado, consulte el segundo ejemplo de [Cómo: Agregar y tomar elementos de forma individual en una clase BlockingCollection](how-to-add-and-take-items.md).

## <a name="cancelling-add-and-take-operations"></a>Cancelar operaciones de agregar y tomar

Las operaciones de agregar y tomar se realizan normalmente en un bucle. Puede cancelar un bucle al pasar `CancellationToken` a los métodos `TryAdd` o `TryTake`, y después comprobar el valor de la propiedad `IsCancellationRequested` del token en cada iteración. Si el valor es `true`, puede decidir si responde a la solicitud de cancelación limpiando algún recurso y saliendo del bucle. En el ejemplo siguiente, se muestra una sobrecarga de `TryAdd` que toma un token de cancelación y el código que lo usa:

```csharp
BlockingCollection<string> bc = new BlockingCollection<string>(new ConcurrentBag<string>(), 1000 );
```

## <a name="specifying-the-collection-type"></a>Especificar el tipo de colección

Cuando se crea una `BlockingCollection<T>;`, puede especificar no solo la capacidad limitada, sino también el tipo de colección que se usará. Por ejemplo, puede especificar un objeto [ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1) para un comportamiento FIFO (primero en entrar, primero en salir) o un objeto [ConcurrentStack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1) para un comportamiento LIFO (último en entrar, primero en salir). Puede usar cualquier clase de colección que implemente la interfaz [IProducerConsumerCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.IProducerConsumerCollection-1). El tipo de colección predeterminado para `BlockingCollection<T>` es `ConcurrentQueue<T>`. En el ejemplo de código siguiente, se muestra cómo crear una `BlockingCollection<T>` de cadenas que tiene una capacidad de 1000 y usa un objeto [ConcurrentBag&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentBag-1):

```csharp
BlockingCollection<string> bc = new BlockingCollection<string>(new ConcurrentBag<string>(), 1000 );
```

## <a name="ienumerable-support"></a>Compatibilidad con IEnumerable

`BlockingCollection<T>` proporciona un método `GetConsumingEnumerable` que permite a los consumidores usar una instrucción `foreach` para quitar elementos hasta que la colección esté completa, lo que significa que está vacía y no se agregarán más elementos. Para obtener más información, consulte [Cómo: Utilizar ForEach para quitar elementos de BlockingCollection](how-to-use-foreach-to-remove.md).

## <a name="using-many-blockingcollections-as-one"></a>Usar muchas BlockingCollections como una

Para escenarios en los que un consumidor necesita tomar elementos de varias colecciones de forma simultánea, se pueden crear matrices de `BlockingCollection<T>` y usar los métodos estáticos, como `TakeFromAny` y `AddToAny`, que agregarán a cualquiera de las colecciones de la matriz o tomarán desde ellas. Si se bloquea una colección, el método intenta otra de forma inmediata hasta que encuentra una que pueda realizar la operación. Para obtener más información, consulte [Cómo: Usar matrices de colecciones de bloqueo en una canalización](how-to-use-arrays-of-blockingcollections.md).

## <a name="see-also"></a>Vea también

[System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)

[Colecciones y estructuras de datos](../index.md)

[Colecciones seguras para subprocesos](index.md)




<!--HONumber=Nov16_HO3-->


