---
title: 'Operador /=: Referencia de C#'
ms.custom: seodec18
ms.date: 12/13/2018
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: ed4dd6c0c944b77543aae4de8d51534b4df4f4ef
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286525"
---
# <a name="-operator-c-reference"></a>/= (operador) (Referencia de C#)

Operador de asignación y división.

Una expresión que usa el operador `/=`, como

```csharp
x /= y
```

es equivalente a

```csharp
x = x / y
```

salvo que `x` solo se evalúa una vez.

El [operador de división](division-operator.md) `/` divide su primer operando por su segundo operando. Es compatible con todos los tipos numéricos.

En el siguiente ejemplo se muestra el uso del operador `/=`:

[!code-csharp-interactive[divide and assign](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#DivisionAssignment)]

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Si un tipo definido por el usuario [sobrecarga](../keywords/operator.md) el [operador de división](division-operator.md) `/`, el operador de asignación de división `/=` se sobrecarga implícitamente. Un tipo definido por el usuario no puede sobrecargar de forma explícita el operador de asignación de división.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Asignación compuesta](~/_csharplang/spec/expressions.md#compound-assignment) de la [Especificación del lenguaje C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
