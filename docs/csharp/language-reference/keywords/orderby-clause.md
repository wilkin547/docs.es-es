---
title: orderby (Cláusula, Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- orderby
- orderby_CSharpKeyword
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
ms.openlocfilehash: 1fd0036e8bd3c838fe92ca27635cd7638d59ef1d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="orderby-clause-c-reference"></a>orderby (Cláusula, Referencia de C#)
En una expresión de consulta, la cláusula `orderby` hace que la secuencia o subsecuencia (grupo) devuelta se ordene de forma ascendente o descendente. Se pueden especificar varias claves para llevar a cabo una o varias operaciones de ordenación secundaria. La ordenación se realiza mediante el comparador predeterminado del tipo de elemento. El criterio de ordenación predeterminado es el ascendente. También puede especificar un comparador personalizado. En cambio, solo está disponible mediante la sintaxis basada en métodos. Para obtener más información, consulte [Sorting Data](../../programming-guide/concepts/linq/sorting-data.md) (Ordenación de datos).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, la primera consulta ordena las palabras en orden alfabético a partir de la A y la segunda consulta ordena las mismas palabras en orden descendente. (La palabra clave `ascending` es el valor de ordenación predeterminado y puede omitirse).  
  
 [!code-csharp[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, se realiza una ordenación primaria por apellidos de los alumnos y, después, una ordenación secundaria por sus nombres.  
  
 [!code-csharp[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_2.cs)]  
  
## <a name="remarks"></a>Comentarios  
 En tiempo de compilación, la cláusula `orderby` se convierte en una llamada al método <xref:System.Linq.Enumerable.OrderBy%2A>. Varias claves en la cláusula `orderby` se convierten en llamadas al método <xref:System.Linq.Enumerable.ThenBy%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Palabras clave para consultas (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)  
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [group (cláusula)](../../../csharp/language-reference/keywords/group-clause.md)  
 [Introducción a LINQ en C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
