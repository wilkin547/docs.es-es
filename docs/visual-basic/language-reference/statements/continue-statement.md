---
title: Continue (Instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 9ee5fb19db6eafeb7e4bed12935d0b950d6368d6
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005105"
---
# <a name="continue-statement-visual-basic"></a>Continue (Instrucción, Visual Basic)
Transfiere el control inmediatamente a la siguiente iteración de un bucle.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>Comentarios  
 Puede transferir desde dentro de un bucle `Do`, `For` o `While` a la siguiente iteración del bucle. El control pasa inmediatamente a la prueba de la condición de bucle, que es equivalente a transferir a la instrucción `For` o `While`, o a la instrucción `Do` o `Loop` que contiene la cláusula `Until` o `While`.  
  
 Puede usar `Continue` en cualquier ubicación del bucle que permita las transferencias. Las reglas que permiten la transferencia de control son las mismas que con la [instrucción Goto](../../../visual-basic/language-reference/statements/goto-statement.md).  
  
 Por ejemplo, si un bucle está contenido completamente dentro de un bloque `Try`, un bloque `Catch` o un bloque `Finally`, puede usar `Continue` para transferir fuera del bucle. Por otra parte, si la estructura `Try`... `End Try` está contenida en el bucle, no se puede usar `Continue` para transferir el control fuera del bloque `Finally`, y se puede usar para transferir fuera de un bloque `Try` o `Catch` solo si se transfiere completamente fuera del @no_ _ t-6... `End Try` (estructura).  
  
 Si tiene bucles anidados del mismo tipo, por ejemplo, un bucle @no__t 0 dentro de otro bucle `Do`, una instrucción `Continue Do` omite la siguiente iteración del bucle `Do` más interno que lo contiene. No se puede usar `Continue` para pasar a la siguiente iteración de un bucle contenedor del mismo tipo.  
  
 Si tiene bucles anidados de distintos tipos, por ejemplo, un bucle @no__t 0 dentro de un bucle `For`, puede ir directamente a la siguiente iteración de cualquier bucle mediante `Continue Do` o `Continue For`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se usa la instrucción `Continue While` para saltar a la columna siguiente de una matriz si un divisor es cero. El `Continue While` está dentro de un bucle `For`. Se transfiere a la instrucción `While col < lastcol`, que es la siguiente iteración del bucle `While` más interno que contiene el bucle `For`.  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>Vea también

- [Do...Loop (instrucción)](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [For...Next (instrucción)](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [While...End While (instrucción)](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
