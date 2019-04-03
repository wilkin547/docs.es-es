---
title: Where (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: 5632e69039baebb3d1f1fd90c04586d9e50fe40f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834509"
---
# <a name="where-clause-visual-basic"></a>Where (Cláusula, Visual Basic)
Especifica la condición de filtrado para una consulta.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Where condition  
```  
  
## <a name="parts"></a>Elementos  
 `condition`  
 Obligatorio. Una expresión que determina si se incluyen los valores para el elemento actual de la colección en la colección de salida. La expresión debe evaluarse como un `Boolean` valor o el equivalente de un `Boolean` valor. Si la condición se evalúa como `True`, el elemento se incluye en el resultado de la consulta; en caso contrario, se excluye el elemento de resultado de la consulta.  
  
## <a name="remarks"></a>Comentarios  
 El `Where` cláusula permite filtrar los datos de la consulta seleccionando únicamente los elementos que cumplen determinados criterios. Los elementos cuyos valores hacen que la `Where` cláusula se evalúe como `True` se incluyen en el resultado de la consulta; otros elementos se excluyen. La expresión que se usa en un `Where` cláusula debe evaluarse como un `Boolean` o el equivalente de un `Boolean`, como un entero que se evalúa como `False` cuando su valor es cero. Puede combinar varias expresiones en un `Where` cláusula mediante operadores lógicos, como `And`, `Or`, `AndAlso`, `OrElse`, `Is`, y `IsNot`.  
  
 De forma predeterminada, no se evalúan las expresiones de consulta hasta que se tiene acceso a, por ejemplo, cuando están enlazados a datos o iterados a través de un `For` bucle. Como resultado, el `Where` cláusula no se evalúa hasta que se tiene acceso a la consulta. Si tiene los valores externos a la consulta que se usan en el `Where` cláusula, asegúrese de que se usa el valor adecuado en el `Where` cláusula en el momento en que se ejecuta la consulta. Para obtener más información acerca de la ejecución de consultas, vea [escribir su primera consulta con LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
 Puede llamar a funciones dentro de un `Where` cláusula para realizar un cálculo o una operación sobre un valor del elemento actual en la colección. Llamar a una función un `Where` cláusula puede hacer que la consulta que se ejecutará inmediatamente cuando se define en lugar de cuando se tiene acceso a. Para obtener más información acerca de la ejecución de consultas, vea [escribir su primera consulta con LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="example"></a>Ejemplo  
 Consulta la siguiente expresión utiliza una `From` cláusula para declarar una variable de rango `cust` para cada `Customer` objeto en el `customers` colección. El `Where` cláusula usa la variable de rango para restringir los resultados a los clientes de la región especificada. El `For Each` bucle muestra el nombre de la empresa para cada cliente en el resultado de la consulta.  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa `And` y `Or` operadores lógicos en el `Where` cláusula.  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](../../../visual-basic/language-reference/queries/index.md)
- [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)
- [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)
- [For Each...Next (instrucción)](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
