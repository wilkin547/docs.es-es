---
title: 'Operadores de C#: referencia de C#'
ms.date: 04/30/2019
f1_keywords:
- cs.operators
helpviewer_keywords:
- boolean operators [C#]
- expressions [C#], operators
- logical operators [C#]
- operators [C#]
- Visual C#, operators
- indirection operators [C#]
- assignment operators [C#]
- shift operators [C#]
- relational operators [C#]
- bitwise operators [C#]
- address operators [C#]
- keywords [C#], operators
- arithmetic operators [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: 7db61e530ba5c3e0b5ae0ee0002621e369e1833b
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2019
ms.locfileid: "69566839"
---
# <a name="c-operators-c-reference"></a>Operadores de C# (referencia de C#)

C# proporciona una serie de operadores predefinidos compatibles con los tipos integrados. Por ejemplo, los [operadores aritméticos](arithmetic-operators.md) realizan operaciones aritméticas con operandos de tipos numéricos integrados, y los [operadores lógicos booleanos](boolean-logical-operators.md) realizan operaciones lógicas con los operandos [bool](../keywords/bool.md).

Un tipo definido por el usuario puede sobrecargar determinados operadores para definir el comportamiento correspondiente para los operandos de ese tipo. Para obtener más información, vea [Sobrecarga de operadores](operator-overloading.md).

En la tabla siguiente se muestran los operadores de C# desde la precedencia más alta a la más baja. Los operadores de cada fila comparten el mismo nivel de precedencia.

| Operadores | Categoría o nombre |
| --------- | ---------------- |
| [x.y](member-access-operators.md#member-access-operator-), [x?.y](member-access-operators.md#null-conditional-operators--and-), [x?[y]](member-access-operators.md#null-conditional-operators--and-), [f(x)](member-access-operators.md#invocation-operator-), [a&#91;i&#93;](member-access-operators.md#indexer-operator-), [x++](arithmetic-operators.md#increment-operator-), [x--](arithmetic-operators.md#decrement-operator---), [new](new-operator.md), [typeof](type-testing-and-cast.md#typeof-operator), [checked](../keywords/checked.md), [unchecked](../keywords/unchecked.md), [default](default.md), [nameof](nameof.md), [delegate](delegate-operator.md), [sizeof](sizeof.md), [stackalloc](stackalloc.md), [x->y](pointer-related-operators.md#pointer-member-access-operator--) | Principal |
| [+x](arithmetic-operators.md#unary-plus-and-minus-operators), [-x](arithmetic-operators.md#unary-plus-and-minus-operators), [\!x](boolean-logical-operators.md#logical-negation-operator-), [~x](bitwise-and-shift-operators.md#bitwise-complement-operator-), [++x](arithmetic-operators.md#increment-operator-), [--x](arithmetic-operators.md#decrement-operator---), [(T)x](type-testing-and-cast.md#cast-operator-), [await](../keywords/await.md), [&x](pointer-related-operators.md#address-of-operator-), [*x](pointer-related-operators.md#pointer-indirection-operator-), [true and false](true-false-operators.md) | Unario |
| [x * y](arithmetic-operators.md#multiplication-operator-), [x / y](arithmetic-operators.md#division-operator-), [x % y](arithmetic-operators.md#remainder-operator-) | Multiplicativo|
| [x + y](arithmetic-operators.md#addition-operator-), [x – y](arithmetic-operators.md#subtraction-operator--) | Aditivo |
| [x \<\<  y](bitwise-and-shift-operators.md#left-shift-operator-), [x >> y](bitwise-and-shift-operators.md#right-shift-operator-) | Shift |
| [x \< y](comparison-operators.md#less-than-operator-), [x > y](comparison-operators.md#greater-than-operator-), [x \<= y](comparison-operators.md#less-than-or-equal-operator-), [x >= y](comparison-operators.md#greater-than-or-equal-operator-), [is](type-testing-and-cast.md#is-operator), [as](type-testing-and-cast.md#as-operator) | Comprobación de tipos y relacional |
| [x == y](equality-operators.md#equality-operator-), [x != y](equality-operators.md#inequality-operator-) | Igualdad |
| `x & y` | [Operador lógico booleano AND](boolean-logical-operators.md#logical-and-operator-) u [operador lógico bit a bit AND](bitwise-and-shift-operators.md#logical-and-operator-) |
| `x ^ y` | [Operador lógico booleano XOR](boolean-logical-operators.md#logical-exclusive-or-operator-) u [operador lógico bit a bit XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) |
| <code>x &#124; y</code> | [Operador lógico booleano OR](boolean-logical-operators.md#logical-or-operator-) u [operador lógico bit a bit OR](bitwise-and-shift-operators.md#logical-or-operator-) |
| [x && y](boolean-logical-operators.md#conditional-logical-and-operator-) | AND condicional |
| [x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) | OR condicional |
| [x ?? y](null-coalescing-operator.md) | Operador de uso combinado de null |
| [c ? t : f](conditional-operator.md) | Operador condicional |
| [x = y](assignment-operator.md), [x += y](arithmetic-operators.md#compound-assignment), [x -= y](arithmetic-operators.md#compound-assignment), [x *= y](arithmetic-operators.md#compound-assignment), [x /= y](arithmetic-operators.md#compound-assignment), [x %= y](arithmetic-operators.md#compound-assignment), [x &= y](boolean-logical-operators.md#compound-assignment), [x &#124;= y](boolean-logical-operators.md#compound-assignment), [x ^= y](boolean-logical-operators.md#compound-assignment), [x <<= y](bitwise-and-shift-operators.md#compound-assignment), [x >>= y](bitwise-and-shift-operators.md#compound-assignment), [=>](lambda-operator.md) | Asignación y declaración lambda |

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores](../../programming-guide/statements-expressions-operators/operators.md)
