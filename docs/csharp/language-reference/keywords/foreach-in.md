---
title: foreach, in (Referencia de C#)
ms.date: 05/24/2018
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 7613590686f7f7ec6439da4a2bb672e524ab01e8
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34565711"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="af5fb-102">foreach, in (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="af5fb-102">foreach, in (C# Reference)</span></span>

<span data-ttu-id="af5fb-103">La instrucción `foreach` ejecuta una instrucción o un bloque de instrucciones para cada elemento en una instancia del tipo que implementa la interfaz <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="af5fb-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="af5fb-104">La instrucción `foreach` no se limita a esos tipos y puede aplicarse a una instancia de cualquier tipo que satisfaga las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="af5fb-104">The `foreach` statement is not limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="af5fb-105">tiene el método público sin parámetros `GetEnumerator` cuyo tipo de valor devuelto es clase, estructura o tipo de interfaz,</span><span class="sxs-lookup"><span data-stu-id="af5fb-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="af5fb-106">el tipo de valor devuelto del método `GetEnumerator` tiene la propiedad pública `Current` y el método público sin parámetros `MoveNext` cuyo tipo de valor devuelto es <xref:System.Boolean>.</span><span class="sxs-lookup"><span data-stu-id="af5fb-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="af5fb-107">En cualquier punto del bloque de instrucciones `foreach`, se puede salir del bucle mediante la instrucción [break](break.md), o bien se puede ir a la siguiente iteración del bucle mediante la instrucción [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="af5fb-107">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="af5fb-108">También se puede salir de un bucle `foreach` mediante las instrucciones [goto](goto.md), [return](return.md) o [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="af5fb-108">You also can exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="examples"></a><span data-ttu-id="af5fb-109">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="af5fb-109">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="af5fb-110">El siguiente ejemplo muestra el uso de la instrucción `foreach` con una instancia del tipo <xref:System.Collections.Generic.List%601> que implementa la interfaz <xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="af5fb-110">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

<span data-ttu-id="af5fb-111">El siguiente ejemplo utiliza la instrucción `foreach` con una instancia del tipo <xref:System.Span%601?displayProperty=nameWithType>, que no implementa ninguna interfaz:</span><span class="sxs-lookup"><span data-stu-id="af5fb-111">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

[!code-csharp-interactive[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="af5fb-112">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="af5fb-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="af5fb-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="af5fb-113">See also</span></span>

[<span data-ttu-id="af5fb-114">La instrucción foreach (especificación del lenguaje C#)</span><span class="sxs-lookup"><span data-stu-id="af5fb-114">The foreach statement (C# language specification)</span></span>](/dotnet/csharp/language-reference/language-specification/statements#the-foreach-statement)  
[<span data-ttu-id="af5fb-115">Utilizar foreach con matrices</span><span class="sxs-lookup"><span data-stu-id="af5fb-115">Using foreach with Arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)  
[<span data-ttu-id="af5fb-116">for</span><span class="sxs-lookup"><span data-stu-id="af5fb-116">for</span></span>](for.md)  
[<span data-ttu-id="af5fb-117">Instrucciones de iteración</span><span class="sxs-lookup"><span data-stu-id="af5fb-117">Iteration Statements</span></span>](iteration-statements.md)  
[<span data-ttu-id="af5fb-118">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="af5fb-118">C# Keywords</span></span>](index.md)  
[<span data-ttu-id="af5fb-119">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="af5fb-119">C# Reference</span></span>](../index.md)  
[<span data-ttu-id="af5fb-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="af5fb-120">C# Programming Guide</span></span>](../../programming-guide/index.md)  