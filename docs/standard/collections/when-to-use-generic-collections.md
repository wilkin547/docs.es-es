---
title: "Cuándo utilizar colecciones genéricas"
description: "Cuándo utilizar colecciones genéricas"
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 971e08bd-b63f-4832-9e61-9f65cbedd352
translationtype: Human Translation
ms.sourcegitcommit: a5689b2da8b9877af67d46b3ff3f1c99c6899523
ms.openlocfilehash: 0805bae19871f878806050a0c2bf954927894321

---

# <a name="when-to-use-generic-collections"></a>Cuándo utilizar colecciones genéricas

Generalmente se recomienda usar colecciones genéricas, ya que se obtiene la ventaja inmediata de la seguridad de tipos sin necesidad de derivar de un tipo de colección base ni de implementar miembros específicos de tipo. Los tipos de colección genéricos también suelen funcionan mejor que los correspondientes tipos de colección no genéricos (y mejor que los tipos que se derivan de los tipos de colección base no genéricos) cuando los elementos de la colección son tipos de valor; esto se debe a que con los genéricos no es necesario realizar una conversión boxing de los elementos. 

Use las clases de colección genérica en el espacio de nombres [System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent ) cuando varios subprocesos puedan agregar o quitar elementos de la colección al mismo tiempo.

Los siguientes tipos genéricos corresponden a los tipos de colección existentes: 

*   [List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1 ) es la clase genérica que corresponde a [ArrayList](https://docs.microsoft.com/dotnet/core/api/System.Collections.ArrayList ).

*   [Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2 ) y [ConcurrentDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2 ) son las clases genéricas que corresponden a [Hashtable](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable ). 

*   [Colección&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.Collection-1 ) es la clase genérica que corresponde a [CollectionBase](https://docs.microsoft.com/dotnet/core/api/System.Collections.CollectionBase ). `Collection<T>` puede utilizarse como una clase base, pero, a diferencia de `CollectionBase`, no es abstracta. Esto la hace mucho más fácil de usar.

*   [ReadOnlyCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.ReadOnlyCollection-1 ) es la clase genérica que corresponde a [ReadOnlyCollectionBase](https://docs.microsoft.com/dotnet/core/api/System.Collections.ReadOnlyCollectionBase ). `ReadOnlyCollection<T>` no es abstracta y tiene un constructor que hace más fácil exponer un elemento [List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1 ) existente como una colección de solo lectura.

*   Las clases genéricas [Queue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Queue-1 ), [ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1 ), [Stack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Stack-1 ), [ConcurrentStack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1 ) y [SortedList&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2 ) corresponden a las respectivas clases no genéricas del mismo nombre.

## <a name="additional-types"></a>Tipos adicionales

Hay varios tipos de colección genéricos que no tienen un tipo homólogo no genérico. Entre esos tipos se incluyen los siguientes: 

*   [LinkedList&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.LinkedList-1 ) es una lista vinculada de uso general que proporciona operaciones de eliminación e inserción O(1).

*   [SortedDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedDictionary-2 ) es un diccionario ordenado con operaciones de inserción y extracción O(log n), por lo que es una alternativa útil a [SortedList&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2 ). 

*   [KeyedCollection&lt;TKey, TItem&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.KeyedCollection-2 ) es un híbrido entre una lista y un diccionario, lo que proporciona una manera de almacenar objetos que contienen sus propias claves.

*   [BlockingCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.BlockingCollection-1 ) implementa una clase de colección con funcionalidad de límite y bloqueo.

*   [ConcurrentBag&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentBag-1 ) proporciona una rápida inserción y eliminación de elementos no ordenados.

## <a name="linq-to-objects"></a>LINQ to Objects

La característica LINQ to Objects permite usar consultas LINQ para tener acceso a objetos en memoria siempre que el tipo de objeto implemente la interfaz [System.Collections.IEnumerable](https://docs.microsoft.com/dotnet/core/api/System.Collections.IEnumerable ) o [System.Collections.Generic.IEnumerable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IEnumerable-1 ). Las consultas LINQ proporcionan un modelo común para el acceso a datos; suelen ser más concisas y legibles que los bucles `foreach` estándar, y proporcionan capacidades de filtrado, ordenación y agrupación. Las consultas LINQ también pueden mejorar el rendimiento.

## <a name="additional-functionality"></a>Funcionalidad adicional

Algunos de los tipos genéricos tienen funcionalidades que no se encuentran en los tipos de colección no genéricos. Por ejemplo, la clase [List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1 ), que corresponde a la clase [ArrayList](https://docs.microsoft.com/dotnet/core/api/System.Collections.ArrayList ) no genérica, tiene una serie de métodos que aceptan delegados genéricos, como el delegado [Predicate&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Predicate-1 ), que permite especificar los métodos de búsqueda en la lista, y el delegado [Action&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Action-1 ), que representa los métodos que actúan en cada elemento de la lista.

La clase [List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1 ) permite especificar sus propias implementaciones de interfaz genérica [IComparer&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IComparer-1 ) para la ordenación y búsqueda en la lista. Las clases [SortedDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedDictionary-2 ) y [SortedList&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2 ) también tienen esta capacidad. Además, estas clases le permiten especificar los comparadores cuando se crea la colección. De forma similar, las clases [Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2 ) y [KeyedCollection&lt;TKey, TItem&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.KeyedCollection-2 ) le permiten especificar sus propios comparadores de igualdad.

## <a name="see-also"></a>Vea también

[Colecciones y estructuras de datos](index.md) 

[Tipos de colección utilizados normalmente](commonly-used-collection-types.md)



<!--HONumber=Nov16_HO1-->


