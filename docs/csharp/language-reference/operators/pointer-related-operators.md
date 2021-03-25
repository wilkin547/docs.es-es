---
title: Operadores relacionados con el puntero (referencia de C#)
description: Obtenga información sobre los operadores de C# que se pueden usar al trabajar con punteros.
ms.date: 05/20/2019
author: pkulikov
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- pointer related operators [C#]
- address-of operator [C#]
- '& operator [C#]'
- pointer indirection operator [C#]
- dereference operator [C#]
- '* operator [C#]'
- pointer member access operator [C#]
- -> operator [C#]
- pointer element access [C#]
- '[] operator [C#]'
- pointer arithmetic [C#]
- pointer increment [C#]
- pointer decrement [C#]
- pointer comparison [C#]
ms.openlocfilehash: 2d522e9357fb6da7b8d66a663e99e8858c9dd521
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103480383"
---
# <a name="pointer-related-operators-c-reference"></a><span data-ttu-id="38c55-103">Operadores relacionados con el puntero (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="38c55-103">Pointer related operators (C# reference)</span></span>

<span data-ttu-id="38c55-104">Puede usar los siguientes operadores para trabajar con punteros:</span><span class="sxs-lookup"><span data-stu-id="38c55-104">You can use the following operators to work with pointers:</span></span>

- <span data-ttu-id="38c55-105">Operador unario [`&` (address-of)](#address-of-operator-): para obtener la dirección de una variable</span><span class="sxs-lookup"><span data-stu-id="38c55-105">Unary [`&` (address-of)](#address-of-operator-) operator: to get the address of a variable</span></span>
- <span data-ttu-id="38c55-106">Operador unario [`*` (direccionamiento indirecto del puntero)](#pointer-indirection-operator-): para obtener la variable a la que apunta un puntero</span><span class="sxs-lookup"><span data-stu-id="38c55-106">Unary [`*` (pointer indirection)](#pointer-indirection-operator-) operator: to obtain the variable pointed by a pointer</span></span>
- <span data-ttu-id="38c55-107">Operadores [`->` (acceso a miembros)](#pointer-member-access-operator--) y [`[]` (acceso de elemento)](#pointer-element-access-operator-)</span><span class="sxs-lookup"><span data-stu-id="38c55-107">The [`->` (member access)](#pointer-member-access-operator--) and [`[]` (element access)](#pointer-element-access-operator-) operators</span></span>
- <span data-ttu-id="38c55-108">Operadores aritméticos [`+`, `-`, `++` y `--`](#pointer-arithmetic-operators)</span><span class="sxs-lookup"><span data-stu-id="38c55-108">Arithmetic operators [`+`, `-`, `++`, and `--`](#pointer-arithmetic-operators)</span></span>
- <span data-ttu-id="38c55-109">Operadores de comparación [`==`, `!=`, `<`, `>`, `<=` y `>=`](#pointer-comparison-operators)</span><span class="sxs-lookup"><span data-stu-id="38c55-109">Comparison operators [`==`, `!=`, `<`, `>`, `<=`, and `>=`](#pointer-comparison-operators)</span></span>

<span data-ttu-id="38c55-110">Para obtener información sobre los tipos de punteros, vea [Tipos de puntero](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="38c55-110">For information about pointer types, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

> [!NOTE]
> <span data-ttu-id="38c55-111">Cualquier operación con punteros requiere un contexto [unsafe](../keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="38c55-111">Any operation with pointers requires an [unsafe](../keywords/unsafe.md) context.</span></span> <span data-ttu-id="38c55-112">El código que contenga bloques no seguros se tendrá que compilar con la opción del compilador [**AllowUnsafeBlocks**](../compiler-options/language.md#allowunsafeblocks).</span><span class="sxs-lookup"><span data-stu-id="38c55-112">The code that contains unsafe blocks must be compiled with the [**AllowUnsafeBlocks**](../compiler-options/language.md#allowunsafeblocks) compiler option.</span></span>

## <a name="address-of-operator-amp"></a><a name="address-of-operator-"></a> <span data-ttu-id="38c55-113">Operador Address-of &amp;</span><span class="sxs-lookup"><span data-stu-id="38c55-113">Address-of operator &amp;</span></span>

<span data-ttu-id="38c55-114">El operador unario `&` devuelve la dirección de su operando:</span><span class="sxs-lookup"><span data-stu-id="38c55-114">The unary `&` operator returns the address of its operand:</span></span>

[!code-csharp[address of local](snippets/shared/PointerOperators.cs#AddressOf)]

<span data-ttu-id="38c55-115">El operando del operador `&` debe ser una variable fija.</span><span class="sxs-lookup"><span data-stu-id="38c55-115">The operand of the `&` operator must be a fixed variable.</span></span> <span data-ttu-id="38c55-116">Las variables *fijas* son las que residen en ubicaciones de almacenamiento que no se ven afectadas por el funcionamiento del [recolector de elementos no utilizados](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="38c55-116">*Fixed* variables are variables that reside in storage locations that are unaffected by operation of the [garbage collector](../../../standard/garbage-collection/index.md).</span></span> <span data-ttu-id="38c55-117">En el ejemplo anterior, la variable local `number` es una variable fija, ya que reside en la pila.</span><span class="sxs-lookup"><span data-stu-id="38c55-117">In the preceding example, the local variable `number` is a fixed variable, because it resides on the stack.</span></span> <span data-ttu-id="38c55-118">Las variables que residen en ubicaciones de almacenamiento que pueden verse afectadas por el recolector de elementos no utilizados (por ejemplo, reubicadas) se denominan variables *móviles*.</span><span class="sxs-lookup"><span data-stu-id="38c55-118">Variables that reside in storage locations that can be affected by the garbage collector (for example, relocated) are called *movable* variables.</span></span> <span data-ttu-id="38c55-119">Los campos de objeto y los elementos de matriz son ejemplos de variables móviles.</span><span class="sxs-lookup"><span data-stu-id="38c55-119">Object fields and array elements are examples of movable variables.</span></span> <span data-ttu-id="38c55-120">Puede obtener la dirección de una variable móvil si la "fija" o "ancla" con una [instrucción `fixed`](../keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="38c55-120">You can get the address of a movable variable if you "fix", or "pin", it with a [`fixed` statement](../keywords/fixed-statement.md).</span></span> <span data-ttu-id="38c55-121">La dirección obtenida solo es válida dentro del bloque de una instrucción `fixed`.</span><span class="sxs-lookup"><span data-stu-id="38c55-121">The obtained address is valid only inside the block of a `fixed` statement.</span></span> <span data-ttu-id="38c55-122">En el ejemplo siguiente se muestra cómo usar una instrucción `fixed` y el operador `&`:</span><span class="sxs-lookup"><span data-stu-id="38c55-122">The following example shows how to use a `fixed` statement and the `&` operator:</span></span>

[!code-csharp[address of fixed](snippets/shared/PointerOperators.cs#AddressOfFixed)]

<span data-ttu-id="38c55-123">No se puede obtener la dirección de una constante o un valor.</span><span class="sxs-lookup"><span data-stu-id="38c55-123">You can't get the address of a constant or a value.</span></span>

<span data-ttu-id="38c55-124">Para obtener más información sobre las variables fijas y móviles, vea la sección [Variables fijas y móviles](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="38c55-124">For more information about fixed and movable variables, see the [Fixed and moveable variables](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="38c55-125">El operador binario `&` calcula el [AND lógico](boolean-logical-operators.md#logical-and-operator-) de sus operandos booleanos o el [AND lógico bit a bit](bitwise-and-shift-operators.md#logical-and-operator-) de sus operandos enteros.</span><span class="sxs-lookup"><span data-stu-id="38c55-125">The binary `&` operator computes the [logical AND](boolean-logical-operators.md#logical-and-operator-) of its Boolean operands or the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its integral operands.</span></span>

## <a name="pointer-indirection-operator-"></a><span data-ttu-id="38c55-126">Operador de direccionamiento indirecto del puntero \*</span><span class="sxs-lookup"><span data-stu-id="38c55-126">Pointer indirection operator \*</span></span>

<span data-ttu-id="38c55-127">El operador unario de direccionamiento indirecto del puntero `*` obtiene la variable a la que apunta su operando.</span><span class="sxs-lookup"><span data-stu-id="38c55-127">The unary pointer indirection operator `*` obtains the variable to which its operand points.</span></span> <span data-ttu-id="38c55-128">También se conoce como operador de desreferencia.</span><span class="sxs-lookup"><span data-stu-id="38c55-128">It's also known as the dereference operator.</span></span> <span data-ttu-id="38c55-129">El operando del operador `*` debe ser un tipo de puntero.</span><span class="sxs-lookup"><span data-stu-id="38c55-129">The operand of the `*` operator must be of a pointer type.</span></span>

[!code-csharp[pointer indirection](snippets/shared/PointerOperators.cs#PointerIndirection)]

<span data-ttu-id="38c55-130">No se puede aplicar el operador `*` a una expresión de tipo `void*`.</span><span class="sxs-lookup"><span data-stu-id="38c55-130">You cannot apply the `*` operator to an expression of type `void*`.</span></span>

<span data-ttu-id="38c55-131">El operador binario `*` calcula la [multiplicación](arithmetic-operators.md#multiplication-operator-) de sus operandos numéricos.</span><span class="sxs-lookup"><span data-stu-id="38c55-131">The binary `*` operator computes the [product](arithmetic-operators.md#multiplication-operator-) of its numeric operands.</span></span>

## <a name="pointer-member-access-operator--"></a><span data-ttu-id="38c55-132">Operador de acceso a miembros de puntero -></span><span class="sxs-lookup"><span data-stu-id="38c55-132">Pointer member access operator -></span></span>

<span data-ttu-id="38c55-133">El operador `->` combina el [direccionamiento indirecto del puntero](#pointer-indirection-operator-) y el [acceso a miembros](member-access-operators.md#member-access-expression-).</span><span class="sxs-lookup"><span data-stu-id="38c55-133">The `->` operator combines [pointer indirection](#pointer-indirection-operator-) and [member access](member-access-operators.md#member-access-expression-).</span></span> <span data-ttu-id="38c55-134">Es decir, si `x` es un puntero de tipo `T*` y `y` es un miembro accesible de tipo `T`, una expresión con el formato</span><span class="sxs-lookup"><span data-stu-id="38c55-134">That is, if `x` is a pointer of type `T*` and `y` is an accessible member of type `T`, an expression of the form</span></span>

```csharp
x->y
```

<span data-ttu-id="38c55-135">es equivalente a</span><span class="sxs-lookup"><span data-stu-id="38c55-135">is equivalent to</span></span>

```csharp
(*x).y
```

<span data-ttu-id="38c55-136">En el siguiente ejemplo se muestra el uso del operador `->`:</span><span class="sxs-lookup"><span data-stu-id="38c55-136">The following example demonstrates the usage of the `->` operator:</span></span>

[!code-csharp[pointer member access](snippets/shared/PointerOperators.cs#MemberAccess)]

<span data-ttu-id="38c55-137">No se puede aplicar el operador `->` a una expresión de tipo `void*`.</span><span class="sxs-lookup"><span data-stu-id="38c55-137">You cannot apply the `->` operator to an expression of type `void*`.</span></span>

## <a name="pointer-element-access-operator-"></a><span data-ttu-id="38c55-138">Operador de acceso de elemento de puntero []</span><span class="sxs-lookup"><span data-stu-id="38c55-138">Pointer element access operator []</span></span>

<span data-ttu-id="38c55-139">En el caso de una expresión `p` de un tipo de puntero, un acceso de elemento de puntero con el formato `p[n]` se evalúa como `*(p + n)`, donde `n` debe ser de un tipo convertible de forma implícita en `int`, `uint`, `long` o `ulong`.</span><span class="sxs-lookup"><span data-stu-id="38c55-139">For an expression `p` of a pointer type, a pointer element access of the form `p[n]` is evaluated as `*(p + n)`, where `n` must be of a type implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="38c55-140">Para obtener información sobre el comportamiento del operador `+` con punteros, vea la sección [Suma o resta de un valor entero en un puntero](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer).</span><span class="sxs-lookup"><span data-stu-id="38c55-140">For information about the behavior of the `+` operator with pointers, see the [Addition or subtraction of an integral value to or from a pointer](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) section.</span></span>

<span data-ttu-id="38c55-141">En el ejemplo siguiente se muestra cómo acceder a los elementos de matriz con un puntero y el operador `[]`:</span><span class="sxs-lookup"><span data-stu-id="38c55-141">The following example demonstrates how to access array elements with a pointer and the `[]` operator:</span></span>

[!code-csharp[pointer element access](snippets/shared/PointerOperators.cs#ElementAccess)]

<span data-ttu-id="38c55-142">En el ejemplo anterior, una expresión [`stackalloc`](stackalloc.md) asigna un bloque de memoria en la pila.</span><span class="sxs-lookup"><span data-stu-id="38c55-142">In the preceding example, a [`stackalloc` expression](stackalloc.md) allocates a block of memory on the stack.</span></span>

> [!NOTE]
> <span data-ttu-id="38c55-143">El operador de acceso de elemento de puntero no busca errores fuera de límites.</span><span class="sxs-lookup"><span data-stu-id="38c55-143">The pointer element access operator doesn't check for out-of-bounds errors.</span></span>

<span data-ttu-id="38c55-144">No puede usar `[]` para el acceso de elemento de puntero con una expresión de tipo `void*`.</span><span class="sxs-lookup"><span data-stu-id="38c55-144">You cannot use `[]` for pointer element access with an expression of type `void*`.</span></span>

<span data-ttu-id="38c55-145">También puede usar el operador `[]` para [acceso de elemento de matriz o indizador](member-access-operators.md#indexer-operator-).</span><span class="sxs-lookup"><span data-stu-id="38c55-145">You can also use the `[]` operator for [array element or indexer access](member-access-operators.md#indexer-operator-).</span></span>

## <a name="pointer-arithmetic-operators"></a><span data-ttu-id="38c55-146">Operadores aritméticos de puntero</span><span class="sxs-lookup"><span data-stu-id="38c55-146">Pointer arithmetic operators</span></span>

<span data-ttu-id="38c55-147">Puede realizar las siguientes operaciones aritméticas con punteros:</span><span class="sxs-lookup"><span data-stu-id="38c55-147">You can perform the following arithmetic operations with pointers:</span></span>

- <span data-ttu-id="38c55-148">Agregar o restar un valor entero en un puntero</span><span class="sxs-lookup"><span data-stu-id="38c55-148">Add or subtract an integral value to or from a pointer</span></span>
- <span data-ttu-id="38c55-149">Restar dos punteros</span><span class="sxs-lookup"><span data-stu-id="38c55-149">Subtract two pointers</span></span>
- <span data-ttu-id="38c55-150">Incrementar o reducir un puntero</span><span class="sxs-lookup"><span data-stu-id="38c55-150">Increment or decrement a pointer</span></span>

<span data-ttu-id="38c55-151">No es posible realizar esas operaciones con punteros de tipo `void*`.</span><span class="sxs-lookup"><span data-stu-id="38c55-151">You cannot perform those operations with pointers of type `void*`.</span></span>

<span data-ttu-id="38c55-152">Para obtener información sobre las operaciones aritméticas admitidas con tipos numéricos, vea [Operadores aritméticos](arithmetic-operators.md).</span><span class="sxs-lookup"><span data-stu-id="38c55-152">For information about supported arithmetic operations with numeric types, see [Arithmetic operators](arithmetic-operators.md).</span></span>

### <a name="addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer"></a><span data-ttu-id="38c55-153">Suma o resta de un valor entero en un puntero</span><span class="sxs-lookup"><span data-stu-id="38c55-153">Addition or subtraction of an integral value to or from a pointer</span></span>

<span data-ttu-id="38c55-154">En el caso de un puntero `p` de tipo `T*` y una expresión `n` de un tipo convertible de forma implícita en `int`, `uint`, `long` o `ulong`, la suma y la resta se definen de este modo:</span><span class="sxs-lookup"><span data-stu-id="38c55-154">For a pointer `p` of type `T*` and an expression `n` of a type implicitly convertible to `int`, `uint`, `long`, or `ulong`, addition and subtraction are defined as follows:</span></span>

- <span data-ttu-id="38c55-155">Ambas expresiones `p + n` y `n + p` generan un puntero de tipo `T*` que resulta de agregar `n * sizeof(T)` a la dirección proporcionada por `p`.</span><span class="sxs-lookup"><span data-stu-id="38c55-155">Both `p + n` and `n + p` expressions produce a pointer of type `T*` that results from adding `n * sizeof(T)` to the address given by `p`.</span></span>
- <span data-ttu-id="38c55-156">La expresión `p - n` genera un puntero de tipo `T*` que resulta de restar `n * sizeof(T)` a la dirección proporcionada por `p`.</span><span class="sxs-lookup"><span data-stu-id="38c55-156">The `p - n` expression produces a pointer of type `T*` that results from subtracting `n * sizeof(T)` from the address given by `p`.</span></span>

<span data-ttu-id="38c55-157">El [operador `sizeof`](sizeof.md) obtiene el tamaño de un tipo en bytes.</span><span class="sxs-lookup"><span data-stu-id="38c55-157">The [`sizeof` operator](sizeof.md) obtains the size of a type in bytes.</span></span>

<span data-ttu-id="38c55-158">En el siguiente ejemplo se muestra el uso del operador `+` con un puntero:</span><span class="sxs-lookup"><span data-stu-id="38c55-158">The following example demonstrates the usage of the `+` operator with a pointer:</span></span>

[!code-csharp[pointer addition](snippets/shared/PointerOperators.cs#AddNumber)]

### <a name="pointer-subtraction"></a><span data-ttu-id="38c55-159">Resta de puntero</span><span class="sxs-lookup"><span data-stu-id="38c55-159">Pointer subtraction</span></span>

<span data-ttu-id="38c55-160">En el caso de dos punteros `p1` y `p2` de tipo `T*`, la expresión `p1 - p2` genera la diferencia entre las direcciones proporcionadas por `p1` y `p2` dividida por `sizeof(T)`.</span><span class="sxs-lookup"><span data-stu-id="38c55-160">For two pointers `p1` and `p2` of type `T*`, the expression `p1 - p2` produces the difference between the addresses given by `p1` and `p2` divided by `sizeof(T)`.</span></span> <span data-ttu-id="38c55-161">El tipo del resultado es `long`.</span><span class="sxs-lookup"><span data-stu-id="38c55-161">The type of the result is `long`.</span></span> <span data-ttu-id="38c55-162">Es decir, `p1 - p2` se calcula como `((long)(p1) - (long)(p2)) / sizeof(T)`.</span><span class="sxs-lookup"><span data-stu-id="38c55-162">That is, `p1 - p2` is computed as `((long)(p1) - (long)(p2)) / sizeof(T)`.</span></span>

<span data-ttu-id="38c55-163">El ejemplo siguiente muestra la resta de puntero:</span><span class="sxs-lookup"><span data-stu-id="38c55-163">The following example demonstrates the pointer subtraction:</span></span>

[!code-csharp[pointer subtraction](snippets/shared/PointerOperators.cs#SubtractPointers)]

### <a name="pointer-increment-and-decrement"></a><span data-ttu-id="38c55-164">Incremento y decremento de puntero</span><span class="sxs-lookup"><span data-stu-id="38c55-164">Pointer increment and decrement</span></span>

<span data-ttu-id="38c55-165">El operador de incremento `++`[agrega](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 a su operando de puntero.</span><span class="sxs-lookup"><span data-stu-id="38c55-165">The `++` increment operator [adds](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 to its pointer operand.</span></span> <span data-ttu-id="38c55-166">El operador de decremento `--`[resta](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 a su operando de puntero.</span><span class="sxs-lookup"><span data-stu-id="38c55-166">The `--` decrement operator [subtracts](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 from its pointer operand.</span></span>

<span data-ttu-id="38c55-167">Ambos operadores se admiten con dos formatos: postfijo (`p++` y `p--`) y prefijo (`++p` y `--p`).</span><span class="sxs-lookup"><span data-stu-id="38c55-167">Both operators are supported in two forms: postfix (`p++` and `p--`) and prefix (`++p` and `--p`).</span></span> <span data-ttu-id="38c55-168">El resultado de `p++` y `p--` es el valor de `p` *antes* de la operación.</span><span class="sxs-lookup"><span data-stu-id="38c55-168">The result of `p++` and `p--` is the value of `p` *before* the operation.</span></span> <span data-ttu-id="38c55-169">El resultado de `++p` y `--p` es el valor de `p` *después* de la operación.</span><span class="sxs-lookup"><span data-stu-id="38c55-169">The result of `++p` and `--p` is the value of `p` *after* the operation.</span></span>

<span data-ttu-id="38c55-170">El ejemplo siguiente muestra el comportamiento de los operadores de incremento postfijo y prefijo:</span><span class="sxs-lookup"><span data-stu-id="38c55-170">The following example demonstrates the behavior of both postfix and prefix increment operators:</span></span>

[!code-csharp[pointer increment](snippets/shared/PointerOperators.cs#Increment)]

## <a name="pointer-comparison-operators"></a><span data-ttu-id="38c55-171">Operadores de comparación de puntero</span><span class="sxs-lookup"><span data-stu-id="38c55-171">Pointer comparison operators</span></span>

<span data-ttu-id="38c55-172">Puede usar los operadores `==`, `!=`, `<`, `>`, `<=` y `>=` para comparar los operandos de cualquier tipo de puntero, incluido `void*`.</span><span class="sxs-lookup"><span data-stu-id="38c55-172">You can use the `==`, `!=`, `<`, `>`, `<=`, and `>=` operators to compare operands of any pointer type, including `void*`.</span></span> <span data-ttu-id="38c55-173">Esos operadores comparan las direcciones proporcionadas por los dos operandos como si fueran enteros sin signo.</span><span class="sxs-lookup"><span data-stu-id="38c55-173">Those operators compare the addresses given by the two operands as if they were unsigned integers.</span></span>

<span data-ttu-id="38c55-174">Para obtener información sobre el comportamiento de esos operadores para operandos de otros tipos, vea los artículos [Operadores de igualdad](equality-operators.md) y [Operadores de comparación](comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="38c55-174">For information about the behavior of those operators for operands of other types, see the [Equality operators](equality-operators.md) and [Comparison operators](comparison-operators.md) articles.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="38c55-175">Prioridad de operadores</span><span class="sxs-lookup"><span data-stu-id="38c55-175">Operator precedence</span></span>

<span data-ttu-id="38c55-176">En la lista siguiente se ordenan los operadores relacionados con el puntero desde la prioridad más alta a la más baja:</span><span class="sxs-lookup"><span data-stu-id="38c55-176">The following list orders pointer related operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="38c55-177">Operadores de incremento `x++` y decremento `x--` postfijos y operadores `->` y `[]`</span><span class="sxs-lookup"><span data-stu-id="38c55-177">Postfix increment `x++` and decrement `x--` operators and the `->` and `[]` operators</span></span>
- <span data-ttu-id="38c55-178">Operadores de incremento `++x` y decremento `--x` prefijos y operadores `&` y `*`</span><span class="sxs-lookup"><span data-stu-id="38c55-178">Prefix increment `++x` and decrement `--x` operators and the `&` and `*` operators</span></span>
- <span data-ttu-id="38c55-179">Operadores `+` y `-` de suma</span><span class="sxs-lookup"><span data-stu-id="38c55-179">Additive `+` and `-` operators</span></span>
- <span data-ttu-id="38c55-180">Operadores de comparación `<`, `>`, `<=` y `>=`</span><span class="sxs-lookup"><span data-stu-id="38c55-180">Comparison `<`, `>`, `<=`, and `>=` operators</span></span>
- <span data-ttu-id="38c55-181">Operadores de igualdad `==` y `!=`</span><span class="sxs-lookup"><span data-stu-id="38c55-181">Equality `==` and `!=` operators</span></span>

<span data-ttu-id="38c55-182">Use paréntesis, `()`, para cambiar el orden de evaluación impuesto por la prioridad de los operadores.</span><span class="sxs-lookup"><span data-stu-id="38c55-182">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence.</span></span>

<span data-ttu-id="38c55-183">Para obtener la lista completa de los operadores de C# ordenados por nivel de prioridad, vea la sección [Prioridad de operadores](index.md#operator-precedence) del artículo [Operadores de C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="38c55-183">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="38c55-184">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="38c55-184">Operator overloadability</span></span>

<span data-ttu-id="38c55-185">Un tipo definido por el usuario no puede sobrecargar los operadores relacionados con el puntero `&`, `*`, `->` y `[]`.</span><span class="sxs-lookup"><span data-stu-id="38c55-185">A user-defined type cannot overload the pointer related operators `&`, `*`, `->`, and `[]`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="38c55-186">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="38c55-186">C# language specification</span></span>

<span data-ttu-id="38c55-187">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="38c55-187">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="38c55-188">Variables fijas y móviles</span><span class="sxs-lookup"><span data-stu-id="38c55-188">Fixed and moveable variables</span></span>](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables)
- [<span data-ttu-id="38c55-189">El operador address-of</span><span class="sxs-lookup"><span data-stu-id="38c55-189">The address-of operator</span></span>](~/_csharplang/spec/unsafe-code.md#the-address-of-operator)
- [<span data-ttu-id="38c55-190">Direccionamiento indirecto del puntero</span><span class="sxs-lookup"><span data-stu-id="38c55-190">Pointer indirection</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-indirection)
- [<span data-ttu-id="38c55-191">Acceso a miembros de puntero</span><span class="sxs-lookup"><span data-stu-id="38c55-191">Pointer member access</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-member-access)
- [<span data-ttu-id="38c55-192">Acceso de elemento de puntero</span><span class="sxs-lookup"><span data-stu-id="38c55-192">Pointer element access</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-element-access)
- [<span data-ttu-id="38c55-193">Aritmética de puntero</span><span class="sxs-lookup"><span data-stu-id="38c55-193">Pointer arithmetic</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-arithmetic)
- [<span data-ttu-id="38c55-194">Incremento y decremento de puntero</span><span class="sxs-lookup"><span data-stu-id="38c55-194">Pointer increment and decrement</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-increment-and-decrement)
- [<span data-ttu-id="38c55-195">Comparación de punteros</span><span class="sxs-lookup"><span data-stu-id="38c55-195">Pointer comparison</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-comparison)

## <a name="see-also"></a><span data-ttu-id="38c55-196">Vea también</span><span class="sxs-lookup"><span data-stu-id="38c55-196">See also</span></span>

- [<span data-ttu-id="38c55-197">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="38c55-197">C# reference</span></span>](../index.md)
- [<span data-ttu-id="38c55-198">Operadores y expresiones de C#</span><span class="sxs-lookup"><span data-stu-id="38c55-198">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="38c55-199">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="38c55-199">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="38c55-200">unsafe (palabra clave)</span><span class="sxs-lookup"><span data-stu-id="38c55-200">unsafe keyword</span></span>](../keywords/unsafe.md)
- [<span data-ttu-id="38c55-201">fixed (palabra clave)</span><span class="sxs-lookup"><span data-stu-id="38c55-201">fixed keyword</span></span>](../keywords/fixed-statement.md)
- [<span data-ttu-id="38c55-202">stackalloc</span><span class="sxs-lookup"><span data-stu-id="38c55-202">stackalloc</span></span>](stackalloc.md)
- [<span data-ttu-id="38c55-203">sizeof (operador)</span><span class="sxs-lookup"><span data-stu-id="38c55-203">sizeof operator</span></span>](sizeof.md)
