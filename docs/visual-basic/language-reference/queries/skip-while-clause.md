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
ms.openlocfilehash: 7f37a6fa1c9ba7fdf7978ac6853e4c2985bf72e7
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004699"
---
# <a name="skip-while-clause-visual-basic"></a>Skip While (Cláusula, Visual Basic)
Omite los elementos de una colección siempre que el valor de una condición especificada sea `true` y, a continuación, devuelve los elementos restantes.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Skip While expression  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`expression`|Obligatorio. Expresión que representa una condición de la que se van a probar los elementos. La expresión debe devolver un valor `Boolean` o un equivalente funcional, como un `Integer` que se va a evaluar como @no__t 2.|  
  
## <a name="remarks"></a>Comentarios  
 La cláusula `Skip While` omite los elementos desde el principio del resultado de una consulta hasta que el `expression` proporcionado devuelve `false`. Después de que `expression` devuelva `false`, la consulta devolverá todos los elementos restantes. Se omite el `expression` para los resultados restantes.  
  
 La cláusula `Skip While` difiere de la cláusula `Where` en que se puede usar la cláusula `Where` para excluir todos los elementos de una consulta que no cumplan una condición determinada. La cláusula `Skip While` excluye los elementos solo hasta la primera vez que no se cumple la condición. La cláusula `Skip While` es muy útil cuando se trabaja con un resultado de consulta ordenado.  
  
 Puede omitir un número específico de resultados desde el principio del resultado de una consulta mediante la cláusula `Skip`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se usa la cláusula `Skip While` para omitir los resultados hasta que se encuentre el primer cliente de la Estados Unidos.  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](../../../visual-basic/language-reference/queries/index.md)
- [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)
- [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)
- [Skip (cláusula)](../../../visual-basic/language-reference/queries/skip-clause.md)
- [Take While (cláusula)](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [Where (cláusula)](../../../visual-basic/language-reference/queries/where-clause.md)
