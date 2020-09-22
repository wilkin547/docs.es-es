---
title: Cláusula Distinct
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: 49eaab2e6a8c48d61518ea51ef2f644b6eb48314
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875281"
---
# <a name="distinct-clause-visual-basic"></a>Distinct (Cláusula, Visual Basic)

Restringe los valores de la variable de rango actual para eliminar los valores duplicados en las cláusulas de consulta subsiguientes.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a>Comentarios  

 Puede utilizar la `Distinct` cláusula para devolver una lista de elementos únicos. La `Distinct` cláusula hace que la consulta omita los resultados de la consulta duplicada. La `Distinct` cláusula se aplica a los valores duplicados para todos los campos devueltos especificados por la `Select` cláusula. Si no `Select` se especifica ninguna cláusula, la `Distinct` cláusula se aplica a la variable de rango de la consulta identificada en la `From` cláusula. Si la variable de rango no es un tipo inmutable, la consulta solo omitirá el resultado de una consulta si todos los miembros del tipo coinciden con el resultado de una consulta existente.  
  
## <a name="example"></a>Ejemplo  

 La siguiente expresión de consulta combina una lista de clientes y una lista de pedidos de cliente. La `Distinct` cláusula se incluye para devolver una lista de nombres de cliente únicos y fechas de pedido.  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a>Consulte también

- [Introducción a LINQ en Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](index.md)
- [Cláusula FROM](from-clause.md)
- [Select (cláusula)](select-clause.md)
- [Cláusula WHERE](where-clause.md)
