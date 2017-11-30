---
title: "Where (Cláusula, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8c2572f513d00bc72e869cf28d382be799f7a303
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="where-clause-visual-basic"></a>Where (Cláusula, Visual Basic)
Especifica la condición de filtrado para una consulta.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Where condition  
```  
  
## <a name="parts"></a>Elementos  
 `condition`  
 Obligatorio. Una expresión que determina si se incluyen los valores para el elemento actual de la colección en la colección de salida. La expresión debe evaluarse como un `Boolean` valor o el equivalente de un `Boolean` valor. Si la condición se evalúa como `True`, el elemento se incluye en el resultado de la consulta; en caso contrario, el elemento se excluye de los resultados de la consulta.  
  
## <a name="remarks"></a>Comentarios  
 El `Where` cláusula le permite filtrar los datos de consulta seleccionando únicamente los elementos que cumplen determinados criterios. Los elementos cuyos valores hacen que la `Where` cláusula se evalúe como `True` se incluyen en el resultado de la consulta; otros elementos se excluyen. La expresión que se utiliza en una `Where` cláusula debe evaluarse como un `Boolean` o el equivalente de un `Boolean`, como un entero que se evalúa como `False` cuando su valor es cero. Puede combinar varias expresiones en un `Where` cláusula mediante operadores lógicos, como `And`, `Or`, `AndAlso`, `OrElse`, `Is`, y `IsNot`.  
  
 De forma predeterminada, no se evalúan las expresiones de consulta hasta que se accede a estos, por ejemplo, cuando estén enlazados a datos o recorridos en iteración a través de un `For` bucle. Como resultado, el `Where` cláusula no se evalúa hasta que se tiene acceso a la consulta. Si se usan valores externos a la consulta que se usan en el `Where` cláusula, asegúrese de que se usa el valor adecuado en el `Where` cláusula en el momento en que se ejecuta la consulta. Para obtener más información acerca de la ejecución de la consulta, vea [escribir la primera consulta con LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
 Puede llamar a funciones dentro de un `Where` cláusula para realizar un cálculo o una operación en un valor desde el elemento actual de la colección. Llamar a una función un `Where` cláusula puede hacer que la consulta que se ejecute inmediatamente cuando se define en lugar de cuando se tiene acceso. Para obtener más información acerca de la ejecución de la consulta, vea [escribir la primera consulta con LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="example"></a>Ejemplo  
 Consulta la siguiente expresión utiliza una `From` cláusula para declarar una variable de rango `cust` para cada `Customer` objeto en el `customers` colección. El `Where` cláusula utiliza la variable de rango para restringir los resultados a los clientes de la región especificada. El `For Each` bucle muestra el nombre de la compañía de cada cliente en el resultado de la consulta.  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/where-clause_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza `And` y `Or` operadores lógicos en el `Where` cláusula.  
  
 [!code-vb[VbSimpleQuerySamples#31](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/where-clause_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)  
 [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)  
 [For Each...Next (instrucción)](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
