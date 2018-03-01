---
title: "Distinct (Cláusula, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6ed92d5d601c1ec329728346ac881c4fa2bad8aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="distinct-clause-visual-basic"></a>Distinct (Cláusula, Visual Basic)
Restringe los valores de la variable de rango actual para eliminar los valores duplicados en las cláusulas de consulta subsiguientes.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Distinct  
```  
  
## <a name="remarks"></a>Comentarios  
 Puede usar el `Distinct` cláusula para devolver una lista de elementos únicos. El `Distinct` cláusula hace que la consulta pasar por alto los resultados de consulta duplicada. El `Distinct` cláusula se aplica a valores duplicados para todos los devueltos de los campos especificados por el `Select` cláusula. Si no hay ningún `Select` se especifica la cláusula, el `Distinct` cláusula se aplica a la variable de rango de la consulta identificada en el `From` cláusula. Si la variable de rango no es un tipo inmutable, la consulta omitirá únicamente un resultado de consulta si todos los miembros del tipo coinciden con un resultado de consulta existente.  
  
## <a name="example"></a>Ejemplo  
 La siguiente expresión de consulta combina una lista de clientes y una lista de pedidos de cliente. El `Distinct` cláusula se incluye para devolver una lista de nombres de cliente único y las fechas de pedidos.  
  
 [!code-vb[VbSimpleQuerySamples#20](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/distinct-clause_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)  
 [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Where (cláusula)](../../../visual-basic/language-reference/queries/where-clause.md)
