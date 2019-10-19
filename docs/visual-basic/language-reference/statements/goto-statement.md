---
title: GoTo (instrucción) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GoTo
helpviewer_keywords:
- GoTo statement [Visual Basic]
- control flow [Visual Basic], branching
- unconditional branching [Visual Basic]
- branching [Visual Basic]
- branching [Visual Basic], unconditional
- branching [Visual Basic], conditional
- conditional statements [Visual Basic], GoTo statement
- GoTo statement [Visual Basic], syntax
ms.assetid: 313274c2-8ab3-4b9c-9ba3-0fd6798e4f6d
ms.openlocfilehash: 4b7a5cce56dfdd2bdc7e068aadbc18b92bba269d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581816"
---
# <a name="goto-statement"></a>GoTo (Instrucción)
Bifurca incondicionalmente a una línea especificada en un procedimiento.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a>Parte  
 `line`  
 Requerido. Cualquier etiqueta de línea.  
  
## <a name="remarks"></a>Comentarios  
 La instrucción `GoTo` solo puede bifurcar a las líneas del procedimiento en el que aparece. La línea debe tener una etiqueta de línea a la que `GoTo` pueda hacer referencia. Para obtener más información, vea [Cómo: etiquetar instrucciones](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
> [!NOTE]
> `GoTo` instrucciones pueden hacer que el código sea difícil de leer y mantener. Siempre que sea posible, use una estructura de control en su lugar. Para obtener más información, consulte [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).  
  
 No se puede usar una instrucción `GoTo` para bifurcar desde fuera de un `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, 0... 1 o 2... 3 construcción en una etiqueta dentro de.  
  
## <a name="branching-and-try-constructions"></a>Bifurcación y construcciones try  
 Dentro de un `Try`... `Catch`... `Finally` construcción, se aplican las siguientes reglas a la bifurcación con la instrucción `GoTo`.  
  
|Bloque o región|Bifurcación desde fuera|Bifurcar desde dentro|  
|---------------------|-------------------------------|-------------------------------|  
|`Try` bloque)|Solo desde un bloque de `Catch` de la misma construcción <sup>1</sup>|Solo hacia fuera de la construcción completa|  
|`Catch` bloque)|Nunca permitido|Solo hacia fuera de la construcción completa o hasta el `Try` bloque de la misma construcción <sup>1</sup>|  
|`Finally` bloque)|Nunca permitido|Nunca permitido|  
  
 <sup>1</sup> si una `Try`... `Catch`... `Finally` construcción está anidada dentro de otra, un bloque de `Catch` se puede bifurcar en el bloque de `Try` en su propio nivel de anidamiento, pero no en otro bloque de `Try`. Un `Try` anidado... `Catch`... `Finally` construcción debe estar contenida completamente en un bloque de `Try` o `Catch` de la construcción en la que está anidada.  
  
 En la ilustración siguiente se muestra una construcción `Try` anidada dentro de otra. Varias ramas entre los bloques de las dos construcciones se indican como válidas o no válidas.  
  
 ![Diagrama gráfico de bifurcación en construcciones Try](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa la instrucción `GoTo` para bifurcar a las etiquetas de línea de un procedimiento.  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>Vea también

- [Do...Loop (instrucción)](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [For...Next (instrucción)](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [For Each...Next (instrucción)](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [If...Then...Else (instrucción)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Select...Case (instrucción)](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [While...End While (instrucción)](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [With...End With (instrucción)](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
