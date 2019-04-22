---
title: Take While (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 080a106fc1deeb54165511ed03d7c7c5d2060f21
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818754"
---
# <a name="take-while-clause-visual-basic"></a>Take While (Cláusula, Visual Basic)
Incluye los elementos de una colección siempre que el valor de una condición especificada sea `true` y, a continuación, omite los elementos restantes.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Take While expression  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`expression`|Obligatorio. Una expresión que representa una condición para probar los elementos. La expresión debe devolver un `Boolean` valor o un equivalente funcional, como un `Integer` que debe evaluarse como un `Boolean`.|  
  
## <a name="remarks"></a>Comentarios  
 El `Take While` cláusula incluye elementos desde el principio de un resultado de consulta hasta que se ha suministrado `expression` devuelve `false`. Después de la `expression` devuelve `false`, la consulta omitirá todos los elementos restantes. El `expression` se omite para los resultados restantes.  
  
 El `Take While` cláusula difiere el `Where` cláusula en la que el `Where` cláusula puede usarse para incluir todos los elementos de una consulta que cumplen una condición determinada. El `Take While` cláusula incluye elementos hasta que la primera vez que no se cumple la condición. El `Take While` cláusula es muy útil cuando se trabaja con un resultado de consulta ordenada.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código utiliza el `Take While` cláusula para recuperar los resultados hasta que se encuentra el primer cliente sin pedidos.  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](../../../visual-basic/language-reference/queries/index.md)
- [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)
- [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)
- [Take (cláusula)](../../../visual-basic/language-reference/queries/take-clause.md)
- [Skip While (cláusula)](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Where (cláusula)](../../../visual-basic/language-reference/queries/where-clause.md)
