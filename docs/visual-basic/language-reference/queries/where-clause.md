---
title: Cláusula Where
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: 3a43554fb25592bf413525a2df109010e4868492
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869639"
---
# <a name="where-clause-visual-basic"></a>Where (Cláusula, Visual Basic)

Especifica la condición de filtrado para una consulta.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Where condition  
```  
  
## <a name="parts"></a>Partes  

 `condition`  
 Obligatorio. Una expresión que determina si los valores del elemento actual de la colección se incluyen en la colección de salida. La expresión debe evaluarse como un `Boolean` valor o el equivalente de un `Boolean` valor. Si la condición se evalúa como `True` , el elemento se incluye en el resultado de la consulta; de lo contrario, el elemento se excluye del resultado de la consulta.  
  
## <a name="remarks"></a>Comentarios  

 La `Where` cláusula permite filtrar los datos de la consulta seleccionando solo los elementos que cumplen determinados criterios. Los elementos cuyos valores hacen que la `Where` cláusula se evalúe como `True` se incluyen en el resultado de la consulta; se excluyen otros elementos. La expresión que se utiliza en una `Where` cláusula debe evaluarse como `Boolean` o el equivalente de un `Boolean` , como un entero que se evalúa como `False` cuando su valor es cero. Puede combinar varias expresiones en una `Where` cláusula mediante operadores lógicos como `And` , `Or` , `AndAlso` , `OrElse` , `Is` y `IsNot` .  
  
 De forma predeterminada, las expresiones de consulta no se evalúan hasta que se tiene acceso a ellas, por ejemplo, cuando están enlazadas a datos o se recorren en iteración en un `For` bucle. Como resultado, la `Where` cláusula no se evalúa hasta que se tiene acceso a la consulta. Si tiene valores externos a la consulta que se usan en la `Where` cláusula, asegúrese de que se usa el valor adecuado en la `Where` cláusula en el momento en que se ejecuta la consulta. Para obtener más información sobre la ejecución de consultas, vea [escribir su primera consulta LINQ](../../programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
 Puede llamar a funciones dentro de una `Where` cláusula para realizar un cálculo o una operación en un valor del elemento actual de la colección. Llamar a una función en una `Where` cláusula puede hacer que la consulta se ejecute inmediatamente cuando se define en lugar de cuando se tiene acceso a ella. Para obtener más información sobre la ejecución de consultas, vea [escribir su primera consulta LINQ](../../programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="example"></a>Ejemplo  

 La siguiente expresión de consulta utiliza una `From` cláusula para declarar una variable `cust` de rango para cada `Customer` objeto de la `customers` colección. La `Where` cláusula usa la variable de rango para restringir la salida a los clientes de la región especificada. El `For Each` bucle muestra el nombre de la compañía para cada cliente en el resultado de la consulta.  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usan los `And` `Or` operadores lógicos y en la `Where` cláusula.  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a>Consulte también

- [Introducción a LINQ en Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](index.md)
- [Cláusula FROM](from-clause.md)
- [Select (cláusula)](select-clause.md)
- [Instrucción For Each...Next](../statements/for-each-next-statement.md)
