---
title: Cuándo utilizar colecciones genéricas
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- collections [.NET Framework], generic
- generic collections [.NET Framework]
ms.assetid: e7b868b1-11fe-4ac5-bed3-de68aca47739
ms.openlocfilehash: 7d59259c1cab6842ef62888bf5326225394d8d44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "75711212"
---
# <a name="when-to-use-generic-collections"></a>Cuándo utilizar colecciones genéricas
Generalmente se recomienda usar colecciones genéricas, ya que se obtiene la ventaja inmediata de la seguridad de tipos sin necesidad de derivar de un tipo de colección base ni de implementar miembros específicos de tipo. Los tipos de colección genéricos también suelen funcionan mejor que los correspondientes tipos de colección no genéricos (y mejor que los tipos que se derivan de los tipos de colección base no genéricos) cuando los elementos de la colección son tipos de valor; esto se debe a que con los genéricos no es necesario realizar una conversión boxing de los elementos.  
  
 En programas destinados a .NET Framework 4 o una versión posterior, utilice las clases de colección genérica en el espacio de nombres <xref:System.Collections.Concurrent> cuando varios subprocesos puedan agregar o quitar elementos de la colección al mismo tiempo.  
  
 Los siguientes tipos genéricos corresponden a los tipos de colección existentes:  
  
- <xref:System.Collections.Generic.List%601> es la clase genérica que se corresponde con <xref:System.Collections.ArrayList>.  
  
- <xref:System.Collections.Generic.Dictionary%602> y <xref:System.Collections.Concurrent.ConcurrentDictionary%602> son las clases genéricas que se corresponden con <xref:System.Collections.Hashtable>.  
  
- <xref:System.Collections.ObjectModel.Collection%601> es la clase genérica que se corresponde con <xref:System.Collections.CollectionBase>. <xref:System.Collections.ObjectModel.Collection%601> puede utilizarse como una clase base, pero, a diferencia de <xref:System.Collections.CollectionBase>, no es abstracta. Esto la hace mucho más fácil de usar.  
  
- <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> es la clase genérica que se corresponde con <xref:System.Collections.ReadOnlyCollectionBase>. <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> no es abstracta y tiene un constructor que hace más fácil exponer una <xref:System.Collections.Generic.List%601> existente como una colección de solo lectura.  
  
- Las clases genéricas <xref:System.Collections.Generic.Queue%601>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, <xref:System.Collections.Generic.Stack%601>, <xref:System.Collections.Concurrent.ConcurrentStack%601>y <xref:System.Collections.Generic.SortedList%602> se corresponden con las respectivas clases no genéricas de igual nombre.  
  
## <a name="additional-types"></a>Tipos adicionales  
 Hay varios tipos de colección genéricos que no tienen un tipo homólogo no genérico. Entre esos tipos se incluyen los siguientes:  
  
- <xref:System.Collections.Generic.LinkedList%601> es una lista vinculada de uso general que proporciona operaciones de eliminación e inserción O(1).  
  
- <xref:System.Collections.Generic.SortedDictionary%602> es un diccionario ordenado con operaciones de eliminación e inserción O(log `n`), lo que lo convierte en una alternativa útil a <xref:System.Collections.Generic.SortedList%602>.  
  
- <xref:System.Collections.ObjectModel.KeyedCollection%602> es un híbrido entre una lista y un diccionario, lo que proporciona una manera de almacenar objetos que contienen sus propias claves.  
  
- <xref:System.Collections.Concurrent.BlockingCollection%601> implementa una clase de colección con funcionalidad de límite y bloqueo.  
  
- <xref:System.Collections.Concurrent.ConcurrentBag%601> proporciona una rápida inserción y eliminación de elementos no ordenados.  
  
## <a name="linq-to-objects"></a>LINQ to Objects  
 La característica LINQ to Objects permite usar consultas LINQ para obtener acceso a los objetos en memoria mientras el tipo de objeto implemente la interfaz <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> . Las consultas LINQ proporcionan un modelo común para el acceso a datos; suelen ser más concisas y legibles que los bucles `foreach` estándar, y proporcionan capacidades de filtrado, ordenación y agrupación. Las consultas LINQ también pueden mejorar el rendimiento. Para más información, vea [LINQ to Objects (C#)](../../csharp/programming-guide/concepts/linq/linq-to-objects.md), [LINQ to Objects (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) y [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## <a name="additional-functionality"></a>Funcionalidad adicional  
 Algunos de los tipos genéricos tienen funcionalidades que no se encuentran en los tipos de colección no genéricos. Por ejemplo, la clase <xref:System.Collections.Generic.List%601> , que se corresponde con la clase <xref:System.Collections.ArrayList> no genérica, tiene una serie de métodos que aceptan delegados genéricos, como el delegado <xref:System.Predicate%601> que permite especificar los métodos de búsqueda en la lista, el delegado <xref:System.Action%601> que representa los métodos que actúan en cada elemento de la lista y el delegado <xref:System.Converter%602> que permite definir conversiones entre tipos.  
  
 La clase <xref:System.Collections.Generic.List%601> permite especificar sus propias implementaciones de interfaz genérica <xref:System.Collections.Generic.IComparer%601> para la ordenación y búsqueda en la lista. Las clases <xref:System.Collections.Generic.SortedDictionary%602> y <xref:System.Collections.Generic.SortedList%602> también tienen esta capacidad. Además, estas clases le permiten especificar los comparadores cuando se crea la colección. De forma similar, las clases <xref:System.Collections.Generic.Dictionary%602> y <xref:System.Collections.ObjectModel.KeyedCollection%602> le permiten especificar sus propios comparadores de igualdad.  
  
## <a name="see-also"></a>Vea también

- [Colecciones y estructuras de datos](../../../docs/standard/collections/index.md)
- [Tipos de colección utilizados normalmente](../../../docs/standard/collections/commonly-used-collection-types.md)
- [Genéricos](../../../docs/standard/generics/index.md)
