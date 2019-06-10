---
title: Operador = - Referencia de C#
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 85182acb84ea79cb00a9edb315c3954f440305f4
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758355"
---
# <a name="-operator-c-reference"></a>Operador = (Referencia de C#)

El operador de asignación `=` asigna el valor de su operando de la derecha a una variable, una [propiedad](../../programming-guide/classes-and-structs/properties.md) o un elemento de [indizador](../../../csharp/programming-guide/indexers/index.md) proporcionado por el operando de la izquierda. El resultado de una expresión de asignación es el valor asignado al operando izquierdo. El tipo del operando de la derecha debe ser el mismo que el del operando de la izquierda o debe poder convertirse implícitamente en él.

El operador de asignación es asociativo a la derecha, es decir, una expresión de la forma

```csharp
a = b = c
```

se evalúa como

```csharp
a = (b = c)
```

El ejemplo siguiente muestra el uso del operador de asignación para asignar valores a una variable local, una propiedad y un elemento de indizador:

[!code-csharp-interactive[assignment operator](~/samples/csharp/language-reference/operators/AssignmentExamples.cs#Assignments)]

## <a name="ref-assignment-operator"></a>Operador de asignación ref

A partir C# 7.3, puede usar el operador de asignación ref `= ref` para reasignar una variable [local de tipo ref](../keywords/ref.md#ref-locals) o [local de tipo ref readonly](../keywords/ref.md#ref-readonly-locals). En el siguiente ejemplo se muestra el uso del operador de asignación ref:

[!code-csharp[ref assignment operator](~/samples/csharp/language-reference/operators/AssignmentExamples.cs#RefAssignment)]

En el caso del operador de asignación ref, el tipo del operando de la izquierda y el operando de la derecha debe ser los mismos.

Para más información, vea la [nota de propuesta de características](../../../../_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Un tipo definido por el usuario no puede sobrecargar el operador de asignación. Sin embargo, un tipo definido por el usuario puede definir una conversión implícita a otro tipo. De este modo, el valor de un tipo definido por el usuario puede asignarse a una variable, una propiedad o un elemento de indizador de otro tipo. Para más información, consulte el artículo sobre la palabra clave [implicit](../keywords/implicit.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea la sección [Asignación simple](~/_csharplang/spec/expressions.md#simple-assignment) de la [Especificación del lenguaje C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- [ref (palabra clave)](../keywords/ref.md)
