---
title: + Operadores + y += (referencia de C#)
ms.date: 05/24/2019
f1_keywords:
- +_CSharpKeyword
- +=_CSharpKeyword
helpviewer_keywords:
- addition operator [C#]
- concatenation operator [C#]
- delegate combination [C#]
- + operator [C#]
- addition assignment operator [C#]
- event subscription [C#]
- += operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: 0c468f0fe56c68a16de660dbb3bd6356b4b6a00f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712772"
---
# <a name="-and--operators-c-reference"></a>Operadores + y += (referencia de C#)

Los operadores `+` y `+=` son compatibles con los tipos numéricos [enteros](../builtin-types/integral-numeric-types.md) y de [punto flotante](../builtin-types/floating-point-numeric-types.md), el tipo [string](../builtin-types/reference-types.md#the-string-type) y los tipos [delegados](../builtin-types/reference-types.md#the-delegate-type).

Para obtener información acerca del operador aritmético `+`, consulte las secciones correspondientes a los [operadores unarios más y menos](arithmetic-operators.md#unary-plus-and-minus-operators) y al [operador de suma +](arithmetic-operators.md#addition-operator-) del artículo [Operadores aritméticos](arithmetic-operators.md).

## <a name="string-concatenation"></a>Concatenación de cadenas

Cuando uno o ambos operandos son de tipo [cadena](../builtin-types/reference-types.md#the-string-type), el operador `+` concatena las representaciones de cadena de sus operandos:

[!code-csharp-interactive[string concatenation](~/samples/csharp/language-reference/operators/AdditionOperator.cs#AddStrings)]

A partir de C# 6, la [interpolación de cadenas](../tokens/interpolated.md) proporciona una manera más conveniente de dar formato a las cadenas:

[!code-csharp-interactive[string interpolation](~/samples/csharp/language-reference/operators/AdditionOperator.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a>Combinación de delegados

Para los operandos del mismo tipo de [delegado](../builtin-types/reference-types.md#the-delegate-type), el operador `+` devuelve una nueva instancia de delegado que, cuando se invoca, invoca el operando de la izquierda y luego invoca el operando de la derecha. Si alguno de los operandos es `null`, el operador `+` devuelve el valor del otro operando (que también podría ser `null`). El ejemplo siguiente muestra cómo los delegados se pueden combinar con el operador `+`:

[!code-csharp-interactive[delegate combination](~/samples/csharp/language-reference/operators/AdditionOperator.cs#AddDelegates)]

Para llevar a cabo la eliminación de delegados, utilice el [operador `-`](subtraction-operator.md#delegate-removal).

Para más información sobre los tipos de delegado, vea [Delegados](../../programming-guide/delegates/index.md).

## <a name="addition-assignment-operator-"></a>Operador de asignación y suma +=

Una expresión que usa el operador `+=`, como

```csharp
x += y
```

es equivalente a

```csharp
x = x + y
```

salvo que `x` solo se evalúa una vez.

En el siguiente ejemplo se muestra el uso del operador `+=`:

[!code-csharp-interactive[+= examples](~/samples/csharp/language-reference/operators/AdditionOperator.cs#AddAndAssign)]

También usa el operador `+=` para especificar un método de controlador de eventos cuando se suscribe a un [evento](../keywords/event.md). Para obtener más información, vea [Procedimientos para suscribir y cancelar la suscripción a eventos](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Un tipo definido por el usuario puede [sobrecargar](operator-overloading.md) el operador `+`. Cuando se sobrecarga un operador `+` binario, el operador `+=` también se sobrecarga de modo implícito. Un tipo definido por el usuario no puede sobrecargar de forma explícita el operador `+=`.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, consulte las secciones [Operador unario más](~/_csharplang/spec/expressions.md#unary-plus-operator) y [Operador de suma](~/_csharplang/spec/expressions.md#addition-operator) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
- [Concatenación de varias cadenas](../../how-to/concatenate-multiple-strings.md)
- [Eventos](../../programming-guide/events/index.md)
- [Operadores aritméticos](arithmetic-operators.md)
- [Operadores - y -=](subtraction-operator.md)
