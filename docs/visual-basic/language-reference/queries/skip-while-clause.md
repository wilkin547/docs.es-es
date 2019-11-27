---
title: Skip While (Cláusula)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: 47703e445865435f5bf5312c3fe41833ac21aa3f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333141"
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
|`expression`|Obligatorio. Expresión que representa una condición de la que se van a probar los elementos. La expresión debe devolver un valor `Boolean` o un equivalente funcional, como un `Integer` que se va a evaluar como `Boolean`.|  
  
## <a name="remarks"></a>Comentarios  
 La cláusula `Skip While` omite los elementos desde el principio del resultado de una consulta hasta que el `expression` proporcionado devuelve `false`. Después de que `expression` devuelve `false`, la consulta devuelve todos los elementos restantes. El `expression` se omite para los resultados restantes.  
  
 La cláusula `Skip While` difiere de la cláusula `Where` en que la cláusula `Where` se puede utilizar para excluir todos los elementos de una consulta que no cumplan una condición determinada. La cláusula `Skip While` excluye los elementos solo hasta la primera vez que la condición no se cumple. La cláusula `Skip While` es muy útil cuando se trabaja con un resultado de consulta ordenado.  
  
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
