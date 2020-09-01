---
description: foreach, in (Referencia de C#)
title: Instrucción foreach de C#
ms.date: 07/22/2020
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 2ed89fa52b2d3d369d668bf79ab32eaf7be18a8a
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142081"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="7e019-103">foreach, in (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="7e019-103">foreach, in (C# reference)</span></span>

<span data-ttu-id="7e019-104">La instrucción `foreach` ejecuta una instrucción o un bloque de instrucciones para cada elemento de una instancia del tipo que implementa la interfaz <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7e019-104">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface, as the following example shows:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="1" interactive="try-dotnet-method" :::

<span data-ttu-id="7e019-105">La instrucción `foreach` no está limitada a esos tipos.</span><span class="sxs-lookup"><span data-stu-id="7e019-105">The `foreach` statement isn't limited to those types.</span></span> <span data-ttu-id="7e019-106">Puede usarla con una instancia de cualquier tipo que cumpla las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7e019-106">You can use it with an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="7e019-107">un tipo tiene el método público sin parámetros `GetEnumerator` cuyo tipo de valor devuelto es clase, estructura o tipo de interfaz;</span><span class="sxs-lookup"><span data-stu-id="7e019-107">a type has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="7e019-108">el tipo de valor devuelto del método `GetEnumerator` tiene la propiedad pública `Current` y el método público sin parámetros `MoveNext` cuyo tipo de valor devuelto es <xref:System.Boolean>.</span><span class="sxs-lookup"><span data-stu-id="7e019-108">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="7e019-109">En el siguiente ejemplo se usa la instrucción `foreach` con una instancia del tipo <xref:System.Span%601?displayProperty=nameWithType>, que no implementa ninguna interfaz:</span><span class="sxs-lookup"><span data-stu-id="7e019-109">The following example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="2" :::

<span data-ttu-id="7e019-110">A partir de C# 7.3, si la propiedad `Current` del enumerador devuelve un [valor devuelto de referencia](ref.md#reference-return-values) (`ref T` donde `T` es el tipo de un elemento de colección), se puede declarar una variable de iteración con el modificador `ref` o `ref readonly`, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7e019-110">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](ref.md#reference-return-values) (`ref T` where `T` is the type of a collection element), you can declare an iteration variable with the `ref` or `ref readonly` modifier, as the following example shows:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="RefSpan" :::

<span data-ttu-id="7e019-111">A partir de C# 8.0, puede usar la instrucción `await foreach` para usar una secuencia de datos asincrónica, es decir, el tipo de colección que implementa la interfaz <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="7e019-111">Beginning with C# 8.0, you can use the `await foreach` statement to consume an asynchronous stream of data, that is, the collection type that implements the <xref:System.Collections.Generic.IAsyncEnumerable%601> interface.</span></span> <span data-ttu-id="7e019-112">Cada iteración del bucle se puede suspender mientras el siguiente elemento se recupera de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="7e019-112">Each iteration of the loop may be suspended while the next element is retrieved asynchronously.</span></span> <span data-ttu-id="7e019-113">En el ejemplo siguiente se muestra cómo usar la instrucción `await foreach`:</span><span class="sxs-lookup"><span data-stu-id="7e019-113">The following example shows how to use the `await foreach` statement:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="AwaitForeach" :::

<span data-ttu-id="7e019-114">Los elementos de secuencia se procesan de forma predeterminada en el contexto capturado.</span><span class="sxs-lookup"><span data-stu-id="7e019-114">By default, stream elements are processed in the captured context.</span></span> <span data-ttu-id="7e019-115">Si quiere deshabilitar la captura del contexto, use el método de extensión <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7e019-115">If you want to disable capturing of the context, use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> extension method.</span></span> <span data-ttu-id="7e019-116">Para obtener más información sobre los contextos de sincronización y la captura del contexto actual, vea [Utilizar el modelo asincrónico basado en tareas](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="7e019-116">For more information about synchronization contexts and capturing the current context, see [Consuming the Task-based asynchronous pattern](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span></span> <span data-ttu-id="7e019-117">Para obtener más información sobre secuencias asincrónicas, vea la sección [Secuencias asincrónicas](../../whats-new/csharp-8.md#asynchronous-streams) del artículo [Novedades de C# 8.0](../../whats-new/csharp-8.md).</span><span class="sxs-lookup"><span data-stu-id="7e019-117">For more information about asynchronous streams, see the [Asynchronous streams](../../whats-new/csharp-8.md#asynchronous-streams) section of the [What's new in C# 8.0](../../whats-new/csharp-8.md) article.</span></span>

<span data-ttu-id="7e019-118">En cualquier punto del bloque de instrucciones `foreach`, se puede salir del bucle mediante la instrucción [break](break.md), o bien se puede ir a la siguiente iteración del bucle mediante la instrucción [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="7e019-118">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="7e019-119">También se puede salir de un bucle `foreach` mediante las instrucciones [goto](goto.md), [return](return.md) o [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="7e019-119">You can also exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

<span data-ttu-id="7e019-120">Si la instrucción `foreach` se aplica a `null`, se produce <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="7e019-120">If the `foreach` statement is applied to `null`, a <xref:System.NullReferenceException> is thrown.</span></span> <span data-ttu-id="7e019-121">Si la colección de origen de la instrucción `foreach` está vacía, el cuerpo del bucle `foreach` no se ejecuta y se omite.</span><span class="sxs-lookup"><span data-stu-id="7e019-121">If the source collection of the `foreach` statement is empty, the body of the `foreach` loop isn't executed and skipped.</span></span>

## <a name="type-of-an-iteration-variable"></a><span data-ttu-id="7e019-122">Tipo de una variable de iteración</span><span class="sxs-lookup"><span data-stu-id="7e019-122">Type of an iteration variable</span></span>

<span data-ttu-id="7e019-123">Puede usar la palabra clave `var` para permitir que el compilador infiera el tipo de una variable de iteración de la instrucción `foreach`, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="7e019-123">You can use the `var` keyword to let the compiler infer the type of an iteration variable in the `foreach` statement, as the following code shows:</span></span>

```csharp
foreach (var item in collection) { }
```

<span data-ttu-id="7e019-124">También puede especificar de forma explícita el tipo de una variable de iteración, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="7e019-124">You can also explicitly specify the type of an iteration variable, as the following code shows:</span></span>

```csharp
IEnumerable<T> collection = new T[5];
foreach (V item in collection) { }
```

<span data-ttu-id="7e019-125">En el formulario anterior, el tipo `T` de un elemento de colección se debe poder convertir de forma implícita o explícita en el tipo `V` de una variable de iteración.</span><span class="sxs-lookup"><span data-stu-id="7e019-125">In the preceding form, type `T` of a collection element must be implicitly or explicitly convertible to type `V` of an iteration variable.</span></span> <span data-ttu-id="7e019-126">Si se produce un error en una conversión explícita de `T` en `V` en tiempo de ejecución, la instrucción `foreach` produce <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="7e019-126">If an explicit conversion from `T` to `V` fails at run time, the `foreach` statement throws an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="7e019-127">Por ejemplo, si `T` es un tipo de clase no sellada, `V` puede ser cualquier tipo de interfaz, incluso uno que `T` no implemente.</span><span class="sxs-lookup"><span data-stu-id="7e019-127">For example, if `T` is a non-sealed class type, `V` can be any interface type, even the one that `T` doesn't implement.</span></span> <span data-ttu-id="7e019-128">En tiempo de ejecución, el tipo de un elemento de colección puede ser el que deriva de `T` y realmente implementa `V`.</span><span class="sxs-lookup"><span data-stu-id="7e019-128">At run time, the type of a collection element may be the one that derives from `T` and actually implements `V`.</span></span> <span data-ttu-id="7e019-129">Si ese no es el caso, se produce <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="7e019-129">If that's not the case, an <xref:System.InvalidCastException> is thrown.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7e019-130">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="7e019-130">C# language specification</span></span>

<span data-ttu-id="7e019-131">Para más información, vea la sección sobre la [instrucción foreach](~/_csharplang/spec/statements.md#the-foreach-statement) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="7e019-131">For more information, see [The foreach statement](~/_csharplang/spec/statements.md#the-foreach-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7e019-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e019-132">See also</span></span>

- [<span data-ttu-id="7e019-133">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="7e019-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="7e019-134">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="7e019-134">C# keywords</span></span>](index.md)
- [<span data-ttu-id="7e019-135">Utilizar foreach con matrices</span><span class="sxs-lookup"><span data-stu-id="7e019-135">Using foreach with arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="7e019-136">for (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="7e019-136">for statement</span></span>](for.md)
