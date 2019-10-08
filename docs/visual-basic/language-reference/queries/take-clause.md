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
ms.openlocfilehash: 32a4c7fd7f1e2f6fe640f3f53f15579f014759d5
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004718"
---
# <a name="take-clause-visual-basic"></a>Take (Cláusula, Visual Basic)
Devuelve un número especificado de elementos contiguos desde el principio de una colección.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Take count  
```  
  
## <a name="parts"></a>Elementos  
 `count`  
 Obligatorio. Un valor o una expresión que se evalúa como el número de elementos de la secuencia que se va a devolver.  
  
## <a name="remarks"></a>Comentarios  
 La cláusula `Take` hace que una consulta incluya un número especificado de elementos contiguos desde el principio de una lista de resultados. El número de elementos que se van a incluir se especifica mediante el parámetro `count`.  
  
 Puede usar la cláusula `Take` con la cláusula `Skip` para devolver un intervalo de datos de cualquier segmento de una consulta. Para ello, pase el índice del primer elemento del intervalo a la cláusula `Skip` y el tamaño del intervalo a la cláusula `Take`. En este caso, se debe especificar la cláusula `Take` después de la cláusula `Skip`.  
  
 Cuando se usa la cláusula `Take` en una consulta, también es necesario asegurarse de que los resultados se devuelven en un orden que permita a la cláusula `Take` incluir los resultados deseados. Para obtener más información sobre cómo ordenar los resultados de una consulta, vea [cláusula order by](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Puede usar la cláusula `TakeWhile` para especificar que solo se devuelvan determinados elementos, en función de una condición proporcionada.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se usa la cláusula `Take` junto con la cláusula `Skip` para devolver datos de una consulta en páginas. La función GetCustomers usa la cláusula `Skip` para omitir los clientes de la lista hasta el valor del índice de inicio proporcionado y usa la cláusula `Take` para devolver una página de clientes a partir de ese valor de índice.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](../../../visual-basic/language-reference/queries/index.md)
- [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)
- [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)
- [Order By (cláusula)](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Take While (cláusula)](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [Skip (cláusula)](../../../visual-basic/language-reference/queries/skip-clause.md)
