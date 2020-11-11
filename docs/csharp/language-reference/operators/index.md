---
title: Operadores y expresiones de C# (referencia de C#)
description: Más información sobre las expresiones y los operadores de C#, así como la precedencia y la asociatividad de estos
ms.date: 08/04/2020
f1_keywords:
- cs.operators
helpviewer_keywords:
- operators [C#]
- operator precedence [C#]
- operator associativity [C#]
- expressions [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: 9e7ca2087938317f7369043e21fd455dbad7f07b
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94439669"
---
# <a name="c-operators-and-expressions-c-reference"></a>Operadores y expresiones de C# (referencia de C#)

C# proporciona una serie de operadores. Muchos de ellos son compatibles con los [tipos integrados](../builtin-types/built-in-types.md) y permiten realizar operaciones básicas con valores de esos tipos. Entre estos operadores se incluyen los siguientes grupos:

- [Operadores aritméticos](arithmetic-operators.md), que realizan operaciones aritméticas con operandos numéricos.
- [Operadores de comparación](comparison-operators.md), que comparan operandos numéricos.
- [Operadores lógicos booleanos](boolean-logical-operators.md), que realizan operaciones lógicas con operandos [`bool`](../builtin-types/bool.md).
- [Operadores bit a bit y de desplazamiento](bitwise-and-shift-operators.md), que realizan operaciones bit a bit o de desplazamiento con operandos de tipos enteros.
- [Operadores de igualdad](equality-operators.md), que comprueban si sus operandos son iguales o no.

Normalmente, puede [sobrecargar](operator-overloading.md) esos operadores, es decir, puede especificar el comportamiento del operador para los operandos de un tipo definido por el usuario.

Las expresiones más simples de C# son literales (por ejemplo, números [enteros](../builtin-types/integral-numeric-types.md#integer-literals) y [reales](../builtin-types/floating-point-numeric-types.md#real-literals)) y nombres de variables. Puede combinarlas para crear expresiones complejas mediante el uso de operadores. La [precedencia](#operator-precedence) y la [asociatividad](#operator-associativity) de los operadores determinan el orden en el que se realizan las operaciones en una expresión. Puede usar los paréntesis para cambiar el orden de evaluación impuesto por la prioridad y la asociatividad de operadores.

En el código siguiente, se muestran ejemplos de expresiones en el lado derecho de las asignaciones:

[!code-csharp[expression examples](snippets/shared/Overview.cs#Expressions)]

Normalmente, una expresión genera un resultado que se puede incluir en otra expresión. Un método de llamada [`void`](../builtin-types/void.md) es un ejemplo de expresión que no genera un resultado. Solo se puede usar como [instrucción](../../programming-guide/statements-expressions-operators/statements.md), tal como se muestra en el ejemplo siguiente:

```csharp
Console.WriteLine("Hello, world!");
```

A continuación se indican otros tipos de expresiones que ofrece C#:

- [Expresiones de cadenas interpoladas](../tokens/interpolated.md), que proporcionan una sintaxis práctica para crear cadenas con formato:

  [!code-csharp-interactive[interpolated string](snippets/shared/Overview.cs#InterpolatedString)]

- [Expresiones lambda](lambda-expressions.md), que permiten crear funciones anónimas.

  [!code-csharp-interactive[lambda expression](snippets/shared/Overview.cs#Lambda)]

- [Expresiones de consulta](../keywords/query-keywords.md), que permiten usar capacidades de consulta directamente en C# :

  [!code-csharp-interactive[query expression](snippets/shared/Overview.cs#Query)]

Puede usar una [definición de cuerpo de expresiones](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) para proporcionar una definición concisa para un método, un constructor, una propiedad, un indexador o un finalizador.

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
| [x.y](member-access-operators.md#member-access-expression-), [f(x)](member-access-operators.md#invocation-expression-), [a&#91;i&#93;](member-access-operators.md#indexer-operator-), [`x?.y`](member-access-operators.md#null-conditional-operators--and-), [`x?[y]`](member-access-operators.md#null-conditional-operators--and-), [x++](arithmetic-operators.md#increment-operator-), [x--](arithmetic-operators.md#decrement-operator---), [x!](null-forgiving.md), [new](new-operator.md), [typeof](type-testing-and-cast.md#typeof-operator), [checked](../keywords/checked.md), [unchecked](../keywords/unchecked.md), [default](default.md), [nameof](nameof.md), [delegate](delegate-operator.md), [sizeof](sizeof.md), [stackalloc](stackalloc.md), [x->y](pointer-related-operators.md#pointer-member-access-operator--) | Principal |
| [+x](arithmetic-operators.md#unary-plus-and-minus-operators), [-x](arithmetic-operators.md#unary-plus-and-minus-operators), [\!x](boolean-logical-operators.md#logical-negation-operator-), [~x](bitwise-and-shift-operators.md#bitwise-complement-operator-), [++x](arithmetic-operators.md#increment-operator-), [--x](arithmetic-operators.md#decrement-operator---), [^x](member-access-operators.md#index-from-end-operator-), [(T)x](type-testing-and-cast.md#cast-expression), [await](await.md), [&x](pointer-related-operators.md#address-of-operator-), [*x](pointer-related-operators.md#pointer-indirection-operator-), [true and false](true-false-operators.md) | Unario |
| [x..y](member-access-operators.md#range-operator-) | Intervalo |
| [switch](switch-expression.md) | Expresión `switch` |
| [con](with-expression.md) | Expresión `with` |
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

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):

- [Expresiones](~/_csharplang/spec/expressions.md)
- [Operadores](~/_csharplang/spec/expressions.md#operators)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Sobrecarga de operadores](operator-overloading.md)
- [Árboles de expresión](../../programming-guide/concepts/expression-trees/index.md)
