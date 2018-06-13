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
ms.openlocfilehash: 1810bf4a6573c6fa36f1d8149bf341d45cfd6f52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602832"
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
 El `Skip` cláusula hace que una consulta omita los elementos al principio de una lista de resultados y devolver los elementos restantes. El número de elementos que se van a omitir se identifica mediante el `count` parámetro.  
  
 Puede usar el `Skip` cláusula con el `Take` cláusula para devolver un intervalo de datos de cualquier segmento de una consulta. Para ello, pase el índice del primer elemento del intervalo para el `Skip` cláusula y el tamaño del intervalo para el `Take` cláusula.  
  
 Cuando se usa el `Skip` cláusula en una consulta, también debe asegurarse de que los resultados se devuelven en un orden que permita la `Skip` cláusula para omitir los resultados previstos. Para obtener más información sobre cómo ordenar los resultados de la consulta, vea [cláusula Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Puede usar el `SkipWhile` cláusula para especificar que sólo ciertos elementos se omiten, dependiendo de la condición proporcionada.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código utiliza el `Skip` cláusula junto con el `Take` cláusula se devuelven datos de una consulta en páginas. El `GetCustomers` función utiliza la `Skip` cláusula para omitir los clientes en la lista hasta que la proporcionada a partir de índice valor y se utiliza el `Take` cláusula para devolver una página de los clientes a partir de ese valor de índice.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-clause_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)  
 [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Order By (cláusula)](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Skip While (cláusula)](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Take (cláusula)](../../../visual-basic/language-reference/queries/take-clause.md)
