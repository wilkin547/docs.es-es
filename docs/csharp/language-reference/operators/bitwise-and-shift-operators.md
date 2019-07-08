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
ms.openlocfilehash: c18a06971887049a443f0bd1af7c77610a787a27
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2019
ms.locfileid: "67609952"
---
# <a name="bitwise-and-shift-operators-c-reference"></a><span data-ttu-id="bfbb4-103">Operadores de desplazamiento y bit a bit (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="bfbb4-103">Bitwise and shift operators (C# reference)</span></span>

<span data-ttu-id="bfbb4-104">Los siguientes operadores realizan operaciones de desplazamiento o bit a bit con operandos de [tipo entero](../builtin-types/integral-numeric-types.md):</span><span class="sxs-lookup"><span data-stu-id="bfbb4-104">The following operators perform bitwise or shift operations with operands of the [integral types](../builtin-types/integral-numeric-types.md):</span></span>

- <span data-ttu-id="bfbb4-105">Operador unario [`~` (complemento bit a bit)](#bitwise-complement-operator-)</span><span class="sxs-lookup"><span data-stu-id="bfbb4-105">Unary [`~` (bitwise complement)](#bitwise-complement-operator-) operator</span></span>
- <span data-ttu-id="bfbb4-106">Operadores de desplazamiento binarios [`<<` (desplazamiento izquierdo)](#left-shift-operator-) y [`>>` (desplazamiento derecho)](#right-shift-operator-)</span><span class="sxs-lookup"><span data-stu-id="bfbb4-106">Binary [`<<` (left shift)](#left-shift-operator-) and [`>>` (right shift)](#right-shift-operator-) shift operators</span></span>
- <span data-ttu-id="bfbb4-107">Operadores binarios [`&` (AND lógico)](#logical-and-operator-), [`|` (OR lógico)](#logical-or-operator-) y [`^` (OR exclusivo lógico)](#logical-exclusive-or-operator-)</span><span class="sxs-lookup"><span data-stu-id="bfbb4-107">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators</span></span>

<span data-ttu-id="bfbb4-108">Estos operadores se definen para los tipos `int`, `uint`, `long` y `ulong`.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-108">Those operators are defined for the `int`, `uint`, `long`, and `ulong` types.</span></span> <span data-ttu-id="bfbb4-109">Cuando ambos operandos son de otro tipo entero (`sbyte`, `byte`, `short`, `ushort` o `char`), sus valores se convierten en el tipo `int`, que también es el tipo de resultado de una operación.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-109">When both operands are of other integral types (`sbyte`, `byte`, `short`, `ushort`, or `char`), their values are converted to the `int` type, which is also the result type of an operation.</span></span> <span data-ttu-id="bfbb4-110">Cuando los operandos son de tipo entero diferente, sus valores se convierten en el tipo entero más cercano que contenga.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-110">When operands are of different integral types, their values are converted to the closest containing integral type.</span></span> <span data-ttu-id="bfbb4-111">Para obtener más información, vea la sección [Promociones numéricas](~/_csharplang/spec/expressions.md#numeric-promotions) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="bfbb4-111">For more information, see the [Numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="bfbb4-112">Los operadores `&`, `|` y `^` también se definen para los operandos de tipo `bool`.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-112">The `&`, `|`, and `^` operators are also defined for the operands of the `bool` type.</span></span> <span data-ttu-id="bfbb4-113">Para obtener más información, vea [Operadores lógicos booleanos](boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="bfbb4-113">For more information, see [Boolean logical operators](boolean-logical-operators.md).</span></span>

<span data-ttu-id="bfbb4-114">Las operaciones de desplazamiento y bit a bit nunca producen desbordamiento y generan los mismos resultados en contextos [Checked y Unchecked](../keywords/checked-and-unchecked.md).</span><span class="sxs-lookup"><span data-stu-id="bfbb4-114">Bitwise and shift operations never cause overflow and produce the same results in [checked and unchecked](../keywords/checked-and-unchecked.md) contexts.</span></span>

## <a name="bitwise-complement-operator-"></a><span data-ttu-id="bfbb4-115">Operador de complemento bit a bit ~</span><span class="sxs-lookup"><span data-stu-id="bfbb4-115">Bitwise complement operator ~</span></span>

<span data-ttu-id="bfbb4-116">El operador `~` genera un complemento bit a bit de su operando al invertir cada bit:</span><span class="sxs-lookup"><span data-stu-id="bfbb4-116">The `~` operator produces a bitwise complement of its operand by reversing each bit:</span></span>

[!code-csharp-interactive[bitwise NOT](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseComplement)]

<span data-ttu-id="bfbb4-117">También se puede usar el símbolo `~` para declarar finalizadores.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-117">You can also use the `~` symbol to declare finalizers.</span></span> <span data-ttu-id="bfbb4-118">Para obtener más información, vea [Finalizadores](../../programming-guide/classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="bfbb4-118">For more information, see [Finalizers](../../programming-guide/classes-and-structs/destructors.md).</span></span>

## <a name="left-shift-operator-"></a><span data-ttu-id="bfbb4-119">Operador de desplazamiento izquierdo \<\<</span><span class="sxs-lookup"><span data-stu-id="bfbb4-119">Left-shift operator \<\<</span></span>

<span data-ttu-id="bfbb4-120">El operador `<<` desplaza el operando izquierdo a la izquierda el número de bits definido por el operando derecho.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-120">The `<<` operator shifts its left-hand operand left by the number of bits defined by its right-hand operand.</span></span>

<span data-ttu-id="bfbb4-121">La operación de desplazamiento izquierdo descarta los bits de orden superior que están fuera del rango del tipo de resultado y establece las posiciones de bits vacías de orden inferior en cero, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfbb4-121">The left-shift operation discards the high-order bits that are outside the range of the result type and sets the low-order empty bit positions to zero, as the following example shows:</span></span>

[!code-csharp-interactive[left shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LeftShift)]

<span data-ttu-id="bfbb4-122">Dado que los operadores de desplazamiento solo se definen para los tipos `int`, `uint`, `long` y `ulong`, el resultado de una operación siempre contiene al menos 32 bits.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-122">Because the shift operators are defined only for the `int`, `uint`, `long`, and `ulong` types, the result of an operation always contains at least 32 bits.</span></span> <span data-ttu-id="bfbb4-123">Si el operando izquierdo es de otro tipo entero (`sbyte`, `byte`, `short`, `ushort` o `char`), su valor se convierte al tipo `int`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfbb4-123">If the left-hand operand is of another integral type (`sbyte`, `byte`, `short`, `ushort`, or `char`), its value is converted to the `int` type, as the following example shows:</span></span>

[!code-csharp-interactive[left shift with promotion](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LeftShiftPromoted)]

<span data-ttu-id="bfbb4-124">Para obtener información sobre cómo el operando derecho del operador `<<` define el recuento de desplazamiento, vea la sección [Recuento de desplazamiento de los operadores de desplazamiento](#shift-count-of-the-shift-operators).</span><span class="sxs-lookup"><span data-stu-id="bfbb4-124">For information about how the right-hand operand of the `<<` operator defines the shift count, see the [Shift count of the shift operators](#shift-count-of-the-shift-operators) section.</span></span>

## <a name="right-shift-operator-"></a><span data-ttu-id="bfbb4-125">Operador de desplazamiento derecho >></span><span class="sxs-lookup"><span data-stu-id="bfbb4-125">Right-shift operator >></span></span>

<span data-ttu-id="bfbb4-126">El operador `>>` desplaza el operando izquierdo a la derecha el número de bits definido por el operando derecho.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-126">The `>>` operator shifts its left-hand operand right by the number of bits defined by its right-hand operand.</span></span>

<span data-ttu-id="bfbb4-127">La operación de desplazamiento derecho descarta los bits de orden inferior, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfbb4-127">The right-shift operation discards the low-order bits, as the following example shows:</span></span>

[!code-csharp-interactive[right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#RightShift)]

<span data-ttu-id="bfbb4-128">Las posiciones de bits vacíos de orden superior se establecen basándose en el tipo del operando izquierdo, tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="bfbb4-128">The high-order empty bit positions are set based on the type of the left-hand operand as follows:</span></span>

- <span data-ttu-id="bfbb4-129">Si el operando izquierdo es de tipo [int](../builtin-types/integral-numeric-types.md) o [long](../builtin-types/integral-numeric-types.md), el operador de desplazamiento a la derecha realiza un desplazamiento *aritmético*: el valor del bit más significativo (el bit de signo) del operando izquierdo se propaga a las posiciones de bits vacíos de orden superior.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-129">If the left-hand operand is of type [int](../builtin-types/integral-numeric-types.md) or [long](../builtin-types/integral-numeric-types.md), the right-shift operator performs an *arithmetic* shift: the value of the most significant bit (the sign bit) of the left-hand operand is propagated to the high-order empty bit positions.</span></span> <span data-ttu-id="bfbb4-130">Es decir, las posiciones de bits vacíos de orden superior se establecen en cero si el operando izquierdo no es negativo y, en caso de serlo, se establecen en uno.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-130">That is, the high-order empty bit positions are set to zero if the left-hand operand is non-negative and set to one if it's negative.</span></span>

  [!code-csharp-interactive[arithmetic right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#ArithmeticRightShift)]

- <span data-ttu-id="bfbb4-131">Si el operando izquierdo es de tipo [uint](../builtin-types/integral-numeric-types.md) o [ulong](../builtin-types/integral-numeric-types.md), el operador de desplazamiento a la derecha realiza un desplazamiento *lógico*: las posiciones de bits vacíos de orden superior se establecen siempre en cero.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-131">If the left-hand operand is of type [uint](../builtin-types/integral-numeric-types.md) or [ulong](../builtin-types/integral-numeric-types.md), the right-shift operator performs a *logical* shift: the high-order empty bit positions are always set to zero.</span></span>

  [!code-csharp-interactive[logical right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LogicalRightShift)]

<span data-ttu-id="bfbb4-132">Para obtener información sobre cómo el operando derecho del operador `>>` define el recuento de desplazamiento, vea la sección [Recuento de desplazamiento de los operadores de desplazamiento](#shift-count-of-the-shift-operators).</span><span class="sxs-lookup"><span data-stu-id="bfbb4-132">For information about how the right-hand operand of the `>>` operator defines the shift count, see the [Shift count of the shift operators](#shift-count-of-the-shift-operators) section.</span></span>

## <a name="logical-and-operator-"></a> <span data-ttu-id="bfbb4-133">Operador AND lógico &amp;</span><span class="sxs-lookup"><span data-stu-id="bfbb4-133">Logical AND operator &amp;</span></span>

<span data-ttu-id="bfbb4-134">El operador `&` calcula el AND lógico bit a bit de sus operandos:</span><span class="sxs-lookup"><span data-stu-id="bfbb4-134">The `&` operator computes the bitwise logical AND of its operands:</span></span>

[!code-csharp-interactive[bitwise AND](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseAnd)]

<span data-ttu-id="bfbb4-135">En el caso de los operandos de tipo `bool`, el operador `&` calcula el [AND lógico](boolean-logical-operators.md#logical-and-operator-) de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-135">For the operands of the `bool` type, the `&` operator computes the [logical AND](boolean-logical-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="bfbb4-136">El operador `&` unario es el [operador address-of](pointer-related-operators.md#address-of-operator-).</span><span class="sxs-lookup"><span data-stu-id="bfbb4-136">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="bfbb4-137">Operador IR exclusivo lógico ^</span><span class="sxs-lookup"><span data-stu-id="bfbb4-137">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="bfbb4-138">El operador `^` calcula el OR exclusivo lógico bit a bit, también conocido como XOR lógico bit a bit, de sus operandos:</span><span class="sxs-lookup"><span data-stu-id="bfbb4-138">The `^` operator computes the bitwise logical exclusive OR, also known as the bitwise logical XOR, of its operands:</span></span>

[!code-csharp-interactive[bitwise XOR](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseXor)]

<span data-ttu-id="bfbb4-139">En el caso de los operandos de tipo `bool`, el operador `^` calcula el [OR exclusivo lógico](boolean-logical-operators.md#logical-exclusive-or-operator-) de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-139">For the operands of the `bool` type, the `^` operator computes the [logical exclusive OR](boolean-logical-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="bfbb4-140">Operador lógico OR |</span><span class="sxs-lookup"><span data-stu-id="bfbb4-140">Logical OR operator |</span></span>

<span data-ttu-id="bfbb4-141">El operador `|` calcula el OR lógico bit a bit de sus operandos:</span><span class="sxs-lookup"><span data-stu-id="bfbb4-141">The `|` operator computes the bitwise logical OR of its operands:</span></span>

[!code-csharp-interactive[bitwise OR](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseOr)]

<span data-ttu-id="bfbb4-142">En el caso de los operandos de tipo `bool`, el operador `|` calcula el [OR lógico](boolean-logical-operators.md#logical-or-operator-) de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-142">For the operands of the `bool` type, the `|` operator computes the [logical OR](boolean-logical-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="bfbb4-143">Asignación compuesta</span><span class="sxs-lookup"><span data-stu-id="bfbb4-143">Compound assignment</span></span>

<span data-ttu-id="bfbb4-144">Para un operador binario `op`, una expresión de asignación compuesta con el formato</span><span class="sxs-lookup"><span data-stu-id="bfbb4-144">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="bfbb4-145">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="bfbb4-145">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="bfbb4-146">salvo que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-146">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="bfbb4-147">En el ejemplo siguiente se muestra el uso de la asignación compuesta con operadores de desplazamiento y bit a bit:</span><span class="sxs-lookup"><span data-stu-id="bfbb4-147">The following example demonstrates the usage of compound assignment with bitwise and shift operators:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#CompoundAssignment)]

<span data-ttu-id="bfbb4-148">A causa de las [promociones numéricas](~/_csharplang/spec/expressions.md#numeric-promotions), el resultado de la operación `op` podría no ser convertible de forma implícita en el tipo `T` de `x`.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-148">Because of [numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions), the result of the `op` operation might be not implicitly convertible to the type `T` of `x`.</span></span> <span data-ttu-id="bfbb4-149">En tal caso, si `op` es un operador predefinido y el resultado de la operación es convertible de forma explícita en el tipo `T` de `x`, una expresión de asignación compuesta con el formato `x op= y` es equivalente a `x = (T)(x op y)`, excepto que `x` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-149">In such a case, if `op` is a predefined operator and the result of the operation is explicitly convertible to the type `T` of `x`, a compound assignment expression of the form `x op= y` is equivalent to `x = (T)(x op y)`, except that `x` is only evaluated once.</span></span> <span data-ttu-id="bfbb4-150">En el ejemplo siguiente se muestra ese comportamiento:</span><span class="sxs-lookup"><span data-stu-id="bfbb4-150">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[compound assignment with cast](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#CompoundAssignmentWithCast)]

## <a name="operator-precedence"></a><span data-ttu-id="bfbb4-151">Prioridad de operadores</span><span class="sxs-lookup"><span data-stu-id="bfbb4-151">Operator precedence</span></span>

<span data-ttu-id="bfbb4-152">En la lista siguiente se ordenan los operadores de desplazamiento y bit a bit desde la prioridad más alta a la más baja:</span><span class="sxs-lookup"><span data-stu-id="bfbb4-152">The following list orders bitwise and shift operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="bfbb4-153">Operador de complemento bit a bit `~`</span><span class="sxs-lookup"><span data-stu-id="bfbb4-153">Bitwise complement operator `~`</span></span>
- <span data-ttu-id="bfbb4-154">Operadores de desplazamiento `<<` y `>>`</span><span class="sxs-lookup"><span data-stu-id="bfbb4-154">Shift operators `<<` and `>>`</span></span>
- <span data-ttu-id="bfbb4-155">Operador AND lógico `&`</span><span class="sxs-lookup"><span data-stu-id="bfbb4-155">Logical AND operator `&`</span></span>
- <span data-ttu-id="bfbb4-156">Operador OR exclusivo lógico `^`</span><span class="sxs-lookup"><span data-stu-id="bfbb4-156">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="bfbb4-157">Operador OR lógico `|`</span><span class="sxs-lookup"><span data-stu-id="bfbb4-157">Logical OR operator `|`</span></span>

<span data-ttu-id="bfbb4-158">Use los paréntesis, `()`, para cambiar el orden de evaluación impuesto por la prioridad de los operadores:</span><span class="sxs-lookup"><span data-stu-id="bfbb4-158">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#Precedence)]

<span data-ttu-id="bfbb4-159">Para obtener la lista completa de los operadores de C# ordenados por nivel de prioridad, vea [Operadores de C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="bfbb4-159">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="shift-count-of-the-shift-operators"></a><span data-ttu-id="bfbb4-160">Recuento de desplazamiento de los operadores de desplazamiento</span><span class="sxs-lookup"><span data-stu-id="bfbb4-160">Shift count of the shift operators</span></span>

<span data-ttu-id="bfbb4-161">En el caso de los operadores de desplazamiento `<<` y `>>`, el tipo del operando derecho debe ser [int](../builtin-types/integral-numeric-types.md) o un tipo que tenga una [conversión numérica implícita predefinida](../keywords/implicit-numeric-conversions-table.md) en `int`.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-161">For the shift operators `<<` and `>>`, the type of the right-hand operand must be [int](../builtin-types/integral-numeric-types.md) or a type that has a [predefined implicit numeric conversion](../keywords/implicit-numeric-conversions-table.md) to `int`.</span></span>

<span data-ttu-id="bfbb4-162">En el caso de las expresiones `x << count` y `x >> count`, el recuento de desplazamiento real depende del tipo de `x`, de esta forma:</span><span class="sxs-lookup"><span data-stu-id="bfbb4-162">For the `x << count` and `x >> count` expressions, the actual shift count depends on the type of `x` as follows:</span></span>

- <span data-ttu-id="bfbb4-163">Si el tipo de `x` es [int](../builtin-types/integral-numeric-types.md) o [uint](../builtin-types/integral-numeric-types.md), el recuento de desplazamiento viene definido por los *cinco* bits de orden inferior del operando derecho.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-163">If the type of `x` is [int](../builtin-types/integral-numeric-types.md) or [uint](../builtin-types/integral-numeric-types.md), the shift count is defined by the low-order *five* bits of the right-hand operand.</span></span> <span data-ttu-id="bfbb4-164">Es decir, el valor de desplazamiento se calcula a partir de `count & 0x1F` (o `count & 0b_1_1111`).</span><span class="sxs-lookup"><span data-stu-id="bfbb4-164">That is, the shift count is computed from `count & 0x1F` (or `count & 0b_1_1111`).</span></span>

- <span data-ttu-id="bfbb4-165">Si el tipo de `x` es [long](../builtin-types/integral-numeric-types.md) o [ulong](../builtin-types/integral-numeric-types.md), el recuento de desplazamiento viene definido por los *seis* bits de orden inferior del operando derecho.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-165">If the type of `x` is [long](../builtin-types/integral-numeric-types.md) or [ulong](../builtin-types/integral-numeric-types.md), the shift count is defined by the low-order *six* bits of the right-hand operand.</span></span> <span data-ttu-id="bfbb4-166">Es decir, el valor de desplazamiento se calcula a partir de `count & 0x3F` (o `count & 0b_11_1111`).</span><span class="sxs-lookup"><span data-stu-id="bfbb4-166">That is, the shift count is computed from `count & 0x3F` (or `count & 0b_11_1111`).</span></span>

<span data-ttu-id="bfbb4-167">En el ejemplo siguiente se muestra ese comportamiento:</span><span class="sxs-lookup"><span data-stu-id="bfbb4-167">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[shift count example](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#ShiftCount)]

## <a name="enumeration-logical-operators"></a><span data-ttu-id="bfbb4-168">Operadores lógicos de enumeración</span><span class="sxs-lookup"><span data-stu-id="bfbb4-168">Enumeration logical operators</span></span>

<span data-ttu-id="bfbb4-169">Los operadores `~`, `&`, `|` y `^` también se definen para cualquier tipo de [enumeración](../keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="bfbb4-169">The `~`, `&`, `|`, and `^` operators are also defined for any [enumeration](../keywords/enum.md) type.</span></span> <span data-ttu-id="bfbb4-170">En el caso de los operandos del mismo tipo de enumeración, se realiza una operación lógica en los valores correspondientes del tipo entero subyacente.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-170">For the operands of the same enumeration type, a logical operation is performed on the corresponding values of the underlying integral type.</span></span> <span data-ttu-id="bfbb4-171">Por ejemplo, para cualquier `x` e `y` de un tipo de enumeración `T` con un tipo subyacente `U`, la expresión `x & y` produce el mismo resultado que la expresión `(T)((U)x & (U)y)`.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-171">For example, for any `x` and `y` of an enumeration type `T` with an underlying type `U`, the `x & y` expression produces the same result as the `(T)((U)x & (U)y)` expression.</span></span>

<span data-ttu-id="bfbb4-172">Normalmente, los operadores lógicos bit a bit se usan con un tipo de enumeración definido con el atributo [Flags](xref:System.FlagsAttribute).</span><span class="sxs-lookup"><span data-stu-id="bfbb4-172">You typically use bitwise logical operators with an enumeration type which is defined with the [Flags](xref:System.FlagsAttribute) attribute.</span></span> <span data-ttu-id="bfbb4-173">Para obtener más información, vea la sección [Tipos de enumeración como marcas de bits](../../programming-guide/enumeration-types.md#enumeration-types-as-bit-flags) del artículo [Tipos de enumeración](../../programming-guide/enumeration-types.md).</span><span class="sxs-lookup"><span data-stu-id="bfbb4-173">For more information, see the [Enumeration types as bit flags](../../programming-guide/enumeration-types.md#enumeration-types-as-bit-flags) section of the [Enumeration types](../../programming-guide/enumeration-types.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="bfbb4-174">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="bfbb4-174">Operator overloadability</span></span>

<span data-ttu-id="bfbb4-175">Un tipo definido por el usuario puede [sobrecargar](operator-overloading.md) los operadores `~`, `<<`, `>>`, `&`, `|` y `^`.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-175">A user-defined type can [overload](operator-overloading.md) the `~`, `<<`, `>>`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="bfbb4-176">Cuando se sobrecarga un operador binario, también se sobrecarga de forma implícita el operador de asignación compuesta correspondiente.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-176">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="bfbb4-177">Un tipo definido por el usuario no puede sobrecargar de forma explícita un operador de asignación compuesta.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-177">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="bfbb4-178">Si un tipo definido por el usuario `T` sobrecarga el operador `<<` o `>>`, el tipo del operando izquierdo debe ser `T` y el del derecho `int`.</span><span class="sxs-lookup"><span data-stu-id="bfbb4-178">If a user-defined type `T` overloads the `<<` or `>>` operator, the type of the left-hand operand must be `T` and the type of the right-hand operand must be `int`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bfbb4-179">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="bfbb4-179">C# language specification</span></span>

<span data-ttu-id="bfbb4-180">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="bfbb4-180">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="bfbb4-181">Operador de complemento bit a bit</span><span class="sxs-lookup"><span data-stu-id="bfbb4-181">Bitwise complement operator</span></span>](~/_csharplang/spec/expressions.md#bitwise-complement-operator)
- [<span data-ttu-id="bfbb4-182">Operadores de desplazamiento</span><span class="sxs-lookup"><span data-stu-id="bfbb4-182">Shift operators</span></span>](~/_csharplang/spec/expressions.md#shift-operators)
- [<span data-ttu-id="bfbb4-183">Operadores lógicos</span><span class="sxs-lookup"><span data-stu-id="bfbb4-183">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="bfbb4-184">Asignación compuesta</span><span class="sxs-lookup"><span data-stu-id="bfbb4-184">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)
- [<span data-ttu-id="bfbb4-185">Promociones numéricas</span><span class="sxs-lookup"><span data-stu-id="bfbb4-185">Numeric promotions</span></span>](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a><span data-ttu-id="bfbb4-186">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfbb4-186">See also</span></span>

- [<span data-ttu-id="bfbb4-187">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="bfbb4-187">C# reference</span></span>](../index.md)
- [<span data-ttu-id="bfbb4-188">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="bfbb4-188">C# operators</span></span>](index.md)
- [<span data-ttu-id="bfbb4-189">Operadores lógicos booleanos</span><span class="sxs-lookup"><span data-stu-id="bfbb4-189">Boolean logical operators</span></span>](boolean-logical-operators.md)
