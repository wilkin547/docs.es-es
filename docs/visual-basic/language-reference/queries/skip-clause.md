---
title: Skip (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: 615f98bf36d29c1f269d6866b1232ad33a5ae2f2
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925442"
---
# <a name="skip-clause-visual-basic"></a>Skip (Cláusula, Visual Basic)
Omite un número especificado de elementos de una colección y, a continuación, devuelve los elementos restantes.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Skip count  
```  
  
## <a name="parts"></a>Elementos  
 `count`  
 Requerido. Un valor o una expresión que se evalúa como el número de elementos de la secuencia que se va a omitir.  
  
## <a name="remarks"></a>Comentarios  
 El `Skip` cláusula hace una consulta para omitir los elementos al principio de una lista de resultados y devolver los elementos restantes. Identifica el número de elementos para omitir la `count` parámetro.  
  
 Puede usar el `Skip` cláusula con el `Take` cláusula para devolver un intervalo de datos de cualquier segmento de una consulta. Para ello, pase el índice del primer elemento del intervalo para el `Skip` cláusula y el tamaño del intervalo para el `Take` cláusula.  
  
 Cuando se usa el `Skip` cláusula en una consulta, es posible que también deberá asegurarse de que los resultados se devuelven en un orden que le permitirán la `Skip` cláusula para omitir los resultados deseados. Para obtener más información sobre cómo ordenar los resultados de la consulta, vea [cláusula Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Puede usar el `SkipWhile` cláusula para especificar que sólo determinados elementos se omiten, dependiendo de la condición proporcionada.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código utiliza el `Skip` cláusula junto con el `Take` cláusula para devolver datos de una consulta en las páginas. El `GetCustomers` función usa el `Skip` cláusula para omitir los clientes en la lista hasta que la proporcionada a partir de índice valor y se usa el `Take` cláusula para devolver una página de clientes a partir de ese valor de índice.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-clause_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Consultas](../../../visual-basic/language-reference/queries/index.md)  
 [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Order By (cláusula)](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Skip While (cláusula)](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Take (cláusula)](../../../visual-basic/language-reference/queries/take-clause.md)
