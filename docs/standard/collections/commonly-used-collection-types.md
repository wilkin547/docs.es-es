---
title: "Tipos de colección utilizados normalmente | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- collections [.NET Framework], generic
- objects [.NET Framework], grouping in collections
- generics [.NET Framework], collections
- IList interface, grouping data in collections
- IDictionary interface, grouping data in collections
- grouping data in collections, generic collection types
- Collections classes
- generic collections
ms.assetid: f5d4c6a4-0d7b-4944-a9fb-3b12d9ebfd55
caps.latest.revision: 29
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1f8d938d61492b4da4b35a56fba169a12ed4787e
ms.lasthandoff: 04/18/2017

---
# <a name="commonly-used-collection-types"></a>Tipos de colección utilizados normalmente
Los tipos de colecciones son las variaciones comunes de las colecciones de datos, como tablas hash, colas, pilas, bolsas, diccionarios y listas.  
  
 Las colecciones se basan en las interfaces <xref:System.Collections.ICollection>, <xref:System.Collections.IList>, <xref:System.Collections.IDictionary> o sus equivalentes genéricos. Las interfaces <xref:System.Collections.IList> y <xref:System.Collections.IDictionary> se derivan de la interfaz <xref:System.Collections.ICollection>; por lo tanto, todas las colecciones se basan en la interfaz <xref:System.Collections.ICollection> directa o indirectamente. En colecciones basadas en la interfaz <xref:System.Collections.IList> (como <xref:System.Array>, <xref:System.Collections.ArrayList>, o <xref:System.Collections.Generic.List%601>) o directamente en la interfaz <xref:System.Collections.ICollection> (como <xref:System.Collections.Queue>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, <xref:System.Collections.Stack>, <xref:System.Collections.Concurrent.ConcurrentStack%601> o <xref:System.Collections.Generic.LinkedList%601>), cada elemento solo contiene un valor. En colecciones basadas en la interfaz <xref:System.Collections.IDictionary> (como las clases <xref:System.Collections.Hashtable> y <xref:System.Collections.SortedList> y las clases genéricas <xref:System.Collections.Generic.Dictionary%602> y <xref:System.Collections.Generic.SortedList%602>), o las clases <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, cada elemento contiene una clave y un valor.  La clase <xref:System.Collections.ObjectModel.KeyedCollection%602> es única porque es una lista de valores con claves insertadas en los valores y, por tanto, se comporta como una lista y como un diccionario.  
  
 Las colecciones genéricas son la mejor solución para elementos fuertemente tipados. Sin embargo, si su lenguaje no admite genéricos, el espacio de nombres <xref:System.Collections> incluye colecciones base, como <xref:System.Collections.CollectionBase>, <xref:System.Collections.ReadOnlyCollectionBase> y <xref:System.Collections.DictionaryBase>, que son clases base abstractas que se pueden extender para crear clases de colección fuertemente tipadas. Cuando se requiera un acceso eficaz a una colección multiproceso, use las colecciones genéricas del espacio de nombres <xref:System.Collections.Concurrent>.  
  
 Las colecciones pueden variar en función de cómo se almacenan los elementos, cómo se ordenan, cómo se realizan las búsquedas y cómo se realizan las comparaciones. La clase <xref:System.Collections.Queue> y la clase genérica <xref:System.Collections.Generic.Queue%601> proporcionan listas elementos FIFO (el primero en entrar es el primero en salir), mientras que la clase <xref:System.Collections.Stack>(clase) y la clase genérica <xref:System.Collections.Generic.Stack%601> proporcionan listas de tipo LIFO (el último en entrar es el primero en salir). La clase <xref:System.Collections.SortedList> y la clase genérica <xref:System.Collections.Generic.SortedList%602> proporcionan versiones ordenadas de versiones de la clase <xref:System.Collections.Hashtable> y la clase genérica <xref:System.Collections.Generic.Dictionary%602>. Los elementos de la clase <xref:System.Collections.Hashtable> o de la clase genérica <xref:System.Collections.Generic.Dictionary%602> son accesibles por la clave del elemento, pero los elementos de la clase <xref:System.Collections.SortedList> o una clase genérica <xref:System.Collections.ObjectModel.KeyedCollection%602> son accesibles por la clave o el índice del elemento. Los índices de todas las colecciones son de base cero, excepto <xref:System.Array>, que permite matrices que no son de base cero.  
  
 La característica LINQ to Objects permite usar consultas LINQ para acceder a objetos en memoria siempre que el tipo de objeto implemente la interfaz <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>. Las consultas LINQ proporcionan un modelo común para el acceso a datos; suelen ser más concisas y legibles que los bucles `foreach` estándar, y proporcionan capacidades de filtrado, ordenación y agrupación. Las consultas LINQ también pueden mejorar el rendimiento. Para más información, consulte [LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9) y [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Título|Descripción|  
|-----------|-----------------|  
|[Colecciones y estructuras de datos](../../../docs/standard/collections/index.md)|Describe los diversos tipos de colecciones disponibles en [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], como pilas, colas, listas, matrices y diccionarios.|  
|[Tipos de las colecciones Hashtable y Dictionary](../../../docs/standard/collections/hashtable-and-dictionary-collection-types.md)|Describe las características de los tipos de diccionario basado en hash genéricos y no genéricos.|  
|[Tipos de colecciones ordenadas](../../../docs/standard/collections/sorted-collection-types.md)|Describe las clases que proporcionan funcionalidad de ordenación para las listas y los conjuntos.|  
|[Genéricos](../../../docs/standard/generics/index.md)|Describe la característica de genéricos, incluidos colecciones, delegados e interfaces genéricos proporcionados por [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]. Proporciona vínculos a la documentación de características para C#, Visual Basic y Visual C++, así como a tecnologías de apoyo como la reflexión.|  
  
## <a name="reference"></a>Referencia  
 <xref:System.Collections?displayProperty=fullName>  
  
 <xref:System.Collections.Generic?displayProperty=fullName>  
  
 <xref:System.Collections.ICollection?displayProperty=fullName>  
  
 <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName>  
  
 <xref:System.Collections.IList?displayProperty=fullName>  
  
 <xref:System.Collections.Generic.IList%601?displayProperty=fullName>  
  
 <xref:System.Collections.IDictionary?displayProperty=fullName>  
  
 <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>
