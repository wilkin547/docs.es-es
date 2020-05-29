---
title: Sobrecarga de operadores - Referencia de C#
description: Obtenga información sobre cómo sobrecargar un operador de C# y qué operadores de C# se pueden sobrecargar.
ms.date: 07/05/2019
f1_keywords:
- operator_CSharpKeyword
helpviewer_keywords:
- operator keyword [C#]
- operator overloading [C#]
ms.openlocfilehash: 29ae9fcec414af988019463a51c964d46b009534
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378915"
---
# <a name="operator-overloading-c-reference"></a>Sobrecarga de operadores (referencia de C#)

Un tipo definido por el usuario puede sobrecargar un operador de C# predefinido. Es decir, un tipo puede proporcionar la implementación personalizada de una operación cuando uno o los dos operandos son de ese tipo. En la sección [Operadores sobrecargables](#overloadable-operators) se muestra qué operadores de C# pueden sobrecargarse.

Use la palabra clave `operator` para declarar un operador. Una declaración de operador debe cumplir las reglas siguientes:

- Incluye los modificadores `public` y `static`.
- Un operador unario tiene un parámetro de entrada. Un operador binario tiene dos parámetros de entrada. En cada caso, al menos un parámetro debe ser de tipo `T` o `T?` donde `T` es el tipo que contiene la declaración del operador.

En el ejemplo siguiente se muestra una estructura simplificada para representar un número racional. La estructura sobrecarga algunos de los [operadores aritméticos](arithmetic-operators.md):

[!code-csharp[fraction example](snippets/OperatorOverloading.cs)]

Puede ampliar el ejemplo anterior mediante la [definición de una conversión implícita](user-defined-conversion-operators.md) de `int` a `Fraction`. A continuación, los operadores sobrecargados admiten argumentos de esos dos tipos. Es decir, sería posible agregar un valor entero a una fracción y obtener como resultado una fracción.

También usa la palabra clave `operator` para definir una conversión de tipos personalizada. Para obtener más información, vea [Operadores de conversión definidos por el usuario](user-defined-conversion-operators.md).

## <a name="overloadable-operators"></a>Operadores sobrecargables

En la tabla siguiente se proporciona información sobre la posibilidad de sobrecarga de los operadores de C#:

| Operadores | Posibilidad de sobrecarga |
| --------- | --------------- |
|[+x](arithmetic-operators.md#unary-plus-and-minus-operators), [-x](arithmetic-operators.md#unary-plus-and-minus-operators), [!x](boolean-logical-operators.md#logical-negation-operator-), [~x](bitwise-and-shift-operators.md#bitwise-complement-operator-), [++](arithmetic-operators.md#increment-operator-), [--](arithmetic-operators.md#decrement-operator---), [true](true-false-operators.md), [false](true-false-operators.md)|Estos operadores unarios se pueden sobrecargar.|
|[x + y](addition-operator.md), [x - y](subtraction-operator.md), [x \* y](arithmetic-operators.md#multiplication-operator-), [x / y](arithmetic-operators.md#division-operator-), [x % y](arithmetic-operators.md#remainder-operator-), [x & y](boolean-logical-operators.md#logical-and-operator-), [x &#124; y](boolean-logical-operators.md#logical-or-operator-), [x ^ y](boolean-logical-operators.md#logical-exclusive-or-operator-), [x \<\< y](bitwise-and-shift-operators.md#left-shift-operator-), [x >> y](bitwise-and-shift-operators.md#right-shift-operator-), [x == y](equality-operators.md#equality-operator-), [x != y](equality-operators.md#inequality-operator-), [x \< y](comparison-operators.md#less-than-operator-), [x > y](comparison-operators.md#greater-than-operator-), [x \<= y](comparison-operators.md#less-than-or-equal-operator-), [x >= y](comparison-operators.md#greater-than-or-equal-operator-)|Estos operadores binarios se pueden sobrecargar. Determinados operadores deben sobrecargarse en pares; para obtener más información, vea la nota que está a continuación de esta tabla.|
|[x && y](boolean-logical-operators.md#conditional-logical-and-operator-), [x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-)|No se pueden sobrecargar los operadores lógicos condicionales. Sin embargo, si un tipo con [los operadores `true` y `false`](true-false-operators.md) sobrecargados, también sobrecarga el operador `&` o <code>&#124;</code> de determinada manera, el operador `&&` o <code>&#124;&#124;</code>, respectivamente, se puede evaluar para los operandos de ese tipo. Para obtener más información, vea la sección [Operadores lógicos condicionales definidos por el usuario](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).|
|[a&#91;i&#93;](member-access-operators.md#indexer-operator-), [`a?[i]`](member-access-operators.md#null-conditional-operators--and-)|El acceso a un elemento no se considera un operador sobrecargable, pero puede definir un [indizador](../../programming-guide/indexers/index.md).|
|[(T)x](type-testing-and-cast.md#cast-expression)|No se puede sobrecargar el operador de conversión, pero pueden definirse conversiones de tipos personalizadas que pueden realizarse mediante una expresión de conversión. Para obtener más información, vea [Operadores de conversión definidos por el usuario](user-defined-conversion-operators.md).|
|[+=](arithmetic-operators.md#compound-assignment), [-=](arithmetic-operators.md#compound-assignment), [\*=](arithmetic-operators.md#compound-assignment), [/=](arithmetic-operators.md#compound-assignment), [%=](arithmetic-operators.md#compound-assignment), [&=](boolean-logical-operators.md#compound-assignment), [&#124;=](boolean-logical-operators.md#compound-assignment), [^=](boolean-logical-operators.md#compound-assignment), [\<\<=](bitwise-and-shift-operators.md#compound-assignment), [>>=](bitwise-and-shift-operators.md#compound-assignment)|Los operadores de asignación compuestos no pueden sobrecargarse explícitamente. Pero cuando se sobrecarga un operador binario, el operador de asignación compuesto correspondiente, si lo hay, también se sobrecarga de modo implícito. Por ejemplo, `+=` se evalúa con `+`, que se pueden sobrecargar.|
|[^x](member-access-operators.md#index-from-end-operator-), [x = y](assignment-operator.md), [x.y](member-access-operators.md#member-access-expression-), [`x?.y`](member-access-operators.md#null-conditional-operators--and-), [c ? t : f](conditional-operator.md), [x ?? y](null-coalescing-operator.md), [x ??= y](null-coalescing-operator.md), [x..y](member-access-operators.md#range-operator-), [x->y](pointer-related-operators.md#pointer-member-access-operator--), [=>](lambda-operator.md), [f(x)](member-access-operators.md#invocation-expression-), [as](type-testing-and-cast.md#as-operator), [await](await.md), [checked](../keywords/checked.md), [unchecked](../keywords/unchecked.md), [default](default.md), [delegate](delegate-operator.md), [is](type-testing-and-cast.md#is-operator), [nameof](nameof.md), [new](new-operator.md), [sizeof](sizeof.md), [stackalloc](stackalloc.md), [typeof](type-testing-and-cast.md#typeof-operator)|Estos operadores no se pueden sobrecargar.|

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
- [Directrices de diseño: sobrecargas de operador](../../../standard/design-guidelines/operator-overloads.md)
- [Directrices de diseño: operadores de igualdad](../../../standard/design-guidelines/equality-operators.md)
- [Why are overloaded operators always static in C#?](https://docs.microsoft.com/archive/blogs/ericlippert/why-are-overloaded-operators-always-static-in-c) (¿Por qué los operadores sobrecargados son siempre estáticos en C#?)
