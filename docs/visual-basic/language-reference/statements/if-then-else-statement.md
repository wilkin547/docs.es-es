---
title: If...Then...Else (Instrucción)
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
ms.openlocfilehash: f505755caeb9cc3cfeeb1ba83b6de15f48314103
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351159"
---
# <a name="ifthenelse-statement-visual-basic"></a>Instrucción If...Then...Else (Visual Basic)

Ejecuta condicionalmente un grupo de instrucciones en función del valor de una expresión.

## <a name="syntax"></a>Sintaxis

```vb
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

En este artículo se incluyen varios ejemplos que ilustran los usos de la instrucción `If`...`Then`...`Else`:

- [Ejemplo de sintaxis de varias líneas](#multi-line)
- [Ejemplo de sintaxis anidada](#nested)
- [Ejemplo de sintaxis de una sola línea](#single-line)

## <a name="parts"></a>Elementos

`condition` \
Obligatorio. Expresiones. Debe evaluarse como `True` o `False`, o a un tipo de datos que se pueda convertir implícitamente a `Boolean`.

Si la expresión es una variable de `Boolean` que [acepta valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) y que se evalúa como [Nothing](../../../visual-basic/language-reference/nothing.md), la condición se trata como si la expresión fuese `False`, y los bloques de `ElseIf` se evalúan si existen, o el bloque de `Else` se ejecuta si existe.

`Then` \
Requerido en la sintaxis de una sola línea; opcional en la sintaxis de varias líneas.

`statements` \
Opcional. Una o varias instrucciones que siguen `If`...`Then` que se ejecutan si `condition` se evalúa como `True`.

`elseifcondition` \
Obligatorio si `ElseIf` está presente. Expresiones. Debe evaluarse como `True` o `False`, o a un tipo de datos que se pueda convertir implícitamente a `Boolean`.

`elseifstatements` \
Opcional. Una o varias instrucciones que siguen `ElseIf`...`Then` que se ejecutan si `elseifcondition` se evalúa como `True`.

`elsestatements` \
Opcional. Una o varias instrucciones que se ejecutan si ninguna expresión `condition` o `elseifcondition` anterior se evalúa como `True`.

`End If` \
Finaliza la versión de varias líneas del bloque `If`...`Then`...`Else`.

## <a name="remarks"></a>Comentarios

### <a name="multiline-syntax"></a>Sintaxis de varias líneas

Cuando se encuentra una instrucción `If`...`Then`...`Else`, se prueba `condition`. Si `condition` se `True`, se ejecutan las instrucciones siguientes `Then`. Si se `False``condition`, cada instrucción de `ElseIf` (si hay alguna) se evalúa en orden. Cuando se encuentra un `elseifcondition` de `True`, se ejecutan las instrucciones inmediatamente después de la `ElseIf` asociada. Si ningún `elseifcondition` se evalúa como `True`, o si no hay ninguna instrucción `ElseIf`, se ejecutan las instrucciones siguientes `Else`. Después de ejecutar las instrucciones que siguen `Then`, `ElseIf`o `Else`, la ejecución continúa con la instrucción que sigue a `End If`.

Las cláusulas `ElseIf` y `Else` son opcionales. Puede tener tantas cláusulas `ElseIf` como desee en una instrucción `If`...`Then`...`Else`, pero no puede aparecer una cláusula `ElseIf` después de una cláusula `Else`. las instrucciones `If`...`Then`...`Else` se pueden anidar unas dentro de otras.

En la sintaxis de varias líneas, la instrucción `If` debe ser la única instrucción en la primera línea. Las instrucciones `ElseIf`, `Else`y `End If` solo pueden ir precedidas de una etiqueta de línea. El bloque `If`...`Then`...`Else` debe terminar con una instrucción `End If`.

> [!TIP]
> La [selección... La instrucción Case](../../../visual-basic/language-reference/statements/select-case-statement.md) podría ser más útil cuando se evalúa una expresión única que tiene varios valores posibles.

### <a name="single-line-syntax"></a>Sintaxis de una sola línea

Puede usar la sintaxis de una sola línea para una única condición con el código que se ejecutará si es true. Sin embargo, la sintaxis de varias líneas proporciona más estructura y flexibilidad y es más fácil de leer, mantener y depurar.

Lo que sigue a la palabra clave `Then` se examina para determinar si una instrucción es un `If`de una sola línea. Si aparece cualquier cosa que no sea un comentario después de `Then` en la misma línea, la instrucción se trata como una instrucción de `If` de una sola línea. Si falta `Then`, debe ser el inicio de una `If`de varias líneas...`Then`...`Else`.

En la sintaxis de una sola línea, se pueden ejecutar varias instrucciones como resultado de una `If`...`Then` decisión. Todas las instrucciones deben estar en la misma línea y deben estar separadas por dos puntos.

## <a name="multiline-syntax-example"></a>Ejemplo de sintaxis de varias líneas

<a name="multi-line"></a>

En el ejemplo siguiente se muestra el uso de la sintaxis de varias líneas de la instrucción `If`...`Then`...`Else`.

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a>Ejemplo de sintaxis anidada

<a name="nested"></a>

En el ejemplo siguiente se incluyen instrucciones anidadas `If`...`Then`...`Else`.

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
