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
# <a name="arithmetic-operators-c-reference"></a><span data-ttu-id="c3cb1-103">Operadores aritméticos (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c3cb1-103">Arithmetic operators (C# reference)</span></span>

<span data-ttu-id="c3cb1-104">Los operadores siguientes realizan operaciones aritméticas con operandos de tipos numéricos:</span><span class="sxs-lookup"><span data-stu-id="c3cb1-104">The following operators perform arithmetic operations with operands of numeric types:</span></span>

- <span data-ttu-id="c3cb1-105">Operadores unarios [`++` (incremento)](#increment-operator-), [`--` (decremento)](#decrement-operator---), [`+` (más)](#unary-plus-and-minus-operators) y [`-` (menos)](#unary-plus-and-minus-operators).</span><span class="sxs-lookup"><span data-stu-id="c3cb1-105">Unary [`++` (increment)](#increment-operator-), [`--` (decrement)](#decrement-operator---), [`+` (plus)](#unary-plus-and-minus-operators), and [`-` (minus)](#unary-plus-and-minus-operators) operators</span></span>
- <span data-ttu-id="c3cb1-106">Operadores binarios [`*` (multiplicación)](#multiplication-operator-), [`/` (división)](#division-operator-), [`%` (resto)](#remainder-operator-), [`+` (suma)](#addition-operator-) y [`-` (resta)](#subtraction-operator--).</span><span class="sxs-lookup"><span data-stu-id="c3cb1-106">Binary [`*` (multiplication)](#multiplication-operator-), [`/` (division)](#division-operator-), [`%` (remainder)](#remainder-operator-), [`+` (addition)](#addition-operator-), and [`-` (subtraction)](#subtraction-operator--) operators</span></span>

<span data-ttu-id="c3cb1-107">Estos operadores se admiten en todos los tipos numéricos [enteros](../builtin-types/integral-numeric-types.md) y de [punto flotante](../builtin-types/floating-point-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="c3cb1-107">Those operators are supported by all [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types.</span></span>

<span data-ttu-id="c3cb1-108">En el caso de tipos enteros, dichos operadores (excepto los operadores `++` y `--`) se definen para los tipos `int`, `uint`, `long` y `ulong`.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-108">In the case of integral types, those operators (except the `++` and `--` operators) are defined for the `int`, `uint`, `long`, and `ulong` types.</span></span> <span data-ttu-id="c3cb1-109">Cuando los operandos son de otro tipo entero (`sbyte`, `byte`, `short`, `ushort` o `char`), sus valores se convierten en el tipo `int`, que también es el tipo de resultado de una operación.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-109">When operands are of other integral types (`sbyte`, `byte`, `short`, `ushort`, or `char`), their values are converted to the `int` type, which is also the result type of an operation.</span></span> <span data-ttu-id="c3cb1-110">Cuando los operandos son de distintos tipos enteros o de punto flotante, sus valores se convierten al tipo contenedor más cercano, si ese tipo existe.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-110">When operands are of different integral or floating-point types, their values are converted to the closest containing type, if such a type exists.</span></span> <span data-ttu-id="c3cb1-111">Para obtener más información, vea la sección [Promociones numéricas](~/_csharplang/spec/expressions.md#numeric-promotions) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="c3cb1-111">For more information, see the [Numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span> <span data-ttu-id="c3cb1-112">Los operadores `++` y `--` se definen para todos los tipos numéricos enteros y de punto flotante y el tipo [char](../builtin-types/char.md).</span><span class="sxs-lookup"><span data-stu-id="c3cb1-112">The `++` and `--` operators are defined for all integral and floating-point numeric types and the [char](../builtin-types/char.md) type.</span></span>

## <a name="increment-operator-"></a><span data-ttu-id="c3cb1-113">Operador de incremento ++</span><span class="sxs-lookup"><span data-stu-id="c3cb1-113">Increment operator ++</span></span>

<span data-ttu-id="c3cb1-114">El operador de incremento unario `++` incrementa su operando en 1.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-114">The unary increment operator `++` increments its operand by 1.</span></span> <span data-ttu-id="c3cb1-115">El operando debe ser una variable, un acceso de [propiedad](../../programming-guide/classes-and-structs/properties.md) o un acceso de [indexador](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="c3cb1-115">The operand must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../programming-guide/indexers/index.md) access.</span></span>

<span data-ttu-id="c3cb1-116">El operador de incremento se admite en dos formas: el operador de incremento posfijo (`x++`) y el operador de incremento prefijo (`++x`).</span><span class="sxs-lookup"><span data-stu-id="c3cb1-116">The increment operator is supported in two forms: the postfix increment operator, `x++`, and the prefix increment operator, `++x`.</span></span>

### <a name="postfix-increment-operator"></a><span data-ttu-id="c3cb1-117">Operador de incremento de postfijo</span><span class="sxs-lookup"><span data-stu-id="c3cb1-117">Postfix increment operator</span></span>

<span data-ttu-id="c3cb1-118">El resultado de `x++` es el valor de `x`*antes* de la operación, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c3cb1-118">The result of `x++` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix increment](snippets/shared/ArithmeticOperators.cs#PostfixIncrement)]

### <a name="prefix-increment-operator"></a><span data-ttu-id="c3cb1-119">Operador de incremento prefijo</span><span class="sxs-lookup"><span data-stu-id="c3cb1-119">Prefix increment operator</span></span>

<span data-ttu-id="c3cb1-120">El resultado de `++x` es el valor de `x`*después* de la operación, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c3cb1-120">The result of `++x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix increment](snippets/shared/ArithmeticOperators.cs#PrefixIncrement)]

## <a name="decrement-operator---"></a><span data-ttu-id="c3cb1-121">Operador de decremento --</span><span class="sxs-lookup"><span data-stu-id="c3cb1-121">Decrement operator --</span></span>

<span data-ttu-id="c3cb1-122">El operador de decremento unario `--` disminuye su operando en 1.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-122">The unary decrement operator `--` decrements its operand by 1.</span></span> <span data-ttu-id="c3cb1-123">El operando debe ser una variable, un acceso de [propiedad](../../programming-guide/classes-and-structs/properties.md) o un acceso de [indexador](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="c3cb1-123">The operand must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../programming-guide/indexers/index.md) access.</span></span>

<span data-ttu-id="c3cb1-124">El operador de decremento se admite en dos formas: el operador de decremento posfijo (`x--`) y el operador de decremento prefijo (`--x`).</span><span class="sxs-lookup"><span data-stu-id="c3cb1-124">The decrement operator is supported in two forms: the postfix decrement operator, `x--`, and the prefix decrement operator, `--x`.</span></span>

### <a name="postfix-decrement-operator"></a><span data-ttu-id="c3cb1-125">Operador de decremento de postfijo</span><span class="sxs-lookup"><span data-stu-id="c3cb1-125">Postfix decrement operator</span></span>

<span data-ttu-id="c3cb1-126">El resultado de `x--` es el valor de `x`*antes* de la operación, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c3cb1-126">The result of `x--` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix decrement](snippets/shared/ArithmeticOperators.cs#PostfixDecrement)]

### <a name="prefix-decrement-operator"></a><span data-ttu-id="c3cb1-127">Operador de decremento de prefijo</span><span class="sxs-lookup"><span data-stu-id="c3cb1-127">Prefix decrement operator</span></span>

<span data-ttu-id="c3cb1-128">El resultado de `--x` es el valor de `x`*después* de la operación, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c3cb1-128">The result of `--x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix decrement](snippets/shared/ArithmeticOperators.cs#PrefixDecrement)]

## <a name="unary-plus-and-minus-operators"></a><span data-ttu-id="c3cb1-129">Operadores unarios más y menos</span><span class="sxs-lookup"><span data-stu-id="c3cb1-129">Unary plus and minus operators</span></span>

<span data-ttu-id="c3cb1-130">El operador `+` unario devuelve el valor de su operando.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-130">The unary `+` operator returns the value of its operand.</span></span> <span data-ttu-id="c3cb1-131">El operador unario `-` calcula la negación numérica del operando.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-131">The unary `-` operator computes the numeric negation of its operand.</span></span>

[!code-csharp-interactive[unary plus and minus](snippets/shared/ArithmeticOperators.cs#UnaryPlusAndMinus)]

<span data-ttu-id="c3cb1-132">El operador unario `-` no es compatible con el tipo [ulong](../builtin-types/integral-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="c3cb1-132">The [ulong](../builtin-types/integral-numeric-types.md) type doesn't support the unary `-` operator.</span></span>

## <a name="multiplication-operator-"></a><span data-ttu-id="c3cb1-133">Operador de multiplicación \*</span><span class="sxs-lookup"><span data-stu-id="c3cb1-133">Multiplication operator \*</span></span>

<span data-ttu-id="c3cb1-134">El operador de multiplicación `*` calcula el producto de sus operandos:</span><span class="sxs-lookup"><span data-stu-id="c3cb1-134">The multiplication operator `*` computes the product of its operands:</span></span>

[!code-csharp-interactive[multiplication operator](snippets/shared/ArithmeticOperators.cs#Multiplication)]

<span data-ttu-id="c3cb1-135">El operador unario `*` es el [operador de direccionamiento indirecto del puntero](pointer-related-operators.md#pointer-indirection-operator-).</span><span class="sxs-lookup"><span data-stu-id="c3cb1-135">The unary `*` operator is the [pointer indirection operator](pointer-related-operators.md#pointer-indirection-operator-).</span></span>

## <a name="division-operator-"></a><span data-ttu-id="c3cb1-136">Operador de división /</span><span class="sxs-lookup"><span data-stu-id="c3cb1-136">Division operator /</span></span>

<span data-ttu-id="c3cb1-137">El operador de división `/` divide el operando izquierdo entre el derecho.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-137">The division operator `/` divides its left-hand operand by its right-hand operand.</span></span>

### <a name="integer-division"></a><span data-ttu-id="c3cb1-138">División de enteros</span><span class="sxs-lookup"><span data-stu-id="c3cb1-138">Integer division</span></span>

<span data-ttu-id="c3cb1-139">Para los operandos de tipos enteros, el resultado del operador `/` es de un tipo entero y equivale al cociente de los dos operandos redondeados hacia cero:</span><span class="sxs-lookup"><span data-stu-id="c3cb1-139">For the operands of integer types, the result of the `/` operator is of an integer type and equals the quotient of the two operands rounded towards zero:</span></span>

[!code-csharp-interactive[integer division](snippets/shared/ArithmeticOperators.cs#IntegerDivision)]

<span data-ttu-id="c3cb1-140">Para obtener el cociente de los dos operandos como número de punto flotante, use el tipo `float`, `double` o `decimal`:</span><span class="sxs-lookup"><span data-stu-id="c3cb1-140">To obtain the quotient of the two operands as a floating-point number, use the `float`, `double`, or `decimal` type:</span></span>

[!code-csharp-interactive[integer as floating-point division](snippets/shared/ArithmeticOperators.cs#IntegerAsFloatingPointDivision)]

### <a name="floating-point-division"></a><span data-ttu-id="c3cb1-141">División de punto flotante</span><span class="sxs-lookup"><span data-stu-id="c3cb1-141">Floating-point division</span></span>

<span data-ttu-id="c3cb1-142">Para los tipos `float`, `double` y `decimal`, el resultado del operador `/` es el cociente de los dos operandos:</span><span class="sxs-lookup"><span data-stu-id="c3cb1-142">For the `float`, `double`, and `decimal` types, the result of the `/` operator is the quotient of the two operands:</span></span>

[!code-csharp-interactive[floating-point division](snippets/shared/ArithmeticOperators.cs#FloatingPointDivision)]

<span data-ttu-id="c3cb1-143">Si uno de los operandos es `decimal`, otro operando no puede ser `float` ni `double`, ya que ni `float` ni `double` se convierte de forma implícita a `decimal`.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-143">If one of the operands is `decimal`, another operand can be neither `float` nor `double`, because neither `float` nor `double` is implicitly convertible to `decimal`.</span></span> <span data-ttu-id="c3cb1-144">Debe convertir explícitamente el operando `float` o `double` al tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-144">You must explicitly convert the `float` or `double` operand to the `decimal` type.</span></span> <span data-ttu-id="c3cb1-145">Para obtener más información sobre las conversiones entre tipos numéricos, consulte [Conversiones numéricas integradas](../builtin-types/numeric-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="c3cb1-145">For more information about conversions between numeric types, see [Built-in numeric conversions](../builtin-types/numeric-conversions.md).</span></span>

## <a name="remainder-operator-"></a><span data-ttu-id="c3cb1-146">Operador de resto %</span><span class="sxs-lookup"><span data-stu-id="c3cb1-146">Remainder operator %</span></span>

<span data-ttu-id="c3cb1-147">El operador de resto `%` calcula el resto después de dividir el operando izquierdo entre el derecho.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-147">The remainder operator `%` computes the remainder after dividing its left-hand operand by its right-hand operand.</span></span>

### <a name="integer-remainder"></a><span data-ttu-id="c3cb1-148">Resto entero</span><span class="sxs-lookup"><span data-stu-id="c3cb1-148">Integer remainder</span></span>

<span data-ttu-id="c3cb1-149">En el caso de los operandos de tipos enteros, el resultado de `a % b` es el valor producido por `a - (a / b) * b`.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-149">For the operands of integer types, the result of `a % b` is the value produced by `a - (a / b) * b`.</span></span> <span data-ttu-id="c3cb1-150">El signo de resto distinto de cero es el mismo que el del operando izquierdo, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c3cb1-150">The sign of the non-zero remainder is the same as that of the left-hand operand, as the following example shows:</span></span>

[!code-csharp-interactive[integer remainder](snippets/shared/ArithmeticOperators.cs#IntegerRemainder)]

<span data-ttu-id="c3cb1-151">Use el método <xref:System.Math.DivRem%2A?displayProperty=nameWithType> para calcular los resultados de la división de enteros y del resto.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-151">Use the <xref:System.Math.DivRem%2A?displayProperty=nameWithType> method to compute both integer division and remainder results.</span></span>

### <a name="floating-point-remainder"></a><span data-ttu-id="c3cb1-152">Resto de punto flotante</span><span class="sxs-lookup"><span data-stu-id="c3cb1-152">Floating-point remainder</span></span>

<span data-ttu-id="c3cb1-153">En el caso de los operandos `float` y `double`, el resultado de `x % y` para `x` e `y` finitos es el valor `z`, de modo que</span><span class="sxs-lookup"><span data-stu-id="c3cb1-153">For the `float` and `double` operands, the result of `x % y` for the finite `x` and `y` is the value `z` such that</span></span>

- <span data-ttu-id="c3cb1-154">el signo de `z`, si no es cero, es el mismo que el signo de `x`;</span><span class="sxs-lookup"><span data-stu-id="c3cb1-154">The sign of `z`, if non-zero, is the same as the sign of `x`.</span></span>
- <span data-ttu-id="c3cb1-155">el valor absoluto de `z` es el valor producido por `|x| - n * |y|`, donde `n` es el entero más grande posible que sea menor o igual que `|x| / |y|`, y `|x|` e `|y|` son los valores absolutos de `x` e `y`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-155">The absolute value of `z` is the value produced by `|x| - n * |y|` where `n` is the largest possible integer that is less than or equal to `|x| / |y|` and `|x|` and `|y|` are the absolute values of `x` and `y`, respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="c3cb1-156">Este método de cálculo del resto es análogo al que se usa para los operandos enteros, pero difiere de la especificación IEEE 754.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-156">This method of computing the remainder is analogous to that used for integer operands, but different from the IEEE 754 specification.</span></span> <span data-ttu-id="c3cb1-157">Si necesita la operación de resto conforme con la especificación IEEE 754, use el método <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-157">If you need the remainder operation that complies with the IEEE 754 specification, use the <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="c3cb1-158">Para información sobre el comportamiento del operador `%` con operandos no finitos, vea la sección [Operador de resto](~/_csharplang/spec/expressions.md#remainder-operator) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="c3cb1-158">For information about the behavior of the `%` operator with non-finite operands, see the [Remainder operator](~/_csharplang/spec/expressions.md#remainder-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="c3cb1-159">En el caso de los operandos `decimal`, el operador de resto `%` es equivalente al [operador de resto](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) del tipo <xref:System.Decimal?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-159">For the `decimal` operands, the remainder operator `%` is equivalent to the [remainder operator](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) of the <xref:System.Decimal?displayProperty=nameWithType> type.</span></span>

<span data-ttu-id="c3cb1-160">En el ejemplo siguiente se muestra el comportamiento del operador de resto con operandos de punto flotante:</span><span class="sxs-lookup"><span data-stu-id="c3cb1-160">The following example demonstrates the behavior of the remainder operator with floating-point operands:</span></span>

[!code-csharp-interactive[floating-point remainder](snippets/shared/ArithmeticOperators.cs#FloatingPointRemainder)]

## <a name="addition-operator-"></a><span data-ttu-id="c3cb1-161">Operador de suma +</span><span class="sxs-lookup"><span data-stu-id="c3cb1-161">Addition operator +</span></span>

<span data-ttu-id="c3cb1-162">El operador de suma `+` calcula la suma de sus operandos:</span><span class="sxs-lookup"><span data-stu-id="c3cb1-162">The addition operator `+` computes the sum of its operands:</span></span>

[!code-csharp-interactive[addition operator](snippets/shared/ArithmeticOperators.cs#Addition)]

<span data-ttu-id="c3cb1-163">También puede usar el operador `+` para la concatenación de cadenas y la combinación de delegados.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-163">You can also use the `+` operator for string concatenation and delegate combination.</span></span> <span data-ttu-id="c3cb1-164">Para obtener más información, consulte [Operadores `+` y `+=`](addition-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c3cb1-164">For more information, see the [`+` and `+=` operators](addition-operator.md) article.</span></span>

## <a name="subtraction-operator--"></a><span data-ttu-id="c3cb1-165">Operador de resta -</span><span class="sxs-lookup"><span data-stu-id="c3cb1-165">Subtraction operator -</span></span>

<span data-ttu-id="c3cb1-166">El operador de resta `-` resta el operando derecho del izquierdo:</span><span class="sxs-lookup"><span data-stu-id="c3cb1-166">The subtraction operator `-` subtracts its right-hand operand from its left-hand operand:</span></span>

[!code-csharp-interactive[subtraction operator](snippets/shared/ArithmeticOperators.cs#Subtraction)]

<span data-ttu-id="c3cb1-167">También puede usar el operador `-` para la eliminación de delegados.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-167">You can also use the `-` operator for delegate removal.</span></span> <span data-ttu-id="c3cb1-168">Para obtener más información, consulte [Operadores `-` y `-=`](subtraction-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c3cb1-168">For more information, see the [`-` and `-=` operators](subtraction-operator.md) article.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="c3cb1-169">Asignación compuesta</span><span class="sxs-lookup"><span data-stu-id="c3cb1-169">Compound assignment</span></span>

<span data-ttu-id="c3cb1-170">Para un operador binario `op`, una expresión de asignación compuesta con el formato</span><span class="sxs-lookup"><span data-stu-id="c3cb1-170">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="c3cb1-171">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="c3cb1-171">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="c3cb1-172">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-172">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="c3cb1-173">En el ejemplo siguiente se muestra el uso de la asignación compuesta con operadores aritméticos:</span><span class="sxs-lookup"><span data-stu-id="c3cb1-173">The following example demonstrates the usage of compound assignment with arithmetic operators:</span></span>

[!code-csharp-interactive[compound assignment](snippets/shared/ArithmeticOperators.cs#CompoundAssignment)]

<span data-ttu-id="c3cb1-174">A causa de las [promociones numéricas](~/_csharplang/spec/expressions.md#numeric-promotions), el resultado de la operación `op` podría no ser convertible de forma implícita en el tipo `T` de `x`.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-174">Because of [numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions), the result of the `op` operation might be not implicitly convertible to the type `T` of `x`.</span></span> <span data-ttu-id="c3cb1-175">En tal caso, si `op` es un operador predefinido y el resultado de la operación es convertible de forma explícita en el tipo `T` de `x`, una expresión de asignación compuesta con el formato `x op= y` es equivalente a `x = (T)(x op y)`, excepto que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-175">In such a case, if `op` is a predefined operator and the result of the operation is explicitly convertible to the type `T` of `x`, a compound assignment expression of the form `x op= y` is equivalent to `x = (T)(x op y)`, except that `x` is only evaluated once.</span></span> <span data-ttu-id="c3cb1-176">En el ejemplo siguiente se muestra ese comportamiento:</span><span class="sxs-lookup"><span data-stu-id="c3cb1-176">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[compound assignment with cast](snippets/shared/ArithmeticOperators.cs#CompoundAssignmentWithCast)]

<span data-ttu-id="c3cb1-177">Los operadores `+=` y `-=` también se usan para suscribirse y cancelar la suscripción a un [evento](../keywords/event.md), respectivamente.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-177">You also use the `+=` and `-=` operators to subscribe to and unsubscribe from an [event](../keywords/event.md), respectively.</span></span> <span data-ttu-id="c3cb1-178">Para obtener más información, vea [Procedimiento para suscribir y cancelar la suscripción a eventos](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="c3cb1-178">For more information, see [How to subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-precedence-and-associativity"></a><span data-ttu-id="c3cb1-179">Prioridad y asociatividad de los operadores</span><span class="sxs-lookup"><span data-stu-id="c3cb1-179">Operator precedence and associativity</span></span>

<span data-ttu-id="c3cb1-180">En la lista siguiente se ordenan los operadores aritméticos de la prioridad más alta a la más baja:</span><span class="sxs-lookup"><span data-stu-id="c3cb1-180">The following list orders arithmetic operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="c3cb1-181">Operadores de incremento `x++` y decremento `x--` posfijos</span><span class="sxs-lookup"><span data-stu-id="c3cb1-181">Postfix increment `x++` and decrement `x--` operators</span></span>
- <span data-ttu-id="c3cb1-182">Operadores de incremento `++x` y decremento `--x` prefijos, y operadores unarios `+` y `-`.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-182">Prefix increment `++x` and decrement `--x` and unary `+` and `-` operators</span></span>
- <span data-ttu-id="c3cb1-183">Operadores de multiplicación `*`, `/` y `%`.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-183">Multiplicative `*`, `/`, and `%` operators</span></span>
- <span data-ttu-id="c3cb1-184">Operadores de suma adición `+` y `-`.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-184">Additive `+` and `-` operators</span></span>

<span data-ttu-id="c3cb1-185">Los operadores aritméticos binarios son asociativos a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-185">Binary arithmetic operators are left-associative.</span></span> <span data-ttu-id="c3cb1-186">Es decir, los operadores con el mismo nivel de prioridad se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-186">That is, operators with the same precedence level are evaluated from left to right.</span></span>

<span data-ttu-id="c3cb1-187">Use los paréntesis, `()`, para cambiar el orden de evaluación impuesto por la prioridad y la asociatividad de operadores.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-187">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence and associativity.</span></span>

[!code-csharp-interactive[precedence and associativity](snippets/shared/ArithmeticOperators.cs#PrecedenceAndAssociativity)]

<span data-ttu-id="c3cb1-188">Para obtener la lista completa de los operadores de C# ordenados por nivel de prioridad, vea la sección [Prioridad de operadores](index.md#operator-precedence) del artículo [Operadores de C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="c3cb1-188">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="arithmetic-overflow-and-division-by-zero"></a><span data-ttu-id="c3cb1-189">Desbordamiento aritmético y división por cero</span><span class="sxs-lookup"><span data-stu-id="c3cb1-189">Arithmetic overflow and division by zero</span></span>

<span data-ttu-id="c3cb1-190">Si el resultado de una operación aritmética está fuera del intervalo de valores finitos posibles del tipo numérico implicado, el comportamiento de un operador aritmético depende del tipo de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-190">When the result of an arithmetic operation is outside the range of possible finite values of the involved numeric type, the behavior of an arithmetic operator depends on the type of its operands.</span></span>

### <a name="integer-arithmetic-overflow"></a><span data-ttu-id="c3cb1-191">Desbordamiento aritmético de enteros</span><span class="sxs-lookup"><span data-stu-id="c3cb1-191">Integer arithmetic overflow</span></span>

<span data-ttu-id="c3cb1-192">La división de enteros por cero siempre produce una <xref:System.DivideByZeroException>.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-192">Integer division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

<span data-ttu-id="c3cb1-193">En el caso de desbordamiento aritmético de enteros, el comportamiento resultante lo controla un contexto de comprobación de desbordamiento, que puede ser [comprobado o no comprobado](../keywords/checked-and-unchecked.md):</span><span class="sxs-lookup"><span data-stu-id="c3cb1-193">In case of integer arithmetic overflow, an overflow checking context, which can be [checked or unchecked](../keywords/checked-and-unchecked.md), controls the resulting behavior:</span></span>

- <span data-ttu-id="c3cb1-194">En un contexto comprobado, si el desbordamiento se produce en una expresión constante, se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-194">In a checked context, if overflow happens in a constant expression, a compile-time error occurs.</span></span> <span data-ttu-id="c3cb1-195">De lo contrario, si la operación se realiza en tiempo de ejecución, se inicia una excepción <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-195">Otherwise, when the operation is performed at run time, an <xref:System.OverflowException> is thrown.</span></span>
- <span data-ttu-id="c3cb1-196">En un contexto no comprobado, el resultado se trunca mediante el descarte de los bits de orden superior que no caben en el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-196">In an unchecked context, the result is truncated by discarding any high-order bits that don't fit in the destination type.</span></span>

<span data-ttu-id="c3cb1-197">Junto con las instrucciones [comprobadas y no comprobadas](../keywords/checked-and-unchecked.md), puede usar los operadores `checked` y `unchecked` para controlar el contexto de comprobación de desbordamiento, en el que se evalúa una expresión:</span><span class="sxs-lookup"><span data-stu-id="c3cb1-197">Along with the [checked and unchecked](../keywords/checked-and-unchecked.md) statements, you can use the `checked` and `unchecked` operators to control the overflow checking context, in which an expression is evaluated:</span></span>

[!code-csharp-interactive[checked and unchecked](snippets/shared/ArithmeticOperators.cs#CheckedUnchecked)]

<span data-ttu-id="c3cb1-198">De forma predeterminada, las operaciones aritméticas se producen en un contexto *no comprobado*.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-198">By default, arithmetic operations occur in an *unchecked* context.</span></span>

### <a name="floating-point-arithmetic-overflow"></a><span data-ttu-id="c3cb1-199">Desbordamiento aritmético de punto flotante</span><span class="sxs-lookup"><span data-stu-id="c3cb1-199">Floating-point arithmetic overflow</span></span>

<span data-ttu-id="c3cb1-200">Las operaciones aritméticas con los tipos `float` y `double` nunca inician una excepción.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-200">Arithmetic operations with the `float` and `double` types never throw an exception.</span></span> <span data-ttu-id="c3cb1-201">El resultado de las operaciones aritméticas con esos tipos puede ser uno de varios valores especiales que representan infinito y no un número:</span><span class="sxs-lookup"><span data-stu-id="c3cb1-201">The result of arithmetic operations with those types can be one of special values that represent infinity and not-a-number:</span></span>

[!code-csharp-interactive[double non-finite values](snippets/shared/ArithmeticOperators.cs#FloatingPointOverflow)]

<span data-ttu-id="c3cb1-202">Para los operandos del tipo `decimal`, el desbordamiento aritmético siempre inicia una excepción <xref:System.OverflowException> y la división por cero siempre inicia una excepción <xref:System.DivideByZeroException>.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-202">For the operands of the `decimal` type, arithmetic overflow always throws an <xref:System.OverflowException> and division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

## <a name="round-off-errors"></a><span data-ttu-id="c3cb1-203">Errores de redondeo</span><span class="sxs-lookup"><span data-stu-id="c3cb1-203">Round-off errors</span></span>

<span data-ttu-id="c3cb1-204">Debido a las limitaciones generales de la representación de punto flotante de los números reales y la aritmética de punto flotante, es posible que se produzcan errores de redondeo en los cálculos con tipos de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-204">Because of general limitations of the floating-point representation of real numbers and floating-point arithmetic, round-off errors might occur in calculations with floating-point types.</span></span> <span data-ttu-id="c3cb1-205">Es decir, es posible que el resultado de una expresión difiera del resultado matemático esperado.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-205">That is, the produced result of an expression might differ from the expected mathematical result.</span></span> <span data-ttu-id="c3cb1-206">En el ejemplo siguiente se muestran varios de estos casos:</span><span class="sxs-lookup"><span data-stu-id="c3cb1-206">The following example demonstrates several such cases:</span></span>

[!code-csharp-interactive[round-off errors](snippets/shared/ArithmeticOperators.cs#RoundOffErrors)]

<span data-ttu-id="c3cb1-207">Para más información, vea los comentarios en las páginas de referencia de [System.Double](/dotnet/api/system.double#remarks), [System.Single](/dotnet/api/system.single#remarks) o [System.Decimal](/dotnet/api/system.decimal#remarks).</span><span class="sxs-lookup"><span data-stu-id="c3cb1-207">For more information, see remarks at the [System.Double](/dotnet/api/system.double#remarks), [System.Single](/dotnet/api/system.single#remarks), or [System.Decimal](/dotnet/api/system.decimal#remarks) reference pages.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="c3cb1-208">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="c3cb1-208">Operator overloadability</span></span>

<span data-ttu-id="c3cb1-209">Un tipo definido por el usuario puede [sobrecargar](operator-overloading.md) los operadores unarios (`++`, `--`, `+` y `-`), los operadores binarios (`*`, `/`, `%`, `+` y `-`) y los operadores aritméticos.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-209">A user-defined type can [overload](operator-overloading.md) the unary (`++`, `--`, `+`, and `-`) and binary (`*`, `/`, `%`, `+`, and `-`) arithmetic operators.</span></span> <span data-ttu-id="c3cb1-210">Cuando se sobrecarga un operador binario, también se sobrecarga de forma implícita el operador de asignación compuesta correspondiente.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-210">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="c3cb1-211">Un tipo definido por el usuario no puede sobrecargar de forma explícita un operador de asignación compuesta.</span><span class="sxs-lookup"><span data-stu-id="c3cb1-211">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c3cb1-212">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c3cb1-212">C# language specification</span></span>

<span data-ttu-id="c3cb1-213">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="c3cb1-213">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="c3cb1-214">Operadores de incremento y decremento posfijos</span><span class="sxs-lookup"><span data-stu-id="c3cb1-214">Postfix increment and decrement operators</span></span>](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators)
- [<span data-ttu-id="c3cb1-215">Operadores de incremento y decremento prefijos</span><span class="sxs-lookup"><span data-stu-id="c3cb1-215">Prefix increment and decrement operators</span></span>](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators)
- [<span data-ttu-id="c3cb1-216">Operador unario más</span><span class="sxs-lookup"><span data-stu-id="c3cb1-216">Unary plus operator</span></span>](~/_csharplang/spec/expressions.md#unary-plus-operator)
- [<span data-ttu-id="c3cb1-217">Operador unario menos</span><span class="sxs-lookup"><span data-stu-id="c3cb1-217">Unary minus operator</span></span>](~/_csharplang/spec/expressions.md#unary-minus-operator)
- [<span data-ttu-id="c3cb1-218">Operador de multiplicación</span><span class="sxs-lookup"><span data-stu-id="c3cb1-218">Multiplication operator</span></span>](~/_csharplang/spec/expressions.md#multiplication-operator)
- [<span data-ttu-id="c3cb1-219">Operador de división</span><span class="sxs-lookup"><span data-stu-id="c3cb1-219">Division operator</span></span>](~/_csharplang/spec/expressions.md#division-operator)
- [<span data-ttu-id="c3cb1-220">Operador de resto</span><span class="sxs-lookup"><span data-stu-id="c3cb1-220">Remainder operator</span></span>](~/_csharplang/spec/expressions.md#remainder-operator)
- [<span data-ttu-id="c3cb1-221">Operador de suma</span><span class="sxs-lookup"><span data-stu-id="c3cb1-221">Addition operator</span></span>](~/_csharplang/spec/expressions.md#addition-operator)
- [<span data-ttu-id="c3cb1-222">Operador de resta</span><span class="sxs-lookup"><span data-stu-id="c3cb1-222">Subtraction operator</span></span>](~/_csharplang/spec/expressions.md#subtraction-operator)
- [<span data-ttu-id="c3cb1-223">Asignación compuesta</span><span class="sxs-lookup"><span data-stu-id="c3cb1-223">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)
- [<span data-ttu-id="c3cb1-224">Operadores checked y unchecked</span><span class="sxs-lookup"><span data-stu-id="c3cb1-224">The checked and unchecked operators</span></span>](~/_csharplang/spec/expressions.md#the-checked-and-unchecked-operators)
- [<span data-ttu-id="c3cb1-225">Promociones numéricas</span><span class="sxs-lookup"><span data-stu-id="c3cb1-225">Numeric promotions</span></span>](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a><span data-ttu-id="c3cb1-226">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3cb1-226">See also</span></span>

- [<span data-ttu-id="c3cb1-227">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="c3cb1-227">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c3cb1-228">Operadores y expresiones de C#</span><span class="sxs-lookup"><span data-stu-id="c3cb1-228">C# operators and expressions</span></span>](index.md)
- <xref:System.Math?displayProperty=nameWithType>
- <xref:System.MathF?displayProperty=nameWithType>
- [<span data-ttu-id="c3cb1-229">Valores numéricos en .NET</span><span class="sxs-lookup"><span data-stu-id="c3cb1-229">Numerics in .NET</span></span>](../../../standard/numerics.md)
