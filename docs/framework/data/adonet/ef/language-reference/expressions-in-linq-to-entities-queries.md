---
description: 'Más información sobre: expresiones en consultas de LINQ to Entities'
title: Expresiones en consultas de LINQ to Entities
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: 3ab9e04adb7e823538638ae262f0e481b6948a24
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786373"
---
# <a name="expressions-in-linq-to-entities-queries"></a>Expresiones en consultas de LINQ to Entities

Una expresión es un fragmento de código que se puede evaluar como un valor, objeto, método o espacio de nombres único. Las expresiones pueden contener un valor literal, una llamada a un método, un operador y sus operandos, o un nombre simple. Los nombres simples pueden ser el nombre de una variable, el miembro de un tipo, el parámetro de un método, un espacio de nombres o un tipo. Las expresiones pueden utilizar operadores que a su vez utilizan otras expresiones como parámetros, o llamadas a métodos cuyos parámetros son a su vez otras llamadas a métodos. Por consiguiente, las expresiones pueden ser de muy simples a muy complejas.  
  
 En LINQ to Entities consultas, las expresiones pueden contener cualquier elemento permitido por los tipos dentro del <xref:System.Linq.Expressions> espacio de nombres, incluidas las expresiones lambda. Las expresiones que se pueden usar en las consultas de LINQ to Entities son un superconjunto de las expresiones que se pueden utilizar para consultar el Entity Framework. las expresiones que forman parte de las consultas en el Entity Framework se limitan a las operaciones admitidas por `ObjectQuery<T>` y el origen de datos subyacente.  
  
 En el ejemplo siguiente, la comparación en la cláusula `Where` es una expresión:  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
> Las construcciones de lenguaje específicas, como C# `unchecked` , no tienen ningún significado en LINQ to Entities.  
  
## <a name="in-this-section"></a>En esta sección  

 [Expresiones constantes](constant-expressions.md)  
  
 [Expresiones de comparación](comparison-expressions.md)  
  
 [Comparaciones NULL](null-comparisons.md)  
  
 [Expresiones de inicialización](initialization-expressions.md)  
  
 [Relaciones, propiedades de navegación y claves externas](/ef/ef6/fundamentals/relationships)  
  
## <a name="see-also"></a>Vea también

- [ADO.NET Entity Framework](../index.md)
