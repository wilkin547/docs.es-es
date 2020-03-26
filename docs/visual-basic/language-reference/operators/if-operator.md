---
title: Operador If
ms.date: 07/20/2015
f1_keywords:
- vb.IfOperator
- IfOperator
helpviewer_keywords:
- ternary operators [Visual Basic]
- conditional execution
- If expressions [Visual Basic]
- conditional operator [Visual Basic]
- If Operator [Visual Basic]
ms.assetid: dd56c9df-7cd4-442c-9ba6-20c70ee44c8f
ms.openlocfilehash: 3b45a5afe331bd00c2b92f8c305351b77bc319cf
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249492"
---
# <a name="if-operator-visual-basic"></a>If (Operador) (Visual Basic)

Utiliza la evaluación de cortocircuito para devolver condicionalmente uno de dos valores. Se `If` puede llamar al operador con tres argumentos o con dos argumentos.

## <a name="syntax"></a>Sintaxis

```vb
If( [argument1,] argument2, argument3 )
```

## <a name="if-operator-called-with-three-arguments"></a>Si el operador llamó con tres argumentos

Cuando `If` se llama mediante tres argumentos, el primer argumento debe evaluarse como un valor que se puede convertir como un `Boolean`archivo . Ese `Boolean` valor determinará cuál de los otros dos argumentos se evalúa y se devuelve. La lista siguiente solo `If` se aplica cuando se llama al operador mediante tres argumentos.

### <a name="parts"></a>Partes

|Término|Definición|
|---|---|
|`argument1`|Necesario. `Boolean`. Determina cuál de los otros argumentos se va a evaluar y devolver.|
|`argument2`|Necesario. `Object`. Evaluado y devuelto `argument1` si `True`se evalúa como .|
|`argument3`|Necesario. `Object`. Evaluado y devuelto `argument1` si `False` se `argument1` evalúa como o si es una variable [nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` que se evalúa como [Nothing](../../../visual-basic/language-reference/nothing.md).|

Un `If` operador al que se llama `IIf` con tres argumentos funciona como una función, excepto que utiliza la evaluación de cortocircuito. Una `IIf` función siempre evalúa los tres argumentos, mientras que un `If` operador que tiene tres argumentos evalúa solo dos de ellos. El `If` primer argumento se evalúa y el `Boolean` resultado `True` `False`se convierte como un valor, o . Si el `True`valor `argument2` es , se evalúa y `argument3` se devuelve su valor, pero no se evalúa. Si el valor `Boolean` de `False` `argument3` la expresión es , se `argument2` evalúa y se devuelve su valor, pero no se evalúa. Los siguientes ejemplos ilustran el uso de `If` cuando se utilizan tres argumentos:

[!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]

En el ejemplo siguiente se muestra el valor de la evaluación de cortocircuitos. El ejemplo muestra dos `number` intentos `divisor` de `divisor` dividir variable por variable excepto cuando es cero. En ese caso, se debe devolver un 0 y no se debe intentar realizar la división porque se produciría un error en tiempo de ejecución. Dado `If` que la expresión utiliza la evaluación de cortocircuito, evalúa el segundo o el tercer argumento, dependiendo del valor del primer argumento. Si el primer argumento es true, el divisor no es cero y es seguro evaluar el segundo argumento y realizar la división. Si el primer argumento es false, solo se evalúa el tercer argumento y se devuelve un 0. Por lo tanto, cuando el divisor es 0, no se intenta realizar la división y no se produce ningún error. Sin `IIf` embargo, dado que no utiliza la evaluación de cortocircuito, el segundo argumento se evalúa incluso cuando el primer argumento es false. Esto provoca un error de división por cero en tiempo de ejecución.

[!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]

## <a name="if-operator-called-with-two-arguments"></a>Si operador llamó con dos argumentos

Se puede `If` omitir el primer argumento que se puede omitir. Esto permite llamar al operador mediante el uso de solo dos argumentos. La lista siguiente solo `If` se aplica cuando se llama al operador con dos argumentos.

### <a name="parts"></a>Partes

|Término|Definición|
|---|---|
|`argument2`|Necesario. `Object`. Debe ser un tipo de valor de referencia o que acepta valores NULL. Evaluado y devuelto cuando se evalúa `Nothing`como algo distinto de .|
|`argument3`|Necesario. `Object`. Evaluado y devuelto `argument2` si `Nothing`se evalúa como .|

Cuando `Boolean` se omite el argumento, el primer argumento debe ser una referencia o un tipo de valor que acepta valores NULL. Si el primer argumento `Nothing`se evalúa como , se devuelve el valor del segundo argumento. En todos los demás casos, se devuelve el valor del primer argumento. En el ejemplo siguiente se muestra cómo funciona esta evaluación:

[!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [Tipos de valores que aceptan valores NULL](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Nothing](../nothing.md)
