---
title: Return (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: efc85a3a844898345aa2d16926ba0e35d7346d1b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333011"
---
# <a name="return-statement-visual-basic"></a>Return (Instrucción, Visual Basic)
Devuelve el control al código que llamó a un procedimiento `Function`, `Sub`, `Get`, `Set`o `Operator`.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a>Parte  
 `expression`  
 Obligatorio en un procedimiento `Function`, `Get`o `Operator`. Expresión que representa el valor que se va a devolver al código de llamada.  
  
## <a name="remarks"></a>Comentarios  
 En un procedimiento `Sub` o `Set`, la instrucción `Return` es equivalente a una instrucción `Exit Sub` o `Exit Property` y no se debe proporcionar `expression`.  
  
 En un procedimiento `Function`, `Get`o `Operator`, la instrucción `Return` debe incluir `expression`y `expression` debe evaluarse como un tipo de datos que se pueda convertir al tipo de valor devuelto del procedimiento. En un procedimiento `Function` o `Get`, también tiene la alternativa de asignar una expresión al nombre del procedimiento para que sirva como valor devuelto y, a continuación, ejecutar una instrucción `Exit Function` o `Exit Property`. En un procedimiento `Operator`, debe utilizar `Return expression`.  
  
 Puede incluir tantas instrucciones `Return` como corresponda en el mismo procedimiento.  
  
> [!NOTE]
> El código de un bloque de `Finally` se ejecuta después de que se encuentre una instrucción de `Return` en un bloque de `Try` o `Catch`, pero antes de que se ejecute la instrucción `Return`. No se puede incluir una instrucción `Return` en un bloque de `Finally`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza la instrucción `Return` varias veces para volver al código de llamada cuando el procedimiento no tiene que hacer nada más.  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a>Vea también

- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Get (instrucción)](../../../visual-basic/language-reference/statements/get-statement.md)
- [Set (instrucción)](../../../visual-basic/language-reference/statements/set-statement.md)
- [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)
- [Exit (instrucción)](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
