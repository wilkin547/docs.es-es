---
title: 'Operador =: referencia de C#'
ms.custom: seodec18
ms.date: 06/21/2019
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: ef9c9bab5c1cebb06edf934254507180e2197349
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306560"
---
# <a name="-operator-c-reference"></a>Operador = (referencia de C#)

El operador de asignación `=` asigna el valor de su operando de la derecha a una variable, una [propiedad](../../programming-guide/classes-and-structs/properties.md) o un elemento de [indizador](../../../csharp/programming-guide/indexers/index.md) proporcionado por el operando de la izquierda. El resultado de una expresión de asignación es el valor asignado al operando izquierdo. El tipo del operando de la derecha debe ser el mismo que el del operando de la izquierda o debe poder convertirse implícitamente en él.

El operador de asignación es asociativo a la derecha, es decir, una expresión de la forma

```csharp
a = b = c
```

se evalúa como

```csharp
a = (b = c)
```

En el ejemplo siguiente se muestra el uso del operador de asignación con una variable local, una propiedad y un elemento indexador como su operando izquierdo:

[!code-csharp-interactive[simple assignment](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#Simple)]

## <a name="ref-assignment-operator"></a>Operador de asignación ref

A partir C# 7.3, puede usar el operador de asignación ref `= ref` para reasignar una variable [local de tipo ref](../keywords/ref.md#ref-locals) o [local de tipo ref readonly](../keywords/ref.md#ref-readonly-locals). En el siguiente ejemplo se muestra el uso del operador de asignación ref:

[!code-csharp[ref assignment operator](~/samples/csharp/language-reference/operators/AssignmentOperator.cs#RefAssignment)]

En el caso del operador de asignación ref, el tipo de ambos operandos debe ser el mismo.

Para más información, vea la [nota de propuesta de características](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).

## <a name="compound-assignment"></a>Asignación compuesta

Para un operador binario `op`, una expresión de asignación compuesta con el formato

```csharp
x op= y
```

es equivalente a

```csharp
x = x op y
```

salvo que `x` solo se evalúa una vez.

La asignación compuesta es compatible con operadores [aritméticos](arithmetic-operators.md#compound-assignment), [lógicos booleanos](boolean-logical-operators.md#compound-assignment) y de [desplazamiento y lógicos bit a bit](bitwise-and-shift-operators.md#compound-assignment).

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Un tipo definido por el usuario no puede sobrecargar el operador de asignación. Sin embargo, un tipo definido por el usuario puede definir una conversión implícita a otro tipo. De este modo, el valor de un tipo definido por el usuario puede asignarse a una variable, una propiedad o un elemento de indizador de otro tipo. Para más información, consulte el artículo sobre la palabra clave [implicit](../keywords/implicit.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, consulte la sección sobre [operadores de asignación](~/_csharplang/spec/expressions.md#assignment-operators) de la [Especificación del lenguaje C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
- [ref (palabra clave)](../keywords/ref.md)
