---
title: Continue (Instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 23bb57ec022e62cd586c533d4ed4c792789a0b38
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627010"
---
# <a name="continue-statement-visual-basic"></a>Continue (Instrucción, Visual Basic)
Transfiere el control inmediatamente a la siguiente iteración de un bucle.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>Comentarios  
 Puede transferir desde dentro de un `Do`, `For`, o `While` bucle a la siguiente iteración del bucle. El control pasa inmediatamente a la comprobación de condición del bucle, que es equivalente a transferir a la `For` o `While` instrucción, o a la `Do` o `Loop` instrucción que contiene el `Until` o `While` cláusula.  
  
 Puede usar `Continue` en cualquier ubicación en el bucle que permite las transferencias. Las reglas que permiten la transferencia de control son los mismos que con la [instrucción GoTo](../../../visual-basic/language-reference/statements/goto-statement.md).  
  
 Por ejemplo, si un bucle es totalmente independiente dentro de un `Try` bloque, un `Catch` bloque, o un `Finally` bloque, puede usar `Continue` para transferir el bucle. Si es, por otro lado, el `Try`... `End Try` estructura está dentro del bucle, no se puede usar `Continue` para transferir el control fuera de la `Finally` bloque y se puede usar para transferir fuera de un `Try` o `Catch` sólo se bloquea si transfirió completamente fuera de la `Try`... `End Try` estructura.  
  
 Si tiene bucles anidados del mismo tipo, por ejemplo un `Do` bucle dentro de otro `Do` bucle, un `Continue Do` omite la instrucción a la siguiente iteración de la más interna `Do` bucle que lo contiene. No puede usar `Continue` para ir directamente a la siguiente iteración de un bucle que contiene el mismo tipo.  
  
 Si tiene bucles anidados de tipos diferentes, por ejemplo un `Do` en bucle dentro de un `For` bucle, puede ir a la siguiente iteración del bucle de cualquier mediante el uso `Continue Do` o `Continue For`.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código utiliza el `Continue While` instrucción para pasar a la siguiente columna de una matriz si un divisor es cero. El `Continue While` está dentro de un `For` bucle. Transfiere a la `While col < lastcol` instrucción, que es la siguiente iteración del interior `While` bucle que contiene el `For` bucle.  
  
 [!code-vb[VbVbalrStatements#14](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/continue-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también
- [Do...Loop (instrucción)](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [For...Next (instrucción)](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [While...End While (instrucción)](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
