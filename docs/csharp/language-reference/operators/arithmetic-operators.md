---
title: Operadores aritméticos (referencia de C#)
description: Obtenga información sobre los operadores de C# que realizan operaciones de multiplicación, división, resto, suma y resta con tipos numéricos.
ms.date: 05/11/2020
author: pkulikov
f1_keywords:
- ++_CSharpKeyword
- --_CSharpKeyword
- '*_CSharpKeyword'
- /_CSharpKeyword
- '%_CSharpKeyword'
- +_CSharpKeyword
- -_CSharpKeyword
- '%=_CSharpKeyword'
- '*=_CSharpKeyword'
helpviewer_keywords:
- arithmetic operators [C#]
- increment operator [C#]
- ++ operator [C#]
- decrement operator [C#]
- -- operator [C#]
- multiplication operator [C#]
- '* operator [C#]'
- division operator [C#]
- / operator [C#]
- remainder operator [C#]
- '% operator [C#]'
- addition operator [C#]
- + operator [C#]
- subtraction operator [C#]
- '- operator [C#]'
ms.openlocfilehash: f5da9c4433ffcf3e6a110bbb1543343289240778
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916958"
---
# <a name="arithmetic-operators-c-reference"></a>Operadores aritméticos (referencia de C#)

Los operadores siguientes realizan operaciones aritméticas con operandos de tipos numéricos:

- Operadores unarios [`++` (incremento)](#increment-operator-), [`--` (decremento)](#decrement-operator---), [`+` (más)](#unary-plus-and-minus-operators) y [`-` (menos)](#unary-plus-and-minus-operators).
- Operadores binarios [`*` (multiplicación)](#multiplication-operator-), [`/` (división)](#division-operator-), [`%` (resto)](#remainder-operator-), [`+` (suma)](#addition-operator-) y [`-` (resta)](#subtraction-operator--).

Estos operadores se admiten en todos los tipos numéricos [enteros](../builtin-types/integral-numeric-types.md) y de [punto flotante](../builtin-types/floating-point-numeric-types.md).

En el caso de tipos enteros, dichos operadores (excepto los operadores `++` y `--`) se definen para los tipos `int`, `uint`, `long` y `ulong`. Cuando los operandos son de otro tipo entero (`sbyte`, `byte`, `short`, `ushort` o `char`), sus valores se convierten en el tipo `int`, que también es el tipo de resultado de una operación. Cuando los operandos son de distintos tipos enteros o de punto flotante, sus valores se convierten al tipo contenedor más cercano, si ese tipo existe. Para obtener más información, vea la sección [Promociones numéricas](~/_csharplang/spec/expressions.md#numeric-promotions) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md). Los operadores `++` y `--` se definen para todos los tipos numéricos enteros y de punto flotante y el tipo [char](../builtin-types/char.md).

## <a name="increment-operator-"></a>Operador de incremento ++

El operador de incremento unario `++` incrementa su operando en 1. El operando debe ser una variable, un acceso de [propiedad](../../programming-guide/classes-and-structs/properties.md) o un acceso de [indexador](../../programming-guide/indexers/index.md).

El operador de incremento se admite en dos formas: el operador de incremento posfijo (`x++`) y el operador de incremento prefijo (`++x`).

### <a name="postfix-increment-operator"></a>Operador de incremento de postfijo

El resultado de `x++` es el valor de `x`*antes* de la operación, tal y como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[postfix increment](snippets/shared/ArithmeticOperators.cs#PostfixIncrement)]

### <a name="prefix-increment-operator"></a>Operador de incremento prefijo

El resultado de `++x` es el valor de `x`*después* de la operación, tal y como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[prefix increment](snippets/shared/ArithmeticOperators.cs#PrefixIncrement)]

## <a name="decrement-operator---"></a>Operador de decremento --

El operador de decremento unario `--` disminuye su operando en 1. El operando debe ser una variable, un acceso de [propiedad](../../programming-guide/classes-and-structs/properties.md) o un acceso de [indexador](../../programming-guide/indexers/index.md).

El operador de decremento se admite en dos formas: el operador de decremento posfijo (`x--`) y el operador de decremento prefijo (`--x`).

### <a name="postfix-decrement-operator"></a>Operador de decremento de postfijo

El resultado de `x--` es el valor de `x`*antes* de la operación, tal y como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[postfix decrement](snippets/shared/ArithmeticOperators.cs#PostfixDecrement)]

### <a name="prefix-decrement-operator"></a>Operador de decremento de prefijo

El resultado de `--x` es el valor de `x`*después* de la operación, tal y como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[prefix decrement](snippets/shared/ArithmeticOperators.cs#PrefixDecrement)]

## <a name="unary-plus-and-minus-operators"></a>Operadores unarios más y menos

El operador `+` unario devuelve el valor de su operando. El operador unario `-` calcula la negación numérica del operando.

[!code-csharp-interactive[unary plus and minus](snippets/shared/ArithmeticOperators.cs#UnaryPlusAndMinus)]

El operador unario `-` no es compatible con el tipo [ulong](../builtin-types/integral-numeric-types.md).

## <a name="multiplication-operator-"></a>Operador de multiplicación *

El operador de multiplicación `*` calcula el producto de sus operandos:

[!code-csharp-interactive[multiplication operator](snippets/shared/ArithmeticOperators.cs#Multiplication)]

El operador unario `*` es el [operador de direccionamiento indirecto del puntero](pointer-related-operators.md#pointer-indirection-operator-).

## <a name="division-operator-"></a>Operador de división /

El operador de división `/` divide el operando izquierdo entre el derecho.

### <a name="integer-division"></a>División de enteros

Para los operandos de tipos enteros, el resultado del operador `/` es de un tipo entero y equivale al cociente de los dos operandos redondeados hacia cero:

[!code-csharp-interactive[integer division](snippets/shared/ArithmeticOperators.cs#IntegerDivision)]

Para obtener el cociente de los dos operandos como número de punto flotante, use el tipo `float`, `double` o `decimal`:

[!code-csharp-interactive[integer as floating-point division](snippets/shared/ArithmeticOperators.cs#IntegerAsFloatingPointDivision)]

### <a name="floating-point-division"></a>División de punto flotante

Para los tipos `float`, `double` y `decimal`, el resultado del operador `/` es el cociente de los dos operandos:

[!code-csharp-interactive[floating-point division](snippets/shared/ArithmeticOperators.cs#FloatingPointDivision)]

Si uno de los operandos es `decimal`, otro operando no puede ser `float` ni `double`, ya que ni `float` ni `double` se convierte de forma implícita a `decimal`. Debe convertir explícitamente el operando `float` o `double` al tipo `decimal`. Para obtener más información sobre las conversiones entre tipos numéricos, consulte [Conversiones numéricas integradas](../builtin-types/numeric-conversions.md).

## <a name="remainder-operator-"></a>Operador de resto %

El operador de resto `%` calcula el resto después de dividir el operando izquierdo entre el derecho.

### <a name="integer-remainder"></a>Resto entero

En el caso de los operandos de tipos enteros, el resultado de `a % b` es el valor producido por `a - (a / b) * b`. El signo de resto distinto de cero es el mismo que el del operando izquierdo, como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[integer remainder](snippets/shared/ArithmeticOperators.cs#IntegerRemainder)]

Use el método <xref:System.Math.DivRem%2A?displayProperty=nameWithType> para calcular los resultados de la división de enteros y del resto.

### <a name="floating-point-remainder"></a>Resto de punto flotante

En el caso de los operandos `float` y `double`, el resultado de `x % y` para `x` e `y` finitos es el valor `z`, de modo que

- el signo de `z`, si no es cero, es el mismo que el signo de `x`;
- el valor absoluto de `z` es el valor producido por `|x| - n * |y|`, donde `n` es el entero más grande posible que sea menor o igual que `|x| / |y|`, y `|x|` e `|y|` son los valores absolutos de `x` e `y`, respectivamente.

> [!NOTE]
> Este método de cálculo del resto es análogo al que se usa para los operandos enteros, pero difiere de la especificación IEEE 754. Si necesita la operación de resto conforme con la especificación IEEE 754, use el método <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>.

Para información sobre el comportamiento del operador `%` con operandos no finitos, vea la sección [Operador de resto](~/_csharplang/spec/expressions.md#remainder-operator) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

En el caso de los operandos `decimal`, el operador de resto `%` es equivalente al [operador de resto](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) del tipo <xref:System.Decimal?displayProperty=nameWithType>.

En el ejemplo siguiente se muestra el comportamiento del operador de resto con operandos de punto flotante:

[!code-csharp-interactive[floating-point remainder](snippets/shared/ArithmeticOperators.cs#FloatingPointRemainder)]

## <a name="addition-operator-"></a>Operador de suma +

El operador de suma `+` calcula la suma de sus operandos:

[!code-csharp-interactive[addition operator](snippets/shared/ArithmeticOperators.cs#Addition)]

También puede usar el operador `+` para la concatenación de cadenas y la combinación de delegados. Para obtener más información, consulte [Operadores `+` y `+=`](addition-operator.md).

## <a name="subtraction-operator--"></a>Operador de resta -

El operador de resta `-` resta el operando derecho del izquierdo:

[!code-csharp-interactive[subtraction operator](snippets/shared/ArithmeticOperators.cs#Subtraction)]

También puede usar el operador `-` para la eliminación de delegados. Para obtener más información, consulte [Operadores `-` y `-=`](subtraction-operator.md).

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

En el ejemplo siguiente se muestra el uso de la asignación compuesta con operadores aritméticos:

[!code-csharp-interactive[compound assignment](snippets/shared/ArithmeticOperators.cs#CompoundAssignment)]

A causa de las [promociones numéricas](~/_csharplang/spec/expressions.md#numeric-promotions), el resultado de la operación `op` podría no ser convertible de forma implícita en el tipo `T` de `x`. En tal caso, si `op` es un operador predefinido y el resultado de la operación es convertible de forma explícita en el tipo `T` de `x`, una expresión de asignación compuesta con el formato `x op= y` es equivalente a `x = (T)(x op y)`, excepto que `x` solo se evalúa una vez. En el ejemplo siguiente se muestra ese comportamiento:

[!code-csharp-interactive[compound assignment with cast](snippets/shared/ArithmeticOperators.cs#CompoundAssignmentWithCast)]

Los operadores `+=` y `-=` también se usan para suscribirse y cancelar la suscripción a un [evento](../keywords/event.md), respectivamente. Para obtener más información, vea [Procedimiento para suscribir y cancelar la suscripción a eventos](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="operator-precedence-and-associativity"></a>Prioridad y asociatividad de los operadores

En la lista siguiente se ordenan los operadores aritméticos de la prioridad más alta a la más baja:

- Operadores de incremento `x++` y decremento `x--` posfijos
- Operadores de incremento `++x` y decremento `--x` prefijos, y operadores unarios `+` y `-`.
- Operadores de multiplicación `*`, `/` y `%`.
- Operadores de suma adición `+` y `-`.

Los operadores aritméticos binarios son asociativos a la izquierda. Es decir, los operadores con el mismo nivel de prioridad se evalúan de izquierda a derecha.

Use los paréntesis, `()`, para cambiar el orden de evaluación impuesto por la prioridad y la asociatividad de operadores.

[!code-csharp-interactive[precedence and associativity](snippets/shared/ArithmeticOperators.cs#PrecedenceAndAssociativity)]

Para obtener la lista completa de los operadores de C# ordenados por nivel de prioridad, vea la sección [Prioridad de operadores](index.md#operator-precedence) del artículo [Operadores de C#](index.md).

## <a name="arithmetic-overflow-and-division-by-zero"></a>Desbordamiento aritmético y división por cero

Si el resultado de una operación aritmética está fuera del intervalo de valores finitos posibles del tipo numérico implicado, el comportamiento de un operador aritmético depende del tipo de sus operandos.

### <a name="integer-arithmetic-overflow"></a>Desbordamiento aritmético de enteros

La división de enteros por cero siempre produce una <xref:System.DivideByZeroException>.

En el caso de desbordamiento aritmético de enteros, el comportamiento resultante lo controla un contexto de comprobación de desbordamiento, que puede ser [comprobado o no comprobado](../keywords/checked-and-unchecked.md):

- En un contexto comprobado, si el desbordamiento se produce en una expresión constante, se produce un error de compilación. De lo contrario, si la operación se realiza en tiempo de ejecución, se inicia una excepción <xref:System.OverflowException>.
- En un contexto no comprobado, el resultado se trunca mediante el descarte de los bits de orden superior que no caben en el tipo de destino.

Junto con las instrucciones [comprobadas y no comprobadas](../keywords/checked-and-unchecked.md), puede usar los operadores `checked` y `unchecked` para controlar el contexto de comprobación de desbordamiento, en el que se evalúa una expresión:

[!code-csharp-interactive[checked and unchecked](snippets/shared/ArithmeticOperators.cs#CheckedUnchecked)]

De forma predeterminada, las operaciones aritméticas se producen en un contexto *no comprobado*.

### <a name="floating-point-arithmetic-overflow"></a>Desbordamiento aritmético de punto flotante

Las operaciones aritméticas con los tipos `float` y `double` nunca inician una excepción. El resultado de las operaciones aritméticas con esos tipos puede ser uno de varios valores especiales que representan infinito y no un número:

[!code-csharp-interactive[double non-finite values](snippets/shared/ArithmeticOperators.cs#FloatingPointOverflow)]

Para los operandos del tipo `decimal`, el desbordamiento aritmético siempre inicia una excepción <xref:System.OverflowException> y la división por cero siempre inicia una excepción <xref:System.DivideByZeroException>.

## <a name="round-off-errors"></a>Errores de redondeo

Debido a las limitaciones generales de la representación de punto flotante de los números reales y la aritmética de punto flotante, es posible que se produzcan errores de redondeo en los cálculos con tipos de punto flotante. Es decir, es posible que el resultado de una expresión difiera del resultado matemático esperado. En el ejemplo siguiente se muestran varios de estos casos:

[!code-csharp-interactive[round-off errors](snippets/shared/ArithmeticOperators.cs#RoundOffErrors)]

Para más información, vea los comentarios en las páginas de referencia de [System.Double](/dotnet/api/system.double#remarks), [System.Single](/dotnet/api/system.single#remarks) o [System.Decimal](/dotnet/api/system.decimal#remarks).

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Un tipo definido por el usuario puede [sobrecargar](operator-overloading.md) los operadores unarios (`++`, `--`, `+` y `-`), los operadores binarios (`*`, `/`, `%`, `+` y `-`) y los operadores aritméticos. Cuando se sobrecarga un operador binario, también se sobrecarga de forma implícita el operador de asignación compuesta correspondiente. Un tipo definido por el usuario no puede sobrecargar de forma explícita un operador de asignación compuesta.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):

- [Operadores de incremento y decremento posfijos](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators)
- [Operadores de incremento y decremento prefijos](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators)
- [Operador unario más](~/_csharplang/spec/expressions.md#unary-plus-operator)
- [Operador unario menos](~/_csharplang/spec/expressions.md#unary-minus-operator)
- [Operador de multiplicación](~/_csharplang/spec/expressions.md#multiplication-operator)
- [Operador de división](~/_csharplang/spec/expressions.md#division-operator)
- [Operador de resto](~/_csharplang/spec/expressions.md#remainder-operator)
- [Operador de suma](~/_csharplang/spec/expressions.md#addition-operator)
- [Operador de resta](~/_csharplang/spec/expressions.md#subtraction-operator)
- [Asignación compuesta](~/_csharplang/spec/expressions.md#compound-assignment)
- [Operadores checked y unchecked](~/_csharplang/spec/expressions.md#the-checked-and-unchecked-operators)
- [Promociones numéricas](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores y expresiones de C#](index.md)
- <xref:System.Math?displayProperty=nameWithType>
- <xref:System.MathF?displayProperty=nameWithType>
- [Valores numéricos en .NET](../../../standard/numerics.md)
