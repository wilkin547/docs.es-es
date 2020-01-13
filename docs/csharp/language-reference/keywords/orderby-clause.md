---
title: 'Cláusula orderby: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- orderby
- orderby_CSharpKeyword
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
ms.openlocfilehash: d88b2b40f63f0616cfd54e8abb62f1bc2183f776
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713295"
---
# <a name="orderby-clause-c-reference"></a>orderby (Cláusula, Referencia de C#)

En una expresión de consulta, la cláusula `orderby` hace que la secuencia o subsecuencia (grupo) devuelta se ordene de forma ascendente o descendente. Se pueden especificar varias claves para llevar a cabo una o varias operaciones de ordenación secundaria. La ordenación se realiza mediante el comparador predeterminado del tipo de elemento. El criterio de ordenación predeterminado es el ascendente. También puede especificar un comparador personalizado. En cambio, solo está disponible mediante la sintaxis basada en métodos. Para obtener más información, consulte [Sorting Data](../../programming-guide/concepts/linq/sorting-data.md) (Ordenación de datos).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, la primera consulta ordena las palabras en orden alfabético a partir de la A y la segunda consulta ordena las mismas palabras en orden descendente. (La palabra clave `ascending` es el valor de ordenación predeterminado y puede omitirse).

[!code-csharp[cscsrefQueryKeywords#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#20)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, se realiza una ordenación primaria por apellidos de los alumnos y, después, una ordenación secundaria por sus nombres.

[!code-csharp[cscsrefQueryKeywords#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#22)]

## <a name="remarks"></a>Comentarios

En tiempo de compilación, la cláusula `orderby` se convierte en una llamada al método <xref:System.Linq.Enumerable.OrderBy%2A>. Varias claves en la cláusula `orderby` se convierten en llamadas al método <xref:System.Linq.Enumerable.ThenBy%2A>.

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Palabras clave para consultas (LINQ)](query-keywords.md)
- [Language-Integrated Query (LINQ)](../../linq/index.md)
- [group (cláusula)](group-clause.md)
- [Introducción a LINQ en C#](/dotnet/csharp/programming-guide/concepts/linq/)
