---
title: Colecciones y estructuras de datos
description: Colecciones y estructuras de datos
keywords: .NET, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 9e70255a-c02a-4046-86b7-10c84bab2d38
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 30e53c38bd58e15668e01f2af79defb0a0918192
ms.lasthandoff: 03/02/2017

---

# <a name="collections-and-data-structures"></a>Colecciones y estructuras de datos

A menudo, los datos similares pueden controlarse de forma más eficaz si se almacenan y manipulan como si fuesen una colección. Puede usar la clase [System.Array](https://docs.microsoft.com/dotnet/core/api/System.Array) o las clases en los espacios de nombres [System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections), [System.Collections.Generic](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic) o [System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent) para agregar, quitar y modificar elementos individuales o un conjunto de elementos de una colección.

Hay dos tipos principales de colecciones: las colecciones genéricas y las colecciones no genéricas. Las colecciones genéricas son de seguridad de tipos en tiempo de compilación. Debido a esto, las colecciones genéricas normalmente ofrecen un mejor rendimiento. Las colecciones genéricas aceptan un parámetro de tipo cuando se construyen y no requieren conversiones con el tipo [Object](https://docs.microsoft.com/dotnet/core/api/System.Object) al agregar o quitar elementos de la colección. Las colecciones no genéricas almacenan elementos como [Object](https://docs.microsoft.com/dotnet/core/api/System.Object) y requieren una conversión. Puede que vea colecciones no genéricas en código antiguo.

Las colecciones del espacio de nombres [System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent) proporcionan operaciones eficaces y seguras para subprocesos con el fin de obtener acceso a los elementos de la colección desde varios subprocesos.

## <a name="common-collection-features"></a>Características comunes de las colecciones

Todas las colecciones ofrecen métodos para agregar, quitar o buscar elementos en la colección. Además, todas las colecciones que implementan directa o indirectamente las interfaces [ICollection](https://docs.microsoft.com/dotnet/core/api/System.Collections.ICollection) o [ICollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.ICollection-1) comparten estas características: 

* **Capacidad para enumerar la colección**

   Las colecciones de .NET framework implementan [System.Collections.IEnumerable](https://docs.microsoft.com/dotnet/core/api/System.Collections.IEnumerable) o [System.Collections.Generic.IEnumerable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IEnumerable-1) para habilitar la colección a través de la que se debe realizar la iteración. Un enumerador puede considerarse como un puntero móvil para cualquier elemento de la colección. La instrucción `foreach, in` (C#) usa el enumerador expuesto por el método `GetEnumerator` y oculta la complejidad que supone manipular el enumerador. Además, cualquier colección que implementa [System.Collections.Generic.IEnumerable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IEnumerable-1) se considera un tipo consultable y se puede consultar con LINQ. Las consultas LINQ proporcionan un modelo común para acceder a los datos. Por lo general, son más concisas y legibles que los bucles estándar y ofrecen capacidad de filtrado, ordenación y agrupación. Las consultas LINQ también pueden mejorar el rendimiento.
    
* **Capacidad de copiar el contenido de la colección en una matriz**

   Todas las colecciones se pueden copiar en una matriz mediante el método `CopyTo`; pero el orden de los elementos de la nueva matriz se basa en la secuencia en la que los devuelve el enumerador. La matriz resultante siempre es unidimensional con un límite inferior de cero.
    
Además, muchas clases de colecciones contienen las siguientes características:

* **Propiedades de capacidad y recuento**

   La capacidad de una colección es el número de elementos que puede contener. El recuento de una colección es el número de elementos que realmente contiene. Algunas colecciones ocultan la capacidad, el recuento, o ambos.
    
   La mayoría de las colecciones expanden automáticamente su capacidad cuando se alcanza la capacidad actual. La memoria se reasigna y los elementos de la antigua colección se copian en la nueva. Esto reduce el código necesario para utilizar la colección; sin embargo, el rendimiento de la colección podría verse afectado negativamente. Por ejemplo, en [List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1), si `Count` es menor que `Capacity`, el hecho de agregar un elemento supone una operación O(1). Si es necesario aumentar la capacidad para alojar el nuevo elemento, agregar un elemento se convierte en una operación O(n), donde n es `Count`. La mejor manera de evitar el rendimiento deficiente provocado por múltiples reasignaciones es establecer la capacidad inicial el tamaño estimado de la colección. 
    
   [BitArray](https://docs.microsoft.com/dotnet/core/api/System.Collections.BitArray) es un caso especial; su capacidad es igual que su longitud, que es la misma que su recuento.
    
*   **Límite inferior coherente**

   El límite inferior de una colección es el índice de su primer elemento. Todas las colecciones indizadas en el espacio de nombres [System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections) tienen un límite inferior de cero, lo que significa que están indizadas en 0. De forma predeterminada, [Array](https://docs.microsoft.com/dotnet/core/api/System.Array) tiene un límite inferior de cero, pero se puede definir un límite inferior diferente al crear una instancia de la clase `Array` con `Array.CreateInstance`.

*   **Sincronización para el acceso de varios subprocesos** (solo clases [System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections)).

   Los tipos de colecciones no genéricas del espacio de nombres [System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections) proporcionan una seguridad para subprocesos con sincronización; normalmente se exponen a través de los miembros `SyncRoot` y `IsSynchronized`. Estas colecciones no son seguras para subprocesos de forma predeterminada. Si necesita un acceso multiproceso escalable y eficaz a una colección, use una de las clases del espacio de nombres [System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent) o considere el uso de una colección inmutable. Para obtener más información, consulte [Colecciones seguras para subprocesos](threadsafe/index.md).    
    
## <a name="choosing-a-collection"></a>Elegir una colección 

En general, debería utilizar colecciones genéricas. En la tabla siguiente se describen algunos escenarios habituales de las colecciones y las clases de colección que puede utilizar en esos escenarios. Si es la primera vez que usa colecciones genéricas, con esta tabla le será más fácil elegir la colección genérica que funciona mejor para su tarea.

Deseo... | Opciones de colección genérica | Opciones de colección no genérica
---------- | ---------------------------- | --------------------------------
Almacenar elementos como pares clave/valor para una consulta rápida por clave | [System.Collections.Generic.Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) | [Hashtable](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable)
Acceso a elementos por índice | [System.Collections.Generic.List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1) | [System.Array](https://docs.microsoft.com/dotnet/core/api/System.Array), [System.Collections.ArrayList](https://docs.microsoft.com/dotnet/core/api/System.Collections.ArrayList)
Utilizar elementos FIFO (el primero en entrar es el primero en salir) | [System.Collections.Generic.Queue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Queue-1) | [System.Collections.Queue](https://docs.microsoft.com/dotnet/core/api/System.Collections.Queue)
Utilizar datos LIFO (el último en entrar es el primero en salir) | [System.Collections.Generic.Stack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Stack-1) | [System.Collections.Stack](https://docs.microsoft.com/dotnet/core/api/System.Collections.Stack)
Acceso a elementos de forma secuencial | [System.Collections.Generic.LinkedList&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.LinkedList-1) | Sin recomendación
Recibir notificaciones cuando se quitan o se agregan elementos a la colección. (implementa [INotifyPropertyChanged](https://docs.microsoft.com/dotnet/core/api/System.ComponentModel.INotifyPropertyChanged) e [INotifyCollectionChanged](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.INotifyCollectionChanged)) | [System.Collections.ObjectModel.ObservableCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.ObservableCollection-1) | Sin recomendación
Una colección ordenada | [System.Collections.Generic.SortedList&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2) | [System.Collections.SortedList](https://docs.microsoft.com/dotnet/core/api/System.Collections.SortedList)
Administrar el acceso y almacenamiento eficientes de elementos únicos | [System.Collections.Generic.HashSet&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.HashSet-1), [System.Collections.Generic.SortedSet&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedSet-1) | Sin recomendación

## <a name="related-topics"></a>Temas relacionados

Título | Descripción
----- | -----------
[Seleccionar una clase de colección](selecting-a-collection-class.md) | Describe las diferentes colecciones y le ayuda a seleccionar una para su escenario.
[Tipos de colección utilizados normalmente](commonly-used-collection-types.md) | Describe los tipos de colección genéricos y no genéricos más usados, como [System.Array](https://docs.microsoft.com/dotnet/core/api/System.Array), [System.Collections.Generic.List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1) y [System.Collections.Generic.Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2). 
[Cuándo utilizar colecciones genéricas](when-to-use-generic-collections.md) | Describe el uso de los tipos de colección genéricos.
[Comparaciones y ordenaciones en colecciones](comparisons-and-sorts-within-collections.md) | Describe el uso de las comparaciones de igualdad y ordenación en las colecciones.
[Tipos de colecciones ordenadas](sorted-collection-types.md) | Describe las características y el rendimiento de colecciones ordenadas.
[Tipos de las colecciones Hashtable y Dictionary](hashtable-and-dictionary-collection-types.md) | Describe las características de los tipos de diccionarios basados en hash genéricos y no genéricos.
[Colecciones seguras para subprocesos](threadsafe/index.md) | Describe los tipos de colecciones, como [System.Collections.Concurrent.BlockingCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.BlockingCollection-1) y [System.Collections.Concurrent.ConcurrentBag&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentBag-1) que admiten un acceso simultáneo seguro y eficaz desde varios subprocesos.

## <a name="reference"></a>Referencia

[System.Array](https://docs.microsoft.com/dotnet/core/api/System.Array)

[System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections)

[System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)

[System.Collections.Generic](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic)

[System.Collections.Specialized](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized)

[System.Linq](https://docs.microsoft.com/dotnet/core/api/System.Linq)
  

