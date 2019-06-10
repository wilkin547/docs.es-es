---
title: 'Operadores de acceso a miembros: referencia de C#'
description: Obtenga información sobre los operadores de C# que puede usar para acceder a los miembros de tipos.
ms.date: 05/09/2019
author: pkulikov
f1_keywords:
- ._CSharpKeyword
- '[]_CSharpKeyword'
- ()_CSharpKeyword
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
ms.openlocfilehash: de0715a2ac946fa47f0d83ac8569595e622f0b97
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758087"
---
# <a name="member-access-operators-c-reference"></a><span data-ttu-id="83198-103">Operadores de acceso a miembros (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="83198-103">Member access operators (C# Reference)</span></span>

<span data-ttu-id="83198-104">Puede usar los siguientes operadores cuando tiene acceso a un miembro de tipo:</span><span class="sxs-lookup"><span data-stu-id="83198-104">You might use the following operators when you access a type member:</span></span>

- <span data-ttu-id="83198-105">[`.` (acceso a miembros)](#member-access-operator-): para acceder a un miembro de un espacio de nombres o un tipo</span><span class="sxs-lookup"><span data-stu-id="83198-105">[`.` (member access)](#member-access-operator-): to access a member of a namespace or a type</span></span>
- <span data-ttu-id="83198-106">[`[]` (elemento de matriz o acceso a indizador)](#indexer-operator-): para acceder a un elemento de matriz o un indizador de tipo</span><span class="sxs-lookup"><span data-stu-id="83198-106">[`[]` (array element or indexer access)](#indexer-operator-): to access an array element or a type indexer</span></span>
- <span data-ttu-id="83198-107">[`?.` y `?[]` (operadores condicionales NULL)](#null-conditional-operators--and-): para realizar una operación de acceso a elementos o miembros solo si un operando es distinto de NULL</span><span class="sxs-lookup"><span data-stu-id="83198-107">[`?.` and `?[]` (null-conditional operators)](#null-conditional-operators--and-): to perform a member or element access operation only if an operand is non-null</span></span>
- <span data-ttu-id="83198-108">[`()` (invocación)](#invocation-operator-): para llamar a un método de acceso o invocar un delegado</span><span class="sxs-lookup"><span data-stu-id="83198-108">[`()` (invocation)](#invocation-operator-): to call an accessed method or invoke a delegate</span></span>

## <a name="member-access-operator-"></a><span data-ttu-id="83198-109">Operador de acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="83198-109">Member access operator .</span></span>

<span data-ttu-id="83198-110">Use el token `.` para acceder a un miembro de un espacio de nombres o un tipo, como se muestran en los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="83198-110">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="83198-111">Use `.` para acceder a un espacio de nombres anidado dentro de un espacio de nombres, como se muestra en el siguiente ejemplo de una [directiva `using`](../keywords/using-directive.md):</span><span class="sxs-lookup"><span data-stu-id="83198-111">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#NestedNamespace)]

- <span data-ttu-id="83198-112">Use `.` para formar un *nombre completo* para tener acceso a un tipo dentro de un espacio de nombres, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="83198-112">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#QualifiedName)]

  <span data-ttu-id="83198-113">Utilice una [directiva `using`](../keywords/using-directive.md) para hacer que el uso de nombres completos sea opcional.</span><span class="sxs-lookup"><span data-stu-id="83198-113">Use a [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="83198-114">Use `.` para tener acceso a los [miembros de tipo](../../programming-guide/classes-and-structs/index.md#members), que no son estáticos y, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="83198-114">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#TypeMemberAccess)]

<span data-ttu-id="83198-115">También puede usar `.` para acceder a un [método de extensión](../../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="83198-115">You can also use `.` to access an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="indexer-operator-"></a><span data-ttu-id="83198-116">Operador del indizador []</span><span class="sxs-lookup"><span data-stu-id="83198-116">Indexer operator []</span></span>

<span data-ttu-id="83198-117">Los corchetes, `[]`, se suelen usar para el acceso a matriz, indizador o elemento de puntero.</span><span class="sxs-lookup"><span data-stu-id="83198-117">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

### <a name="array-access"></a><span data-ttu-id="83198-118">Acceso a matriz</span><span class="sxs-lookup"><span data-stu-id="83198-118">Array access</span></span>

<span data-ttu-id="83198-119">En el ejemplo siguiente se muestra cómo se obtiene acceso a los elementos de matriz:</span><span class="sxs-lookup"><span data-stu-id="83198-119">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Arrays)]

<span data-ttu-id="83198-120">Si un índice de matriz se encuentra fuera de los límites de la dimensión correspondiente de una matriz, se produce una excepción <xref:System.IndexOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="83198-120">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="83198-121">Tal como se muestra en el ejemplo anterior, también usa corchetes al declarar un tipo de matriz o crear instancias de matriz.</span><span class="sxs-lookup"><span data-stu-id="83198-121">As the preceding example shows, you also use square brackets when you declare an array type or instantiate an array instance.</span></span>

<span data-ttu-id="83198-122">Para obtener más información sobre las matrices, consulte [Matrices](../../programming-guide/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="83198-122">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

### <a name="indexer-access"></a><span data-ttu-id="83198-123">Acceso a indizador</span><span class="sxs-lookup"><span data-stu-id="83198-123">Indexer access</span></span>

<span data-ttu-id="83198-124">En el siguiente ejemplo se usa el tipo <xref:System.Collections.Generic.Dictionary%602> de .NET para mostrar el acceso a indizador:</span><span class="sxs-lookup"><span data-stu-id="83198-124">The following example uses .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Indexers)]

<span data-ttu-id="83198-125">Los indizadores le permiten indizar las instancias de un tipo definido por el usuario de un modo similar a la indización de matrices.</span><span class="sxs-lookup"><span data-stu-id="83198-125">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="83198-126">A diferencia de los índices de matriz, que deben ser enteros, los argumentos de indizador se pueden declarar para ser de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="83198-126">Unlike array indices, which must be integer, the indexer arguments can be declared to be of any type.</span></span>

<span data-ttu-id="83198-127">Para más información sobre los indizadores, consulte [Indizadores](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="83198-127">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="83198-128">Otros usos de []</span><span class="sxs-lookup"><span data-stu-id="83198-128">Other usages of []</span></span>

<span data-ttu-id="83198-129">Para información sobre el acceso de los elementos de puntero, consulte la sección [Operador de acceso de elemento de puntero](pointer-related-operators.md#pointer-element-access-operator-) del artículo [Operadores relacionados con el puntero](pointer-related-operators.md).</span><span class="sxs-lookup"><span data-stu-id="83198-129">For information about pointer element access, see the [Pointer element access operator []](pointer-related-operators.md#pointer-element-access-operator-) section of the [Pointer related operators](pointer-related-operators.md) article.</span></span>

<span data-ttu-id="83198-130">También usa los corchetes para especificar [atributos](../../programming-guide/concepts/attributes/index.md):</span><span class="sxs-lookup"><span data-stu-id="83198-130">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="null-conditional-operators--and-"></a><span data-ttu-id="83198-131">Operadores condicionales NULL ?.</span><span class="sxs-lookup"><span data-stu-id="83198-131">Null-conditional operators ?.</span></span> <span data-ttu-id="83198-132">y ?[]</span><span class="sxs-lookup"><span data-stu-id="83198-132">and ?[]</span></span>

<span data-ttu-id="83198-133">Disponible en C# 6 y versiones posteriores, un operador condicional NULL aplica una operación de acceso a miembros, `?.`, o acceso a elementos, `?[]`, a su operando solo si dicho operando se evalúa como no NULL.</span><span class="sxs-lookup"><span data-stu-id="83198-133">Available in C# 6 and later, a null-conditional operator applies a member access, `?.`, or element access, `?[]`, operation to its operand only if that operand evaluates to non-null.</span></span> <span data-ttu-id="83198-134">Si el operando se evalúa como `null`, el resultado de aplicar el operador es `null`.</span><span class="sxs-lookup"><span data-stu-id="83198-134">If the operand evaluates to `null`, the result of applying the operator is `null`.</span></span> <span data-ttu-id="83198-135">El operador de acceso de miembro condicional NULL `?.` también se conoce con el nombre de operador Elvis.</span><span class="sxs-lookup"><span data-stu-id="83198-135">The null-conditional member access operator `?.` is also known as the Elvis operator.</span></span>

<span data-ttu-id="83198-136">Los operadores de condición NULL se cortocircuitan.</span><span class="sxs-lookup"><span data-stu-id="83198-136">The null-conditional operators are short-circuiting.</span></span> <span data-ttu-id="83198-137">Es decir, si una operación en una cadena de la operación de acceso a elementos o miembros condicional devuelve `null`, no se ejecuta el resto de la cadena.</span><span class="sxs-lookup"><span data-stu-id="83198-137">That is, if one operation in a chain of conditional member or element access operations returns `null`, the rest of the chain doesn't execute.</span></span> <span data-ttu-id="83198-138">En el ejemplo siguiente, `B` no se evalúa si `A` se evalúa como `null` y `C` no se evalúa si `A` o `B` se evalúan como `null`:</span><span class="sxs-lookup"><span data-stu-id="83198-138">In the following example, `B` is not evaluated if `A` evaluates to `null` and `C` is not evaluated if `A` or `B` evaluates to `null`:</span></span>

```csharp
A?.B?.Do(C);
A?.B?[C];
```

<span data-ttu-id="83198-139">En el siguiente ejemplo se muestra el uso de los operadores `?.` y `?[]`:</span><span class="sxs-lookup"><span data-stu-id="83198-139">The following example demonstrates the usage of the `?.` and `?[]` operators:</span></span>

[!code-csharp-interactive[null-conditional operators](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#NullConditional)]

<span data-ttu-id="83198-140">El ejemplo anterior también muestra el uso del [operador de uso combinado de NULL](null-coalescing-operator.md).</span><span class="sxs-lookup"><span data-stu-id="83198-140">The preceding example also shows the usage of the [null-coalescing operator](null-coalescing-operator.md).</span></span> <span data-ttu-id="83198-141">Puede usar el operador de uso combinado de NULL para proporcionar una expresión alternativa a fin de evaluar en caso de que el resultado de la operación condicional NULL sea `null`.</span><span class="sxs-lookup"><span data-stu-id="83198-141">You might use the null-coalescing operator to provide an alternative expression to evaluate in case the result of the null-conditional operation is `null`.</span></span>

### <a name="thread-safe-delegate-invocation"></a><span data-ttu-id="83198-142">Invocación de delegado seguro para subprocesos</span><span class="sxs-lookup"><span data-stu-id="83198-142">Thread-safe delegate invocation</span></span>

<span data-ttu-id="83198-143">Use el operador `?.` para comprobar si un delegado es distinto de NULL y se invoca de forma segura para subprocesos (por ejemplo, cuando se [genera un evento](../../../standard/events/how-to-raise-and-consume-events.md)), tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="83198-143">Use the `?.` operator to check if a delegate is non-null and invoke it in a thread-safe way (for example, when you [raise an event](../../../standard/events/how-to-raise-and-consume-events.md)), as the following code shows:</span></span>

```csharp
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="83198-144">Ese código es equivalente al código siguiente que se usaría en C# 5 o una versión anterior:</span><span class="sxs-lookup"><span data-stu-id="83198-144">That code is equivalent to the following code that you would use in C# 5 or earlier:</span></span>

```csharp
var handler = this.PropertyChanged;
if (handler != null)
{
    handler(…);
}
```

## <a name="invocation-operator-"></a><span data-ttu-id="83198-145">Operador de invocación ()</span><span class="sxs-lookup"><span data-stu-id="83198-145">Invocation operator ()</span></span>

<span data-ttu-id="83198-146">Utilice paréntesis, `()`, para llamar a un [método](../../programming-guide/classes-and-structs/methods.md) o invocar un [delegado](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="83198-146">Use parentheses, `()`, to call a [method](../../programming-guide/classes-and-structs/methods.md) or invoke a [delegate](../../programming-guide/delegates/index.md).</span></span>

<span data-ttu-id="83198-147">En el ejemplo siguiente se muestra cómo llamar a un método, con o sin argumentos, y cómo invocar un delegado:</span><span class="sxs-lookup"><span data-stu-id="83198-147">The following example demonstrates how to call a method, with or without arguments, and invoke a delegate:</span></span>

[!code-csharp-interactive[invocation with ()](~/samples/csharp/language-reference/operators/MemberAccessOperators.cs#Invocation)]

<span data-ttu-id="83198-148">También usa paréntesis al invocar un [constructor](../../programming-guide/classes-and-structs/constructors.md) con un operador [`new`](../keywords/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="83198-148">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with a [`new`](../keywords/new-operator.md) operator.</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="83198-149">Otros usos de ()</span><span class="sxs-lookup"><span data-stu-id="83198-149">Other usages of ()</span></span>

<span data-ttu-id="83198-150">También usa los paréntesis para especificar el orden en el que se van a evaluar operaciones en una expresión.</span><span class="sxs-lookup"><span data-stu-id="83198-150">You also use parentheses to specify the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="83198-151">Para más información, consulte la sección [Agregar paréntesis](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) del artículo [Operadores](../../programming-guide/statements-expressions-operators/operators.md).</span><span class="sxs-lookup"><span data-stu-id="83198-151">For more information, see the [Adding parentheses](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) section of the [Operators](../../programming-guide/statements-expressions-operators/operators.md) article.</span></span> <span data-ttu-id="83198-152">Para ver la lista de operadores ordenados por nivel de precedencia, consulte [Operadores de C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="83198-152">For the list of operators ordered by precedence level, see [C# operators](index.md).</span></span>

<span data-ttu-id="83198-153">Las [expresiones de conversión](invocation-operator.md#cast-expression), que invocan un operador de conversión, también usan el paréntesis.</span><span class="sxs-lookup"><span data-stu-id="83198-153">[Cast expressions](invocation-operator.md#cast-expression), which invoke a conversion operator, also use parentheses.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="83198-154">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="83198-154">Operator overloadability</span></span>

<span data-ttu-id="83198-155">Los operadores `.` y `()` no se pueden sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="83198-155">The `.` and `()` operators cannot be overloaded.</span></span> <span data-ttu-id="83198-156">El operador `[]` también se considera un operador que no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="83198-156">The `[]` operator is also considered a non-overloadable operator.</span></span> <span data-ttu-id="83198-157">Use [indizadores](../../programming-guide/indexers/index.md) para admitir la indización con tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="83198-157">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="83198-158">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="83198-158">C# language specification</span></span>

<span data-ttu-id="83198-159">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="83198-159">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="83198-160">Acceso a miembros</span><span class="sxs-lookup"><span data-stu-id="83198-160">Member access</span></span>](~/_csharplang/spec/expressions.md#member-access)
- [<span data-ttu-id="83198-161">Acceso a elementos</span><span class="sxs-lookup"><span data-stu-id="83198-161">Element access</span></span>](~/_csharplang/spec/expressions.md#element-access)
- [<span data-ttu-id="83198-162">Operador condicional de NULL</span><span class="sxs-lookup"><span data-stu-id="83198-162">Null-conditional operator</span></span>](~/_csharplang/spec/expressions.md#null-conditional-operator)
- [<span data-ttu-id="83198-163">Expresiones de invocación</span><span class="sxs-lookup"><span data-stu-id="83198-163">Invocation expressions</span></span>](~/_csharplang/spec/expressions.md#invocation-expressions)

## <a name="see-also"></a><span data-ttu-id="83198-164">Vea también</span><span class="sxs-lookup"><span data-stu-id="83198-164">See also</span></span>

- [<span data-ttu-id="83198-165">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="83198-165">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="83198-166">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="83198-166">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="83198-167">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="83198-167">C# Operators</span></span>](index.md)
- [<span data-ttu-id="83198-168">?? (operador de uso combinado de NULL)</span><span class="sxs-lookup"><span data-stu-id="83198-168">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)
