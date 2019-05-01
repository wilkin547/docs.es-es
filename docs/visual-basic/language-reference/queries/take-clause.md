---
title: Take (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: cb109eaf43fee19b77ac690492b85919c9d78301
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054398"
---
# <a name="take-clause-visual-basic"></a>Take (Cláusula, Visual Basic)
Devuelve un número especificado de elementos contiguos desde el principio de una colección.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Take count  
```  
  
## <a name="parts"></a>Elementos  
 `count`  
 Obligatorio. Un valor o una expresión que se evalúa como el número de elementos de la secuencia que se va a devolver.  
  
## <a name="remarks"></a>Comentarios  
 El `Take` cláusula hace una consulta incluir un número especificado de elementos contiguos desde el principio de una lista de resultados. Especificado por el número de elementos que desee incluir el `count` parámetro.  
  
 Puede usar el `Take` cláusula con el `Skip` cláusula para devolver un intervalo de datos de cualquier segmento de una consulta. Para ello, pase el índice del primer elemento del intervalo para el `Skip` cláusula y el tamaño del intervalo para el `Take` cláusula. En este caso, el `Take` cláusula debe especificarse después el `Skip` cláusula.  
  
 Cuando se usa el `Take` cláusula en una consulta, es posible que también deberá asegurarse de que los resultados se devuelven en un orden que le permitirán la `Take` cláusula para incluir los resultados deseados. Para obtener más información sobre cómo ordenar los resultados de la consulta, vea [cláusula Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Puede usar el `TakeWhile` cláusula para especificar que se devuelvan sólo ciertos elementos, según la condición proporcionada.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código utiliza el `Take` cláusula junto con el `Skip` cláusula para devolver datos de una consulta en las páginas. El GetCustomers función usa el `Skip` cláusula para omitir los clientes en la lista hasta que la proporcionada a partir de índice valor y se usa el `Take` cláusula para devolver una página de clientes a partir de ese valor de índice.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](../../../visual-basic/language-reference/queries/index.md)
- [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)
- [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)
- [Order By (cláusula)](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Take While (cláusula)](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [Skip (cláusula)](../../../visual-basic/language-reference/queries/skip-clause.md)
