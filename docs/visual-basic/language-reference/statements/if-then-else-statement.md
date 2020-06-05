---
title: Instrucción If...Then...Else
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
ms.openlocfilehash: 0884b71c24742286e695e720add9d00dd4bfe52b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404594"
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

En este artículo se incluyen varios ejemplos que muestran los usos de `If` ... `Then` ...`Else` privacidad

- [Ejemplo de sintaxis de varias líneas](#multi-line)
- [Ejemplo de sintaxis anidada](#nested)
- [Ejemplo de sintaxis de una sola línea](#single-line)

## <a name="parts"></a>Partes

`condition` \
Necesario. Expresión. Debe evaluarse como `True` o `False` , o en un tipo de datos que se pueda convertir implícitamente en `Boolean` .

Si la expresión es una variable que [acepta valores NULL](../../programming-guide/language-features/data-types/nullable-value-types.md) y `Boolean` que se evalúa como [Nothing](../nothing.md), la condición se trata como si la expresión fuese `False` , y los `ElseIf` bloques se evalúan si existen, o el `Else` bloque se ejecuta si existe.

`Then` \
Requerido en la sintaxis de una sola línea; opcional en la sintaxis de varias líneas.

`statements` \
Opcional. Una o más instrucciones `If` que siguen a... `Then` que se ejecutan si se `condition` evalúa como `True` .

`elseifcondition` \
Obligatorio si `ElseIf` está presente. Expresión. Debe evaluarse como `True` o `False` , o en un tipo de datos que se pueda convertir implícitamente en `Boolean` .

`elseifstatements` \
Opcional. Una o más instrucciones `ElseIf` que siguen a... `Then` que se ejecutan si se `elseifcondition` evalúa como `True` .

`elsestatements` \
Opcional. Una o varias instrucciones que se ejecutan si ninguna `condition` expresión or anterior se `elseifcondition` evalúa como `True` .

`End If` \
Finaliza la versión multilínea de `If` ... `Then` ...`Else` sin.

## <a name="remarks"></a>Observaciones

### <a name="multiline-syntax"></a>Sintaxis de varias líneas

Cuando `If` ... `Then` ...`Else` la instrucción se ha encontrado, `condition` se ha probado. Si `condition` es `True` , `Then` se ejecutan las instrucciones siguientes. Si `condition` es `False` , cada `ElseIf` instrucción (si hay alguna) se evalúa en orden. Cuando `True` `elseifcondition` se encuentra un objeto, se ejecutan las instrucciones inmediatamente después del objeto asociado `ElseIf` . Si no `elseifcondition` se evalúa como `True` , o si no hay ninguna `ElseIf` instrucción, `Else` se ejecutan las instrucciones siguientes. Después de ejecutar las instrucciones que `Then` siguen `ElseIf` a, o `Else` , la ejecución continúa con la instrucción que sigue a `End If` .

Las `ElseIf` `Else` cláusulas y son opcionales. Puede tener tantas `ElseIf` cláusulas como desee en `If` ... `Then` ...`Else` , pero no `ElseIf` puede aparecer una cláusula después de una `Else` cláusula. `If`...`Then` ...`Else` las instrucciones se pueden anidar unas dentro de otras.

En la sintaxis de varias líneas, la `If` instrucción debe ser la única instrucción en la primera línea. Las `ElseIf` `Else` instrucciones, y `End If` solo pueden ir precedidas de una etiqueta de línea. `If`... `Then` ...`Else` el bloque debe terminar con una `End If` instrucción.

> [!TIP]
> La [selección... La instrucción Case](select-case-statement.md) podría ser más útil cuando se evalúa una expresión única que tiene varios valores posibles.

### <a name="single-line-syntax"></a>Sintaxis de una sola línea

Puede usar la sintaxis de una sola línea para una única condición con el código que se ejecutará si es true. Sin embargo, la sintaxis de varias líneas proporciona más estructura y flexibilidad y es más fácil de leer, mantener y depurar.

Lo que sigue `Then` a la palabra clave se examina para determinar si una instrucción es una sola línea `If` . Si aparece cualquier cosa que no sea un comentario después `Then` de en la misma línea, la instrucción se trata como una instrucción de una sola línea `If` . Si `Then` no está presente, debe ser el inicio de una `If` ... `Then` ...`Else`.

En la sintaxis de una sola línea, se pueden ejecutar varias instrucciones como resultado de una `If` decisión... `Then` . Todas las instrucciones deben estar en la misma línea y deben estar separadas por dos puntos.

## <a name="multiline-syntax-example"></a>Ejemplo de sintaxis de varias líneas

<a name="multi-line"></a>

En el ejemplo siguiente se muestra el uso de la sintaxis de varias líneas de `If` ... `Then` ...`Else` privacidad.

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a>Ejemplo de sintaxis anidada

<a name="nested"></a>

El ejemplo siguiente contiene anidado `If` ... `Then` ...`Else` afirma.

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a>Ejemplo de sintaxis de una sola línea

<a name="single-line"></a>En el ejemplo siguiente se muestra el uso de la sintaxis de una sola línea.

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [#If...Then...#Else (directivas)](../directives/if-then-else-directives.md)
- [Instrucción Select...Case](select-case-statement.md)
- [Estructuras de control anidadas](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [Estructuras de decisión](../../programming-guide/language-features/control-flow/decision-structures.md)
- [Operadores lógicos y bit a bit en Visual Basic](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Operador If](../operators/if-operator.md)
