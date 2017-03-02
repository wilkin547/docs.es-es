---
title: Tipos de colecciones ordenadas
description: Tipos de colecciones ordenadas
keywords: .NET, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: bdc9c13e-e56a-433b-a293-c92364f6e9cb
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 28d5024f759b3a7474aef1fa344d39f9933b6322
ms.lasthandoff: 03/02/2017

---

# <a name="sorted-collection-types"></a>Tipos de colecciones ordenadas  
 
 La clase [System.Collections.SortedList](https://docs.microsoft.com/dotnet/core/api/System.Collections.SortedList), la clase genérica [System.Collections.Generic.SortedList&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2) y la clase genérica [System.Collections.Generic.SortedDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedDictionary-2) son similares a la clase [Hashtable](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable) y la clase genérica [Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) porque implementan la interfaz [IDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary), pero mantienen sus elementos en el criterio de ordenación por clave y no tienen la característica de inserción y recuperación O(1) de las tablas hash. Las tres clases tienen varias características en común:  

 *   Las tres clases implementan la interfaz [System.Collections.IDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary). Las dos clases genéricas también implementan la interfaz genérica [System.Collections.Generic.IDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IDictionary-2).  
 
 *   Cada elemento es un par de clave y valor para propósitos de enumeración.   
  
> [!NOTE]  
> La clase no genérica [SortedList](https://docs.microsoft.com/dotnet/core/api/System.Collections.SortedList) devuelve objetos [DictionaryEntry](https://docs.microsoft.com/dotnet/core/api/System.Collections.DictionaryEntry) cuando se enumera, aunque los dos tipos genéricos devuelven objetos [KeyValuePair&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.KeyValuePair-2).  
   
*   Los elementos se ordenan de acuerdo con una implementación [System.Collections.IComparer](https://docs.microsoft.com/dotnet/core/api/System.Collections.IComparer) (para `SortedList` no genérica) o una implementación [System.Collections.Generic.IComparer&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IComparer-1) (para las dos clases genéricas).  
   
 *   Cada clase proporciona propiedades que devuelven colecciones que contienen solo las claves o solo los valores.  
   
La tabla siguiente enumera algunas de las diferencias entre las dos clases de lista ordenada y la clase [SortedDictionary<TKey, TValue>](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedDictionary-2).  
   
 Clase no genérica `SortedList` y clase genérica `SortedList<TKey, TValue>` | Clase genérica `SortedDictionary<TKey, TValue>`  
 --------------------------------------------------------------------------------- | ------------------------------  
 Las propiedades que devuelven claves y valores se indizan, lo que permite una recuperación indizada eficaz. | Sin recuperación indizada.  
 La recuperación es O(log n). | La recuperación es O(log n).  
 La inserción y eliminación son generalmente O(n); pero la inserción es O(1) para los datos que ya están en el criterio de ordenación, de manera que cada elemento se agrega al final de la lista. (Se supone que no es necesario cambiar de tamaño). | La inserción y eliminación son O(log n).  
 Usa menos memoria que `SortedDictionary<TKey, TValue>`. | Usa más memoria que la clase no genérica `SortedList` y la clase genérica `SortedList<TKey, TValue>`.  
  
 Para listas ordenadas o diccionarios que deben ser accesibles simultáneamente desde varios subprocesos, se puede agregar una lógica de ordenación a una clase que deriva de [ConcurrentDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2).  
  
 > [!NOTE]  
 > Para los valores que contienen sus propias claves (por ejemplo, registros de empleados que contienen un número de id. de empleado), puede derivar de la clase genérica [KeyedCollection&lt;TKey, TItem&gt;]() para crear una colección con clave que tenga algunas características de lista y algunas características de diccionario.  
   
 La clase [SortedSet&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedSet-1) proporciona un árbol que mantiene los datos ordenados después de las inserciones, eliminaciones y búsquedas. Esta clase y la clase [HashSet&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.HashSet-1) implementan la interfaz [ISet&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.ISet-1).  
   
## <a name="see-also"></a>Vea también  
  
[System.Collections.IDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary)  
   
[System.Collections.Generic.IDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IDictionary-2)  
   
[ConcurrentDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2)  
 
[Tipos de colección utilizados normalmente](commonly-used-collection-types.md) 

