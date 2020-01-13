---
title: 'Operadores de asignación: referencia de C#'
ms.date: 09/10/2019
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 19f74e6835ae555a3a38aa6ca8679948c7f290dd
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712759"
---
# <a name="assignment-operators-c-reference"></a>Operadores de asignación (referencia de C#)

El operador de asignación `=` asigna el valor de su operando de la derecha a una variable, una [propiedad](../../programming-guide/classes-and-structs/properties.md) o un elemento de [indizador](../../programming-guide/indexers/index.md) proporcionado por el operando de la izquierda. El resultado de una expresión de asignación es el valor asignado al operando izquierdo. El tipo del operando de la derecha debe ser el mismo que el del operando de la izquierda o debe poder convertirse implícitamente en él.

El operador de asignación `=` es asociativo a la derecha, es decir, una expresión con el formato

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

En el caso del operador de asignación de referencias, sus dos operandos deben ser del mismo tipo.

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

## <a name="null-coalescing-assignment"></a>Asignación de uso combinado de NULL

A partir de C# 8.0, puede usar el operador de asignación de uso combinado de NULL `??=` para asignar el valor de su operando derecho al operando izquierdo solo si el operando izquierdo se evalúa como `null`. Para obtener más información, consulte [Operadores ?? y ??](null-coalescing-operator.md).

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Un tipo definido por el usuario no puede [sobrecargar](operator-overloading.md) el operador de asignación. Sin embargo, un tipo definido por el usuario puede definir una conversión implícita a otro tipo. De este modo, el valor de un tipo definido por el usuario puede asignarse a una variable, una propiedad o un elemento de indizador de otro tipo. Para obtener más información, vea [Operadores de conversión definidos por el usuario](user-defined-conversion-operators.md).

Un tipo definido por el usuario no puede sobrecargar de forma explícita un operador de asignación compuesta. Pero si un tipo definido por el usuario sobrecarga un operador binario `op`, el operador `op=`, si existe, también se sobrecarga de forma implícita.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, consulte la sección sobre [operadores de asignación](~/_csharplang/spec/expressions.md#assignment-operators) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

Para más información sobre el operador de asignación de referencias `= ref`, vea la [nota de propuesta de características](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
- [ref (palabra clave)](../keywords/ref.md)
