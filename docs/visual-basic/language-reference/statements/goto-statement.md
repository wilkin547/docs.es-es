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
ms.openlocfilehash: 3034c84684e94dfe8c334107a16df8cbd227c4d4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912448"
---
# <a name="goto-statement"></a>GoTo (Instrucción)
Bifurca incondicionalmente a una línea especificada en un procedimiento.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
GoTo line  
```  
  
## <a name="part"></a>Parte  
 `line`  
 Necesario. Cualquier etiqueta de línea.  
  
## <a name="remarks"></a>Comentarios  
 La `GoTo` instrucción solo puede bifurcar a las líneas del procedimiento en el que aparece. La línea debe tener una etiqueta de línea `GoTo` que pueda hacer referencia a. Para obtener más información, vea [Cómo: Instrucciones](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)de etiqueta.  
  
> [!NOTE]
> `GoTo`las instrucciones pueden hacer que el código sea difícil de leer y mantener. Siempre que sea posible, use una estructura de control en su lugar. Para obtener más información, consulte [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).  
  
 No se puede usar `GoTo` una instrucción para bifurcar desde `For`fuera de... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With`, o`Using`... `End Using` construcción de una etiqueta dentro de.  
  
## <a name="branching-and-try-constructions"></a>Bifurcación y construcciones try  
 Dentro de `Try`... `Catch`... la construcción de, se aplican las siguientes reglas a `GoTo` la bifurcación con la instrucción. `Finally`  
  
|Bloque o región|Bifurcación desde fuera|Bifurcar desde dentro|  
|---------------------|-------------------------------|-------------------------------|  
|`Try`sin|Solo desde un `Catch` bloque de la misma construcción <sup>1</sup>|Solo hacia fuera de la construcción completa|  
|`Catch`sin|Nunca permitido|Solo hacia fuera de la construcción completa o hasta el `Try` bloque de la misma construcción <sup>1</sup>|  
|`Finally`sin|Nunca permitido|Nunca permitido|  
  
 <sup>1</sup> si uno `Try`... `Catch`... la construcción está anidada dentro de otra `Catch` , un bloque se puede `Try` bifurcar en el bloque en su propio nivel de anidamiento, pero `Try` no en ningún otro bloque. `Finally` Una instrucción anidada `Try`... `Catch`... la construcción debe estar contenida completamente `Try` en `Catch` un bloque o de la construcción en la que está anidada. `Finally`  
  
 En la ilustración siguiente se `Try` muestra una construcción anidada dentro de otra. Varias ramas entre los bloques de las dos construcciones se indican como válidas o no válidas.  
  
 ![Diagrama gráfico de bifurcación en construcciones Try](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se `GoTo` usa la instrucción para bifurcar a las etiquetas de línea de un procedimiento.  
  
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
