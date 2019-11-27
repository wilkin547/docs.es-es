---
title: Let (Cláusula)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: 63eaf97016db259870eb77199651ecbdc5f809c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350432"
---
# <a name="let-clause-visual-basic"></a>Cláusula Let (Visual Basic)
Calcula un valor y lo asigna a una nueva variable dentro de la consulta.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`variable`|Obligatorio. Un alias que se puede usar para hacer referencia a los resultados de la expresión proporcionada.|  
|`expression`|Obligatorio. Expresión que se evaluará y asignará a la variable especificada.|  
  
## <a name="remarks"></a>Comentarios  
 La cláusula `Let` permite calcular valores para cada resultado de la consulta y hacer referencia a ellos mediante un alias. El alias se puede usar en otras cláusulas, como la cláusula `Where`. La cláusula `Let` le permite crear una instrucción de consulta que es más fácil de leer, ya que puede especificar un alias para una cláusula Expression incluida en la consulta y sustituir el alias cada vez que se use la cláusula Expression.  
  
 Puede incluir cualquier número de asignaciones de `variable` y `expression` en la cláusula `Let`. Separe cada asignación con una coma (,).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se usa la cláusula `Let` para calcular un 10% de descuento en productos.  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](../../../visual-basic/language-reference/queries/index.md)
- [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)
- [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)
- [Where (cláusula)](../../../visual-basic/language-reference/queries/where-clause.md)
