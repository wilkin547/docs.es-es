---
title: GoTo (Instrucción)
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
ms.openlocfilehash: 27ebc677bab8b7f61a02408fddb30a6ec21c43cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="goto-statement"></a>GoTo (Instrucción)
Realiza una bifurcación incondicional a una línea especificada en un procedimiento.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
GoTo line  
```  
  
## <a name="part"></a>Parte  
 `line`  
 Requerido. Cualquier etiqueta de línea.  
  
## <a name="remarks"></a>Comentarios  
 El `GoTo` instrucción puede crear una bifurcación únicamente a las líneas en el procedimiento en el que aparece. La línea debe tener una línea en la etiqueta que `GoTo` pueden hacer referencia a. Para obtener más información, consulte [Cómo: instrucciones de la etiqueta](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
> [!NOTE]
>  `GoTo` las instrucciones pueden dificultar la lectura y el mantenimiento del código. Siempre que sea posible, utilice en su lugar una estructura de control. Para obtener más información, consulte [flujo de Control](../../../visual-basic/programming-guide/language-features/control-flow/index.md).  
  
 No se puede utilizar un `GoTo` instrucción para bifurcar desde fuera de un `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With`, o `Using`... `End Using` construcción en una etiqueta dentro.  
  
## <a name="branching-and-try-constructions"></a>Bifurcación y construcciones Try  
 Dentro de un `Try`... `Catch`... `Finally` construcción, las reglas siguientes se aplican a la bifurcación con la `GoTo` instrucción.  
  
|Bloque o región|Bifurcación hacia dentro desde fuera|Bifurcación hacia fuera desde dentro de|  
|---------------------|-------------------------------|-------------------------------|  
|`Try` Bloque|Sólo desde un `Catch` bloque de la misma construcción <sup>1</sup>|Solo fuera de la construcción completa|  
|`Catch` Bloque|Nunca se permite|Solo fuera de la construcción completa o a la `Try` bloque de la misma construcción <sup>1</sup>|  
|`Finally` Bloque|Nunca se permite|Nunca se permite|  
  
 <sup>1</sup> si `Try`... `Catch`... `Finally` construcción está anidada dentro de otra, un `Catch` bloque puede crear una bifurcación en el `Try` bloque en su propio nivel de anidamiento, pero no en cualquier otro `Try` bloque. Anidada `Try`... `Catch`... `Finally` construcción debe estar contenida completamente en un `Try` o `Catch` bloque de la construcción dentro del cual está anidado.  
  
 En la siguiente ilustración muestra una `Try` construcción anidada dentro de otra. Las distintas bifurcaciones entre los bloques de las dos construcciones se indican como válidos o no es válido.  
  
 ![Diagrama gráfico de bifurcación en construcciones Try](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")  
Bifurcaciones válidas como no válidas en construcciones Try  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `GoTo` instrucción para bifurcar a etiquetas de línea en un procedimiento.  
  
 [!code-vb[VbVbalrStatements#31](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/goto-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Do...Loop (instrucción)](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [For...Next (instrucción)](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [For Each...Next (instrucción)](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [If...Then...Else (instrucción)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [Select...Case (instrucción)](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [While...End While (instrucción)](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [With...End With (instrucción)](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
