---
title: Realizar combinaciones externas izquierdas (LINQ en C#)
description: Obtenga información sobre cómo realizar combinaciones externas izquierdas con LINQ en C#.
ms.date: 12/01/2016
ms.assetid: f542cee6-3169-4dcf-a631-3a6a79ccd473
ms.openlocfilehash: cc08a1c8670623a10d1e0bf10221d02037a8d7bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "61688584"
---
# <a name="perform-left-outer-joins"></a>Realizar operaciones de combinación externa izquierda

Una combinación externa izquierda es una combinación en la que se devuelve cada elemento de la primera colección, independientemente de si tiene elementos correlacionados en la segunda colección. Puede usar LINQ para realizar una combinación externa izquierda llamando al método <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> en los resultados de una combinación agrupada.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo usar el método <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> en los resultados de una combinación agrupada para realizar una combinación externa izquierda.

El primer paso para generar una combinación externa izquierda de dos colecciones consiste en realizar una combinación interna usando una combinación agrupada. (Vea [Realizar combinaciones internas](perform-inner-joins.md) para obtener una explicación de este proceso). En este ejemplo, la lista de objetos de `Person` está unida a la lista de objetos `Pet` basándose en un objeto `Person` que coincide con `Pet.Owner`.

El segundo paso consiste en incluir cada elemento de la primera colección (izquierda) en el conjunto de resultados, incluso cuando no haya coincidencias en la colección derecha. Esto se realiza llamando a <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> en cada secuencia de elementos coincidentes de la combinación agrupada. En este ejemplo, se llama a <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> en cada secuencia de objetos `Pet` coincidentes. El método devuelve una colección que contiene un único, valor predeterminado si la secuencia de objetos `Pet` coincidentes está vacía para cualquier objeto `Person`, con lo que cada objeto `Person` se representa en la colección de resultados.

> [!NOTE]
> El valor predeterminado para un tipo de referencia es `null`; por consiguiente, el ejemplo busca una referencia NULL antes de tener acceso a cada elemento de cada colección de `Pet`.

[!code-csharp[CsLINQProgJoining#7](~/samples/snippets/csharp/concepts/linq/how-to-perform-left-outer-joins_1.cs)]

## <a name="see-also"></a>Vea también

- <xref:System.Linq.Enumerable.Join%2A>
- <xref:System.Linq.Enumerable.GroupJoin%2A>
- [Realizar combinaciones internas](perform-inner-joins.md)
- [Realizar combinaciones agrupadas](perform-grouped-joins.md)
- [Tipos anónimos (Guía de programación de C#)](../programming-guide/classes-and-structs/anonymous-types.md).
