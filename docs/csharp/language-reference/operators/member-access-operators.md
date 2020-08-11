---
title: 'Operadores y expresiones de acceso a miembros: referencia de C#'
description: Obtenga información sobre los operadores de C# que puede usar para acceder a los miembros de tipos.
ms.date: 04/17/2020
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
ms.openlocfilehash: 688a1fcff84a6e8f2fa31533a2bc459bf8c8717a
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916793"
---
# <a name="member-access-operators-and-expressions-c-reference"></a><span data-ttu-id="4bd48-103">Operadores y expresiones de acceso a miembros (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="4bd48-103">Member access operators and expressions (C# reference)</span></span>

<span data-ttu-id="4bd48-104">Puede usar los operadores y expresiones siguientes cuando accede a un miembro de tipo:</span><span class="sxs-lookup"><span data-stu-id="4bd48-104">You can use the following operators and expressions when you access a type member:</span></span>

- <span data-ttu-id="4bd48-105">[`.` (acceso a miembros)](#member-access-expression-): para acceder a un miembro de un espacio de nombres o un tipo</span><span class="sxs-lookup"><span data-stu-id="4bd48-105">[`.` (member access)](#member-access-expression-): to access a member of a namespace or a type</span></span>
- <span data-ttu-id="4bd48-106">[`[]` (elemento de matriz o acceso a indizador)](#indexer-operator-): para acceder a un elemento de matriz o un indizador de tipo</span><span class="sxs-lookup"><span data-stu-id="4bd48-106">[`[]` (array element or indexer access)](#indexer-operator-): to access an array element or a type indexer</span></span>
- <span data-ttu-id="4bd48-107">[`?.` y `?[]` (operadores condicionales NULL)](#null-conditional-operators--and-): para realizar una operación de acceso a elementos o miembros solo si un operando es distinto de NULL</span><span class="sxs-lookup"><span data-stu-id="4bd48-107">[`?.` and `?[]` (null-conditional operators)](#null-conditional-operators--and-): to perform a member or element access operation only if an operand is non-null</span></span>
- <span data-ttu-id="4bd48-108">[`()` (invocación)](#invocation-expression-): para llamar a un método de acceso o invocar un delegado</span><span class="sxs-lookup"><span data-stu-id="4bd48-108">[`()` (invocation)](#invocation-expression-): to call an accessed method or invoke a delegate</span></span>
- <span data-ttu-id="4bd48-109">[`^` (índice desde el final) ](#index-from-end-operator-): para indicar que la posición del elemento se encuentra a partir del final de una secuencia</span><span class="sxs-lookup"><span data-stu-id="4bd48-109">[`^` (index from end)](#index-from-end-operator-): to indicate that the element position is from the end of a sequence</span></span>
- <span data-ttu-id="4bd48-110">[`..` (intervalo)](#range-operator-): para especificar un intervalo de índices que puede utilizar para obtener un intervalo de elementos de secuencia</span><span class="sxs-lookup"><span data-stu-id="4bd48-110">[`..` (range)](#range-operator-): to specify a range of indices that you can use to obtain a range of sequence elements</span></span>

## <a name="member-access-expression-"></a><span data-ttu-id="4bd48-111">Expresión de acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="4bd48-111">Member access expression .</span></span>

<span data-ttu-id="4bd48-112">Use el token `.` para acceder a un miembro de un espacio de nombres o un tipo, como se muestran en los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4bd48-112">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="4bd48-113">Use `.` para acceder a un espacio de nombres anidado dentro de un espacio de nombres, como se muestra en el siguiente ejemplo de una [directiva `using`](../keywords/using-directive.md):</span><span class="sxs-lookup"><span data-stu-id="4bd48-113">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](snippets/shared/MemberAccessOperators.cs#NestedNamespace)]

- <span data-ttu-id="4bd48-114">Use `.` para formar un *nombre completo* para tener acceso a un tipo dentro de un espacio de nombres, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="4bd48-114">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](snippets/shared/MemberAccessOperators.cs#QualifiedName)]

  <span data-ttu-id="4bd48-115">Utilice una [directiva `using`](../keywords/using-directive.md) para hacer que el uso de nombres completos sea opcional.</span><span class="sxs-lookup"><span data-stu-id="4bd48-115">Use a [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="4bd48-116">Use `.` para tener acceso a los [miembros de tipo](../../programming-guide/classes-and-structs/index.md#members), que no son estáticos y, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="4bd48-116">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](snippets/shared/MemberAccessOperators.cs#TypeMemberAccess)]

<span data-ttu-id="4bd48-117">También puede usar `.` para acceder a un [método de extensión](../../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="4bd48-117">You can also use `.` to access an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="indexer-operator-"></a><span data-ttu-id="4bd48-118">Operador del indizador []</span><span class="sxs-lookup"><span data-stu-id="4bd48-118">Indexer operator []</span></span>

<span data-ttu-id="4bd48-119">Los corchetes, `[]`, se suelen usar para el acceso a matriz, indizador o elemento de puntero.</span><span class="sxs-lookup"><span data-stu-id="4bd48-119">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

### <a name="array-access"></a><span data-ttu-id="4bd48-120">Acceso a matriz</span><span class="sxs-lookup"><span data-stu-id="4bd48-120">Array access</span></span>

<span data-ttu-id="4bd48-121">En el ejemplo siguiente se muestra cómo se obtiene acceso a los elementos de matriz:</span><span class="sxs-lookup"><span data-stu-id="4bd48-121">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](snippets/shared/MemberAccessOperators.cs#Arrays)]

<span data-ttu-id="4bd48-122">Si un índice de matriz se encuentra fuera de los límites de la dimensión correspondiente de una matriz, se produce una excepción <xref:System.IndexOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="4bd48-122">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="4bd48-123">Tal como se muestra en el ejemplo anterior, también usa corchetes al declarar un tipo de matriz o crear instancias de matriz.</span><span class="sxs-lookup"><span data-stu-id="4bd48-123">As the preceding example shows, you also use square brackets when you declare an array type or instantiate an array instance.</span></span>

<span data-ttu-id="4bd48-124">Para obtener más información sobre las matrices, consulte [Matrices](../../programming-guide/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="4bd48-124">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

### <a name="indexer-access"></a><span data-ttu-id="4bd48-125">Acceso a indizador</span><span class="sxs-lookup"><span data-stu-id="4bd48-125">Indexer access</span></span>

<span data-ttu-id="4bd48-126">En el ejemplo siguiente se usa el tipo <xref:System.Collections.Generic.Dictionary%602> de .NET para mostrar el acceso al indizador:</span><span class="sxs-lookup"><span data-stu-id="4bd48-126">The following example uses the .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](snippets/shared/MemberAccessOperators.cs#Indexers)]

<span data-ttu-id="4bd48-127">Los indizadores le permiten indizar las instancias de un tipo definido por el usuario de un modo similar a la indización de matrices.</span><span class="sxs-lookup"><span data-stu-id="4bd48-127">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="4bd48-128">A diferencia de los índices de matriz, que deben ser enteros, los parámetros de indizador se pueden declarar para ser de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="4bd48-128">Unlike array indices, which must be integer, the indexer parameters can be declared to be of any type.</span></span>

<span data-ttu-id="4bd48-129">Para más información sobre los indizadores, consulte [Indizadores](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="4bd48-129">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="4bd48-130">Otros usos de []</span><span class="sxs-lookup"><span data-stu-id="4bd48-130">Other usages of []</span></span>

<span data-ttu-id="4bd48-131">Para información sobre el acceso de los elementos de puntero, consulte la sección [Operador de acceso de elemento de puntero](pointer-related-operators.md#pointer-element-access-operator-) del artículo [Operadores relacionados con el puntero](pointer-related-operators.md).</span><span class="sxs-lookup"><span data-stu-id="4bd48-131">For information about pointer element access, see the [Pointer element access operator []](pointer-related-operators.md#pointer-element-access-operator-) section of the [Pointer related operators](pointer-related-operators.md) article.</span></span>

<span data-ttu-id="4bd48-132">También usa los corchetes para especificar [atributos](../../programming-guide/concepts/attributes/index.md):</span><span class="sxs-lookup"><span data-stu-id="4bd48-132">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a><span data-ttu-id="4bd48-133">Operadores condicionales NULL ?.</span><span class="sxs-lookup"><span data-stu-id="4bd48-133">Null-conditional operators ?.</span></span> <span data-ttu-id="4bd48-134">y ?[]</span><span class="sxs-lookup"><span data-stu-id="4bd48-134">and ?[]</span></span>

<span data-ttu-id="4bd48-135">Disponible en C# 6 y versiones posteriores, un operador condicional NULL aplica una operación de [acceso a miembros](#member-access-expression-), `?.`, o [acceso a elementos](#indexer-operator-), `?[]`, a su operando solo si dicho operando se evalúa como no `null`.</span><span class="sxs-lookup"><span data-stu-id="4bd48-135">Available in C# 6 and later, a null-conditional operator applies a [member access](#member-access-expression-), `?.`, or [element access](#indexer-operator-), `?[]`, operation to its operand only if that operand evaluates to non-null; otherwise, it returns `null`.</span></span> <span data-ttu-id="4bd48-136">Es decir:</span><span class="sxs-lookup"><span data-stu-id="4bd48-136">That is,</span></span>

- <span data-ttu-id="4bd48-137">Si `a` se evalúa como `null`, el resultado de `a?.x` o `a?[x]` es `null`.</span><span class="sxs-lookup"><span data-stu-id="4bd48-137">If `a` evaluates to `null`, the result of `a?.x` or `a?[x]` is `null`.</span></span>
- <span data-ttu-id="4bd48-138">Si `a` se evalúa como no NULL, el resultado de `a?.x` o `a?[x]` es el mismo que el resultado de `a.x` o `a[x]`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="4bd48-138">If `a` evaluates to non-null, the result of `a?.x` or `a?[x]` is the same as the result of `a.x` or `a[x]`, respectively.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4bd48-139">Si `a.x` o `a[x]` producen una excepción, `a?.x` o `a?[x]` produciría la misma excepción para `a` no NULL.</span><span class="sxs-lookup"><span data-stu-id="4bd48-139">If `a.x` or `a[x]` throws an exception, `a?.x` or `a?[x]` would throw the same exception for non-null `a`.</span></span> <span data-ttu-id="4bd48-140">Por ejemplo, si `a` es una instancia de matriz que no es NULL y `x` está fuera de los límites de `a`, `a?[x]` produciría una excepción <xref:System.IndexOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="4bd48-140">For example, if `a` is a non-null array instance and `x` is outside the bounds of `a`, `a?[x]` would throw an <xref:System.IndexOutOfRangeException>.</span></span>

<span data-ttu-id="4bd48-141">Los operadores de condición NULL se cortocircuitan.</span><span class="sxs-lookup"><span data-stu-id="4bd48-141">The null-conditional operators are short-circuiting.</span></span> <span data-ttu-id="4bd48-142">Es decir, si una operación en una cadena de la operación de acceso a elementos o miembros condicional devuelve `null`, no se ejecuta el resto de la cadena.</span><span class="sxs-lookup"><span data-stu-id="4bd48-142">That is, if one operation in a chain of conditional member or element access operations returns `null`, the rest of the chain doesn't execute.</span></span> <span data-ttu-id="4bd48-143">En el ejemplo siguiente, `B` no se evalúa si `A` se evalúa como `null` y `C` no se evalúa si `A` o `B` se evalúan como `null`:</span><span class="sxs-lookup"><span data-stu-id="4bd48-143">In the following example, `B` is not evaluated if `A` evaluates to `null` and `C` is not evaluated if `A` or `B` evaluates to `null`:</span></span>

```csharp
A?.B?.Do(C);
A?.B?[C];
```

<span data-ttu-id="4bd48-144">En el siguiente ejemplo se muestra el uso de los operadores `?.` y `?[]`:</span><span class="sxs-lookup"><span data-stu-id="4bd48-144">The following example demonstrates the usage of the `?.` and `?[]` operators:</span></span>

[!code-csharp-interactive[null-conditional operators](snippets/shared/MemberAccessOperators.cs#NullConditional)]

<span data-ttu-id="4bd48-145">En el ejemplo anterior también se usa el [operador de fusión de NULL `??`](null-coalescing-operator.md) para especificar una expresión alternativa que se evaluará en caso de que el resultado de la operación condicional NULL sea `null`.</span><span class="sxs-lookup"><span data-stu-id="4bd48-145">The preceding example also uses the [null-coalescing operator `??`](null-coalescing-operator.md) to specify an alternative expression to evaluate in case the result of a null-conditional operation is `null`.</span></span>

<span data-ttu-id="4bd48-146">Si `a.x` o `a[x]` es de un tipo de valor que no admite un valor NULL, `T`, `a?.x` o `a?[x]` es del [tipo de valor que admite un valor NULL](../builtin-types/nullable-value-types.md) `T?` correspondiente.</span><span class="sxs-lookup"><span data-stu-id="4bd48-146">If `a.x` or `a[x]` is of a non-nullable value type `T`, `a?.x` or `a?[x]` is of the corresponding [nullable value type](../builtin-types/nullable-value-types.md) `T?`.</span></span> <span data-ttu-id="4bd48-147">Si necesita una expresión de tipo `T`, aplique el operador de fusión de NULL `??` a una expresión condicional NULL, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4bd48-147">If you need an expression of type `T`, apply the null-coalescing operator `??` to a null-conditional expression, as the following example shows:</span></span>

[!code-csharp-interactive[null-conditional with null-coalescing](snippets/shared/MemberAccessOperators.cs#NullConditionalWithNullCoalescing)]

<span data-ttu-id="4bd48-148">En el ejemplo anterior, si no utiliza el operador `??`, `numbers?.Length < 2` da como resultado `false` cuando `numbers` es `null`.</span><span class="sxs-lookup"><span data-stu-id="4bd48-148">In the preceding example, if you don't use the `??` operator, `numbers?.Length < 2` evaluates to `false` when `numbers` is `null`.</span></span>

<span data-ttu-id="4bd48-149">El operador de acceso de miembro condicional NULL `?.` también se conoce con el nombre de operador Elvis.</span><span class="sxs-lookup"><span data-stu-id="4bd48-149">The null-conditional member access operator `?.` is also known as the Elvis operator.</span></span>

> [!NOTE]
> <span data-ttu-id="4bd48-150">En C# 8, el [operador null-forgiving](null-forgiving.md) finaliza la lista de operaciones null-conditional anteriores.</span><span class="sxs-lookup"><span data-stu-id="4bd48-150">In C# 8, the [null-forgiving operator](null-forgiving.md) terminates the list of preceding null-conditional operations.</span></span> <span data-ttu-id="4bd48-151">Por ejemplo, la expresión `x?.y!.z` se analiza como `(x?.y)!.z`.</span><span class="sxs-lookup"><span data-stu-id="4bd48-151">For example, the expression `x?.y!.z` is parsed as `(x?.y)!.z`.</span></span> <span data-ttu-id="4bd48-152">Debido a esta interpretación, `z` se evalúa incluso si `x` es `null`, lo que puede dar lugar a <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="4bd48-152">Due to this interpretation, `z` is evaluated even if `x` is `null`, which may result in a <xref:System.NullReferenceException>.</span></span>

### <a name="thread-safe-delegate-invocation"></a><span data-ttu-id="4bd48-153">Invocación de delegado seguro para subprocesos</span><span class="sxs-lookup"><span data-stu-id="4bd48-153">Thread-safe delegate invocation</span></span>

<span data-ttu-id="4bd48-154">Use el operador `?.` para comprobar si un delegado es distinto de NULL y se invoca de forma segura para subprocesos (por ejemplo, cuando se [genera un evento](../../../standard/events/how-to-raise-and-consume-events.md)), tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="4bd48-154">Use the `?.` operator to check if a delegate is non-null and invoke it in a thread-safe way (for example, when you [raise an event](../../../standard/events/how-to-raise-and-consume-events.md)), as the following code shows:</span></span>

```csharp
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="4bd48-155">Ese código es equivalente al código siguiente que se usaría en C# 5 o una versión anterior:</span><span class="sxs-lookup"><span data-stu-id="4bd48-155">That code is equivalent to the following code that you would use in C# 5 or earlier:</span></span>

```csharp
var handler = this.PropertyChanged;
if (handler != null)
{
    handler(…);
}
```

<span data-ttu-id="4bd48-156">Es un modo seguro para subprocesos de asegurarse de que solo se invoca un `handler` que no es NULL.</span><span class="sxs-lookup"><span data-stu-id="4bd48-156">That is a thread-safe way to ensure that only a non-null `handler` is invoked.</span></span> <span data-ttu-id="4bd48-157">Dado que las instancias de delegado son inmutables, ningún subproceso puede cambiar el valor al que hace referencia la variable local `handler`.</span><span class="sxs-lookup"><span data-stu-id="4bd48-157">Because delegate instances are immutable, no thread can change the object referenced by the `handler` local variable.</span></span> <span data-ttu-id="4bd48-158">En concreto, si el código que ha ejecutado otro subproceso cancela la suscripción del evento `PropertyChanged` y `PropertyChanged` se convierte en `null` antes de que se invoque `handler`, el objeto al que hace referencia `handler` queda intacto.</span><span class="sxs-lookup"><span data-stu-id="4bd48-158">In particular, if the code executed by another thread unsubscribes from the `PropertyChanged` event and `PropertyChanged` becomes `null` before `handler` is invoked, the object referenced by `handler` remains unaffected.</span></span> <span data-ttu-id="4bd48-159">El operador `?.` evalúa el operando de la izquierda no más de una vez, lo que garantiza que no se pueda cambiar a `null` después de verificarse como no NULL.</span><span class="sxs-lookup"><span data-stu-id="4bd48-159">The `?.` operator evaluates its left-hand operand no more than once, guaranteeing that it cannot be changed to `null` after being verified as non-null.</span></span>

## <a name="invocation-expression-"></a><span data-ttu-id="4bd48-160">Expresión de invocación ()</span><span class="sxs-lookup"><span data-stu-id="4bd48-160">Invocation expression ()</span></span>

<span data-ttu-id="4bd48-161">Utilice paréntesis, `()`, para llamar a un [método](../../programming-guide/classes-and-structs/methods.md) o invocar un [delegado](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="4bd48-161">Use parentheses, `()`, to call a [method](../../programming-guide/classes-and-structs/methods.md) or invoke a [delegate](../../programming-guide/delegates/index.md).</span></span>

<span data-ttu-id="4bd48-162">En el ejemplo siguiente se muestra cómo llamar a un método, con o sin argumentos, y cómo invocar un delegado:</span><span class="sxs-lookup"><span data-stu-id="4bd48-162">The following example demonstrates how to call a method, with or without arguments, and invoke a delegate:</span></span>

[!code-csharp-interactive[invocation with ()](snippets/shared/MemberAccessOperators.cs#Invocation)]

<span data-ttu-id="4bd48-163">También usa paréntesis al invocar un [constructor](../../programming-guide/classes-and-structs/constructors.md) con el operador [`new`](new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="4bd48-163">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with the [`new`](new-operator.md) operator.</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="4bd48-164">Otros usos de ()</span><span class="sxs-lookup"><span data-stu-id="4bd48-164">Other usages of ()</span></span>

<span data-ttu-id="4bd48-165">También usa los paréntesis para ajustar el orden en el que se van a evaluar operaciones en una expresión.</span><span class="sxs-lookup"><span data-stu-id="4bd48-165">You also use parentheses to adjust the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="4bd48-166">Para obtener más información, vea [Operadores de C# (referencia de C#)](index.md).</span><span class="sxs-lookup"><span data-stu-id="4bd48-166">For more information, see [C# operators](index.md).</span></span>

<span data-ttu-id="4bd48-167">[Expresiones de conversión](type-testing-and-cast.md#cast-expression), que realizan conversiones de tipo explícitas, también utilizan paréntesis.</span><span class="sxs-lookup"><span data-stu-id="4bd48-167">[Cast expressions](type-testing-and-cast.md#cast-expression), which perform explicit type conversions, also use parentheses.</span></span>

## <a name="index-from-end-operator-"></a><span data-ttu-id="4bd48-168">Indexación desde el operador final ^</span><span class="sxs-lookup"><span data-stu-id="4bd48-168">Index from end operator ^</span></span>

<span data-ttu-id="4bd48-169">Disponible en C# 8.0 y versiones posteriores, el operador `^` indica la posición del elemento a partir del final de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="4bd48-169">Available in C# 8.0 and later, the `^` operator indicates the element position from the end of a sequence.</span></span> <span data-ttu-id="4bd48-170">En el caso de una secuencia de longitud `length`, `^n` apunta al elemento con desplazamiento `length - n` desde el inicio de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="4bd48-170">For a sequence of length `length`, `^n` points to the element with offset `length - n` from the start of a sequence.</span></span> <span data-ttu-id="4bd48-171">Por ejemplo, `^1` apunta al último elemento de una secuencia y `^length` apunta al primer elemento de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="4bd48-171">For example, `^1` points to the last element of a sequence and `^length` points to the first element of a sequence.</span></span>

[!code-csharp[index from end](snippets/shared/MemberAccessOperators.cs#IndexFromEnd)]

<span data-ttu-id="4bd48-172">Como se muestra en el ejemplo anterior, la expresión `^e` es del tipo <xref:System.Index?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4bd48-172">As the preceding example shows, expression `^e` is of the <xref:System.Index?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="4bd48-173">En la expresión `^e`, el resultado de `e` debe poderse convertir implícitamente a `int`.</span><span class="sxs-lookup"><span data-stu-id="4bd48-173">In expression `^e`, the result of `e` must be implicitly convertible to `int`.</span></span>

<span data-ttu-id="4bd48-174">También puede usar el operador `^` con el [operador de intervalo](#range-operator-) para crear un intervalo de índices.</span><span class="sxs-lookup"><span data-stu-id="4bd48-174">You can also use the `^` operator with the [range operator](#range-operator-) to create a range of indices.</span></span> <span data-ttu-id="4bd48-175">Para más información, consulte [Índices y rangos](../../tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="4bd48-175">For more information, see [Indices and ranges](../../tutorials/ranges-indexes.md).</span></span>

## <a name="range-operator-"></a><span data-ttu-id="4bd48-176">Operador de intervalo .</span><span class="sxs-lookup"><span data-stu-id="4bd48-176">Range operator ..</span></span>

<span data-ttu-id="4bd48-177">Disponible en C# 8.0 y versiones posteriores, el operador `..` especifica el inicio y el final de un intervalo de índices como sus operandos.</span><span class="sxs-lookup"><span data-stu-id="4bd48-177">Available in C# 8.0 and later, the `..` operator specifies the start and end of a range of indices as its operands.</span></span> <span data-ttu-id="4bd48-178">El operando izquierdo es un inicio *inclusivo* de un intervalo.</span><span class="sxs-lookup"><span data-stu-id="4bd48-178">The left-hand operand is an *inclusive* start of a range.</span></span> <span data-ttu-id="4bd48-179">El operando derecho es un inicio *exclusivo* de un intervalo.</span><span class="sxs-lookup"><span data-stu-id="4bd48-179">The right-hand operand is an *exclusive* end of a range.</span></span> <span data-ttu-id="4bd48-180">Cualquiera de los operandos puede ser un índice desde el inicio o desde el final de una secuencia, tal y como muestra el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4bd48-180">Either of operands can be an index from the start or from the end of a sequence, as the following example shows:</span></span>

[!code-csharp[range examples](snippets/shared/MemberAccessOperators.cs#Ranges)]

<span data-ttu-id="4bd48-181">Como se muestra en el ejemplo anterior, la expresión `a..b` es del tipo <xref:System.Range?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4bd48-181">As the preceding example shows, expression `a..b` is of the <xref:System.Range?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="4bd48-182">En la expresión `a..b`, los resultados de `a` y `b` deben poderse convertir implícitamente a `int` o <xref:System.Index>.</span><span class="sxs-lookup"><span data-stu-id="4bd48-182">In expression `a..b`, the results of `a` and `b` must be implicitly convertible to `int` or <xref:System.Index>.</span></span>

<span data-ttu-id="4bd48-183">Puede omitir cualquiera de los operandos del operador `..` para obtener un intervalo abierto:</span><span class="sxs-lookup"><span data-stu-id="4bd48-183">You can omit any of the operands of the `..` operator to obtain an open-ended range:</span></span>

- <span data-ttu-id="4bd48-184">`a..` es equivalente a `a..^0`</span><span class="sxs-lookup"><span data-stu-id="4bd48-184">`a..` is equivalent to `a..^0`</span></span>
- <span data-ttu-id="4bd48-185">`..b` es equivalente a `0..b`</span><span class="sxs-lookup"><span data-stu-id="4bd48-185">`..b` is equivalent to `0..b`</span></span>
- <span data-ttu-id="4bd48-186">`..` es equivalente a `0..^0`</span><span class="sxs-lookup"><span data-stu-id="4bd48-186">`..` is equivalent to `0..^0`</span></span>

[!code-csharp[ranges with omitted operands](snippets/shared/MemberAccessOperators.cs#RangesOptional)]

<span data-ttu-id="4bd48-187">Para más información, consulte [Índices y rangos](../../tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="4bd48-187">For more information, see [Indices and ranges](../../tutorials/ranges-indexes.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="4bd48-188">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="4bd48-188">Operator overloadability</span></span>

<span data-ttu-id="4bd48-189">Los operadores `.`, `()`, `^` y `..` no se pueden sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="4bd48-189">The `.`, `()`, `^`, and `..` operators cannot be overloaded.</span></span> <span data-ttu-id="4bd48-190">El operador `[]` también se considera un operador que no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="4bd48-190">The `[]` operator is also considered a non-overloadable operator.</span></span> <span data-ttu-id="4bd48-191">Use [indizadores](../../programming-guide/indexers/index.md) para admitir la indización con tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="4bd48-191">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4bd48-192">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="4bd48-192">C# language specification</span></span>

<span data-ttu-id="4bd48-193">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="4bd48-193">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="4bd48-194">Acceso a miembros</span><span class="sxs-lookup"><span data-stu-id="4bd48-194">Member access</span></span>](~/_csharplang/spec/expressions.md#member-access)
- [<span data-ttu-id="4bd48-195">Acceso a elementos</span><span class="sxs-lookup"><span data-stu-id="4bd48-195">Element access</span></span>](~/_csharplang/spec/expressions.md#element-access)
- [<span data-ttu-id="4bd48-196">Operador condicional de NULL</span><span class="sxs-lookup"><span data-stu-id="4bd48-196">Null-conditional operator</span></span>](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [<span data-ttu-id="4bd48-197">Expresiones de invocación</span><span class="sxs-lookup"><span data-stu-id="4bd48-197">Invocation expressions</span></span>](~/_csharplang/spec/expressions.md#invocation-expressions)

<span data-ttu-id="4bd48-198">Para más información sobre índices y rangos, vea la [nota de propuesta de características](~/_csharplang/proposals/csharp-8.0/ranges.md).</span><span class="sxs-lookup"><span data-stu-id="4bd48-198">For more information about indices and ranges, see the [feature proposal note](~/_csharplang/proposals/csharp-8.0/ranges.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4bd48-199">Vea también</span><span class="sxs-lookup"><span data-stu-id="4bd48-199">See also</span></span>

- [<span data-ttu-id="4bd48-200">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="4bd48-200">C# reference</span></span>](../index.md)
- [<span data-ttu-id="4bd48-201">Operadores y expresiones de C#</span><span class="sxs-lookup"><span data-stu-id="4bd48-201">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="4bd48-202">?? (operador de uso combinado de NULL)</span><span class="sxs-lookup"><span data-stu-id="4bd48-202">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="4bd48-203">Operador ::</span><span class="sxs-lookup"><span data-stu-id="4bd48-203">:: operator</span></span>](namespace-alias-qualifier.md)
