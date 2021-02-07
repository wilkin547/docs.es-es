---
description: 'Más información sobre: Return (instrucción) (Visual Basic)'
title: Instrucción Return
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: 62086090ede7e634b09d3edc3dc42feb28d15793
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741203"
---
# <a name="return-statement-visual-basic"></a>Return (Instrucción, Visual Basic)

Devuelve el control al código que llamó a `Function` un `Sub` procedimiento,, `Get` , `Set` o `Operator` .  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a>Parte  

 `expression`  
 Requerido en un `Function` `Get` procedimiento, o `Operator` . Expresión que representa el valor que se va a devolver al código de llamada.  
  
## <a name="remarks"></a>Observaciones  

 En un `Sub` `Set` procedimiento o, la `Return` instrucción es equivalente a una `Exit Sub` `Exit Property` instrucción o, y `expression` no se debe proporcionar.  
  
 En un `Function` `Get` procedimiento, o `Operator` , la `Return` instrucción debe incluir `expression` y `expression` debe evaluarse como un tipo de datos que se pueda convertir al tipo de valor devuelto del procedimiento. En un `Function` `Get` procedimiento o, también tiene la alternativa de asignar una expresión al nombre del procedimiento para que sirva como valor devuelto y, a continuación, ejecutar una `Exit Function` instrucción o `Exit Property` . En un `Operator` procedimiento, debe usar `Return expression` .  
  
 Puede incluir tantas `Return` instrucciones como corresponda en el mismo procedimiento.  
  
> [!NOTE]
> El código de un `Finally` bloque se ejecuta después de `Return` que se encuentre una instrucción en un `Try` `Catch` bloque o, pero antes de que se `Return` ejecute la instrucción. `Return`No se puede incluir una instrucción en un `Finally` bloque.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se utiliza la `Return` instrucción varias veces para volver al código de llamada cuando el procedimiento no tiene que hacer nada más.  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a>Vea también

- [Instrucción Function](function-statement.md)
- [Instrucción Sub](sub-statement.md)
- [Get (Instrucción)](get-statement.md)
- [Set (instrucción)](set-statement.md)
- [Operator Statement](operator-statement.md)
- [Property Statement](property-statement.md)
- [Instrucción Exit](exit-statement.md)
- [Try...Catch...Finally (instrucción)](try-catch-finally-statement.md)
