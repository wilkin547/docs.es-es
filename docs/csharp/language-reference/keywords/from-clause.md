---
description: from (cláusula) - Referencia de C#
title: from (cláusula) - Referencia de C#
ms.date: 07/20/2015
f1_keywords:
- from_CSharpKeyword
- from
helpviewer_keywords:
- from clause [C#]
- from keyword [C#]
ms.assetid: 1aefd18c-1314-47f8-99ec-9bcefb09e699
ms.openlocfilehash: 474b22f5a9d8f12c8a4365159817f878761b563c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89140794"
---
# <a name="from-clause-c-reference"></a>from (Cláusula, Referencia de C#)

Una expresión de consulta debe comenzar con una cláusula `from`, Además, una expresión de consulta puede contener subconsultas, que también comienzan con una cláusula `from`. La cláusula `from` especifica lo siguiente:

- El origen de datos en el que se ejecutará la consulta o subconsulta.

- Una *variable de rango* local que representa cada elemento de la secuencia de origen.

Tanto la variable de rango como el origen de datos están fuertemente tipados. El origen de datos al que se hace referencia en la cláusula `from` debe tener un tipo de <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601> o un tipo derivado como <xref:System.Linq.IQueryable%601>.

En el ejemplo siguiente, `numbers` es el origen de datos y `num` es la variable de rango. Tenga en cuenta que ambas variables están fuertemente tipadas a pesar de que se usa la palabra clave [var](var.md).

[!code-csharp[cscsrefQueryKeywords#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/From.cs#1)]

## <a name="the-range-variable"></a>Variable de rango

El compilador deduce el tipo de la variable de rango cuando el origen de datos implementa <xref:System.Collections.Generic.IEnumerable%601>. Por ejemplo, si el origen tiene un tipo de `IEnumerable<Customer>`, entonces se deduce que la variable de rango es `Customer`. La única vez en que debe especificar el tipo explícitamente es cuando el origen es un tipo `IEnumerable` no genérico como <xref:System.Collections.ArrayList>. Para obtener más información, vea [Procedimiento para consultar un objeto ArrayList con LINQ (C#)](../../programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md).

En el ejemplo anterior, `num` se deduce que es de tipo `int`. Como la variable de rango está fuertemente tipada, puede llamar a los métodos en ella o usarla en otras operaciones. Por ejemplo, en lugar de escribir `select num`, podría escribir `select num.ToString()` para hacer que la expresión de consulta devuelva una secuencia de cadenas en lugar de enteros. O podría escribir `select num + 10` para hacer que la expresión devuelva la secuencia 14, 11, 13, 12, 10. Para obtener más información, vea [Cláusula select](select-clause.md).

La variable de rango es como una variable de iteración en una instrucción [foreach](foreach-in.md) excepto por una diferencia muy importante: una variable de rango realmente nunca almacena datos del origen. Es solo una comodidad sintáctica que permite a la consulta describir lo que ocurrirá cuando se ejecute la consulta. Para obtener más información, vea [Introducción a las consultas LINQ (C#)](../../programming-guide/concepts/linq/introduction-to-linq-queries.md).

## <a name="compound-from-clauses"></a>Cláusulas From compuestas

En algunos casos, cada elemento de la secuencia de origen puede ser por sí mismo una secuencia o contener una. Por ejemplo, su origen de datos puede ser un `IEnumerable<Student>` donde cada objeto de estudiante en la secuencia contiene una lista de resultados de las pruebas. Para tener acceso a la lista interna dentro de cada elemento `Student`, puede usar las cláusulas `from` compuestas. La técnica es como usar instrucciones [foreach](foreach-in.md) anidadas. Puede agregar cláusulas [where](partial-method.md) u [orderby](orderby-clause.md) a cualquier cláusula `from` para filtrar los resultados. En el ejemplo siguiente se muestra una secuencia de objetos `Student`, cada uno de los cuales contiene un `List` interno de enteros que representa los resultados de las pruebas. Para tener acceso a la lista interna, use una cláusula `from` compuesta. Puede insertar cláusulas entre las dos cláusulas `from` si es necesario.

[!code-csharp[cscsrefQueryKeywords#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/From.cs#2)]

## <a name="using-multiple-from-clauses-to-perform-joins"></a>Usar cláusulas From múltiples para realizar combinaciones

Una cláusula `from` compuesta se usa para tener acceso a las colecciones internas en un origen de datos único. En cambio, una consulta también puede contener varias cláusulas `from` que generan consultas adicionales de orígenes de datos independientes. Esta técnica le permite realizar determinados tipos de operaciones de combinación que no son posibles mediante la [cláusula join](join-clause.md).

En el siguiente ejemplo se muestra cómo pueden usarse dos cláusulas `from` para formar una combinación cruzada completa de dos orígenes de datos.

[!code-csharp[cscsrefQueryKeywords#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/From.cs#3)]

Para obtener más información sobre las operaciones de combinación que usan varias cláusulas `from`, vea [Realizar operaciones de combinación externa izquierda](../../linq/perform-left-outer-joins.md).

## <a name="see-also"></a>Vea también

- [Palabras clave para consultas (LINQ)](query-keywords.md)
- [Language-Integrated Query (LINQ)](../../linq/index.md)
