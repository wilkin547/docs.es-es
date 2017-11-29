---
title: "Exit (Instrucción, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Exit
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- Exit statement [Visual Basic]
- program termination
- execution [Visual Basic], stopping
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2df63ecbf0605d07296e1692f18b1b015e27cd03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="exit-statement-visual-basic"></a>Exit (Instrucción, Visual Basic)
Sale de un procedimiento o bloque y transfiere el control inmediatamente a la instrucción que sigue a la llamada de procedimiento o la definición del bloque.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## <a name="statements"></a>Instrucciones  
 `Exit Do`  
 Sale inmediatamente del `Do` bucle en el que aparece. La ejecución continúa con la siguiente instrucción la `Loop` instrucción. `Exit Do`Puede usar solo dentro de un `Do` bucle. Cuando se usa en anidados `Do` bucles, `Exit Do` sale del bucle más interno y transfiere el control al siguiente nivel más alto de anidamiento.  
  
 `Exit For`  
 Sale inmediatamente del `For` bucle en el que aparece. La ejecución continúa con la siguiente instrucción la `Next` instrucción. `Exit For`Puede usar solo dentro de un `For`... `Next` o `For Each`... `Next` bucle. Cuando se usa en anidados `For` bucles, `Exit For` sale del bucle más interno y transfiere el control al siguiente nivel más alto de anidamiento.  
  
 `Exit Function`  
 Sale inmediatamente del `Function` procedimiento en el que aparece. La ejecución continúa con la instrucción que sigue a la instrucción que llamó la `Function` procedimiento. `Exit Function`Puede usar solo dentro de un `Function` procedimiento.  
  
 Para especificar un valor devuelto, puede asignar el valor al nombre de función en una línea antes de la `Exit Function` instrucción. Para asignar el valor devuelto y salir de la función en una sola instrucción, puede usar en su lugar el [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 `Exit Property`  
 Sale inmediatamente del `Property` procedimiento en el que aparece. La ejecución continúa con la instrucción que llamó la `Property` procedimiento, es decir, con la instrucción que solicita o establece el valor de la propiedad. `Exit Property`se pueden usar solo dentro de una propiedad `Get` o `Set` procedimiento.  
  
 Para especificar un valor devuelto en un `Get` procedimiento, puede asignar el valor al nombre de función en una línea antes de la `Exit Property` instrucción. Para asignar el valor devuelto y salir del `Get` procedimiento en una instrucción, puede usar en su lugar el `Return` instrucción.  
  
 En un `Set` procedimiento, el `Exit Property` instrucción es equivalente a la `Return` instrucción.  
  
 `Exit Select`  
 Sale inmediatamente del `Select Case` bloque en el que aparece. La ejecución continúa con la siguiente instrucción la `End Select` instrucción. `Exit Select`Puede usar solo dentro de un `Select Case` instrucción.  
  
 `Exit Sub`  
 Sale inmediatamente del `Sub` procedimiento en el que aparece. La ejecución continúa con la instrucción que sigue a la instrucción que llamó la `Sub` procedimiento. `Exit Sub`Puede usar solo dentro de un `Sub` procedimiento.  
  
 En un `Sub` procedimiento, el `Exit Sub` instrucción es equivalente a la `Return` instrucción.  
  
 `Exit Try`  
 Sale inmediatamente del `Try` o `Catch` bloque en el que aparece. La ejecución continúa con la `Finally` bloquear si hay alguno, o con la siguiente instrucción la `End Try` instrucción en caso contrario. `Exit Try`Puede usar solo dentro de un `Try` o `Catch` bloque y no dentro un `Finally` bloque.  
  
 `Exit While`  
 Sale inmediatamente del `While` bucle en el que aparece. La ejecución continúa con la siguiente instrucción la `End While` instrucción. `Exit While`Puede usar solo dentro de un `While` bucle. Cuando se usa en anidados `While` bucles, `Exit While` transfiere el control al bucle que está anidado un nivel por encima del bucle donde `Exit While` se produce.  
  
## <a name="remarks"></a>Comentarios  
 No confunda `Exit` instrucciones con `End` instrucciones. `Exit`no se define el final de una instrucción.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, la condición del bucle detiene el bucle cuando la `index` variable es mayor que 100. El `If` instrucción del bucle, sin embargo, hace que el `Exit Do` instrucción para detener el bucle cuando la variable de índice es mayor que 10.  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se asigna el valor devuelto al nombre de función `myFunction`y, a continuación, usa `Exit Function` para devolver de la función.  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_2.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md) para asignar el valor devuelto y salir de la función.  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_3.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Continue (instrucción)](../../../visual-basic/language-reference/statements/continue-statement.md)  
 [Do...Loop (instrucción)](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [End (instrucción)](../../../visual-basic/language-reference/statements/end-statement.md)  
 [For Each...Next (instrucción)](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [For...Next (instrucción)](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Return (instrucción)](../../../visual-basic/language-reference/statements/return-statement.md)  
 [Stop (instrucción)](../../../visual-basic/language-reference/statements/stop-statement.md)  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
