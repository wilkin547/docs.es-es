---
title: "Continue (Instrucción, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4a47819600a6c1d58f09c2f8ed3443632e9dab68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="continue-statement-visual-basic"></a>Continue (Instrucción, Visual Basic)
Transfiere el control inmediatamente a la siguiente iteración de un bucle.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>Comentarios  
 Puede transferir desde dentro de un `Do`, `For`, o `While` loop a la siguiente iteración del bucle. Control pasa inmediatamente a la comprobación de condición del bucle, que es equivalente a transferir a la `For` o `While` (instrucción), o a la `Do` o `Loop` instrucción que contiene el `Until` o `While` cláusula.  
  
 Puede usar `Continue` en cualquier ubicación en el bucle que permite las transferencias. Las reglas que permiten la transferencia del control son los mismos que con la [instrucción GoTo](../../../visual-basic/language-reference/statements/goto-statement.md).  
  
 Por ejemplo, si un bucle es totalmente independiente dentro de un `Try` bloque, un `Catch` bloque, o un `Finally` bloque, puede usar `Continue` para transferir fuera del bucle. Si es, por otro lado, la `Try`... `End Try` estructura está dentro del bucle, no se puede usar `Continue` para transferir el control fuera de la `Finally` bloque y se puede usar para transferir fuera de un `Try` o `Catch` sólo se bloquea si transfirió completamente fuera de la `Try`... `End Try` estructura.  
  
 Si tiene bucles anidados del mismo tipo, por ejemplo un `Do` bucle dentro de otro `Do` bucles, un `Continue Do` omite la instrucción a la siguiente iteración de la más interna `Do` bucle que lo contiene. No se puede utilizar `Continue` para ir directamente a la siguiente iteración de un bucle que contiene el mismo tipo.  
  
 Si tiene bucles anidados de tipos diferentes, por ejemplo un `Do` bucle dentro de un `For` bucle, puede omitir a la siguiente iteración de cualquiera de esos bucles utilizando `Continue Do` o `Continue For`.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código utiliza el `Continue While` instrucción para pasar a la siguiente columna de una matriz si un divisor es cero. El `Continue While` está dentro de un `For` bucle. Transfiere a la `While col < lastcol` instrucción, que es la siguiente iteración de la más interna `While` bucle que contiene el `For` bucle.  
  
 [!code-vb[VbVbalrStatements#14](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/continue-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Do...Loop (instrucción)](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [For...Next (instrucción)](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [While...End While (instrucción)](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
