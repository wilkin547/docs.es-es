---
title: 'Operador *=: Referencia de C#'
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 70461f79e714e44354fe4137e5360769fa048d3e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967391"
---
# <a name="-operator-c-reference"></a>Operador \*= (Referencia de C#)

Operador de asignación de multiplicación.

Una expresión que usa el operador `*=`, como

```csharp
x *= y
```

es equivalente a

```csharp
x = x * y
```

salvo que `x` solo se evalúa una vez.

Para tipos numéricos, el [operador \*](multiplication-operator.md) calcula la suma de sus operandos.

En el siguiente ejemplo se muestra el uso del operador `*=`:

[!code-csharp-interactive[multiply and assign](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#MultiplyAndAssign)]

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Si un tipo definido por el usuario [sobrecarga](../keywords/operator.md) el [operador de multiplicación](multiplication-operator.md) `*`, el operador de asignación de multiplicación `*=` se sobrecarga implícitamente. Un tipo definido por el usuario no puede sobrecargar de forma implícita el operador de asignación de multiplicación.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Asignación compuesta](~/_csharplang/spec/expressions.md#compound-assignment) de la [Especificación del lenguaje C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
