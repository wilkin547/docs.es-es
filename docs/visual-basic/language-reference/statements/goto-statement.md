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
ms.openlocfilehash: d5cdcd214c9679e245645505fe11cb5d521ce085
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351086"
---
# <a name="goto-statement"></a>GoTo (Instrucción)
Bifurca incondicionalmente a una línea especificada en un procedimiento.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a>Parte  
 `line`  
 Obligatorio. Cualquier etiqueta de línea.  
  
## <a name="remarks"></a>Comentarios  
 La instrucción `GoTo` solo puede bifurcar a las líneas del procedimiento en el que aparece. La línea debe tener una etiqueta de línea a la que `GoTo` pueda hacer referencia. Para obtener más información, vea [Cómo: etiquetar instrucciones](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
> [!NOTE]
> `GoTo` instrucciones pueden hacer que el código sea difícil de leer y mantener. Siempre que sea posible, use una estructura de control en su lugar. Para obtener más información, consulte [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).  
  
 No se puede usar una instrucción `GoTo` para bifurcar desde fuera de una `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`o `Using`...`End Using` construcción a una etiqueta dentro de.  
  
## <a name="branching-and-try-constructions"></a>Bifurcación y construcciones try  
 Dentro de una construcción `Try`...`Catch`...`Finally`, se aplican las siguientes reglas a la bifurcación con la instrucción `GoTo`.  
  
|Bloque o región|Bifurcación desde fuera|Bifurcar desde dentro|  
|---------------------|-------------------------------|-------------------------------|  
|`Try` bloque)|Solo desde un bloque de `Catch` de la misma construcción <sup>1</sup>|Solo hacia fuera de la construcción completa|  
|`Catch` bloque)|Nunca permitido|Solo hacia fuera de la construcción completa o hasta el `Try` bloque de la misma construcción <sup>1</sup>|  
|`Finally` bloque)|Nunca permitido|Nunca permitido|  
  
 <sup>1</sup> si una construcción `Try`...`Catch`...`Finally` está anidada dentro de otra, un bloque de `Catch` se puede bifurcar en el bloque de `Try` en su propio nivel de anidamiento, pero no en otro bloque de `Try`. Una construcción `Try`anidada...`Catch`...`Finally` debe estar contenida completamente en un bloque `Try` o `Catch` de la construcción en la que está anidada.  
  
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
