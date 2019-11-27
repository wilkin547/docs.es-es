---
title: Take While (Cláusula)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 23b7c84a9f896161a66059fcb1f30753d3b863d5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347109"
---
# <a name="take-while-clause-visual-basic"></a>Take While (Cláusula, Visual Basic)
Incluye los elementos de una colección siempre que el valor de una condición especificada sea `true` y, a continuación, omite los elementos restantes.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`expression`|Obligatorio. Expresión que representa una condición de la que se van a probar los elementos. La expresión debe devolver un valor `Boolean` o un equivalente funcional, como un `Integer` que se va a evaluar como `Boolean`.|  
  
## <a name="remarks"></a>Comentarios  
 La cláusula `Take While` incluye elementos desde el principio del resultado de una consulta hasta que el `expression` proporcionado devuelve `false`. Una vez que el `expression` devuelva `false`, la consulta omitirá todos los elementos restantes. El `expression` se omite para los resultados restantes.  
  
 La cláusula `Take While` difiere de la cláusula `Where` en que la cláusula `Where` se puede utilizar para incluir todos los elementos de una consulta que cumplan una condición determinada. La cláusula `Take While` solo incluye elementos hasta la primera vez que la condición no se cumple. La cláusula `Take While` es muy útil cuando se trabaja con un resultado de consulta ordenado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se usa la cláusula `Take While` para recuperar los resultados hasta que se encuentre el primer cliente sin ningún pedido.  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](../../../visual-basic/language-reference/queries/index.md)
- [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)
- [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)
- [Take (cláusula)](../../../visual-basic/language-reference/queries/take-clause.md)
- [Skip While (cláusula)](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Where (cláusula)](../../../visual-basic/language-reference/queries/where-clause.md)
