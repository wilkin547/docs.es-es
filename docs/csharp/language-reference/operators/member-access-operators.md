---
title: 'Operadores de acceso a miembros: referencia de C#'
description: Obtenga información sobre los operadores de C# que puede usar para acceder a los miembros de tipos.
ms.date: 09/18/2019
author: pkulikov
f1_keywords:
- ._CSharpKeyword
- '[]_CSharpKeyword'
- ()_CSharpKeyword
- ^_CSharpKeyword
- .._CSharpKeyword
helpviewer_keywords:
- member access operators [C#]
- member access operator [C#]
- dot operator [C#]
- . operator [C#]
- subscript operator [C#]
- square brackets [] operator [C#]
- indexer operator [C#]
- '[] operator [C#]'
- null-conditional operators [C#]
- Elvis operator [C#]
- ?. operator [C#]
- ?[] operator [C#]
- invocation operator [C#]
- method call [C#]
- method invocation [C#]
- delegate invocation [C#]
- () operator [C#]
- ^ operator [C#]
- index from end operator [C#]
- hat operator [C#]
- .. operator [C#]
- range operator [C#]
ms.openlocfilehash: ba2a8cd4995b9baab2071d3fb3c7980e45565692
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73038999"
---
# <a name="member-access-operators-c-reference"></a><span data-ttu-id="a681c-103">Operadores de acceso a miembros (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a681c-103">Member access operators (C# reference)</span></span>

<span data-ttu-id="a681c-104">Puede usar los operadores siguientes cuando accede a un miembro de tipo:</span><span class="sxs-lookup"><span data-stu-id="a681c-104">You can use the following operators when you access a type member:</span></span>

- <span data-ttu-id="a681c-105">[`.` (acceso a miembros)](#member-access-operator-): para acceder a un miembro de un espacio de nombres o un tipo</span><span class="sxs-lookup"><span data-stu-id="a681c-105">[`.` (member access)](#member-access-operator-): to access a member of a namespace or a type</span></span>
- <span data-ttu-id="a681c-106">[`[]` (elemento de matriz o acceso a indizador)](#indexer-operator-): para acceder a un elemento de matriz o un indizador de tipo</span><span class="sxs-lookup"><span data-stu-id="a681c-106">[`[]` (array element or indexer access)](#indexer-operator-): to access an array element or a type indexer</span></span>
- <span data-ttu-id="a681c-107">[`?.` y `?[]` (operadores condicionales NULL)](#null-conditional-operators--and-): para realizar una operación de acceso a elementos o miembros solo si un operando es distinto de NULL</span><span class="sxs-lookup"><span data-stu-id="a681c-107">[`?.` and `?[]` (null-conditional operators)](#null-conditional-operators--and-): to perform a member or element access operation only if an operand is non-null</span></span>
- <span data-ttu-id="a681c-108">[`()` (invocación)](#invocation-operator-): para llamar a un método de acceso o invocar un delegado</span><span class="sxs-lookup"><span data-stu-id="a681c-108">[`()` (invocation)](#invocation-operator-): to call an accessed method or invoke a delegate</span></span>
- <span data-ttu-id="a681c-109">[`^` (índice desde el final) ](#index-from-end-operator-): para indicar que la posición del elemento se encuentra a partir del final de una secuencia</span><span class="sxs-lookup"><span data-stu-id="a681c-109">[`^` (index from end)](#index-from-end-operator-): to indicate that the element position is from the end of a sequence</span></span>
- <span data-ttu-id="a681c-110">[`..` (intervalo)](#range-operator-): para especificar un intervalo de índices que puede utilizar para obtener un intervalo de elementos de secuencia</span><span class="sxs-lookup"><span data-stu-id="a681c-110">[`..` (range)](#range-operator-): to specify a range of indices that you can use to obtain a range of sequence elements</span></span>

## <a name="member-access-operator-"></a><span data-ttu-id="a681c-111">Operador de acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="a681c-111">Member access operator .</span></span>

<span data-ttu-id="a681c-112">Use el token `.` para acceder a un miembro de un espacio de nombres o un tipo, como se muestran en los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a681c-112">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="a681c-113">Use `.` para acceder a un espacio de nombres anidado dentro de un espacio de nombres, como se muestra en el siguiente ejemplo de una [directiva `using`](../keywords/using-directive.md):</span><span class="sxs-lookup"><span data-stu-id="a681c-113">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#NestedNamespace)]

- <span data-ttu-id="a681c-114">Use `.` para formar un *nombre completo* para tener acceso a un tipo dentro de un espacio de nombres, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="a681c-114">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#QualifiedName)]

  <span data-ttu-id="a681c-115">Utilice una [directiva `using`](../keywords/using-directive.md) para hacer que el uso de nombres completos sea opcional.</span><span class="sxs-lookup"><span data-stu-id="a681c-115">Use a [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="a681c-116">Use `.` para tener acceso a los [miembros de tipo](../../programming-guide/classes-and-structs/index.md#members), que no son estáticos y, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="a681c-116">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#TypeMemberAccess)]

<span data-ttu-id="a681c-117">También puede usar `.` para acceder a un [método de extensión](../../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="a681c-117">You can also use `.` to access an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="indexer-operator-"></a><span data-ttu-id="a681c-118">Operador del indizador []</span><span class="sxs-lookup"><span data-stu-id="a681c-118">Indexer operator []</span></span>

<span data-ttu-id="a681c-119">Los corchetes, `[]`, se suelen usar para el acceso a matriz, indizador o elemento de puntero.</span><span class="sxs-lookup"><span data-stu-id="a681c-119">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

### <a name="array-access"></a><span data-ttu-id="a681c-120">Acceso a matriz</span><span class="sxs-lookup"><span data-stu-id="a681c-120">Array access</span></span>

<span data-ttu-id="a681c-121">En el ejemplo siguiente se muestra cómo se obtiene acceso a los elementos de matriz:</span><span class="sxs-lookup"><span data-stu-id="a681c-121">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Arrays)]

<span data-ttu-id="a681c-122">Si un índice de matriz se encuentra fuera de los límites de la dimensión correspondiente de una matriz, se produce una excepción <xref:System.IndexOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="a681c-122">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="a681c-123">Tal como se muestra en el ejemplo anterior, también usa corchetes al declarar un tipo de matriz o crear instancias de matriz.</span><span class="sxs-lookup"><span data-stu-id="a681c-123">As the preceding example shows, you also use square brackets when you declare an array type or instantiate an array instance.</span></span>

<span data-ttu-id="a681c-124">Para obtener más información sobre las matrices, consulte [Matrices](../../programming-guide/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="a681c-124">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

### <a name="indexer-access"></a><span data-ttu-id="a681c-125">Acceso a indizador</span><span class="sxs-lookup"><span data-stu-id="a681c-125">Indexer access</span></span>

<span data-ttu-id="a681c-126">En el ejemplo siguiente se usa el tipo <xref:System.Collections.Generic.Dictionary%602> de .NET para mostrar el acceso al indizador:</span><span class="sxs-lookup"><span data-stu-id="a681c-126">The following example uses the .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Indexers)]

<span data-ttu-id="a681c-127">Los indizadores le permiten indizar las instancias de un tipo definido por el usuario de un modo similar a la indización de matrices.</span><span class="sxs-lookup"><span data-stu-id="a681c-127">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="a681c-128">A diferencia de los índices de matriz, que deben ser enteros, los parámetros de indizador se pueden declarar para ser de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="a681c-128">Unlike array indices, which must be integer, the indexer parameters can be declared to be of any type.</span></span>

<span data-ttu-id="a681c-129">Para más información sobre los indizadores, consulte [Indizadores](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="a681c-129">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="a681c-130">Otros usos de []</span><span class="sxs-lookup"><span data-stu-id="a681c-130">Other usages of []</span></span>

<span data-ttu-id="a681c-131">Para información sobre el acceso de los elementos de puntero, consulte la sección [Operador de acceso de elemento de puntero](pointer-related-operators.md#pointer-element-access-operator-) del artículo [Operadores relacionados con el puntero](pointer-related-operators.md).</span><span class="sxs-lookup"><span data-stu-id="a681c-131">For information about pointer element access, see the [Pointer element access operator []](pointer-related-operators.md#pointer-element-access-operator-) section of the [Pointer related operators](pointer-related-operators.md) article.</span></span>

<span data-ttu-id="a681c-132">También usa los corchetes para especificar [atributos](../../programming-guide/concepts/attributes/index.md):</span><span class="sxs-lookup"><span data-stu-id="a681c-132">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a><span data-ttu-id="a681c-133">Operadores condicionales NULL ?.</span><span class="sxs-lookup"><span data-stu-id="a681c-133">Null-conditional operators ?.</span></span> <span data-ttu-id="a681c-134">y ?[]</span><span class="sxs-lookup"><span data-stu-id="a681c-134">and ?[]</span></span>

<span data-ttu-id="a681c-135">Disponible en C# 6 y versiones posteriores, un operador condicional NULL aplica una operación de acceso a miembros, `?.`, o acceso a elementos, `?[]`, a su operando solo si dicho operando se evalúa como no NULL.</span><span class="sxs-lookup"><span data-stu-id="a681c-135">Available in C# 6 and later, a null-conditional operator applies a member access, `?.`, or element access, `?[]`, operation to its operand only if that operand evaluates to non-null.</span></span> <span data-ttu-id="a681c-136">Si el operando se evalúa como `null`, el resultado de aplicar el operador es `null`.</span><span class="sxs-lookup"><span data-stu-id="a681c-136">If the operand evaluates to `null`, the result of applying the operator is `null`.</span></span> <span data-ttu-id="a681c-137">El operador de acceso de miembro condicional NULL `?.` también se conoce con el nombre de operador Elvis.</span><span class="sxs-lookup"><span data-stu-id="a681c-137">The null-conditional member access operator `?.` is also known as the Elvis operator.</span></span>

<span data-ttu-id="a681c-138">Los operadores de condición NULL se cortocircuitan.</span><span class="sxs-lookup"><span data-stu-id="a681c-138">The null-conditional operators are short-circuiting.</span></span> <span data-ttu-id="a681c-139">Es decir, si una operación en una cadena de la operación de acceso a elementos o miembros condicional devuelve `null`, no se ejecuta el resto de la cadena.</span><span class="sxs-lookup"><span data-stu-id="a681c-139">That is, if one operation in a chain of conditional member or element access operations returns `null`, the rest of the chain doesn't execute.</span></span> <span data-ttu-id="a681c-140">En el ejemplo siguiente, `B` no se evalúa si `A` se evalúa como `null` y `C` no se evalúa si `A` o `B` se evalúan como `null`:</span><span class="sxs-lookup"><span data-stu-id="a681c-140">In the following example, `B` is not evaluated if `A` evaluates to `null` and `C` is not evaluated if `A` or `B` evaluates to `null`:</span></span>

```csharp
A?.B?.Do(C);
A?.B?[C];
```

<span data-ttu-id="a681c-141">En el siguiente ejemplo se muestra el uso de los operadores `?.` y `?[]`:</span><span class="sxs-lookup"><span data-stu-id="a681c-141">The following example demonstrates the usage of the `?.` and `?[]` operators:</span></span>

[!code-csharp-interactive[null-conditional operators](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#NullConditional)]

<span data-ttu-id="a681c-142">En el ejemplo anterior también se usa el [operador de fusión de NULL `??`](null-coalescing-operator.md) para especificar una expresión alternativa que se evaluará en caso de que el resultado de la operación condicional NULL sea `null`.</span><span class="sxs-lookup"><span data-stu-id="a681c-142">The preceding example also uses the [null-coalescing operator `??`](null-coalescing-operator.md) to specify an alternative expression to evaluate in case the result of a null-conditional operation is `null`.</span></span>

### <a name="thread-safe-delegate-invocation"></a><span data-ttu-id="a681c-143">Invocación de delegado seguro para subprocesos</span><span class="sxs-lookup"><span data-stu-id="a681c-143">Thread-safe delegate invocation</span></span>

<span data-ttu-id="a681c-144">Use el operador `?.` para comprobar si un delegado es distinto de NULL y se invoca de forma segura para subprocesos (por ejemplo, cuando se [genera un evento](../../../standard/events/how-to-raise-and-consume-events.md)), tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="a681c-144">Use the `?.` operator to check if a delegate is non-null and invoke it in a thread-safe way (for example, when you [raise an event](../../../standard/events/how-to-raise-and-consume-events.md)), as the following code shows:</span></span>

```csharp
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="a681c-145">Ese código es equivalente al código siguiente que se usaría en C# 5 o una versión anterior:</span><span class="sxs-lookup"><span data-stu-id="a681c-145">That code is equivalent to the following code that you would use in C# 5 or earlier:</span></span>

```csharp
var handler = this.PropertyChanged;
if (handler != null)
{
    handler(…);
}
```

## <a name="invocation-operator-"></a><span data-ttu-id="a681c-146">Operador de invocación ()</span><span class="sxs-lookup"><span data-stu-id="a681c-146">Invocation operator ()</span></span>

<span data-ttu-id="a681c-147">Utilice paréntesis, `()`, para llamar a un [método](../../programming-guide/classes-and-structs/methods.md) o invocar un [delegado](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="a681c-147">Use parentheses, `()`, to call a [method](../../programming-guide/classes-and-structs/methods.md) or invoke a [delegate](../../programming-guide/delegates/index.md).</span></span>

<span data-ttu-id="a681c-148">En el ejemplo siguiente se muestra cómo llamar a un método, con o sin argumentos, y cómo invocar un delegado:</span><span class="sxs-lookup"><span data-stu-id="a681c-148">The following example demonstrates how to call a method, with or without arguments, and invoke a delegate:</span></span>

[!code-csharp-interactive[invocation with ()](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Invocation)]

<span data-ttu-id="a681c-149">También usa paréntesis al invocar un [constructor](../../programming-guide/classes-and-structs/constructors.md) con el operador [`new`](new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="a681c-149">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with the [`new`](new-operator.md) operator.</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="a681c-150">Otros usos de ()</span><span class="sxs-lookup"><span data-stu-id="a681c-150">Other usages of ()</span></span>

<span data-ttu-id="a681c-151">También usa los paréntesis para ajustar el orden en el que se van a evaluar operaciones en una expresión.</span><span class="sxs-lookup"><span data-stu-id="a681c-151">You also use parentheses to adjust the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="a681c-152">Para obtener más información, vea [Operadores de C# (referencia de C#)](index.md).</span><span class="sxs-lookup"><span data-stu-id="a681c-152">For more information, see [C# operators](index.md).</span></span>

<span data-ttu-id="a681c-153">[Expresiones de conversión](type-testing-and-cast.md#cast-operator-), que realizan conversiones de tipo explícitas, también utilizan paréntesis.</span><span class="sxs-lookup"><span data-stu-id="a681c-153">[Cast expressions](type-testing-and-cast.md#cast-operator-), which perform explicit type conversions, also use parentheses.</span></span>

## <a name="index-from-end-operator-"></a><span data-ttu-id="a681c-154">Indexación desde el operador final ^</span><span class="sxs-lookup"><span data-stu-id="a681c-154">Index from end operator ^</span></span>

<span data-ttu-id="a681c-155">Disponible en C# 8.0 y versiones posteriores, el operador `^` indica la posición del elemento a partir del final de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="a681c-155">Available in C# 8.0 and later, the `^` operator indicates the element position from the end of a sequence.</span></span> <span data-ttu-id="a681c-156">En el caso de una secuencia de longitud `length`, `^n` apunta al elemento con desplazamiento `length - n` desde el inicio de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="a681c-156">For a sequence of length `length`, `^n` points to the element with offset `length - n` from the start of a sequence.</span></span> <span data-ttu-id="a681c-157">Por ejemplo, `^1` apunta al último elemento de una secuencia y `^length` apunta al primer elemento de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="a681c-157">For example, `^1` points to the last element of a sequence and `^length` points to the first element of a sequence.</span></span>

[!code-csharp[index from end](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#IndexFromEnd)]

<span data-ttu-id="a681c-158">Como se muestra en el ejemplo anterior, la expresión `^e` es del tipo <xref:System.Index?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a681c-158">As the preceding example shows, expression `^e` is of the <xref:System.Index?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="a681c-159">En la expresión `^e`, el resultado de `e` debe poderse convertir implícitamente a `int`.</span><span class="sxs-lookup"><span data-stu-id="a681c-159">In expression `^e`, the result of `e` must be implicitly convertible to `int`.</span></span>

<span data-ttu-id="a681c-160">También puede usar el operador `^` con el [operador de intervalo](#range-operator-) para crear un intervalo de índices.</span><span class="sxs-lookup"><span data-stu-id="a681c-160">You also can use the `^` operator with the [range operator](#range-operator-) to create a range of indices.</span></span> <span data-ttu-id="a681c-161">Para más información, consulte [Índices y rangos](../../tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="a681c-161">For more information, see [Indices and ranges](../../tutorials/ranges-indexes.md).</span></span>

## <a name="range-operator-"></a><span data-ttu-id="a681c-162">Operador de intervalo ..</span><span class="sxs-lookup"><span data-stu-id="a681c-162">Range operator ..</span></span>

<span data-ttu-id="a681c-163">Disponible en C# 8.0 y versiones posteriores, el operador `..` especifica el inicio y el final de un intervalo de índices como sus operandos.</span><span class="sxs-lookup"><span data-stu-id="a681c-163">Available in C# 8.0 and later, the `..` operator specifies the start and end of a range of indices as its operands.</span></span> <span data-ttu-id="a681c-164">El operando izquierdo es un inicio *inclusivo* de un intervalo.</span><span class="sxs-lookup"><span data-stu-id="a681c-164">The left-hand operand is an *inclusive* start of a range.</span></span> <span data-ttu-id="a681c-165">El operando derecho es un inicio *exclusivo* de un intervalo.</span><span class="sxs-lookup"><span data-stu-id="a681c-165">The right-hand operand is an *exclusive* end of a range.</span></span> <span data-ttu-id="a681c-166">Cualquiera de los operandos puede ser un índice desde el inicio o desde el final de una secuencia, tal y como muestra el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a681c-166">Either of operands can be an index from the start or from the end of a sequence, as the following example shows:</span></span>

[!code-csharp[range examples](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Ranges)]

<span data-ttu-id="a681c-167">Como se muestra en el ejemplo anterior, la expresión `a..b` es del tipo <xref:System.Range?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a681c-167">As the preceding example shows, expression `a..b` is of the <xref:System.Range?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="a681c-168">En la expresión `a..b`, los resultados de `a` y `b` deben poderse convertir implícitamente a `int` o <xref:System.Index>.</span><span class="sxs-lookup"><span data-stu-id="a681c-168">In expression `a..b`, the results of `a` and `b` must be implicitly convertible to `int` or <xref:System.Index>.</span></span>

<span data-ttu-id="a681c-169">Puede omitir cualquiera de los operandos del operador `..` para obtener un intervalo abierto:</span><span class="sxs-lookup"><span data-stu-id="a681c-169">You can omit any of the operands of the `..` operator to obtain an open-ended range:</span></span>

- <span data-ttu-id="a681c-170">`a..` es equivalente a `a..^0`</span><span class="sxs-lookup"><span data-stu-id="a681c-170">`a..` is equivalent to `a..^0`</span></span>
- <span data-ttu-id="a681c-171">`..b` es equivalente a `0..b`</span><span class="sxs-lookup"><span data-stu-id="a681c-171">`..b` is equivalent to `0..b`</span></span>
- <span data-ttu-id="a681c-172">`..` es equivalente a `0..^0`</span><span class="sxs-lookup"><span data-stu-id="a681c-172">`..` is equivalent to `0..^0`</span></span>

[!code-csharp[ranges with omitted operands](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#RangesOptional)]

<span data-ttu-id="a681c-173">Para más información, consulte [Índices y rangos](../../tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="a681c-173">For more information, see [Indices and ranges](../../tutorials/ranges-indexes.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="a681c-174">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="a681c-174">Operator overloadability</span></span>

<span data-ttu-id="a681c-175">Los operadores `.`, `()`, `^` y `..` no se pueden sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="a681c-175">The `.`, `()`, `^`, and `..` operators cannot be overloaded.</span></span> <span data-ttu-id="a681c-176">El operador `[]` también se considera un operador que no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="a681c-176">The `[]` operator is also considered a non-overloadable operator.</span></span> <span data-ttu-id="a681c-177">Use [indizadores](../../programming-guide/indexers/index.md) para admitir la indización con tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="a681c-177">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a681c-178">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="a681c-178">C# language specification</span></span>

<span data-ttu-id="a681c-179">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="a681c-179">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="a681c-180">Acceso a miembros</span><span class="sxs-lookup"><span data-stu-id="a681c-180">Member access</span></span>](~/_csharplang/spec/expressions.md#member-access)
- [<span data-ttu-id="a681c-181">Acceso a elementos</span><span class="sxs-lookup"><span data-stu-id="a681c-181">Element access</span></span>](~/_csharplang/spec/expressions.md#element-access)
- [<span data-ttu-id="a681c-182">Operador condicional de NULL</span><span class="sxs-lookup"><span data-stu-id="a681c-182">Null-conditional operator</span></span>](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [<span data-ttu-id="a681c-183">Expresiones de invocación</span><span class="sxs-lookup"><span data-stu-id="a681c-183">Invocation expressions</span></span>](~/_csharplang/spec/expressions.md#invocation-expressions)

<span data-ttu-id="a681c-184">Para más información sobre índices y rangos, vea la [nota de propuesta de características](~/_csharplang/proposals/csharp-8.0/ranges.md).</span><span class="sxs-lookup"><span data-stu-id="a681c-184">For more information about indices and ranges, see the [feature proposal note](~/_csharplang/proposals/csharp-8.0/ranges.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a681c-185">Vea también</span><span class="sxs-lookup"><span data-stu-id="a681c-185">See also</span></span>

- [<span data-ttu-id="a681c-186">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="a681c-186">C# reference</span></span>](../index.md)
- [<span data-ttu-id="a681c-187">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="a681c-187">C# operators</span></span>](index.md)
- [<span data-ttu-id="a681c-188">?? (operador de uso combinado de NULL)</span><span class="sxs-lookup"><span data-stu-id="a681c-188">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="a681c-189">Operador ::</span><span class="sxs-lookup"><span data-stu-id="a681c-189">:: operator</span></span>](namespace-alias-qualifier.md)
