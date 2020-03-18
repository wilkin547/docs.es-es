---
title: 'Procedimiento Usar expresiones lambda en una consulta: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], in LINQ
ms.assetid: 3cac4d25-d11f-4abd-9e7c-0f02e97ae06d
ms.openlocfilehash: 92bdbf842c5c30b2f32e06f622f3e08f3c7a878f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75711966"
---
# <a name="how-to-use-lambda-expressions-in-a-query-c-programming-guide"></a>Procedimiento Usar expresiones lambda en una consulta (Guía de programación de C#)
No se pueden usar expresiones lambda directamente en la sintaxis de consulta, pero sí en llamadas de método, y las expresiones de consulta pueden contener llamadas de método. De hecho, algunas operaciones de consulta solo se pueden expresar con la sintaxis de método. Para obtener más información sobre la diferencia entre la sintaxis de consulta y la sintaxis de método, vea [Sintaxis de consultas y sintaxis de métodos en LINQ](../concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra cómo usar una expresión lambda en una consulta basada en métodos con el operador de consulta estándar <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType>. Tenga en cuenta que el método <xref:System.Linq.Enumerable.Where%2A> de este ejemplo tiene un parámetro de entrada de tipo delegado <xref:System.Func%602> y que el delegado toma un entero como entrada y devuelve un valor booleano. La expresión lambda se puede convertir en ese delegado. Si se tratara de una consulta de [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] que usa el método <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>, el tipo de parámetro sería `Expression<Func<int,bool>>` pero la expresión lambda tendría exactamente el mismo aspecto. Para más información sobre el tipo Expression, vea <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType>.  
  
 [!code-csharp[csProgGuideLINQ#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csrefLINQHowTos.cs#1)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar una expresión lambda en una llamada de método de una expresión de consulta. La expresión lambda es necesaria porque el operador de consulta estándar <xref:System.Linq.Enumerable.Sum%2A> no se puede invocar con la sintaxis de consulta.  
  
 La consulta agrupa primero los alumnos por curso, tal y como se define en la enumeración `GradeLevel`. Luego, suma las puntuaciones totales por alumno de cada grupo. Esto requiere dos operaciones `Sum`. La `Sum` interna calcula la puntuación total de cada alumno y la `Sum` externa mantiene un total acumulado conjunto de todos los alumnos del grupo.  
  
 [!code-csharp[csProgGuideLINQ#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csrefLINQHowTos.cs#2)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para ejecutar este código, copie y pegue el método en la clase `StudentClass` que se especifica en [Consultar una colección de objetos](../../linq/query-a-collection-of-objects.md) y llámelo desde el método `Main`.
  
## <a name="see-also"></a>Vea también

- [Expresiones lambda](./lambda-expressions.md)
- [Árboles de expresión (C#)](../concepts/expression-trees/index.md)
