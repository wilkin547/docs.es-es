---
title: '?? operador: Referencia de C#'
ms.custom: seodec18
ms.date: 06/07/2019
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 8ca97261b348b7813ab179abbc1f2c5f535966a1
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816008"
---
# <a name="-operator-c-reference"></a>?? operator (Referencia de C#)

El operador de uso combinado de NULL `??` devuelve el valor del operando izquierdo si no es `null`; en caso contrario, evalúa el operando derecho y devuelve su resultado. El operador `??` no evalúa su operando derecho si el operando izquierdo se evalúa como no NULL.

El operador de uso combinado de NULL es asociativo a la derecha, es decir, una expresión de la forma.

```csharp
a ?? b ?? c
```

se evalúa como

```csharp
a ?? (b ?? c)
```

El operador `??` puede resultar útil en los siguientes escenarios:

- En expresiones con los [operadores no condicionales ? y ?[]](member-access-operators.md#null-conditional-operators--and-), puede usar el operador de uso combinado de NULL para proporcionar una expresión alternativa para evaluar en caso de que el resultado de la expresión con la operación condicional NULL sea `null`:

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- Cuando trabaja con [tipos de valor que aceptan valores NULL](../../programming-guide/nullable-types/index.md) y necesita proporcionar un valor de un tipo de valor subyacente, use el operador de uso combinado de NULL para especificar el valor para proporcionar en caso de que un valor de tipo que acepta valores NULL sea `null`:

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  Use el método <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> si el valor que se va usar cuando un valor de tipo que acepta valores NULL es `null` debe ser el valor predeterminado del tipo de valor subyacente.

- A partir de C# 7.0, puede usar una [expresión `throw`](../keywords/throw.md#the-throw-expression) como el operando derecho del operador de uso combinado de NULL para hacer el código de comprobación de argumentos más conciso:

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  El ejemplo anterior también muestra cómo usar [miembros con forma de expresión](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) para definir una propiedad.

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

El operador de uso combinado de NULL no se puede sobrecargar.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [El operador de uso combinado de NULL](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- [Operadores ?. y ?[]](member-access-operators.md#null-conditional-operators--and-)
- [Operador ?:](conditional-operator.md)
