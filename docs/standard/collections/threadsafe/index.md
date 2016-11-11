---
title: Colecciones seguras para subprocesos
description: Colecciones seguras para subprocesos
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 92d5515d-f5d6-4a09-8bbb-31865d678643
translationtype: Human Translation
ms.sourcegitcommit: cfe65fcba1b3fdc09ffcac704a760d8ce29ea60b
ms.openlocfilehash: 421d46585b5d83f5772fa6596ad581c8c6acbf71

---

# <a name="threadsafe-collections"></a>Colecciones seguras para subprocesos

El espacio de nombres [System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent) incluye varias clases de colección que son a la vez seguras para subprocesos y escalables. Varios subprocesos pueden agregar o quitar elementos de estas colecciones sin ningún riesgo y de un modo eficaz, sin requerir una sincronización adicional en código de usuario. Al escribir un nuevo código, utilice las clases de colección simultáneas siempre que la colección se escriba en varios subprocesos simultáneamente. Si solo está leyendo en una colección compartida, puede usar las clases en el espacio de nombres [System.Collections.Generic](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic). Recomendamos no usar clases de colección [System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections) a menos que estén destinadas a .NET Framework 1.1. o un tiempo de ejecución de una versión anterior.

## <a name="finegrained-locking-and-lockfree-mechanisms"></a>Mecanismos de bloqueo específico y sin bloqueos

Algunos de los tipos de colección simultáneos usan mecanismos de sincronización ligeros como [SpinLock](https://docs.microsoft.com/dotnet/core/api/System.Threading.SpinLock), [SpinWait](https://docs.microsoft.com/dotnet/core/api/System.Threading.SpinWait), [SemaphoreSlim](https://docs.microsoft.com/dotnet/core/api/System.Threading.SemaphoreSlim) y [CountdownEvent](https://docs.microsoft.com/dotnet/core/api/System.Threading.CountdownEvent). Estos tipos de sincronización usan normalmente giro activo durante breves períodos antes de colocar el subproceso en un verdadero estado de `Wait`. Cuando se prevé que los tiempos de espera sean muy cortos, el giro es técnicamente menos costoso que la espera, que implica una costosa transición del kernel. Para las clases de colección que utilizan el giro, esta eficacia significa que se pueden agregar y quitar varios subprocesos con una tasa muy alta.

Las clases [ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1) y [ConcurrentStack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1) no usan ningún tipo de bloqueo. En su lugar, dependen de las operaciones de interbloqueos para lograr la seguridad para subprocesos.

> [!NOTE]
> Como las clases de colección simultáneas son compatibles con [ICollection](https://docs.microsoft.com/dotnet/core/api/System.Collections.ICollection), proporcionan implementaciones para las propiedades `IsSynchronized` y `SyncRoot`, aunque estas propiedades sean irrelevantes. `IsSynchronized` devuelve siempre `false` y `SyncRoot` siempre es null.

La siguiente tabla enumera los tipos de colección en el espacio de nombres [System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent).

Tipo | Descripción
---- | -----------
[BlockingCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.BlockingCollection-1) | Proporciona funcionalidad de límite y bloqueo para cualquier tipo que implemente [IProducerConsumerCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.IProducerConsumerCollection-1). Para obtener más información, consulte [Información general sobre BlockingCollection](blockingcollection-overview.md).
[ConcurrentBag&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentBag-1) | Implementación segura para subprocesos de una colección no ordenada de elementos.
[ConcurrentDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2) | Implementación segura para subprocesos de un diccionario de pares clave-valor.
[ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1) | Implementación segura para subprocesos de una cola FIFO (primero en entrar, primero en salir).
[ConcurrentStack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1) | Implementación segura para subprocesos de una pila LIFO (último en entrar, primero en salir).
[IProducerConsumerCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.IProducerConsumerCollection-1) | Interfaz que debe implementar un tipo para su uso en `BlockingCollection`.

## <a name="thread-synchronization-in-the-net-framework-version-10-and-20-collections"></a>Sincronización de subprocesos en las colecciones de .NET Framework de las versiones 1.0 y 2.0

Las colecciones que se presentaron por primera vez en la versión 1.0 de .NET Framework se encuentran en el espacio de nombres [System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections). Estas colecciones, que incluyen [ArrayList](https://docs.microsoft.com/dotnet/core/api/System.Collections.ArrayList) y [Hashtable](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable) usadas habitualmente, proporcionan cierta seguridad para subprocesos mediante la propiedad `Synchronized`, que devuelve un contenedor seguro para subprocesos en torno a la colección. El contenedor funciona bloqueando toda la colección en cada operación de agregar o quitar. Por consiguiente, cada subproceso que intenta tener acceso a la colección debe esperar su turno para tomar el único bloqueo. Esto no es escalable y puede producir una degradación significativa del rendimiento en las colecciones grandes. Asimismo, el diseño no está totalmente protegido de las condiciones de carrera. 

Las clases de colecciones que se presentaron por primera vez en la versión 2.0 de .NET Framework se encuentran en el espacio de nombres [System.Collections.Generic](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic). Entre ellas se incluyen [List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1), [Dictionary&lt;TKey y TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2). Estas clases proporcionan una seguridad de tipos y un rendimiento mejorados comparados con las clases de `System.Collections`. Pero las clases de colección `System.Collections.Generic` no proporcionan ninguna sincronización de subprocesos; el código de usuario debe proporcionar toda la sincronización cuando se agregan o quitan elementos en varios subprocesos simultáneamente.

Recomendamos las clases de colección de `System.Collections.Concurrent` porque proporcionan no solo la seguridad de tipos de las clases de colección de `System.Collections.Generic`, sino también una seguridad para subprocesos más eficaz y completa que las colecciones de `System.Collections`.

## <a name="related-topics"></a>Temas relacionados

Título | Descripción
----- | -----------
[Información general sobre BlockingCollection](blockingcollection-overview.md) | Describe la funcionalidad proporcionada por el tipo `BlockingCollection<T>`.
[Cuándo usar una colección segura para subprocesos](when-to-use-a-thread-safe-collection.md) | Explica cuándo es adecuado usar una colección segura para subprocesos.
[Cómo agregar y quitar elementos de ConcurrentDictionary](how-to-add-and-remove-items.md) | Describe cómo agregar y quitar los elementos de `ConcurrentDictionary<TKey, TValue>`.
[Cómo agregar y tomar elementos de forma individual en una clase BlockingCollection](how-to-add-and-take-items.md) | Describe cómo agregar y recuperar elementos de una colección de bloqueo sin utilizar el enumerador de solo lectura.
[Cómo agregar la funcionalidad de límite y bloqueo a una colección](how-to-add-bounding-and-blocking.md ) | Describe cómo utilizar cualquier clase de colección como mecanismo de almacenamiento subyacente para una colección `IProducerConsumerCollection<T>;`.
[Cómo utilizar ForEach para quitar elementos de BlockingCollection](how-to-use-foreach-to-remove.md ) | Describe cómo usar `foreach` para quitar todos los elementos en una colección de bloqueo.
[Cómo usar matrices de colecciones de bloqueo en una canalización](how-to-use-arrays-of-blockingcollections.md) | Describe cómo utilizar varias colecciones de bloqueo para implementar una canalización al mismo tiempo.
[Cómo crear un grupo de objetos usando ConcurrentBag](how-to-create-an-object-pool.md) | Muestra cómo usar un controlador simultáneo para mejorar el rendimiento en escenarios donde puede reutilizar objetos en lugar de crear continuamente otros nuevos.

## <a name="reference"></a>Referencia

[System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)






 





<!--HONumber=Nov16_HO1-->


