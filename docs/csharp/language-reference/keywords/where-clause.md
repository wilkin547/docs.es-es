---
title: where (Cláusula, Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- whereclause_CSharpKeyword
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
ms.openlocfilehash: 8607c79a8b1e9a9fd999e4f5b77ecfac786161b3
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "43003156"
---
# <a name="where-clause-c-reference"></a>where (Cláusula, Referencia de C#)
La cláusula `where` se usa en una expresión de consulta para especificar los elementos del origen de datos que se devuelven en dicha expresión. Aplica una condición booleana (*predicate*) a cada elemento de origen (al que hace referencia la variable de rango) y devuelve aquellos en los que la condición especificada se cumple. Puede que una sola expresión de consulta contenga varias cláusulas `where` y que una sola cláusula contenga varias subexpresiones de predicado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, la cláusula `where` filtra todos los números excepto los que son inferiores a cinco. Si la cláusula `where` se quita, se devolverán todos los números del origen de datos. La expresión `num < 5` es el predicado que se aplica a cada elemento.  
  
 [!code-csharp[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 En una sola cláusula `where`, se pueden especificar todos los predicados que sean necesarios mediante los operadores [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) y [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md). En el ejemplo siguiente, la consulta especifica dos predicados para seleccionar únicamente los números pares que sean inferiores a cinco.  
  
 [!code-csharp[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_2.cs)]  
  
## <a name="example"></a>Ejemplo  
 Puede que una cláusula `where` contenga uno o más métodos que devuelvan valores booleanos. En el ejemplo siguiente, la cláusula `where` usa un método para determinar si el valor actual de la variable de rango es par o impar.  
  
 [!code-csharp[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_3.cs)]  
  
## <a name="remarks"></a>Comentarios  
 La cláusula `where` es un mecanismo de filtrado. Se puede colocar prácticamente en cualquier parte en una expresión de consulta, pero no puede ser la primera ni la última cláusula. Puede que una cláusula `where` aparezca antes o después de una cláusula [group](../../../csharp/language-reference/keywords/group-clause.md), en función de que haya que filtrar los elementos de origen antes o después de agruparlos.  
  
 Si un predicado especificado no es válido para los elementos del origen de datos, se producirá un error en tiempo de compilación. Esta es una de las ventajas de la comprobación estricta de tipos que [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] ofrece.  
  
 En tiempo de compilación, la palabra clave `where` se convierte en una llamada al método de operador de consulta estándar <xref:System.Linq.Enumerable.Where%2A>.  
  
## <a name="see-also"></a>Vea también

- [Palabras clave para consultas (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)  
- [from (cláusula)](../../../csharp/language-reference/keywords/from-clause.md)  
- [select (cláusula)](../../../csharp/language-reference/keywords/select-clause.md)  
- [Filtrado de datos](../../programming-guide/concepts/linq/filtering-data.md)  
- [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)  
- [Introducción a LINQ en C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
