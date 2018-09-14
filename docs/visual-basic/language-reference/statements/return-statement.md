---
title: Return (Instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: fe200add4e29fe4bbe0fdf335dcd94107b8ff1eb
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "45515686"
---
# <a name="return-statement-visual-basic"></a>Return (Instrucción, Visual Basic)
Devuelve el control al código que llama a un `Function`, `Sub`, `Get`, `Set`, o `Operator` procedimiento.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a>Parte  
 `expression`  
 Necesario en un `Function`, `Get`, o `Operator` procedimiento. Expresión que representa el valor que se devolverá al código de llamada.  
  
## <a name="remarks"></a>Comentarios  
 En un `Sub` o `Set` procedimiento, el `Return` instrucción es equivalente a un `Exit Sub` o `Exit Property` instrucción, y `expression` no se debe proporcionar.  
  
 En un `Function`, `Get`, o `Operator` procedimiento, el `Return` debe incluir la instrucción `expression`, y `expression` debe evaluarse como un tipo de datos que se pueda convertir al tipo de valor devuelto del procedimiento. En un `Function` o `Get` procedimiento, también tiene la alternativa de asignación de una expresión para el nombre del procedimiento para que actúe como el valor devuelto y, a continuación, ejecutando un `Exit Function` o `Exit Property` instrucción. En un `Operator` procedimiento, debe usar `Return expression`.  
  
 Puede incluir tantos `Return` instrucciones según corresponda en el mismo procedimiento.  
  
> [!NOTE]
>  El código en un `Finally` bloque se ejecuta después de un `Return` instrucción en un `Try` o `Catch` bloque es se ha encontrado, pero antes de que `Return` ejecuta la instrucción. Un `Return` instrucción no puede incluirse en un `Finally` bloque.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Return` instrucción varias veces para volver al código de llamada cuando el procedimiento no tiene que hacer nada más.  
  
 [!code-vb[VbVbalrStatements#53](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/return-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Get (instrucción)](../../../visual-basic/language-reference/statements/get-statement.md)  
 [Set (instrucción)](../../../visual-basic/language-reference/statements/set-statement.md)  
 [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Exit (instrucción)](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
