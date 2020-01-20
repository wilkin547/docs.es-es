---
title: Operadores de desplazamiento y bit a bit (referencia de C#)
description: Obtenga información sobre los operadores de C# que realizan operaciones de desplazamiento o lógicas bit a bit con operandos de tipo entero.
ms.date: 04/18/2019
author: pkulikov
f1_keywords:
- ~_CSharpKeyword
- <<_CSharpKeyword
- '>>_CSharpKeyword'
- '&_CSharpKeyword'
- ^_CSharpKeyword
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise logical operators [C#]
- shift operators [C#]
- tilde operator [C#]
- one's complement operator [C#]
- bitwise complement operator [C#]
- ~ operator [C#]
- left shift operator [C#]
- << operator [C#]
- right shift operator [C#]
- '>> operator [C#]'
- bitwise logical AND operator [C#]
- ampersand operator [C#]
- '& operator [C#]'
- bitwise logical exclusive OR operator [C#]
- bitwise logical XOR operator [C#]
- ^ operator [C#]
- bitwise logical OR operator [C#]
- '| operator [C#]'
ms.openlocfilehash: a9f507ecdfced5b044b9d6338f723f53b1b4c4b7
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2020
ms.locfileid: "76115833"
---
# <a name="bitwise-and-shift-operators-c-reference"></a>Operadores de desplazamiento y bit a bit (referencia de C#)

Los operadores siguientes realizan operaciones de desplazamiento o bit a bit con operandos de los [tipos numéricos enteros](../builtin-types/integral-numeric-types.md) o el tipo [char](../builtin-types/char.md):

- Operador unario [`~` (complemento bit a bit)](#bitwise-complement-operator-)
- Operadores de desplazamiento binarios [`<<` (desplazamiento izquierdo)](#left-shift-operator-) y [`>>` (desplazamiento derecho)](#right-shift-operator-)
- Operadores binarios [`&` (AND lógico)](#logical-and-operator-), [`|` (OR lógico)](#logical-or-operator-) y [`^` (OR exclusivo lógico)](#logical-exclusive-or-operator-)

Estos operadores se definen para los tipos `int`, `uint`, `long` y `ulong`. Cuando ambos operandos son de otro tipo entero (`sbyte`, `byte`, `short`, `ushort` o `char`), sus valores se convierten en el tipo `int`, que también es el tipo de resultado de una operación. Cuando los operandos son de tipo entero diferente, sus valores se convierten en el tipo entero más cercano que contenga. Para obtener más información, vea la sección [Promociones numéricas](~/_csharplang/spec/expressions.md#numeric-promotions) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

Los operadores `&`, `|` y `^` también se definen para los operandos de tipo `bool`. Para obtener más información, vea [Operadores lógicos booleanos](boolean-logical-operators.md).

Las operaciones de desplazamiento y bit a bit nunca producen desbordamiento y generan los mismos resultados en contextos [Checked y Unchecked](../keywords/checked-and-unchecked.md).

## <a name="bitwise-complement-operator-"></a>Operador de complemento bit a bit ~

El operador `~` genera un complemento bit a bit de su operando al invertir cada bit:

[!code-csharp-interactive[bitwise NOT](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseComplement)]

También se puede usar el símbolo `~` para declarar finalizadores. Para obtener más información, vea [Finalizadores](../../programming-guide/classes-and-structs/destructors.md).

## <a name="left-shift-operator-"></a>Operador de desplazamiento izquierdo \<\<

El operador `<<` desplaza el operando izquierdo a la izquierda el [número de bits definido por el operando derecho](#shift-count-of-the-shift-operators).

La operación de desplazamiento izquierdo descarta los bits de orden superior que están fuera del rango del tipo de resultado y establece las posiciones de bits vacías de orden inferior en cero, como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[left shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LeftShift)]

Dado que los operadores de desplazamiento solo se definen para los tipos `int`, `uint`, `long` y `ulong`, el resultado de una operación siempre contiene al menos 32 bits. Si el operando izquierdo es de otro tipo entero (`sbyte`, `byte`, `short`, `ushort` o `char`), su valor se convierte al tipo `int`, como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[left shift with promotion](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LeftShiftPromoted)]

Para obtener información sobre cómo el operando derecho del operador `<<` define el recuento de desplazamiento, vea la sección [Recuento de desplazamiento de los operadores de desplazamiento](#shift-count-of-the-shift-operators).

## <a name="right-shift-operator-"></a>Operador de desplazamiento derecho >>

El operador `>>` desplaza el operando izquierdo a la derecha el [número de bits definido por el operando derecho](#shift-count-of-the-shift-operators).

La operación de desplazamiento derecho descarta los bits de orden inferior, como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#RightShift)]

Las posiciones de bits vacíos de orden superior se establecen basándose en el tipo del operando izquierdo, tal como se indica a continuación:

- Si el operando izquierdo es de tipo `int` o `long`, el operador de desplazamiento a la derecha realiza un desplazamiento *aritmético*: el valor del bit más significativo (el bit de signo) del operando izquierdo se propaga a las posiciones de bits vacíos de orden superior. Es decir, las posiciones de bits vacíos de orden superior se establecen en cero si el operando izquierdo no es negativo y, en caso de serlo, se establecen en uno.

  [!code-csharp-interactive[arithmetic right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#ArithmeticRightShift)]

- Si el operando izquierdo es de tipo `uint` o `ulong`, el operador de desplazamiento a la derecha realiza un desplazamiento *lógico*: las posiciones de bits vacíos de orden superior se establecen siempre en cero.

  [!code-csharp-interactive[logical right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LogicalRightShift)]

Para obtener información sobre cómo el operando derecho del operador `>>` define el recuento de desplazamiento, vea la sección [Recuento de desplazamiento de los operadores de desplazamiento](#shift-count-of-the-shift-operators).

## <a name="logical-and-operator-"></a> Operador AND lógico &amp;

El operador `&` calcula el AND lógico bit a bit de sus operandos:

[!code-csharp-interactive[bitwise AND](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseAnd)]

Para los operandos `bool`, el operador `&` calcula el [AND lógico](boolean-logical-operators.md#logical-and-operator-) de sus operandos. El operador `&` unario es el [operador address-of](pointer-related-operators.md#address-of-operator-).

## <a name="logical-exclusive-or-operator-"></a>Operador IR exclusivo lógico ^

El operador `^` calcula el OR exclusivo lógico bit a bit, también conocido como XOR lógico bit a bit, de sus operandos:

[!code-csharp-interactive[bitwise XOR](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseXor)]

Para los operandos `bool`, el operador `^` calcula el [OR exclusivo lógico](boolean-logical-operators.md#logical-exclusive-or-operator-) de sus operandos.

## <a name="logical-or-operator-"></a>Operador lógico OR |

El operador `|` calcula el OR lógico bit a bit de sus operandos:

[!code-csharp-interactive[bitwise OR](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseOr)]

Para los operandos `bool`, el operador `|` calcula el [OR lógico](boolean-logical-operators.md#logical-or-operator-) de sus operandos.

## <a name="compound-assignment"></a>Asignación compuesta

Para un operador binario `op`, una expresión de asignación compuesta con el formato

```csharp
x op= y
```

es equivalente a

```csharp
x = x op y
```

salvo que `x` solo se evalúa una vez.

En el ejemplo siguiente se muestra el uso de la asignación compuesta con operadores de desplazamiento y bit a bit:

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#CompoundAssignment)]

A causa de las [promociones numéricas](~/_csharplang/spec/expressions.md#numeric-promotions), el resultado de la operación `op` podría no ser convertible de forma implícita en el tipo `T` de `x`. En tal caso, si `op` es un operador predefinido y el resultado de la operación es convertible de forma explícita en el tipo `T` de `x`, una expresión de asignación compuesta con el formato `x op= y` es equivalente a `x = (T)(x op y)`, excepto que `x` solo se evalúa una vez. En el ejemplo siguiente se muestra ese comportamiento:

[!code-csharp-interactive[compound assignment with cast](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#CompoundAssignmentWithCast)]

## <a name="operator-precedence"></a>Prioridad de operadores

En la lista siguiente se ordenan los operadores de desplazamiento y bit a bit desde la prioridad más alta a la más baja:

- Operador de complemento bit a bit `~`
- Operadores de desplazamiento `<<` y `>>`
- Operador AND lógico `&`
- Operador OR exclusivo lógico `^`
- Operador OR lógico `|`

Use los paréntesis, `()`, para cambiar el orden de evaluación impuesto por la prioridad de los operadores:

[!code-csharp-interactive[operator precedence](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#Precedence)]

Para obtener la lista completa de los operadores de C# ordenados por nivel de prioridad, vea la sección [Prioridad de operadores](index.md#operator-precedence) del artículo [Operadores de C#](index.md).

## <a name="shift-count-of-the-shift-operators"></a>Recuento de desplazamiento de los operadores de desplazamiento

En el caso de los operadores de desplazamiento `<<` y `>>`, el tipo del operando derecho debe ser `int` o un tipo que tenga una [conversión numérica implícita predefinida](../builtin-types/numeric-conversions.md#implicit-numeric-conversions) a `int`.

En el caso de las expresiones `x << count` y `x >> count`, el recuento de desplazamiento real depende del tipo de `x`, de esta forma:

- Si el tipo de `x` es `int` o `uint`, el recuento de desplazamiento viene definido por los *cinco* bits de orden inferior del operando derecho. Es decir, el valor de desplazamiento se calcula a partir de `count & 0x1F` (o `count & 0b_1_1111`).

- Si el tipo de `x` es `long` o `ulong`, el recuento de desplazamiento viene definido por los *seis* bits de orden inferior del operando derecho. Es decir, el valor de desplazamiento se calcula a partir de `count & 0x3F` (o `count & 0b_11_1111`).

En el ejemplo siguiente se muestra ese comportamiento:

[!code-csharp-interactive[shift count example](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#ShiftCount)]

> [!NOTE]
> Tal y como se muestra en el ejemplo anterior, el resultado de una operación de desplazamiento puede ser distinto de cero incluso si el valor del operando derecho es mayor que el número de bits del operando izquierdo.

## <a name="enumeration-logical-operators"></a>Operadores lógicos de enumeración

Los operadores `~`, `&`, `|` y `^` también se admiten en cualquier tipo de [enumeración](../builtin-types/enum.md). En el caso de los operandos del mismo tipo de enumeración, se realiza una operación lógica en los valores correspondientes del tipo entero subyacente. Por ejemplo, para cualquier `x` e `y` de un tipo de enumeración `T` con un tipo subyacente `U`, la expresión `x & y` produce el mismo resultado que la expresión `(T)((U)x & (U)y)`.

Normalmente, los operadores lógicos bit a bit se usan con un tipo de enumeración definido con el atributo [Flags](xref:System.FlagsAttribute). Para obtener más información, vea la sección [Tipos de enumeración como marcas de bits](../builtin-types/enum.md#enumeration-types-as-bit-flags) del artículo [Tipos de enumeración](../builtin-types/enum.md).

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Un tipo definido por el usuario puede [sobrecargar](operator-overloading.md) los operadores `~`, `<<`, `>>`, `&`, `|` y `^`. Cuando se sobrecarga un operador binario, también se sobrecarga de forma implícita el operador de asignación compuesta correspondiente. Un tipo definido por el usuario no puede sobrecargar de forma explícita un operador de asignación compuesta.

Si un tipo definido por el usuario `T` sobrecarga el operador `<<` o `>>`, el tipo del operando izquierdo debe ser `T` y el del derecho `int`.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):

- [Operador de complemento bit a bit](~/_csharplang/spec/expressions.md#bitwise-complement-operator)
- [Operadores de desplazamiento](~/_csharplang/spec/expressions.md#shift-operators)
- [Operadores lógicos](~/_csharplang/spec/expressions.md#logical-operators)
- [Asignación compuesta](~/_csharplang/spec/expressions.md#compound-assignment)
- [Promociones numéricas](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
- [Operadores lógicos booleanos](boolean-logical-operators.md)
