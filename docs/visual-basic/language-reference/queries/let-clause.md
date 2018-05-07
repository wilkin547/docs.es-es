---
title: Let (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: 6484da5329c8240735b7c35f506637dd01cbeda4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="let-clause-visual-basic"></a>Let (Cláusula, Visual Basic)
Calcula un valor y lo asigna a una nueva variable en la consulta.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`variable`|Requerido. Un alias que puede utilizarse para hacer referencia a los resultados de la expresión proporcionada.|  
|`expression`|Requerido. Una expresión que se evalúa y se asigna a la variable especificada.|  
  
## <a name="remarks"></a>Comentarios  
 El `Let` cláusula permite calcular valores para cada resultado de la consulta y hacer referencia a ellos mediante un alias. El alias se puede usar en otras cláusulas, como la `Where` cláusula. El `Let` cláusula le permite crear una instrucción de consulta que es más fácil de leer porque puede especificar un alias para una cláusula de expresión incluida en la consulta y sustituya el alias cada vez que se utiliza la cláusula de expresión.  
  
 Puede incluir cualquier número de `variable` y `expression` asignaciones en la `Let` cláusula. Separe cada asignación con una coma (,).  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código utiliza el `Let` cláusula para calcular un 10 por ciento de descuento sobre los productos.  
  
 [!code-vb[VbSimpleQuerySamples#16](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/let-clause_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)  
 [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Where (cláusula)](../../../visual-basic/language-reference/queries/where-clause.md)
