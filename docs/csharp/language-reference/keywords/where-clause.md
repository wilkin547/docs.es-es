---
title: "where (Cláusula, Referencia de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- whereclause_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
caps.latest.revision: 16
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1094f68293dd05fdfe69a39016689cbaa3fd6290
ms.lasthandoff: 03/13/2017

---
# <a name="where-clause-c-reference"></a>where (Cláusula, Referencia de C#)
La cláusula `where` se usa en una expresión de consulta para especificar los elementos del origen de datos que se devuelven en dicha expresión. Aplica una condición booleana (*predicate*) a cada elemento de origen (al que hace referencia la variable de rango) y devuelve aquellos en los que la condición especificada se cumple. Puede que una sola expresión de consulta contenga varias cláusulas `where` y que una sola cláusula contenga varias subexpresiones de predicado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, la cláusula `where` filtra todos los números excepto los que son inferiores a cinco. Si la cláusula `where` se quita, se devolverán todos los números del origen de datos. La expresión `num < 5` es el predicado que se aplica a cada elemento.  
  
 [!code-cs[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 En una sola cláusula `where`, se pueden especificar todos los predicados que sean necesarios mediante los operadores [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) y [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md). En el ejemplo siguiente, la consulta especifica dos predicados para seleccionar únicamente los números pares que sean inferiores a cinco.  
  
 [!code-cs[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_2.cs)]  
  
## <a name="example"></a>Ejemplo  
 Puede que una cláusula `where` contenga uno o más métodos que devuelvan valores booleanos. En el ejemplo siguiente, la cláusula `where` usa un método para determinar si el valor actual de la variable de rango es par o impar.  
  
 [!code-cs[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_3.cs)]  
  
## <a name="remarks"></a>Comentarios  
 La cláusula `where` es un mecanismo de filtrado. Se puede colocar prácticamente en cualquier parte en una expresión de consulta, pero no puede ser la primera ni la última cláusula. Puede que una cláusula `where` aparezca antes o después de una cláusula [group](../../../csharp/language-reference/keywords/group-clause.md), en función de que haya que filtrar los elementos de origen antes o después de agruparlos.  
  
 Si un predicado especificado no es válido para los elementos del origen de datos, se producirá un error en tiempo de compilación. Esta es una de las ventajas de la comprobación estricta de tipos que [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] ofrece.  
  
 En tiempo de compilación, la palabra clave `where` se convierte en una llamada al método de operador de consulta estándar <xref:System.Linq.Enumerable.Where%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Palabras clave para consultas (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [from (Cláusula)](../../../csharp/language-reference/keywords/from-clause.md)   
 [select (Cláusula)](../../../csharp/language-reference/keywords/select-clause.md)   
 [Filtrado de datos](http://msdn.microsoft.com/library/cee88d0f-31aa-4c60-9452-cc122ed0057d)   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Introducción a LINQ en C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
