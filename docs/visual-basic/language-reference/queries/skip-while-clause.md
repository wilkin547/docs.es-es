---
title: "Skip While (Cláusula, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f447a6d9b2eb58fa546ced6c96b987caf68fb3e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="skip-while-clause-visual-basic"></a>Skip While (Cláusula, Visual Basic)
Omite los elementos de una colección siempre que el valor de una condición especificada sea `true` y, a continuación, devuelve los elementos restantes.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Skip While expression  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`expression`|Obligatorio. Una expresión que representa una condición para probar los elementos de. La expresión debe devolver un `Boolean` valor o un equivalente funcional, como un `Integer` que se debe evaluar como un `Boolean`.|  
  
## <a name="remarks"></a>Comentarios  
 El `Skip While` cláusula omite los elementos desde el principio del resultado de una consulta hasta que se ha suministrado `expression` devuelve `false`. Después de `expression` devuelve `false`, la consulta devuelve todos los elementos restantes. El `expression` se omite para los resultados restantes.  
  
 El `Skip While` cláusula difiere de la `Where` cláusula en la que el `Where` cláusula puede usarse para excluir todos los elementos de una consulta que no cumplen una condición determinada. El `Skip While` cláusula excluye los elementos hasta la primera vez que no se cumple la condición. El `Skip While` cláusula es muy útil cuando se trabaja con un resultado de consulta ordenado.  
  
 Puede omitir un número concreto de resultados desde el principio del resultado de una consulta mediante el uso de la `Skip` cláusula.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código utiliza el `Skip While` cláusula para omitir resultados hasta que se encuentre el primer cliente de los Estados Unidos.  
  
 [!code-vb[VbSimpleQuerySamples#3](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-while-clause_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)  
 [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Skip (cláusula)](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [Take While (cláusula)](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [Where (cláusula)](../../../visual-basic/language-reference/queries/where-clause.md)
