---
title: '>>Operador =:Referencia de C#'
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 51914bb5e9ebffd5d868528b5a8d3072a956cea6
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220918"
---
# <a name="-operator-c-reference"></a>Operador >>= (Referencia de C#)

Operador de asignación de desplazamiento a la derecha.

Una expresión que usa el operador `>>=`, como

```csharp
x >>= y
```

es equivalente a

```csharp
x = x >> y
```

salvo que `x` solo se evalúa una vez.

El [operador `>>`](right-shift-operator.md) desplaza su primer operando a la derecha el número de bits definido por su segundo operando.

En el siguiente ejemplo se muestra el uso del operador `>>=`:

[!code-csharp-interactive[right shift assignment](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShiftAssignment)]

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Si un tipo definido por el usuario [sobrecarga](../keywords/operator.md) el [operador `>>`](right-shift-operator.md), el operador de asignación de desplazamiento a la derecha `>>=` se sobrecarga de forma implícita. Un tipo definido por el usuario no puede sobrecargar de forma explícita el operador de asignación de desplazamiento a la derecha.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Asignación compuesta](~/_csharplang/spec/expressions.md#compound-assignment) de la [Especificación del lenguaje C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)