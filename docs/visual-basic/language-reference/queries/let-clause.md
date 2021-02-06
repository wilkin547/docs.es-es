---
description: 'Más información sobre: cláusula Let (Visual Basic)'
title: Cláusula Let
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: 88a7d96bb790a1e6ec5adfa4337c51f807930168
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99653646"
---
# <a name="let-clause-visual-basic"></a>Let (Cláusula, Visual Basic)

Calcula un valor y lo asigna a una nueva variable dentro de la consulta.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`variable`|Obligatorio. Un alias que se puede usar para hacer referencia a los resultados de la expresión proporcionada.|  
|`expression`|Necesario. Expresión que se evaluará y asignará a la variable especificada.|  
  
## <a name="remarks"></a>Observaciones  

 La `Let` cláusula permite calcular valores para cada resultado de la consulta y hacer referencia a ellos mediante un alias. El alias se puede usar en otras cláusulas, como la `Where` cláusula. La `Let` cláusula le permite crear una instrucción de consulta que es más fácil de leer, ya que puede especificar un alias para una cláusula Expression incluida en la consulta y sustituir el alias cada vez que se use la cláusula Expression.  
  
 Puede incluir cualquier número de `variable` asignaciones y `expression` en la `Let` cláusula. Separe cada asignación con una coma (,).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo de código siguiente `Let` se usa la cláusula para calcular un 10% de descuento en productos.  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](index.md)
- [Select (cláusula)](select-clause.md)
- [Cláusula From](from-clause.md)
- [Cláusula WHERE](where-clause.md)
