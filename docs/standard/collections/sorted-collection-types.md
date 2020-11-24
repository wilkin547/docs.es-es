---
title: Tipos de colecciones ordenadas
ms.date: 04/30/2020
helpviewer_keywords:
- SortedDictionary collection type
- SortedList class, grouping data in collections
- grouping data in collections, SortedList collection type
- SortedList collection type
- collections [.NET], SortedList collection type
ms.assetid: 3db965b2-36a6-4b12-b76e-7f074ff7275a
ms.openlocfilehash: 62e0ffde31d91ea2b0bbe3b5c37cddb87349b5a3
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94823828"
---
# <a name="sorted-collection-types"></a>Tipos de colecciones ordenadas

La clase <xref:System.Collections.SortedList?displayProperty=nameWithType>, la clase genérica <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType> y la clase genérica <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType> son similares a la clase <xref:System.Collections.Hashtable> y a la clase genérica <xref:System.Collections.Generic.Dictionary%602> en que implementan la interfaz <xref:System.Collections.IDictionary>, pero mantienen sus elementos en el criterio de ordenación mediante la clave, y no tienen la inserción O(1) y la característica de recuperación de las tablas hash. Las tres clases tienen varias características en común:

- Las tres clases implementan la interfaz <xref:System.Collections.IDictionary?displayProperty=nameWithType>. Las dos clases genéricas también implementan la interfaz genérica <xref:System.Collections.Generic.IDictionary%602?displayProperty=nameWithType>.

- Cada elemento es un par de clave y valor para propósitos de enumeración.

   > [!NOTE]
   > La clase <xref:System.Collections.SortedList> no genérica devuelve objetos <xref:System.Collections.DictionaryEntry> cuando se enumera, aunque los dos tipos genéricos devuelven objetos <xref:System.Collections.Generic.KeyValuePair%602>.

- Los elementos se ordenan según una implementación <xref:System.Collections.IComparer?displayProperty=nameWithType> (para <xref:System.Collections.SortedList> no genérico) o una implementación <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> (para las dos clases genéricas).

- Cada clase proporciona propiedades que devuelven colecciones que contienen solo las claves o solo los valores.

En la tabla siguiente se enumeran algunas de las diferencias entre las dos clases de lista ordenada y la clase <xref:System.Collections.Generic.SortedDictionary%602>.

| Clase no genérica <xref:System.Collections.SortedList> y clase genérica <xref:System.Collections.Generic.SortedList%602> | Clase genérica <xref:System.Collections.Generic.SortedDictionary%602> |
|--|--|
| Las propiedades que devuelven claves y valores se indizan, lo que permite una recuperación indizada eficaz. | Sin recuperación indizada. |
| La recuperación es O(log `n`). | La recuperación es O(log `n`). |
| La inserción y eliminación son generalmente O(`n`); pero la inserción es O(log `n`) para los datos que ya están en el criterio de ordenación, de manera que cada elemento se agrega al final de la lista. (Se supone que no es necesario cambiar de tamaño). | La inserción y eliminación son O(log `n`). |
| Usa menos memoria que <xref:System.Collections.Generic.SortedDictionary%602>. | Usa más memoria que la clase no genérica <xref:System.Collections.SortedList> y la clase genérica <xref:System.Collections.Generic.SortedList%602>. |

Para listas ordenadas o diccionarios que deben ser accesibles simultáneamente desde varios subprocesos, se puede agregar una lógica de ordenación a una clase que deriva de <xref:System.Collections.Concurrent.ConcurrentDictionary%602>. Al considerar la inmutabilidad, los siguientes tipos inmutables correspondientes siguen una semántica de ordenación similar: <xref:System.Collections.Immutable.ImmutableSortedSet%601> y <xref:System.Collections.Immutable.ImmutableSortedDictionary%602>.

> [!NOTE]
> Para los valores que contienen sus propias claves (por ejemplo, registros de empleados que contienen un número de id. de empleado), puede derivar de la clase genérica <xref:System.Collections.ObjectModel.KeyedCollection%602> para crear una colección con clave que tenga algunas características de lista y algunas características de diccionario.

A partir de .NET Framework 4, la clase <xref:System.Collections.Generic.SortedSet%601> proporciona un árbol de equilibrio automático que mantiene los datos ordenados después de las operaciones de inserción, eliminación y búsqueda. Esta clase y la clase <xref:System.Collections.Generic.HashSet%601> implementan la interfaz <xref:System.Collections.Generic.ISet%601>.

## <a name="see-also"></a>Vea también

- <xref:System.Collections.IDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Generic.IDictionary%602?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.ConcurrentDictionary%602>
- [Tipos de colección utilizados normalmente](commonly-used-collection-types.md)
