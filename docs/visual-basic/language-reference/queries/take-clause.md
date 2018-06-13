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
ms.openlocfilehash: 0dddb411af1b4ee269e091c07553a94589d90b2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604034"
---
# <a name="take-clause-visual-basic"></a>Take (Cláusula, Visual Basic)
Devuelve un número especificado de elementos contiguos desde el principio de una colección.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Take count  
```  
  
## <a name="parts"></a>Elementos  
 `count`  
 Requerido. Un valor o una expresión que se evalúa como el número de elementos de la secuencia para devolver.  
  
## <a name="remarks"></a>Comentarios  
 El `Take` cláusula hace una consulta incluir un número especificado de elementos contiguos desde el principio de una lista de resultados. Se especifica el número de elementos que desee incluir el `count` parámetro.  
  
 Puede usar el `Take` cláusula con el `Skip` cláusula para devolver un intervalo de datos de cualquier segmento de una consulta. Para ello, pase el índice del primer elemento del intervalo para el `Skip` cláusula y el tamaño del intervalo para el `Take` cláusula. En este caso, el `Take` cláusula debe especificarse después el `Skip` cláusula.  
  
 Cuando se usa el `Take` cláusula en una consulta, también debe asegurarse de que los resultados se devuelven en un orden que permita la `Take` cláusula para incluir los resultados previstos. Para obtener más información sobre cómo ordenar los resultados de la consulta, vea [cláusula Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Puede usar el `TakeWhile` cláusula para especificar que se devuelvan sólo ciertos elementos, dependiendo de la condición proporcionada.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código utiliza el `Take` cláusula junto con el `Skip` cláusula se devuelven datos de una consulta en páginas. El GetCustomers función utiliza la `Skip` cláusula para omitir los clientes en la lista hasta que la proporcionada a partir de índice valor y se utiliza el `Take` cláusula para devolver una página de los clientes a partir de ese valor de índice.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-clause_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)  
 [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Order By (cláusula)](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Take While (cláusula)](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [Skip (cláusula)](../../../visual-basic/language-reference/queries/skip-clause.md)
