---
title: Exit (Instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Exit
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- Exit statement [Visual Basic]
- program termination
- execution [Visual Basic], stopping
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
ms.openlocfilehash: 1f386694bd7425ee530b9305ab684b730f9b73c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832637"
---
# <a name="exit-statement-visual-basic"></a>Exit (Instrucción, Visual Basic)
Se cierra un procedimiento o bloque y transfiere el control inmediatamente a la instrucción siguiente a la llamada al procedimiento o la definición del bloque.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## <a name="statements"></a>Instrucciones  
 `Exit Do`  
 Inmediatamente después cierra el `Do` bucle en el que aparece. La ejecución continúa con la instrucción que sigue la `Loop` instrucción. `Exit Do` se puede usar solo dentro de un `Do` bucle. Cuando se usa en anidados `Do` bucles, `Exit Do` sale del bucle más interno y transfiere el control al siguiente nivel más alto de anidamiento.  
  
 `Exit For`  
 Inmediatamente después cierra el `For` bucle en el que aparece. La ejecución continúa con la instrucción que sigue la `Next` instrucción. `Exit For` se puede usar solo dentro de un `For`... `Next` o `For Each`... `Next` bucle. Cuando se usa en anidados `For` bucles, `Exit For` sale del bucle más interno y transfiere el control al siguiente nivel más alto de anidamiento.  
  
 `Exit Function`  
 Inmediatamente después cierra el `Function` procedimiento en el que aparece. La ejecución continúa con la instrucción que sigue a la instrucción que llama el `Function` procedimiento. `Exit Function` se puede usar solo dentro de un `Function` procedimiento.  
  
 Para especificar un valor devuelto, puede asignar el valor al nombre de función en una línea antes de la `Exit Function` instrucción. Para asignar el valor devuelto y salir de la función en una sola instrucción, puede usar en su lugar el [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 `Exit Property`  
 Inmediatamente después cierra el `Property` procedimiento en el que aparece. La ejecución continúa con la instrucción que llama el `Property` procedimiento, es decir, con la instrucción que solicita o establece el valor de propiedad. `Exit Property` se puede usar solo dentro de una propiedad `Get` o `Set` procedimiento.  
  
 Para especificar un valor devuelto en un `Get` procedimiento, puede asignar el valor al nombre de función en una línea antes de la `Exit Property` instrucción. Para asignar el valor devuelto y salir del `Get` procedimiento en una sola instrucción, puede usar en su lugar el `Return` instrucción.  
  
 En un `Set` procedimiento, el `Exit Property` instrucción es equivalente a la `Return` instrucción.  
  
 `Exit Select`  
 Inmediatamente después cierra el `Select Case` bloque en el que aparece. La ejecución continúa con la instrucción que sigue la `End Select` instrucción. `Exit Select` se puede usar solo dentro de un `Select Case` instrucción.  
  
 `Exit Sub`  
 Inmediatamente después cierra el `Sub` procedimiento en el que aparece. La ejecución continúa con la instrucción que sigue a la instrucción que llama el `Sub` procedimiento. `Exit Sub` se puede usar solo dentro de un `Sub` procedimiento.  
  
 En un `Sub` procedimiento, el `Exit Sub` instrucción es equivalente a la `Return` instrucción.  
  
 `Exit Try`  
 Inmediatamente después cierra el `Try` o `Catch` bloque en el que aparece. La ejecución continúa con la `Finally` bloquear si hay alguno, o con la instrucción que sigue la `End Try` instrucción en caso contrario. `Exit Try` se puede usar solo dentro de un `Try` o `Catch` bloque y no dentro un `Finally` bloque.  
  
 `Exit While`  
 Inmediatamente después cierra el `While` bucle en el que aparece. La ejecución continúa con la instrucción que sigue la `End While` instrucción. `Exit While` se puede usar solo dentro de un `While` bucle. Cuando se usa dentro de anidar `While` bucles, `Exit While` transfiere el control al bucle que está anidado y un nivel por encima del bucle donde `Exit While` se produce.  
  
## <a name="remarks"></a>Comentarios  
 No confunda `Exit` instrucciones con `End` instrucciones. `Exit` no se define el final de una instrucción.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, la condición del bucle detiene el bucle cuando la `index` variable es mayor que 100. El `If` instrucción del bucle, sin embargo, hace que el `Exit Do` instrucción para detener el bucle cuando la variable de índice es mayor que 10.  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se asigna el valor devuelto para el nombre de función `myFunction`y, a continuación, usa `Exit Function` para devolver de la función.  
  
 [!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md) para asignar el valor devuelto y salir de la función.  
  
 [!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]  
  
## <a name="see-also"></a>Vea también

- [Continue (instrucción)](../../../visual-basic/language-reference/statements/continue-statement.md)
- [Do...Loop (instrucción)](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [End (instrucción)](../../../visual-basic/language-reference/statements/end-statement.md)
- [For Each...Next (instrucción)](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [For...Next (instrucción)](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
- [Return (instrucción)](../../../visual-basic/language-reference/statements/return-statement.md)
- [Stop (instrucción)](../../../visual-basic/language-reference/statements/stop-statement.md)
- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
