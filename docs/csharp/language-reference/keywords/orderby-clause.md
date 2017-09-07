---
title: "orderby (Cláusula, Referencia de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- orderby
- orderby_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ec9507e4c1d9691d90d47cdbb20fdb22fc281d24
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="orderby-clause-c-reference"></a>orderby (Cláusula, Referencia de C#)
En una expresión de consulta, la cláusula `orderby` hace que la secuencia o subsecuencia (grupo) devuelta se ordene de forma ascendente o descendente. Se pueden especificar varias claves para llevar a cabo una o varias operaciones de ordenación secundaria. La ordenación se realiza mediante el comparador predeterminado del tipo de elemento. El criterio de ordenación predeterminado es el ascendente. También puede especificar un comparador personalizado. En cambio, solo está disponible mediante la sintaxis basada en métodos. Para obtener más información, consulte [Sorting Data](http://msdn.microsoft.com/library/6d76e2d7-b418-49b5-ac78-2bcd61169c48) (Ordenación de datos).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, la primera consulta ordena las palabras en orden alfabético a partir de la A y la segunda consulta ordena las mismas palabras en orden descendente. (La palabra clave `ascending` es el valor de ordenación predeterminado y puede omitirse).  
  
 [!code-cs[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, se realiza una ordenación primaria por apellidos de los alumnos y, después, una ordenación secundaria por sus nombres.  
  
 [!code-cs[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_2.cs)]  
  
## <a name="remarks"></a>Comentarios  
 En tiempo de compilación, la cláusula `orderby` se convierte en una llamada al método <xref:System.Linq.Enumerable.OrderBy%2A>. Varias claves en la cláusula `orderby` se convierten en llamadas al método <xref:System.Linq.Enumerable.ThenBy%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Palabras clave de consultas (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [group (Cláusula)](../../../csharp/language-reference/keywords/group-clause.md)   
 [Introducción a LINQ en C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

