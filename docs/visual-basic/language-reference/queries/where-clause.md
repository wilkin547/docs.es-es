---
title: Where (Cláusula)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: 60b7ebe96ce0c4580c36675b2e4aa5f9888732c3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349630"
---
# <a name="where-clause-visual-basic"></a>Where (Cláusula, Visual Basic)
Especifica la condición de filtrado para una consulta.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Where condition  
```  
  
## <a name="parts"></a>Elementos  
 `condition`  
 Obligatorio. Una expresión que determina si los valores del elemento actual de la colección se incluyen en la colección de salida. La expresión debe evaluarse como un valor `Boolean` o el equivalente de un valor `Boolean`. Si la condición se evalúa como `True`, el elemento se incluye en el resultado de la consulta; de lo contrario, el elemento se excluye del resultado de la consulta.  
  
## <a name="remarks"></a>Comentarios  
 La cláusula `Where` permite filtrar los datos de la consulta seleccionando solo los elementos que cumplen determinados criterios. Los elementos cuyos valores hacen que la cláusula `Where` se evalúe como `True` se incluyen en el resultado de la consulta; se excluyen otros elementos. La expresión que se utiliza en una cláusula `Where` debe evaluarse como un `Boolean` o el equivalente de un `Boolean`, como un entero que se evalúa como `False` cuando su valor es cero. Puede combinar varias expresiones en una cláusula `Where` mediante operadores lógicos como `And`, `Or`, `AndAlso`, `OrElse`, `Is`y `IsNot`.  
  
 De forma predeterminada, las expresiones de consulta no se evalúan hasta que se tiene acceso a ellas; por ejemplo, cuando están enlazadas a datos o se recorren en iteración en un bucle `For`. Como resultado, la cláusula `Where` no se evalúa hasta que se tiene acceso a la consulta. Si tiene valores externos a la consulta que se usan en la cláusula `Where`, asegúrese de que se usa el valor adecuado en la cláusula `Where` en el momento en que se ejecuta la consulta. Para obtener más información sobre la ejecución de consultas, vea [escribir su primera consulta LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
 Puede llamar a funciones dentro de una cláusula `Where` para realizar un cálculo o una operación en un valor del elemento actual de la colección. Llamar a una función en una cláusula `Where` puede hacer que la consulta se ejecute inmediatamente cuando se define en lugar de cuando se tiene acceso a ella. Para obtener más información sobre la ejecución de consultas, vea [escribir su primera consulta LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="example"></a>Ejemplo  
 La siguiente expresión de consulta utiliza una cláusula `From` para declarar una variable de rango `cust` para cada `Customer` objeto de la colección de `customers`. La cláusula `Where` usa la variable de rango para restringir la salida a los clientes de la región especificada. El bucle `For Each` muestra el nombre de la compañía para cada cliente en el resultado de la consulta.  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa `And` y `Or` operadores lógicos en la cláusula `Where`.  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](../../../visual-basic/language-reference/queries/index.md)
- [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)
- [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)
- [For Each...Next (instrucción)](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
