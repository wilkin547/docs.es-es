---
title: 'Operadores sobrecargables: Guía de programación de C#'
ms.custom: seodec18
ms.date: 08/27/2018
helpviewer_keywords:
- C# language, operator overloading
- operator overloading [C#]
ms.assetid: 390d9d01-79fc-40ab-9ed3-0bf448da1b6a
ms.openlocfilehash: d0a5555bbe68aa82218c1dbe3d24705b26aff9c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59296581"
---
# <a name="overloadable-operators-c-programming-guide"></a>Operadores sobrecargables (Guía de programación de C#)

C# permite que los tipos definidos por el usuario sobrecarguen operadores al definir funciones miembro estáticas mediante la palabra clave [operator](../../language-reference/keywords/operator.md). Sin embargo, no todos los operadores se pueden sobrecargar y algunos presentan restricciones, como se muestra en esta tabla:

| Operadores | Posibilidad de sobrecarga |
| --------- | --------------- |
|[+](../../language-reference/operators/addition-operator.md), [-](../../language-reference/operators/subtraction-operator.md), [!](../../language-reference/operators/boolean-logical-operators.md#logical-negation-operator-), [~](../../language-reference/operators/bitwise-complement-operator.md), [++](../../language-reference/operators/arithmetic-operators.md#increment-operator-), [--](../../language-reference/operators/arithmetic-operators.md#decrement-operator---), [true](../../language-reference/keywords/true-false-operators.md), [false](../../language-reference/keywords/true-false-operators.md)|Estos operadores unarios se pueden sobrecargar.|
|[+](../../language-reference/operators/addition-operator.md), [-](../../language-reference/operators/subtraction-operator.md), [\*](../../language-reference/operators/arithmetic-operators.md#multiplication-operator-), [/](../../language-reference/operators/arithmetic-operators.md#division-operator-), [%](../../language-reference/operators/arithmetic-operators.md#remainder-operator-), [&](../../language-reference/operators/and-operator.md), [&#124;](../../language-reference/operators/or-operator.md), [^](../../language-reference/operators/xor-operator.md), [\<\<](../../language-reference/operators/left-shift-operator.md), [>>](../../language-reference/operators/right-shift-operator.md)|Estos operadores binarios se pueden sobrecargar.|
|[==](../../language-reference/operators/equality-operators.md#equality-operator-), [!=](../../language-reference/operators/equality-operators.md#inequality-operator-), [\<](../../language-reference/operators/less-than-operator.md), [>](../../language-reference/operators/greater-than-operator.md), [\<=](../../language-reference/operators/less-than-equal-operator.md), [>=](../../language-reference/operators/greater-than-equal-operator.md)|Los operadores de comparación se pueden sobrecargar (pero consulte la nota que aparece a continuación de la tabla).|
|[&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-), [&#124;&#124;](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-)|Los operadores lógicos condicionales no se pueden sobrecargar, pero se evalúan mediante `&` y <code>&#124;</code>, que se pueden sobrecargar.|
|[&#91;&#93;](../../language-reference/operators/index-operator.md)|El operador de indexación de matriz no se puede sobrecargar, pero es posible definir [indexadores](../indexers/index.md).|
|[(T)x](../../language-reference/operators/invocation-operator.md)|El operador de conversión no se puede sobrecargar, pero es posible definir operadores de conversión nuevos (vea [explicit](../../language-reference/keywords/explicit.md) e [implicit](../../language-reference/keywords/implicit.md)).|
|[+=](../../language-reference/operators/addition-assignment-operator.md), [-=](../../language-reference/operators/subtraction-assignment-operator.md), [\*=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [/=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [%=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [&=](../../language-reference/operators/and-assignment-operator.md), [&#124;=](../../language-reference/operators/or-assignment-operator.md), [^=](../../language-reference/operators/xor-assignment-operator.md), [\<\<=](../../language-reference/operators/left-shift-assignment-operator.md), [>>=](../../language-reference/operators/right-shift-assignment-operator.md)|Los operadores de asignación no pueden sobrecargarse explícitamente. Pero cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito. Por ejemplo, `+=` se evalúa con `+`, que se pueden sobrecargar.|
|[=](../../language-reference/operators/assignment-operator.md), [.](../../language-reference/operators/member-access-operator.md), [?:](../../language-reference/operators/conditional-operator.md), [??](../../language-reference/operators/null-coalescing-operator.md), [->](../../language-reference/operators/dereference-operator.md), [=>](../../language-reference/operators/lambda-operator.md), [f(x)](../../language-reference/operators/invocation-operator.md), [as](../../language-reference/keywords/as.md), [checked](../../language-reference/keywords/checked.md), [unchecked](../../language-reference/keywords/unchecked.md), [default](../../programming-guide/statements-expressions-operators/default-value-expressions.md), [delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md), [is](../../language-reference/keywords/is.md), [new](../../language-reference/keywords/new.md), [sizeof](../../language-reference/keywords/sizeof.md), [typeof](../../language-reference/keywords/typeof.md)|Estos operadores no se pueden sobrecargar.|

> [!NOTE]
> Los operadores de comparación, si se sobrecargan, deben sobrecargarse en pares; es decir, si `==` está sobrecargado, también debe estarlo `!=`. Esto también ocurre a la inversa, donde la sobrecarga de `!=` requiere una sobrecarga de `==`. Lo mismo puede ocurrir para los operadores de comparación `<` y `>` y para `<=` y `>=`.

Para obtener información sobre cómo sobrecargar un operador, vea el artículo sobre la palabra clave [operator](../../language-reference/keywords/operator.md).

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Instrucciones, expresiones y operadores](index.md)
- [Operadores](operators.md)
- [Operadores de C#](../../language-reference/operators/index.md)
- [Why are overloaded operators always static in C#?](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/) (¿Por qué los operadores sobrecargados son siempre estáticos en C#?)
