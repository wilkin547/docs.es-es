---
title: Cláusula Take
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: f2377d8d1635912885a310b2b0429a6a00083b47
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869675"
---
# <a name="take-clause-visual-basic"></a>Take (Cláusula, Visual Basic)

Devuelve un número especificado de elementos contiguos desde el principio de una colección.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Take count  
```  
  
## <a name="parts"></a>Partes  

 `count`  
 Obligatorio. Un valor o una expresión que se evalúa como el número de elementos de la secuencia que se va a devolver.  
  
## <a name="remarks"></a>Comentarios  

 La `Take` cláusula hace que una consulta incluya un número especificado de elementos contiguos desde el principio de una lista de resultados. El parámetro especifica el número de elementos que se van a incluir `count` .  
  
 Puede usar la `Take` cláusula con la `Skip` cláusula para devolver un intervalo de datos de cualquier segmento de una consulta. Para ello, pase el índice del primer elemento del intervalo a la `Skip` cláusula y el tamaño del intervalo a la `Take` cláusula. En este caso, la `Take` cláusula debe especificarse después de la `Skip` cláusula.  
  
 Al utilizar la `Take` cláusula en una consulta, puede que también tenga que asegurarse de que los resultados se devuelven en un orden que permita `Take` a la cláusula incluir los resultados deseados. Para obtener más información sobre cómo ordenar los resultados de una consulta, vea [cláusula order by](order-by-clause.md).  
  
 Puede usar la `TakeWhile` cláusula para especificar que solo se devuelvan determinados elementos, en función de una condición proporcionada.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo de código siguiente `Take` se usa la cláusula junto con la `Skip` cláusula para devolver datos de una consulta en páginas. La función GetCustomers usa la `Skip` cláusula para omitir los clientes de la lista hasta el valor del índice de inicio proporcionado y usa la `Take` cláusula para devolver una página de clientes a partir de ese valor de índice.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>Consulte también

- [Introducción a LINQ en Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](index.md)
- [Select (cláusula)](select-clause.md)
- [Cláusula FROM](from-clause.md)
- [Cláusula order by](order-by-clause.md)
- [Cláusula Take While](take-while-clause.md)
- [Cláusula Skip](skip-clause.md)
