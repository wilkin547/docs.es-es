---
title: "Cómo: Usar expresiones lambda en una consulta (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- lambda expressions [C#], in LINQ
ms.assetid: 3cac4d25-d11f-4abd-9e7c-0f02e97ae06d
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
ms.openlocfilehash: 7bfc46015b0d4603c4d63478e804f862c0c65b68
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-use-lambda-expressions-in-a-query-c-programming-guide"></a>Cómo: Usar expresiones lambda en una consulta (Guía de programación de C#)
No se pueden usar expresiones lambda directamente en la sintaxis de consulta, pero sí en llamadas de método, y las expresiones de consulta pueden contener llamadas de método. De hecho, algunas operaciones de consulta solo se pueden expresar con la sintaxis de método. Para obtener más información sobre la diferencia entre la sintaxis de consulta y la sintaxis de método, vea [Query Syntax and Method Syntax in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md) (Sintaxis de consulta y sintaxis de método en LINQ).  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra cómo usar una expresión lambda en una consulta basada en métodos con el operador de consulta estándar <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName>. Tenga en cuenta que el método <xref:System.Linq.Enumerable.Where%2A> de este ejemplo tiene un parámetro de entrada de tipo delegado <xref:System.Func%601> y que el delegado toma un entero como entrada y devuelve un valor booleano. La expresión lambda se puede convertir en ese delegado. Si se tratara de una consulta de [!INCLUDE[vbtecdlinq](../../../csharp/includes/vbtecdlinq_md.md)] que usa el método <xref:System.Linq.Queryable.Where%2A?displayProperty=fullName>, el tipo de parámetro sería `Expression<Func\<int,bool>>` pero la expresión lambda tendría exactamente el mismo aspecto. Para obtener más información sobre el tipo de expresión, vea <xref:System.Linq.Expressions.Expression?displayProperty=fullName>.  
  
 [!code-cs[csProgGuideLINQ#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar una expresión lambda en una llamada de método de una expresión de consulta. La expresión lambda es necesaria porque el operador de consulta estándar <xref:System.Linq.Enumerable.Sum%2A> no se puede invocar con la sintaxis de consulta.  
  
 La consulta agrupa primero los alumnos por curso, tal y como se define en la enumeración `GradeLevel`. Luego, suma las puntuaciones totales por alumno de cada grupo. Esto requiere dos operaciones `Sum`. La `Sum` interna calcula la puntuación total de cada alumno y la `Sum` externa mantiene un total acumulado conjunto de todos los alumnos del grupo.  
  
 [!code-cs[csProgGuideLINQ#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_2.cs)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para ejecutar este código, copie y pegue el método en la `StudentClass` que se especifica en [Cómo: Realizar una consulta en una colección de objetos (Guía de programación de C#)](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md) y llámelo desde el método `Main`.  
  
## <a name="see-also"></a>Vea también  
 [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
 [Árboles de expresión](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)
