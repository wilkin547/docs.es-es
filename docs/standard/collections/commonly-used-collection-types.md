---
title: "Tipos de colección utilizados normalmente"
description: "Tipos de colección utilizados normalmente"
keywords: .NET, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 55861611-1e40-4cc2-9ec5-0b2df4ba6c0c
translationtype: Human Translation
ms.sourcegitcommit: d4e7ef84480aa9f735fb8d1ff03c9e8a61127c83
ms.openlocfilehash: 6cadcd91810f08900b58e402240e8a469fad2018

---

# <a name="commonly-used-collection-types"></a>Tipos de colección utilizados normalmente

Los tipos de colecciones son las variaciones comunes de las colecciones de datos, como tablas hash, colas, pilas, bolsas, diccionarios y listas.

Las colecciones se basan en las interfaces [`ICollection`](https://docs.microsoft.com/dotnet/core/api/System.Collections.ICollection), [`IList`](https://docs.microsoft.com/dotnet/core/api/System.Collections.IList), [`IDictionary`](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary) o en sus equivalentes genéricos. La interfaz `IList` y la interfaz `IDictionary` se derivan ambas de la interfaz `ICollection`; por lo tanto, todas las colecciones se basan en la interfaz `ICollection` directa o indirectamente. En colecciones basadas en la interfaz `IList` (como [`Array`](https://docs.microsoft.com/dotnet/core/api/System.Array), [`ArrayList`](https://docs.microsoft.com/dotnet/core/api/System.Collections.ArrayList) o [`List<T>)`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1)) o directamente en la interfaz `ICollection` (como [`Queue`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Queue), [`ConcurrentQueue<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1), [`Stack`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Stack), [`ConcurrentStack<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1) o [`LinkedList<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.LinkedList-1)), cada elemento contiene un solo valor. En colecciones basadas en la interfaz `IDictionary` (como las clases [`Hashtable`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable) y [`SortedList`](https://docs.microsoft.com/dotnet/core/api/System.Collections.SortedList), y las clases genéricas [`Dictionary<TKey, TValue>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) y [`SortedList<TKey, TValue>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2)), o en las clases [`ConcurrentDictionary<TKey, TValue>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2), cada elemento contiene una clave y un valor. La clase [`KeyedCollection<TKey, TItem>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.KeyedCollection-2) es única porque es una lista de valores con claves insertadas en los valores y, por tanto, se comporta como una lista y como un diccionario.

Las colecciones genéricas son la mejor solución para elementos fuertemente tipados. En cambio, si su lenguaje no admite genéricos, el espacio de nombres [`System.Collections`](https://docs.microsoft.com/dotnet/core/api/System.Collections) incluye colecciones base, como [`CollectionBase`](https://docs.microsoft.com/dotnet/core/api/System.Collections.CollectionBase), [`ReadOnlyCollectionBase`](https://docs.microsoft.com/dotnet/core/api/System.Collections.ReadOnlyCollectionBase) y [`DictionaryBase`](https://docs.microsoft.com/dotnet/core/api/System.Collections.DictionaryBase), que son clases base abstractas que se pueden extender para crear clases de colección fuertemente tipadas. Cuando se requiera un acceso eficaz a una colección multiproceso, use las colecciones genéricas del espacio de nombres [`System.Collections.Concurrent`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent).

Las colecciones pueden variar en función de cómo se almacenan los elementos, cómo se ordenan, cómo se realizan las búsquedas y cómo se realizan las comparaciones. La clase [`Queue`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Queue) y la clase genérica [`Queue<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Queue-1) proporcionan listas de tipo “el primero en entrar es el primero en salir”, mientras que la clase [`Stack`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Stack) y la clase genérica [`Stack<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Stack-1) proporcionan listas de tipo “el último en entrar es el primero en salir”. La clase [`SortedList`](https://docs.microsoft.com/dotnet/core/api/System.Collections.SortedList) y la clase genérica [`SortedList<TKey, TValue>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2) proporcionan versiones ordenadas de la clase [`Hashtable`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable) y de la clase genérica [`Dictionary<TKey, TValue>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2). El acceso a los elementos de `Hashtable` o de `Dictionary<TKey, TValue>` solo es posible mediante la clave del elemento, pero el acceso a los elementos de `SortedList` o de [`KeyedCollection<TKey, TItem>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.KeyedCollection-2) es posible mediante la clave o mediante el índice del elemento. Los índices de todas las colecciones son de base cero, excepto [`Array`](https://docs.microsoft.com/dotnet/core/api/System.Array), que permite matrices que no son de base cero.

La característica LINQ to Objects permite usar consultas LINQ para obtener acceso a los objetos en memoria mientras el tipo de objeto implemente la interfaz [`IEnumerable`](https://docs.microsoft.com/dotnet/core/api/System.Collections.IEnumerable) o [`IEnumerable<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IEnumerable-1). Las consultas LINQ proporcionan un patrón común para el acceso a datos; suelen ser más concisas y legibles que los bucles foreach estándar; y proporcionan capacidades de filtrado, ordenación y agrupación. Las consultas LINQ también pueden mejorar el rendimiento.

## <a name="related-topics"></a>Temas relacionados

Título | Descripción
----- | -----------
[`Collections and Data Structures`](index.md) | Describe los diversos tipos de colecciones disponibles en .NET Framework, incluidas las pilas, colas, listas, matrices y diccionarios.
[`Hashtable and Dictionary Collection Types`](hashtable-and-dictionary-collection-types.md) | Describe las características de los tipos de diccionarios basados en hash genéricos y no genéricos.
[`Sorted Collection Types`](sorted-collection-types.md) | Describe las características y el rendimiento de colecciones ordenadas.

## <a name="reference"></a>Referencia

[`System.Collections`](https://docs.microsoft.com/dotnet/core/api/System.Collections)

[`System.Collections.Generic`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic)

[`System.Collections.ICollection`](https://docs.microsoft.com/dotnet/core/api/System.Collections.ICollection)

[`System.Collections.Generic.ICollection<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.ICollection-1)

[`System.Collections.IList`](https://docs.microsoft.com/dotnet/core/api/System.Collections.IList)

[`System.Collections.Generic.IList<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IList-1)

[`System.Collections.IDictionary`](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary)

[`System.Collections.Generic.IDictionary<TKey, TValue>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IDictionary-2)

[`System.Linq`](https://docs.microsoft.com/dotnet/core/api/System.Linq)



<!--HONumber=Nov16_HO3-->


