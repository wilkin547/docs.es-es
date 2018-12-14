---
title: Instrucción foreach de C#
ms.date: 06/29/2018
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 417a8cefbc9bc7544ae1156992e6e6c549fb828f
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128627"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="17823-102">foreach, in (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="17823-102">foreach, in (C# reference)</span></span>

<span data-ttu-id="17823-103">La instrucción `foreach` ejecuta una instrucción o un bloque de instrucciones para cada elemento en una instancia del tipo que implementa la interfaz <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="17823-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="17823-104">La instrucción `foreach` no se limita a esos tipos y puede aplicarse a una instancia de cualquier tipo que satisfaga las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="17823-104">The `foreach` statement is not limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="17823-105">tiene el método público sin parámetros `GetEnumerator` cuyo tipo de valor devuelto es clase, estructura o tipo de interfaz,</span><span class="sxs-lookup"><span data-stu-id="17823-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="17823-106">el tipo de valor devuelto del método `GetEnumerator` tiene la propiedad pública `Current` y el método público sin parámetros `MoveNext` cuyo tipo de valor devuelto es <xref:System.Boolean>.</span><span class="sxs-lookup"><span data-stu-id="17823-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="17823-107">A partir de C# 7.3, si la propiedad `Current` del enumerador devuelve un [valor devuelto de referencia](ref.md#reference-return-values) (`ref T` donde `T` es el tipo del elemento de colección), se puede declarar la variable de iteración con el modificador `ref` o `ref readonly`.</span><span class="sxs-lookup"><span data-stu-id="17823-107">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](ref.md#reference-return-values) (`ref T` where `T` is the type of the collection element), you can declare the iteration variable with the `ref` or `ref readonly` modifier.</span></span>

<span data-ttu-id="17823-108">En cualquier punto del bloque de instrucciones `foreach`, se puede salir del bucle mediante la instrucción [break](break.md), o bien se puede ir a la siguiente iteración del bucle mediante la instrucción [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="17823-108">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="17823-109">También se puede salir de un bucle `foreach` mediante las instrucciones [goto](goto.md), [return](return.md) o [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="17823-109">You also can exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="examples"></a><span data-ttu-id="17823-110">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="17823-110">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="17823-111">El siguiente ejemplo muestra el uso de la instrucción `foreach` con una instancia del tipo <xref:System.Collections.Generic.List%601> que implementa la interfaz <xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="17823-111">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

<span data-ttu-id="17823-112">El siguiente ejemplo utiliza la instrucción `foreach` con una instancia del tipo <xref:System.Span%601?displayProperty=nameWithType>, que no implementa ninguna interfaz:</span><span class="sxs-lookup"><span data-stu-id="17823-112">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

[!code-csharp-interactive[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

<span data-ttu-id="17823-113">En el ejemplo siguiente se usa una variable de iteración `ref` para establecer el valor de cada elemento de una matriz stackalloc.</span><span class="sxs-lookup"><span data-stu-id="17823-113">The following example uses a `ref` iteration variable to set the value of each item in a stackalloc array.</span></span> <span data-ttu-id="17823-114">La versión `ref readonly` recorre en iteración la colección para imprimir todos los valores.</span><span class="sxs-lookup"><span data-stu-id="17823-114">The `ref readonly` version iterates the collection to print all the values.</span></span> <span data-ttu-id="17823-115">En la declaración de `readonly`, se usa una declaración de variable local implícita.</span><span class="sxs-lookup"><span data-stu-id="17823-115">The `readonly` declaration uses an implicit local variable declaration.</span></span> <span data-ttu-id="17823-116">Las declaraciones de variables implícitas se pueden usar con las declaraciones `ref` o `ref readonly`, al igual que las declaraciones de variables con tipo explícito.</span><span class="sxs-lookup"><span data-stu-id="17823-116">Implicit variable declarations can be used with either `ref` or `ref readonly` declarations, as can explicitly typed variable declarations.</span></span>

[!code-csharp-interactive[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#RefSpan)]

## <a name="c-language-specification"></a><span data-ttu-id="17823-117">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="17823-117">C# language specification</span></span>

<span data-ttu-id="17823-118">Para más información, vea la sección sobre la [instrucción foreach](~/_csharplang/spec/statements.md#the-foreach-statement) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="17823-118">For more information, see [The foreach statement](~/_csharplang/spec/statements.md#the-foreach-statement) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="17823-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="17823-119">See also</span></span>

- [<span data-ttu-id="17823-120">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="17823-120">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="17823-121">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="17823-121">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="17823-122">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="17823-122">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="17823-123">Instrucciones de iteración</span><span class="sxs-lookup"><span data-stu-id="17823-123">Iteration Statements</span></span>](iteration-statements.md)
- [<span data-ttu-id="17823-124">Utilizar foreach con matrices</span><span class="sxs-lookup"><span data-stu-id="17823-124">Using foreach with arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="17823-125">for (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="17823-125">for statement</span></span>](for.md)
