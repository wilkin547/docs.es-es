---
title: Skip While (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: 380372d6aaf8df3050e0ba8606b74eb3834dec67
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972604"
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
|`expression`|Obligatorio. Una expresión que representa una condición para probar los elementos. La expresión debe devolver un `Boolean` valor o un equivalente funcional, como un `Integer` que debe evaluarse como un `Boolean`.|  
  
## <a name="remarks"></a>Comentarios  
 El `Skip While` cláusula omite los elementos desde el principio del resultado de una consulta hasta que se ha suministrado `expression` devuelve `false`. Después de `expression` devuelve `false`, la consulta devuelve todos los elementos restantes. El `expression` se omite para los resultados restantes.  
  
 El `Skip While` cláusula difiere el `Where` cláusula en la que el `Where` cláusula puede usarse para excluir todos los elementos de una consulta que no cumplen una condición determinada. El `Skip While` cláusula excluye los elementos hasta que la primera vez que no se cumple la condición. El `Skip While` cláusula es muy útil cuando se trabaja con un resultado de consulta ordenada.  
  
 Puede omitir un número específico de resultados desde el principio de un resultado de consulta utilizando el `Skip` cláusula.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código utiliza el `Skip While` cláusula para omitir resultados hasta que se encuentra el primer cliente desde los Estados Unidos.  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a>Vea también
- [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](../../../visual-basic/language-reference/queries/index.md)
- [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)
- [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)
- [Skip (cláusula)](../../../visual-basic/language-reference/queries/skip-clause.md)
- [Take While (cláusula)](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [Where (cláusula)](../../../visual-basic/language-reference/queries/where-clause.md)
