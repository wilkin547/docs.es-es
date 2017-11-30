---
title: "from (Cláusula, Referencia de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- from_CSharpKeyword
- from
helpviewer_keywords:
- from clause [C#]
- from keyword [C#]
ms.assetid: 1aefd18c-1314-47f8-99ec-9bcefb09e699
caps.latest.revision: "27"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f718f50d2b8d6f5c612113414a2106fed37fe0fa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="from-clause-c-reference"></a>from (Cláusula, Referencia de C#)
Una expresión de consulta debe comenzar con una cláusula `from`, Además, una expresión de consulta puede contener subconsultas, que también comienzan con una cláusula `from`. La cláusula `from` especifica lo siguiente:  
  
-   El origen de datos en el que se ejecutará la consulta o subconsulta.  
  
-   Una *variable de rango* local que representa cada elemento de la secuencia de origen.  
  
 Tanto la variable de rango como el origen de datos están fuertemente tipados. El origen de datos al que se hace referencia en la cláusula `from` debe tener un tipo de <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601> o un tipo derivado como <xref:System.Linq.IQueryable%601>.  
  
 En el ejemplo siguiente, `numbers` es el origen de datos y `num` es la variable de rango. Tenga en cuenta que ambas variables están fuertemente tipadas a pesar de que se usa la palabra clave [var](../../../csharp/language-reference/keywords/var.md).  
  
 [!code-csharp[cscsrefQueryKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/from-clause_1.cs)]  
  
## <a name="the-range-variable"></a>La variable de rango  
 El compilador deduce el tipo de la variable de rango cuando el origen de datos implementa <xref:System.Collections.Generic.IEnumerable%601>. Por ejemplo, si el origen tiene un tipo de `IEnumerable<Customer>`, entonces se deduce que la variable de rango es `Customer`. La única vez en que debe especificar el tipo explícitamente es cuando el origen es un tipo `IEnumerable` no genérico como <xref:System.Collections.ArrayList>. Para obtener más información, vea [How to: Query an ArrayList with LINQ](../../programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md) (Consultar un objeto ArrayList con LINQ).  
  
 En el ejemplo anterior, `num` se deduce que es de tipo `int`. Como la variable de rango está fuertemente tipada, puede llamar a los métodos en ella o usarla en otras operaciones. Por ejemplo, en lugar de escribir `select num`, podría escribir `select num.ToString()` para hacer que la expresión de consulta devuelva una secuencia de cadenas en lugar de enteros. O podría escribir `select n + 10` para hacer que la expresión devuelva la secuencia 14, 11, 13, 12, 10. Para obtener más información, vea [Cláusula select](../../../csharp/language-reference/keywords/select-clause.md).  
  
 La variable de rango es como una variable de iteración en una instrucción [foreach](../../../csharp/language-reference/keywords/foreach-in.md) excepto por una diferencia muy importante: una variable de rango realmente nunca almacena datos del origen. Es solo una comodidad sintáctica que permite a la consulta describir lo que ocurrirá cuando se ejecute la consulta. Para obtener más información, vea [Introduction to LINQ queries (C#)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) [Introducción a las consultas LINQ (C#)].  
  
## <a name="compound-from-clauses"></a>Cláusulas From compuestas  
 En algunos casos, cada elemento de la secuencia de origen puede ser por sí mismo una secuencia o contener una. Por ejemplo, su origen de datos puede ser un `IEnumerable<Student>` donde cada objeto de estudiante en la secuencia contiene una lista de resultados de las pruebas. Para tener acceso a la lista interna dentro de cada elemento `Student`, puede usar las cláusulas `from` compuestas. La técnica es como usar instrucciones [foreach](../../../csharp/language-reference/keywords/foreach-in.md) anidadas. Puede agregar cláusulas [where](../../../csharp/language-reference/keywords/partial-method.md) u [orderby](../../../csharp/language-reference/keywords/orderby-clause.md) a cualquier cláusula `from` para filtrar los resultados. En el ejemplo siguiente se muestra una secuencia de objetos `Student`, cada uno de los cuales contiene un `List` interno de enteros que representa los resultados de las pruebas. Para tener acceso a la lista interna, use una cláusula `from` compuesta. Puede insertar cláusulas entre las dos cláusulas `from` si es necesario.  
  
 [!code-csharp[cscsrefQueryKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/from-clause_2.cs)]  
  
## <a name="using-multiple-from-clauses-to-perform-joins"></a>Usar cláusulas From múltiples para realizar combinaciones  
 Una cláusula `from` compuesta se usa para tener acceso a las colecciones internas en un origen de datos único. En cambio, una consulta también puede contener varias cláusulas `from` que generan consultas adicionales de orígenes de datos independientes. Esta técnica le permite realizar determinados tipos de operaciones de combinación que no son posibles mediante la [cláusula join](../../../csharp/language-reference/keywords/join-clause.md).  
  
 En el siguiente ejemplo se muestra cómo pueden usarse dos cláusulas `from` para formar una combinación cruzada completa de dos orígenes de datos.  
  
 [!code-csharp[cscsrefQueryKeywords#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/from-clause_3.cs)]  
  
 Para obtener información sobre las operaciones de combinación que usan cláusulas `from` múltiples, vea [Cómo: Realizar operaciones de combinación personalizadas](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md).  
  
## <a name="see-also"></a>Vea también  
 [Palabras clave para consultas (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)  
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)
