---
title: Operador &amp;= (Referencia de C#)
ms.date: 10/29/2018
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
ms.openlocfilehash: 8ce27c999cf21a9059ba23ee3c86b8fa024c7341
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2018
ms.locfileid: "50980614"
---
# <a name="amp-operator-c-reference"></a>Operador &amp;= (Referencia de C#)

El operador de asignación AND.

Una expresión que usa el operador `&=`, como

```csharp
x &= y
```

es equivalente a

```csharp
x = x & y
```

salvo que `x` solo se evalúa una vez.

Para los operandos enteros, el [operador `&`](and-operator.md) calcula el AND lógico bit a bit de sus operandos; para los operandos [bool](../keywords/bool.md), calcula el AND lógico de sus operandos.

En el siguiente ejemplo se muestra el uso del operador `&=`:

[!code-csharp-interactive[AND assignment example](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#AndAssignmentExample)]

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Si un tipo definido por el usuario [sobrecarga](../keywords/operator.md) el [operador `&`](and-operator.md), el operador de asignación AND `&=` se sobrecarga de forma implícita. Un tipo definido por el usuario no puede sobrecargar de forma implícita el operador de asignación AND.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Asignación compuesta](~/_csharplang/spec/expressions.md#compound-assignment) de la [Especificación del lenguaje C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
