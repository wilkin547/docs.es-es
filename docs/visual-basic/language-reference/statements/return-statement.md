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
ms.openlocfilehash: af49ea95d7f9d01072190ac3ccf6ba2f1041347e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957673"
---
# <a name="return-statement-visual-basic"></a>Return (Instrucción, Visual Basic)
Devuelve el control al código que llamó a `Function`un `Sub`procedimiento `Get`, `Set`,, `Operator` o.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a>Parte  
 `expression`  
 Requerido en un `Function`procedimiento `Get`, o `Operator` . Expresión que representa el valor que se va a devolver al código de llamada.  
  
## <a name="remarks"></a>Comentarios  
 En un `Sub` procedimiento `Set` o, la `Return` instrucción es equivalente a una `Exit Sub` instrucción `Exit Property` o, y `expression` no se debe proporcionar.  
  
 En un `Function`procedimiento `Get`, o `Operator` , la `Return` instrucción debe incluir `expression`y `expression` debe evaluarse como un tipo de datos que se pueda convertir al tipo de valor devuelto del procedimiento. En un `Function` procedimiento `Get` o, también tiene la alternativa de asignar una expresión al nombre del procedimiento para que sirva como valor devuelto y, a continuación, ejecutar una `Exit Function` instrucción o `Exit Property` . En un `Operator` procedimiento, debe usar `Return expression`.  
  
 Puede incluir tantas `Return` instrucciones como corresponda en el mismo procedimiento.  
  
> [!NOTE]
> El código de un `Finally` bloque se ejecuta después de que se `Try` encuentre `Catch` una instrucción en un bloque o, `Return` pero antes de que se ejecute la `Return` instrucción. No `Return` se puede incluir una instrucción en `Finally` un bloque.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se `Return` utiliza la instrucción varias veces para volver al código de llamada cuando el procedimiento no tiene que hacer nada más.  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a>Vea también

- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Get (instrucción)](../../../visual-basic/language-reference/statements/get-statement.md)
- [Set (instrucción)](../../../visual-basic/language-reference/statements/set-statement.md)
- [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)
- [Exit (instrucción)](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
