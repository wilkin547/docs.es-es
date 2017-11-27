---
title: "Take While (Cláusula, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5c8add6c55bb9353bac3489e68f497cb32785aad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
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
|`expression`|Obligatorio. Una expresión que representa una condición para probar los elementos de. La expresión debe devolver un `Boolean` valor o un equivalente funcional, como un `Integer` que se debe evaluar como un `Boolean`.|  
  
## <a name="remarks"></a>Comentarios  
 El `Take While` cláusula incluye elementos desde el principio del resultado de una consulta hasta que se ha suministrado `expression` devuelve `false`. Después de la `expression` devuelve `false`, la consulta omitirá todos los elementos restantes. El `expression` se omite para los resultados restantes.  
  
 El `Take While` cláusula difiere de la `Where` cláusula en la que el `Where` cláusula puede usarse para incluir todos los elementos de una consulta que cumplan una condición determinada. El `Take While` cláusula incluye elementos solo hasta que la primera vez que no se cumple la condición. El `Take While` cláusula es muy útil cuando se trabaja con un resultado de consulta ordenado.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código utiliza el `Take While` cláusula para recuperar los resultados hasta que se encuentre el primer cliente sin pedidos.  
  
 [!code-vb[VbSimpleQuerySamples#2](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-while-clause_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)  
 [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Take (cláusula)](../../../visual-basic/language-reference/queries/take-clause.md)  
 [Skip While (cláusula)](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Where (cláusula)](../../../visual-basic/language-reference/queries/where-clause.md)
