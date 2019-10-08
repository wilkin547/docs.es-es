---
title: Distinct (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: e8d3e38261a04c4d29faab351d24d6710413b09a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004792"
---
# <a name="distinct-clause-visual-basic"></a>Distinct (Cláusula, Visual Basic)
Restringe los valores de la variable de rango actual para eliminar los valores duplicados en las cláusulas de consulta subsiguientes.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a>Comentarios  
 Puede usar la cláusula `Distinct` para devolver una lista de elementos únicos. La cláusula `Distinct` hace que la consulta omita los resultados de la consulta duplicada. La cláusula `Distinct` se aplica a los valores duplicados para todos los campos devueltos especificados por la cláusula `Select`. Si no se especifica ninguna cláusula `Select`, se aplica la cláusula `Distinct` a la variable de rango de la consulta identificada en la cláusula `From`. Si la variable de rango no es un tipo inmutable, la consulta solo omitirá el resultado de una consulta si todos los miembros del tipo coinciden con el resultado de una consulta existente.  
  
## <a name="example"></a>Ejemplo  
 La siguiente expresión de consulta combina una lista de clientes y una lista de pedidos de cliente. La cláusula `Distinct` se incluye para devolver una lista de nombres de cliente únicos y fechas de pedido.  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](../../../visual-basic/language-reference/queries/index.md)
- [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)
- [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)
- [Where (cláusula)](../../../visual-basic/language-reference/queries/where-clause.md)
