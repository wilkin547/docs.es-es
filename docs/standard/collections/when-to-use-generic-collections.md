---
title: Cuándo utilizar colecciones genéricas
ms.date: 04/30/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- collections [.NET Framework], generic
- generic collections [.NET Framework]
ms.assetid: e7b868b1-11fe-4ac5-bed3-de68aca47739
ms.openlocfilehash: c59a125a8df95e3c4fe6e1839956d800bd6ee910
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290388"
---
# <a name="when-to-use-generic-collections"></a>Cuándo utilizar colecciones genéricas

El uso de colecciones genéricas ofrece la ventaja inmediata de la seguridad de tipos sin necesidad de derivar de un tipo de colección base ni de implementar miembros específicos de tipo. Los tipos de colección genéricos también suelen funcionan mejor que los correspondientes tipos de colección no genéricos (y mejor que los tipos que se derivan de los tipos de colección base no genéricos) cuando los elementos de la colección son tipos de valor. Esto se debe a que con los genéricos no es necesario realizar una conversión boxing de los elementos.

En programas destinados a .NET Standard 1.0 o una versión posterior, utilice las clases de colección genérica en el espacio de nombres <xref:System.Collections.Concurrent> cuando varios subprocesos puedan agregar o quitar elementos de la colección simultáneamente. Además, cuando busque inmutabilidad, tenga en cuenta las clases de colección genéricas en el espacio de nombres <xref:System.Collections.Immutable>.

Los siguientes tipos genéricos corresponden a los tipos de colección existentes:

- <xref:System.Collections.Generic.List%601> es la clase genérica que se corresponde con <xref:System.Collections.ArrayList>.

- <xref:System.Collections.Generic.Dictionary%602> y <xref:System.Collections.Concurrent.ConcurrentDictionary%602> son las clases genéricas que se corresponden con <xref:System.Collections.Hashtable>.

- <xref:System.Collections.ObjectModel.Collection%601> es la clase genérica que se corresponde con <xref:System.Collections.CollectionBase>. <xref:System.Collections.ObjectModel.Collection%601> puede utilizarse como una clase base pero, a diferencia de <xref:System.Collections.CollectionBase>, no es abstracta, lo que hace que sea mucho más fácil de usar.

- <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> es la clase genérica que se corresponde con <xref:System.Collections.ReadOnlyCollectionBase>. La colección <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> no es abstracta y tiene un constructor que hace más fácil exponer una colección <xref:System.Collections.Generic.List%601> existente como de solo lectura.

- Las clases genéricas <xref:System.Collections.Generic.Queue%601>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, <xref:System.Collections.Immutable.ImmutableQueue%601>, <xref:System.Collections.Immutable.ImmutableArray%601>, <xref:System.Collections.Generic.SortedList%602> y <xref:System.Collections.Immutable.ImmutableSortedSet%601> se corresponden con las respectivas clases no genéricas de igual nombre.

## <a name="additional-types"></a>Tipos adicionales

Hay varios tipos de colección genéricos que no tienen un tipo homólogo no genérico. Entre esos tipos se incluyen los siguientes:

- <xref:System.Collections.Generic.LinkedList%601> es una lista vinculada de uso general que proporciona operaciones de eliminación e inserción O(1).

- <xref:System.Collections.Generic.SortedDictionary%602> es un diccionario ordenado con operaciones de eliminación e inserción O(log `n`), lo que lo convierte en una alternativa útil a <xref:System.Collections.Generic.SortedList%602>.

- <xref:System.Collections.ObjectModel.KeyedCollection%602> es un híbrido entre una lista y un diccionario, lo que proporciona una manera de almacenar objetos que contienen sus propias claves.

- <xref:System.Collections.Concurrent.BlockingCollection%601> implementa una clase de colección con funcionalidad de límite y bloqueo.

- <xref:System.Collections.Concurrent.ConcurrentBag%601> proporciona una rápida inserción y eliminación de elementos no ordenados.

### <a name="immutable-builders"></a>Generadores inmutables

Si quiere disponer de la funcionalidad de inmutabilidad en la aplicación, el espacio de nombres <xref:System.Collections.Immutable> ofrece tipos de colección genéricos que se pueden usar. Todos los tipos de colección inmutables ofrecen clases `Builder` que pueden optimizar el rendimiento cuando se realicen varias mutaciones. La clase `Builder` agrupa las operaciones en un estado mutable. Cuando se hayan completado todas las mutaciones, llame al método `ToImmutable` para "inmovilizar" todos los nodos y crear una colección genérica inmutable, por ejemplo, una colección <xref:System.Collections.Immutable.ImmutableList%601>.

Se puede crear el objeto `Builder` llamando al método `CreateBuilder()` no genérico. En una instancia de `Builder`, se puede llamar a `ToImmutable()`. Del mismo modo, en la colección `Immutable*`, se puede llamar a `ToBuilder()` para crear una instancia de generador a partir de la colección inmutable genérica. Estos son los distintos tipos de `Builder`.

- <xref:System.Collections.Immutable.ImmutableArray%601.Builder>
- <xref:System.Collections.Immutable.ImmutableDictionary%602.Builder>
- <xref:System.Collections.Immutable.ImmutableHashSet%601.Builder>
- <xref:System.Collections.Immutable.ImmutableList%601.Builder>
- <xref:System.Collections.Immutable.ImmutableSortedDictionary%602.Builder>
- <xref:System.Collections.Immutable.ImmutableSortedSet%601.Builder>

## <a name="linq-to-objects"></a>LINQ to Objects

La característica LINQ to Objects permite usar consultas LINQ para obtener acceso a los objetos en memoria mientras el tipo de objeto implemente la interfaz <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> . Las consultas LINQ proporcionan un patrón común para acceder a los datos; suelen ser más concisas y legibles que los bucles `foreach` estándar y proporcionan capacidades de filtrado, ordenación y agrupación. Las consultas LINQ también pueden mejorar el rendimiento. Para más información, vea [LINQ to Objects (C#)](../../csharp/programming-guide/concepts/linq/linq-to-objects.md), [LINQ to Objects (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) y [Parallel LINQ (PLINQ)](../parallel-programming/introduction-to-plinq.md).

## <a name="additional-functionality"></a>Funcionalidad adicional
Algunos de los tipos genéricos tienen funcionalidades que no se encuentran en los tipos de colección no genéricos. Por ejemplo, la clase <xref:System.Collections.Generic.List%601> , que se corresponde con la clase <xref:System.Collections.ArrayList> no genérica, tiene una serie de métodos que aceptan delegados genéricos, como el delegado <xref:System.Predicate%601> que permite especificar los métodos de búsqueda en la lista, el delegado <xref:System.Action%601> que representa los métodos que actúan en cada elemento de la lista y el delegado <xref:System.Converter%602> que permite definir conversiones entre tipos.

La clase <xref:System.Collections.Generic.List%601> permite especificar sus propias implementaciones de interfaz genérica <xref:System.Collections.Generic.IComparer%601> para la ordenación y búsqueda en la lista. Las clases <xref:System.Collections.Generic.SortedDictionary%602> y <xref:System.Collections.Generic.SortedList%602> también tienen esta capacidad. Además, estas clases le permiten especificar los comparadores cuando se crea la colección. De forma similar, las clases <xref:System.Collections.Generic.Dictionary%602> y <xref:System.Collections.ObjectModel.KeyedCollection%602> le permiten especificar sus propios comparadores de igualdad.

## <a name="see-also"></a>Vea también

- [Colecciones y estructuras de datos](index.md)
- [Tipos de colección utilizados normalmente](commonly-used-collection-types.md)
- [Genéricos](../generics/index.md)
