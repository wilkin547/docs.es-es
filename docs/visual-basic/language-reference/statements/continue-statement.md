---
title: Instrucción Continue
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: fd604b281a590073a5e76398788d7648cadd145c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84382099"
---
# <a name="continue-statement-visual-basic"></a>Continue (Instrucción, Visual Basic)
Transfiere el control inmediatamente a la siguiente iteración de un bucle.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>Observaciones  
 Puede transferir desde dentro de un `Do` `For` bucle, o `While` hasta la siguiente iteración del bucle. El control pasa inmediatamente a la prueba de la condición de bucle, que es equivalente a transferir a la `For` `While` instrucción o, o a la `Do` `Loop` instrucción o que contiene la `Until` `While` cláusula o.  
  
 Puede usar `Continue` en cualquier ubicación del bucle que permita las transferencias. Las reglas que permiten la transferencia de control son las mismas que con la [instrucción Goto](goto-statement.md).  
  
 Por ejemplo, si un bucle está totalmente contenido dentro de un bloque, `Try` un `Catch` bloque o un `Finally` bloque, puede usar `Continue` para transferir fuera del bucle. Por otro lado, si la `Try` estructura... `End Try` está contenida dentro del bucle, no se puede usar `Continue` para transferir el control fuera del `Finally` bloque, y se puede utilizar para transferir fuera de un `Try` bloque o `Catch` solo si se transfiere completamente de la `Try` estructura... `End Try` .  
  
 Si tiene bucles anidados del mismo tipo, por ejemplo un `Do` bucle dentro de otro `Do` bucle, una `Continue Do` instrucción salta a la siguiente iteración del bucle más interno `Do` que lo contiene. No se puede usar `Continue` para pasar a la siguiente iteración de un bucle contenedor del mismo tipo.  
  
 Si tiene bucles anidados de distintos tipos, por ejemplo un `Do` bucle dentro de un `For` bucle, puede ir directamente a la siguiente iteración de cualquier bucle mediante `Continue Do` o `Continue For` .  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente `Continue While` se usa la instrucción para saltar a la columna siguiente de una matriz si un divisor es cero. `Continue While`Está dentro de un `For` bucle. Se transfiere a la `While col < lastcol` instrucción, que es la siguiente iteración del bucle más interno `While` que contiene el `For` bucle.  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>Consulte también

- [Instrucción Do...Loop](do-loop-statement.md)
- [Instrucción For...Next](for-next-statement.md)
- [Instrucción While...End While](while-end-while-statement.md)
- [Instrucción Try...Catch...Finally](try-catch-finally-statement.md)
