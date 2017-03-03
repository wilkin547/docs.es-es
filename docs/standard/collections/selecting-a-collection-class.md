---
title: "Seleccionar una clase de colección"
description: "Seleccionar una clase de colección"
keywords: .NET, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 0a60fca7-e082-48d4-9dda-30b0d3e67ec7
translationtype: Human Translation
ms.sourcegitcommit: 763433b00ae7d01cfa0c7fa250f51d23a95f6f15
ms.openlocfilehash: d174d0cb910035340fb317521f3ad930d16853c2
ms.lasthandoff: 01/18/2017

---

# <a name="selecting-a-collection-class"></a>Seleccionar una clase de colección

Asegúrese de elegir con cuidado la clase de colección. Usar un tipo incorrecto puede restringir el uso de la colección. Se preferirán las versiones genéricas y simultáneas de las colecciones por la mayor seguridad de los tipos y otras mejoras. En general, evite usar los tipos del espacio de nombres System.Collections a menos que su objetivo sea específicamente la versión 1.1 de .NET Framework. 

Pregúntese lo siguiente:

* ¿Necesita una lista secuencial en la que normalmente se descarta el elemento después de recuperar su valor? 

    * En caso afirmativo, considere el uso de la clase genérica [System.Collections.Generic.Queue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Queue-1) si necesita un comportamiento FIFO (primero en entrar, primero en salir). Considere el uso de la clase genérica [System.Collections.Generic.Stack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Stack-1) si necesita un comportamiento LIFO (el último en entrar es el primero en salir). Para obtener acceso seguro desde varios subprocesos, use las versiones simultáneas [System.Collections.Concurrent.ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1) y [System.Collections.Concurrent.ConcurrentStack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1).
    
    * En caso contrario, considere usar las demás colecciones.
    
* ¿Necesita acceder a los elementos en cierto orden, como FIFO, LIFO o aleatorio?

    * Las clases genéricas [System.Collections.Generic.Queue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Queue-1) y [System.Collections.Concurrent.ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1) ofrecen acceso FIFO. Para obtener más información, consulte [Cuándo usar una colección segura para subprocesos](threadsafe/when-to-use-a-thread-safe-collection.md).
    
    * Las clases genéricas [System.Collections.Generic.Stack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Stack-1) y [System.Collections.Concurrent.ConcurrentStack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1) ofrecen acceso LIFO. Para obtener más información, consulte [Cuándo usar una colección segura para subprocesos](threadsafe/when-to-use-a-thread-safe-collection.md).
    
    * La clase genérica [System.Collections.Generic.LinkedList&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.LinkedList-1) permite el acceso secuencial desde el encabezado hasta el final o desde el final hasta el encabezado.
    
* ¿Necesita acceder a cada elemento por índice? 

    * La clase [System.Collections.Specialized.StringCollection](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.StringCollection) y la clase genérica [System.Collections.Generic.List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1) ofrecen acceso a sus elementos por el índice de base cero del elemento. 
    
    * Las clases [System.Collections.Specialized.ListDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.ListDictionary) y [System.Collections.Specialized.StringDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.StringDictionary) y las clases genéricas [System.Collections.Generic.Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) y [System.Collections.Generic.SortedDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedDictionary-2) ofrecen acceso a sus elementos por la clave del elemento.
    
    * Las clases [System.Collections.Specialized.NameObjectCollectionBase](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.NameObjectCollectionBase) y [System.Collections.Specialized.NameValueCollection](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.NameValueCollection) y las clases genéricas [System.Collections.ObjectModel.KeyedCollection&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.KeyedCollection-2) y [System.Collections.Generic.SortedList&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2) ofrecen acceso a sus elementos por índice de base cero o por la clave del elemento.
    
* ¿Cada elemento contendrá un valor, una combinación de una clave y un valor, o una combinación de una clave y varios valores? 

    * Un valor: use cualquiera de las colecciones basadas en la interfaz genérica [System.Collections.Generic.IList&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IList-1).
    
    * Una clave y un valor: use cualquiera de las colecciones basadas en la interfaz genérica [System.Collections.Generic.IDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IDictionary-2).
    
    * Un valor con clave incrustada: use la clase genérica [System.Collections.ObjectModel.KeyedCollection&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.KeyedCollection-2).
    
    * Una clave y varios valores: use la clase [System.Collections.Specialized.NameValueCollection](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.NameValueCollection).
    
* ¿Necesita ordenar los elementos de manera diferente a como se especificaron? 

    * La clase [System.Collections.Hashtable](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable) ordena los elementos por sus códigos hash.
    
    * Las clases genéricas [System.Collections.Generic.SortedDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedDictionary-2) y [System.Collections.Generic.SortedList&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2) ordenan sus elementos por la clave, basándose en las implementaciones de la interfaz [System.Collections.IComparer](https://docs.microsoft.com/dotnet/core/api/System.Collections.IComparer) y la interfaz genérica [System.Collections.Generic.IComparer&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IComparer-1).
    
    * La clase genérica [System.Collections.Generic.List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1) proporciona un método `Sort` que toma como parámetro una implementación de la interfaz genérica `IComparer<T>`.
    
* ¿Necesita colecciones que acepten solo cadenas? 

    * [StringCollection](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.StringCollection) (basada en [System.Collections.IList](https://docs.microsoft.com/dotnet/core/api/System.Collections.IList)) y [StringDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.StringDictionary) (basada en [System.Collections.IDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary)) están en el espacio de nombres [System.Collections.Specialized](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized). 
    
    * Además, puede usar cualquiera de las clases de colección genéricas del espacio de nombres [System.Collections.Generic](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic) como colecciones de cadenas fuertemente tipadas especificando la clase `String` para sus argumentos de tipo genéricos.
    
## <a name="linq-to-objects"></a>LINQ to Objects

LINQ to Objects permite a los programadores usar consultas LINQ para tener acceso a objetos en memoria siempre que el tipo de objeto implemente [System.Collections.IEnumerable](https://docs.microsoft.com/dotnet/core/api/System.Collections.IEnumerable) o [System.Collections.Generic.IEnumerable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IEnumerable-1). Las consultas LINQ proporcionan un modelo común para el acceso a datos; suelen ser más concisas y legibles que los bucles foreach estándar, y proporcionan capacidades de filtrado, ordenación y agrupación. Para obtener más información, consulte [Language Integrated Query (LINQ)](../../csharp/linq/index.md).

## <a name="see-also"></a>Vea también

[System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections)

[System.Collections.Specialized](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized)

[System.Collections.Generic](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic)

[Colecciones seguras para subprocesos](threadsafe/index.md)

