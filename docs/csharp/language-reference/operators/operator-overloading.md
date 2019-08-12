---
title: Sobrecarga de operadores - Referencia de C#
description: Obtenga información sobre cómo sobrecargar un operador de C# y qué operadores de C# se pueden sobrecargar.
ms.date: 07/05/2019
f1_keywords:
- operator_CSharpKeyword
helpviewer_keywords:
- operator keyword [C#]
- operator overloading [C#]
ms.openlocfilehash: da1e47d7ebdf91084d94fc895f0ce46d773353d7
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796569"
---
# <a name="operator-overloading-c-reference"></a>Sobrecarga de operadores (referencia de C#)

Un tipo definido por el usuario puede sobrecargar un operador de C# predefinido. Es decir, un tipo puede proporcionar la implementación personalizada de una operación cuando uno o ambos operados son de ese tipo. En la sección [Operadores sobrecargables](#overloadable-operators) se muestra qué operadores de C# pueden sobrecargarse.

Use la palabra clave `operator` para declarar un operador. Una declaración de operador debe cumplir las reglas siguientes:

- Incluye los modificadores `public` y `static`.
- Un operador unario toma un parámetro. Un operador binario toma dos parámetros. En cada caso, al menos un parámetro debe ser de tipo `T` o `T?` donde `T` es el tipo que contiene la declaración del operador.

En el ejemplo siguiente se muestra una estructura simplificada para representar un número racional. La estructura sobrecarga algunos de los [operadores aritméticos](arithmetic-operators.md):

[!code-csharp[fraction example](~/samples/csharp/language-reference/operators/OperatorOverloading.cs)]

Puede ampliar el ejemplo anterior mediante la definición de una conversión implícita de `int` a `Fraction`. A continuación, los operadores sobrecargados admiten argumentos de esos dos tipos. Es decir, sería posible agregar un valor entero a una fracción y obtener como resultado una fracción.

También usa la palabra clave `operator` para definir una conversión de tipos personalizada. Para obtener más información, vea [Operadores de conversión definidos por el usuario](user-defined-conversion-operators.md).

## <a name="overloadable-operators"></a>Operadores sobrecargables

En la tabla siguiente se proporciona información sobre la posibilidad de sobrecarga de los operadores de C#:

| Operadores | Posibilidad de sobrecarga |
| --------- | --------------- |
|[+](arithmetic-operators.md#unary-plus-and-minus-operators), [-](arithmetic-operators.md#unary-plus-and-minus-operators), [!](boolean-logical-operators.md#logical-negation-operator-), [~](bitwise-and-shift-operators.md#bitwise-complement-operator-), [++](arithmetic-operators.md#increment-operator-), [--](arithmetic-operators.md#decrement-operator---), [true](true-false-operators.md), [false](true-false-operators.md)|Estos operadores unarios se pueden sobrecargar.|
|[+](addition-operator.md), [-](subtraction-operator.md), [\*](arithmetic-operators.md#multiplication-operator-), [/](arithmetic-operators.md#division-operator-), [%](arithmetic-operators.md#remainder-operator-), [&](boolean-logical-operators.md#logical-and-operator-), [&#124;](boolean-logical-operators.md#logical-or-operator-), [^](boolean-logical-operators.md#logical-exclusive-or-operator-), [\<\<](bitwise-and-shift-operators.md#left-shift-operator-), [>>](bitwise-and-shift-operators.md#right-shift-operator-), [==](equality-operators.md#equality-operator-), [!=](equality-operators.md#inequality-operator-), [\<](comparison-operators.md#less-than-operator-), [>](comparison-operators.md#greater-than-operator-), [\<=](comparison-operators.md#less-than-or-equal-operator-), [>=](comparison-operators.md#greater-than-or-equal-operator-)|Estos operadores binarios se pueden sobrecargar. Determinados operadores deben sobrecargarse en pares; para obtener más información, vea la nota que está a continuación de esta tabla.|
|[&&](boolean-logical-operators.md#conditional-logical-and-operator-), [&#124;&#124;](boolean-logical-operators.md#conditional-logical-or-operator-)|No se pueden sobrecargar los operadores lógicos condicionales. Sin embargo, si un tipo con [los operadores `true` y `false`](true-false-operators.md) sobrecargados, también sobrecarga el operador `&` o <code>&#124;</code> de determinada manera, el operador `&&` o <code>&#124;&#124;</code>, respectivamente, se puede evaluar para los operandos de ese tipo. Para obtener más información, vea la sección [Operadores lógicos condicionales definidos por el usuario](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).|
|[&#91;&#93;](member-access-operators.md#indexer-operator-)|El acceso a un elemento no se considera un operador sobrecargable, pero puede definir un [indizador](../../programming-guide/indexers/index.md).|
|[(T)x](type-testing-and-conversion-operators.md#cast-operator-)|El operador de conversión no se puede sobrecargar, pero es posible definir operadores de conversión nuevos. Para obtener más información, vea [Operadores de conversión definidos por el usuario](user-defined-conversion-operators.md).|
|[+=](arithmetic-operators.md#compound-assignment), [-=](arithmetic-operators.md#compound-assignment), [\*=](arithmetic-operators.md#compound-assignment), [/=](arithmetic-operators.md#compound-assignment), [%=](arithmetic-operators.md#compound-assignment), [&=](boolean-logical-operators.md#compound-assignment), [&#124;=](boolean-logical-operators.md#compound-assignment), [^=](boolean-logical-operators.md#compound-assignment), [\<\<=](bitwise-and-shift-operators.md#compound-assignment), [>>=](bitwise-and-shift-operators.md#compound-assignment)|Los operadores de asignación compuestos no pueden sobrecargarse explícitamente. Pero cuando se sobrecarga un operador binario, el operador de asignación compuesto correspondiente, si lo hay, también se sobrecarga de modo implícito. Por ejemplo, `+=` se evalúa con `+`, que se pueden sobrecargar.|
|[=](assignment-operator.md), [.](member-access-operators.md#member-access-operator-), [?:](conditional-operator.md), [??](null-coalescing-operator.md), [->](pointer-related-operators.md#pointer-member-access-operator--), [=>](lambda-operator.md), [f(x)](member-access-operators.md#invocation-operator-), [as](type-testing-and-conversion-operators.md#as-operator), [checked](../keywords/checked.md), [unchecked](../keywords/unchecked.md), [default](default.md), [delegate](delegate-operator.md), [is](type-testing-and-conversion-operators.md#is-operator), [nameof](nameof.md), [new](new-operator.md), [sizeof](sizeof.md), [stackalloc](stackalloc.md), [typeof](type-testing-and-conversion-operators.md#typeof-operator)|Estos operadores no se pueden sobrecargar.|

> [!NOTE]
> Los operadores de comparación deben sobrecargarse en pares. Es decir, si se sobrecarga un operador de un par, el otro operador debe sobrecargarse también. Se emparejan de la siguiente manera:
>
> - Operadores `==` y `!=`
> - Operadores `<` y `>`
> - Operadores `<=` y `>=`

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):

- [Sobrecarga de operadores](~/_csharplang/spec/expressions.md#operator-overloading)
- [Operadores](~/_csharplang/spec/classes.md#operators)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
- [Operadores de conversión definidos por el usuario](user-defined-conversion-operators.md)
- [Why are overloaded operators always static in C#?](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/) (¿Por qué los operadores sobrecargados son siempre estáticos en C#?)
