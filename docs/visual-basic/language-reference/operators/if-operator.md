---
description: 'Más información acerca de: operador if (Visual Basic)'
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
ms.openlocfilehash: 3b25ab4b6c5f0d2608644adb6e35ff4ad5128f42
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665879"
---
# <a name="if-operator-visual-basic"></a>If (Operador) (Visual Basic)

Usa la evaluación de cortocircuito para devolver condicionalmente uno de dos valores. `If`Se puede llamar al operador con tres argumentos o con dos argumentos.

## <a name="syntax"></a>Sintaxis

```vb
If( [argument1,] argument2, argument3 )
```

## <a name="if-operator-called-with-three-arguments"></a>Operador if llamado con tres argumentos

Cuando `If` se llama a con tres argumentos, el primer argumento debe evaluarse como un valor que se pueda convertir en `Boolean` . Ese `Boolean` valor determinará cuál de los otros dos argumentos se evalúa y se devuelve. La lista siguiente solo se aplica cuando `If` se llama al operador con tres argumentos.

### <a name="parts"></a>Partes

|Término|Definición|
|---|---|
|`argument1`|Obligatorio. `Boolean`. Determina cuál de los otros argumentos que se evaluarán y devolverán.|
|`argument2`|Obligatorio. `Object`. Se evalúa y se devuelve si `argument1` se evalúa como `True` .|
|`argument3`|Obligatorio. `Object`. Se evalúa y devuelve si `argument1` se evalúa como `False` o si `argument1` es una variable que [acepta valores NULL](../../programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` que se evalúa como [Nothing](../nothing.md).|

Un `If` operador que se llama con tres argumentos funciona como una `IIf` función, salvo que usa la evaluación de cortocircuito. Una `IIf` función siempre evalúa los tres argumentos, mientras que un `If` operador que tiene tres argumentos solo evalúa dos de ellos. `If`Se evalúa el primer argumento y el resultado se convierte en un `Boolean` valor `True` o `False` . Si el valor es `True` , `argument2` se evalúa y se devuelve su valor, pero `argument3` no se evalúa. Si el valor de la `Boolean` expresión es `False` , `argument3` se evalúa y se devuelve su valor, pero `argument2` no se evalúa. En los siguientes ejemplos se muestra el uso de `If` cuando se usan tres argumentos:

[!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]

En el ejemplo siguiente se muestra el valor de la evaluación de cortocircuito. En el ejemplo se muestran dos intentos de dividir variables `number` por variable `divisor` excepto cuando `divisor` es cero. En ese caso, se debe devolver un 0 y no se debe realizar ningún intento para realizar la división porque se produciría un error en tiempo de ejecución. Dado `If` que la expresión utiliza una evaluación de cortocircuito, evalúa el segundo o el tercer argumento, en función del valor del primer argumento. Si el primer argumento es true, el divisor no es cero y es seguro evaluar el segundo argumento y realizar la división. Si el primer argumento es false, solo se evalúa el tercer argumento y se devuelve 0. Por lo tanto, cuando el divisor es 0, no se realiza ningún intento de realizar la división y no se producen resultados de error. Sin embargo, dado `IIf` que no usa la evaluación de cortocircuito, el segundo argumento se evalúa incluso cuando el primer argumento es false. Esto produce un error de división por cero en tiempo de ejecución.

[!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]

## <a name="if-operator-called-with-two-arguments"></a>Operador if llamado con dos argumentos

`If`Se puede omitir el primer argumento de. Esto permite llamar al operador usando solo dos argumentos. La lista siguiente solo se aplica cuando `If` se llama al operador con dos argumentos.

### <a name="parts"></a>Partes

|Término|Definición|
|---|---|
|`argument2`|Obligatorio. `Object`. Debe ser un tipo de valor que acepte valores NULL o de referencia. Se evalúa y se devuelve cuando se evalúa como un valor distinto de `Nothing` .|
|`argument3`|Obligatorio. `Object`. Se evalúa y se devuelve si `argument2` se evalúa como `Nothing` .|

Cuando `Boolean` se omite el argumento, el primer argumento debe ser una referencia o un tipo de valor que acepte valores NULL. Si el primer argumento se evalúa como `Nothing` , se devuelve el valor del segundo argumento. En todos los demás casos, se devuelve el valor del primer argumento. En el ejemplo siguiente se muestra cómo funciona esta evaluación:

[!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [Tipos de valor que aceptan valores NULL](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Nothing](../nothing.md)
