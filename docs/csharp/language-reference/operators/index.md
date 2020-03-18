---
title: 'Operadores de C#: referencia de C#'
ms.date: 08/20/2019
f1_keywords:
- cs.operators
helpviewer_keywords:
- operators [C#]
- operator precedence [C#]
- operator associativity [C#]
- expressions [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: 11c544e7fc923b0820141fb2e096ef7707f0a95f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74552472"
---
# <a name="c-operators-c-reference"></a>Operadores de C# (referencia de C#)

C# proporciona una serie de operadores compatibles con los tipos integrados. Por ejemplo, los [operadores aritméticos](arithmetic-operators.md) realizan operaciones aritméticas con operandos numéricos, y los [operadores lógicos booleanos](boolean-logical-operators.md) realizan operaciones lógicas con los operandos [bool](../builtin-types/bool.md). Algunos operadores se pueden [sobrecargar](operator-overloading.md). Con la sobrecarga de operadores, puede especificar el comportamiento del operador para los operandos de un tipo definido por el usuario.

En una [expresión](../../programming-guide/statements-expressions-operators/expressions.md), la prioridad y la asociatividad de los operadores determinan el orden en el que se realizan las operaciones. Puede usar los paréntesis para cambiar el orden de evaluación impuesto por la prioridad y la asociatividad de operadores.

## <a name="operator-precedence"></a>Prioridad de operadores

En una expresión con varios operadores, los operadores con mayor prioridad se evalúan antes que los operadores con menor prioridad. En el ejemplo siguiente, la multiplicación se realiza primero porque tiene mayor prioridad que la suma:

```csharp-interactive
var a = 2 + 2 * 2;
Console.WriteLine(a); //  output: 6
```

Use paréntesis para cambiar el orden de evaluación impuesto por la prioridad de los operadores:

```csharp-interactive
var a = (2 + 2) * 2;
Console.WriteLine(a); //  output: 8
```

En la tabla siguiente se muestran los operadores de C# desde la precedencia más alta a la más baja. Los operadores de cada fila comparten la prioridad.

| Operadores | Categoría o nombre |
| --------- | ---------------- |
| [x.y](member-access-operators.md#member-access-operator-), [x?.y](member-access-operators.md#null-conditional-operators--and-), [x?[y]](member-access-operators.md#null-conditional-operators--and-), [f(x)](member-access-operators.md#invocation-operator-), [a&#91;i&#93;](member-access-operators.md#indexer-operator-), [x++](arithmetic-operators.md#increment-operator-), [x--](arithmetic-operators.md#decrement-operator---), [new](new-operator.md), [typeof](type-testing-and-cast.md#typeof-operator), [checked](../keywords/checked.md), [unchecked](../keywords/unchecked.md), [default](default.md), [nameof](nameof.md), [delegate](delegate-operator.md), [sizeof](sizeof.md), [stackalloc](stackalloc.md), [x->y](pointer-related-operators.md#pointer-member-access-operator--) | Principal |
| [+x](arithmetic-operators.md#unary-plus-and-minus-operators), [-x](arithmetic-operators.md#unary-plus-and-minus-operators), [\!x](boolean-logical-operators.md#logical-negation-operator-), [~x](bitwise-and-shift-operators.md#bitwise-complement-operator-), [++x](arithmetic-operators.md#increment-operator-), [--x](arithmetic-operators.md#decrement-operator---), [^x](member-access-operators.md#index-from-end-operator-), [(T)x](type-testing-and-cast.md#cast-operator-), [await](await.md), [&x](pointer-related-operators.md#address-of-operator-), [*x](pointer-related-operators.md#pointer-indirection-operator-), [true and false](true-false-operators.md) | Unario |
| [x..y](member-access-operators.md#range-operator-) | Intervalo |
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
| [x = y](assignment-operator.md), [x += y](arithmetic-operators.md#compound-assignment), [x -= y](arithmetic-operators.md#compound-assignment), [x *= y](arithmetic-operators.md#compound-assignment), [x /= y](arithmetic-operators.md#compound-assignment), [x %= y](arithmetic-operators.md#compound-assignment), [x &= y](boolean-logical-operators.md#compound-assignment), [x &#124;= y](boolean-logical-operators.md#compound-assignment), [x ^= y](boolean-logical-operators.md#compound-assignment), [x <<= y](bitwise-and-shift-operators.md#compound-assignment), [x >>= y](bitwise-and-shift-operators.md#compound-assignment), [x ??= y](null-coalescing-operator.md), [=>](lambda-operator.md) | Asignación y declaración lambda |

## <a name="operator-associativity"></a>Asociatividad de los operadores

Cuando los operadores tienen la misma prioridad, su asociatividad determina el orden en el que se realizan las operaciones:

- Los operadores *asociativos a la izquierda* se evalúan, por orden, de izquierda a derecha. A excepción de los [operadores de asignación](assignment-operator.md) y el [operador de integración nula ](null-coalescing-operator.md), todos los operadores binarios son asociativos a la izquierda. Por ejemplo, `a + b - c` se evalúa como `(a + b) - c`.
- Los operadores *asociativos a la derecha* se evalúan, por orden, de derecha a izquierda. Los operadores de asignación, el operador de integración nula y el operador condicional [`?:`](conditional-operator.md) son asociativos a la derecha. Por ejemplo, `x = y = z` se evalúa como `x = (y = z)`.

Use paréntesis, para cambiar el orden de evaluación impuesto por la asociatividad de los operadores:

```csharp-interactive
int a = 13 / 5 / 2;
int b = 13 / (5 / 2);
Console.WriteLine($"a = {a}, b = {b}");  // output: a = 1, b = 6
```

## <a name="operand-evaluation"></a>Evaluación de operandos

Independientemente de la prioridad y la asociatividad de los operadores, los operandos de una expresión se evalúan de izquierda a derecha. En los siguientes ejemplos, se muestra el orden en el que se evalúan los operadores y los operandos:

| Expresión | Orden de evaluación |
| ---------- | ------------------- |
|`a + b`|a, b, +|
|`a + b * c`|a, b, c, *, +|
|`a / b + c * d`|a, b, /, c, d, *, +|
|`a / (b + c) * d`|a, b, c, +, /, d, *|

Normalmente, se evalúan todos los operandos de un operador. Sin embargo, algunos operadores evalúan los operandos de forma condicional. Esto significa que el valor del operando situado más a la izquierda de este tipo de operador define si se deben evaluar otros operandos, o bien qué operandos deben evaluarse. Estos operadores son los operadores lógicos condicionales [AND (`&&`)](boolean-logical-operators.md#conditional-logical-and-operator-) y [OR (`||`)](boolean-logical-operators.md#conditional-logical-or-operator-), los [operadores de integración nula `??` y `??=`](null-coalescing-operator.md), los [operadores condicionales nulos `?.` y `?[]`](member-access-operators.md#null-conditional-operators--and-), así como el [operador condicional `?:`](conditional-operator.md). Para más información, consulte la descripción de cada operador.

## <a name="c-language-specification"></a>especificación del lenguaje C#

Para obtener más información, vea la sección sobre [Operadores](~/_csharplang/spec/expressions.md#operators) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Expresiones](../../programming-guide/statements-expressions-operators/expressions.md)
