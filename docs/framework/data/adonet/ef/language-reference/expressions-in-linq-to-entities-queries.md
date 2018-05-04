---
title: Expresiones en consultas de LINQ to Entities
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: f9230e9b5ac0c906652c03111b82df5147267143
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="expressions-in-linq-to-entities-queries"></a>Expresiones en consultas de LINQ to Entities
Una expresión es un fragmento de código que se puede evaluar como un valor, objeto, método o espacio de nombres único. Las expresiones pueden contener un valor literal, una llamada a un método, un operador y sus operandos, o un nombre simple. Los nombres simples pueden ser el nombre de una variable, el miembro de un tipo, el parámetro de un método, un espacio de nombres o un tipo. Las expresiones pueden utilizar operadores que a su vez utilizan otras expresiones como parámetros, o llamadas a métodos cuyos parámetros son a su vez otras llamadas a métodos. Por consiguiente, las expresiones pueden ser de muy simples a muy complejas.  
  
 En [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] de las consultas, las expresiones pueden contener cualquier elemento permitido por los tipos dentro del <xref:System.Linq.Expressions> espacio de nombres, incluyendo expresiones lambda. Las expresiones que se pueden utilizar en las consultas de [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] son un supraconjunto de las expresiones que se pueden utilizar para consultar [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].  Las expresiones que forman parte de las consultas realizadas en el [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] están limitadas por las operaciones admitidas por `ObjectQuery<T>` y el origen de datos subyacente.  
  
 En el ejemplo siguiente, la comparación en la cláusula `Where` es una expresión:  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
>  Las estructuras de un lenguaje concreto, como `unchecked`de C#, no tienen ningún significado en [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
 [Expresiones constantes](../../../../../../docs/framework/data/adonet/ef/language-reference/constant-expressions.md)  
  
 [Expresiones de comparación](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-expressions.md)  
  
 [Comparaciones NULL](../../../../../../docs/framework/data/adonet/ef/language-reference/null-comparisons.md)  
  
 [Expresiones de inicialización](../../../../../../docs/framework/data/adonet/ef/language-reference/initialization-expressions.md)  
  
 [Propiedades de navegación](http://msdn.microsoft.com/library/41e1e6b9-8a57-467d-99d9-1857d2ca2ea5)  
  
## <a name="see-also"></a>Vea también  
 [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)
