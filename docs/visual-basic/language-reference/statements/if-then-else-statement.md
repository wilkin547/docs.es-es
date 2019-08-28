---
title: Instrucción If...Then...Else (Visual Basic)
ms.date: 04/16/2018
f1_keywords:
- vb.ElseIf
- vb.Then
- vb.If
- vb.EndIf
helpviewer_keywords:
- ElseIf statement [Visual Basic], If...Then...Else
- Then statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], branching
- execution [Visual Basic], conditional
- TypeOf...Is expression, and If...Then...Else statements
- If...Then...Else statements
- If statement [Visual Basic], If...Then...Else
- If statement [Visual Basic]
- Is operator [Visual Basic], in If...Then...Else statements
- If Operator [Visual Basic]
- branching [Visual Basic], conditional
- If function [Visual Basic], and If...Then...Else statements
- Else statement [Visual Basic]
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
ms.openlocfilehash: 97ac8c82df14eb5ddc5e26fdaddf61cc774a0476
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046569"
---
# <a name="ifthenelse-statement-visual-basic"></a>Instrucción If...Then...Else (Visual Basic)

Ejecuta condicionalmente un grupo de instrucciones en función del valor de una expresión.

## <a name="syntax"></a>Sintaxis

```
' Multiline syntax:
If condition [ Then ]
    [ statements ]
[ ElseIf elseifcondition [ Then ]
    [ elseifstatements ] ]
[ Else
    [ elsestatements ] ]
End If

' Single-line syntax:
If condition Then [ statements ] [ Else [ elsestatements ] ]
```

## <a name="quick-links-to-example-code"></a>Vínculos rápidos a código de ejemplo

En este artículo se incluyen varios ejemplos que muestran los `If`usos de... `Then`... `Else` instrucción:

* [Ejemplo de sintaxis de varias líneas](#multi-line)
* [Ejemplo de sintaxis anidada](#nested)
* [Ejemplo de sintaxis de una sola línea](#single-line)

## <a name="parts"></a>Elementos

`condition` \
Necesario. Expresiones. Debe evaluarse `True` como `False`o, o en un tipo de datos que se pueda convertir `Boolean`implícitamente en.

Si la expresión es una `Boolean` variable que [acepta valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `False` y que se evalúa como [Nothing](../../../visual-basic/language-reference/nothing.md), la condición se trata como si la expresión fuese y se ejecuta el `Else` bloque.

`Then` \
Requerido en la sintaxis de una sola línea; opcional en la sintaxis de varias líneas.

`statements` \
Opcional. Una o más instrucciones que `If`siguen a... que se ejecutan `condition` si se evalúa `True`como. `Then`

`elseifcondition` \
Obligatorio si `ElseIf` está presente. Expresiones. Debe evaluarse `True` como `False`o, o en un tipo de datos que se pueda convertir `Boolean`implícitamente en.

`elseifstatements` \
Opcional. Una o más instrucciones que `ElseIf`siguen a... que se ejecutan `elseifcondition` si se evalúa `True`como. `Then`

`elsestatements` \
Opcional. Una o varias instrucciones que se ejecutan si ninguna `condition` expresión `elseifcondition` or anterior se evalúa `True`como.

`End If` \
Finaliza la versión multilínea de `If`... `Then`... `Else` bloque.

## <a name="remarks"></a>Comentarios

### <a name="multiline-syntax"></a>Sintaxis de varias líneas

`If`Cuando... `Then`... la instrucción se ha `condition` encontrado, se ha probado. `Else` Si `condition` `Then` es `True`, se ejecutan las instrucciones siguientes. Si `condition` es `False`, cada`ElseIf` instrucción (si hay alguna) se evalúa en orden. Cuando se `True` encuentra un `elseifcondition` objeto, se ejecutan las instrucciones `ElseIf` inmediatamente después del objeto asociado. Si no `elseifcondition` se evalúa `True`como, o si no hay ninguna `ElseIf` instrucción, se ejecutan `Else` las instrucciones siguientes. Después de ejecutar las instrucciones que `Then`siguen `ElseIf`a, `Else`o, la ejecución continúa con la `End If`instrucción que sigue a.

Las `ElseIf` cláusulas y `Else` son opcionales. Puede tener tantas `ElseIf` cláusulas como desee `If`en... `Then`... , pero no `ElseIf` puede aparecer una cláusula después de `Else` una cláusula. `Else` `If`... `Then`... `Else` las instrucciones se pueden anidar unas dentro de otras.

En la sintaxis de varias líneas `If` , la instrucción debe ser la única instrucción en la primera línea. Las `ElseIf`instrucciones `Else`, y`End If` solo pueden ir precedidas de una etiqueta de línea. `If`... `Then`... el bloque debe terminar con `End If` una instrucción. `Else`

> [!TIP]
> La [selección... La instrucción Case](../../../visual-basic/language-reference/statements/select-case-statement.md) podría ser más útil cuando se evalúa una expresión única que tiene varios valores posibles.

### <a name="single-line-syntax"></a>Sintaxis de una sola línea

Puede usar la sintaxis de una sola línea para una única condición con el código que se ejecutará si es true. Sin embargo, la sintaxis de varias líneas proporciona más estructura y flexibilidad y es más fácil de leer, mantener y depurar.

Lo que sigue `Then` a la palabra clave se examina para determinar si una instrucción es una `If`sola línea. Si aparece cualquier cosa que no sea un `Then` comentario después de en la misma línea, la instrucción se trata como una `If` instrucción de una sola línea. Si `Then` no está presente, debe ser el inicio de una `If`... `Then`... `Else`.

En la sintaxis de una sola línea, se pueden ejecutar varias instrucciones como resultado de `If`... `Then` decisión. Todas las instrucciones deben estar en la misma línea y deben estar separadas por dos puntos.

## <a name="multiline-syntax-example"></a>Ejemplo de sintaxis de varias líneas

<a name="multi-line"></a>

En el ejemplo siguiente se muestra el uso de la sintaxis de varias `If`líneas de... `Then`... `Else` instrucción.

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a>Ejemplo de sintaxis anidada

<a name="nested"></a>

El ejemplo siguiente contiene anidado `If`... `Then`... `Else` instrucciones.

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a>Ejemplo de sintaxis de una sola línea

<a name="single-line"></a>En el ejemplo siguiente se muestra el uso de la sintaxis de una sola línea.

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [#If...Then...#Else (directivas)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Select...Case (instrucción)](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [Estructuras de control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Estructuras de decisión](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Operadores lógicos y bit a bit en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [If (operador)](../../../visual-basic/language-reference/operators/if-operator.md)
