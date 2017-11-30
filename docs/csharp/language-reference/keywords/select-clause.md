---
title: "select (Cláusula, Referencia de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- select_CSharpKeyword
- select
helpviewer_keywords:
- select keyword [C#]
- select clause [C#]
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f40bc26d1812e76ac618c5a0ddf23c4cef2700d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="select-clause-c-reference"></a>select (Cláusula, Referencia de C#)
En una expresión de consulta, la cláusula `select` especifica el tipo de valores que se producirán cuando se ejecute la consulta. El resultado se basa en la evaluación de todas las cláusulas anteriores y en cualquier expresión de la propia cláusula `select`. Una expresión de consulta debe finalizar con una cláusula `select` o con una cláusula [group](../../../csharp/language-reference/keywords/group-clause.md).  
  
 En el ejemplo siguiente, se muestra una cláusula `select` simple en una expresión de consulta.  
  
 [!code-csharp[cscsrefQueryKeywords#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_1.cs)]  
  
 El tipo de la secuencia generada por la cláusula `select` determina el tipo de la variable de consulta `queryHighScores`. En el caso más simple, la cláusula `select` simplemente especifica la variable de rango. Esto hace que la secuencia devuelta contenga elementos del mismo tipo que el origen de datos. Para obtener más información, vea [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md) (Relaciones entre tipos en las operaciones de consulta LINQ). En cambio, la cláusula `select` también proporciona un mecanismo eficaz para transformar (o *proyectar*) el origen de datos en nuevos tipos. Para obtener más información, vea [Transformaciones de datos con LINQ (C#)](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, se muestran las distintas formas que puede tener una cláusula `select`. En cada consulta, tenga en cuenta la relación entre la cláusula `select` y el tipo de la *variable de consulta* (`studentQuery1`, `studentQuery2`, etc.).  
  
 [!code-csharp[cscsrefQueryKeywords#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_2.cs)]  
  
 Como se muestra en `studentQuery8` en el ejemplo anterior, a veces es posible que quiera que los elementos de la secuencia devuelta contengan solo un subconjunto de las propiedades de los elementos de origen. Al mantener la secuencia devuelta lo más pequeña posible, puede reducir los requisitos de memoria y aumentar la velocidad de ejecución de la consulta. Puede hacerlo al crear un tipo anónimo en la cláusula `select` y usar un inicializador de objeto para inicializarlo con las propiedades adecuadas del elemento de origen. Para obtener un ejemplo de cómo hacerlo, consulte [Inicializadores de objeto y de colección](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
## <a name="remarks"></a>Comentarios  
 En tiempo de compilación, la cláusula `select` se convierte en una llamada de método al operador de consulta estándar <xref:System.Linq.Enumerable.Select%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Palabras clave para consultas (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)  
 [from (cláusula)](../../../csharp/language-reference/keywords/from-clause.md)  
 [Partial (método) (referencia de C#)](../../../csharp/language-reference/keywords/partial-method.md)  
 [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [Introducción a LINQ en C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
