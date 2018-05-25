---
title: foreach, in (Referencia de C#)
ms.date: 10/11/2017
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: c0b1481988a2e3199fc6d06ca30cb5194ab2f44c
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2018
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="a731e-102">foreach, in (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a731e-102">foreach, in (C# Reference)</span></span>

<span data-ttu-id="a731e-103">La instrucción `foreach` repite un grupo de instrucciones insertadas por cada elemento de una matriz o una colección de objetos que implementa la interfaz <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a731e-103">The `foreach` statement repeats a group of embedded statements for each element in an array or an object collection that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="a731e-104">La [instrucción foreach](/dotnet/csharp/language-reference/language-specification/statements#the-foreach-statement) se usa para recorrer en iteración la colección para obtener la información que le interesa, pero no se puede usar para agregar o quitar elementos de la colección de origen para evitar efectos secundarios imprevistos.</span><span class="sxs-lookup"><span data-stu-id="a731e-104">The [foreach statement](/dotnet/csharp/language-reference/language-specification/statements#the-foreach-statement) is used to iterate through the collection to get the information that you want, but can not be used to add or remove items from the source collection to avoid unpredictable side effects.</span></span> <span data-ttu-id="a731e-105">Si se necesitan agregar o quitar elementos de la colección de origen, se usa un bucle [for](for.md).</span><span class="sxs-lookup"><span data-stu-id="a731e-105">If you need to add or remove items from the source collection, use a [for](for.md) loop.</span></span>
  
 <span data-ttu-id="a731e-106">Las instrucciones incrustadas continúan ejecutándose para cada elemento de la matriz o la colección.</span><span class="sxs-lookup"><span data-stu-id="a731e-106">The embedded statements continue to execute for each element in the array or collection.</span></span> <span data-ttu-id="a731e-107">Cuando la iteración se completa en todos los elementos de la colección, el control se transfiere a la instrucción que sigue al bloque `foreach`.</span><span class="sxs-lookup"><span data-stu-id="a731e-107">After the iteration has been completed for all the elements in the collection, control is transferred to the next statement following the `foreach` block.</span></span>
  
 <span data-ttu-id="a731e-108">En cualquier punto del bloque `foreach`, se puede salir del bucle mediante la palabra clave [break](break.md), o bien se puede ir a la siguiente iteración del bucle mediante la palabra clave [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="a731e-108">At any point within the `foreach` block, you can break out of the loop by using the [break](break.md) keyword, or step to the next iteration in the loop by using the [continue](continue.md) keyword.</span></span>

 <span data-ttu-id="a731e-109">También se puede salir de un bucle `foreach` mediante las instrucciones [goto](goto.md), [return](return.md) o [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="a731e-109">A `foreach` loop can also be exited by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

 <span data-ttu-id="a731e-110">Para más información sobre la palabra clave `foreach` y obtener ejemplos de código, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="a731e-110">For more information about the `foreach` keyword and code samples, see the following topics:</span></span>  

 [<span data-ttu-id="a731e-111">Utilizar foreach con matrices</span><span class="sxs-lookup"><span data-stu-id="a731e-111">Using foreach with Arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)  

 [<span data-ttu-id="a731e-112">Cómo: Obtener acceso a una clase de colección mediante Foreach</span><span class="sxs-lookup"><span data-stu-id="a731e-112">How to: Access a Collection Class with foreach</span></span>](../../programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  

## <a name="example"></a><span data-ttu-id="a731e-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a731e-113">Example</span></span>

<span data-ttu-id="a731e-114">En el código siguiente, se muestran tres ejemplos:</span><span class="sxs-lookup"><span data-stu-id="a731e-114">The following code shows three examples:</span></span>

> [!TIP]
> <span data-ttu-id="a731e-115">Puede modificar los ejemplos para probar la sintaxis y tantear distintos usos que se acerquen más a su caso particular.</span><span class="sxs-lookup"><span data-stu-id="a731e-115">You can modify the examples to experiment with the syntax and try different usages that are more similar to your use case.</span></span> <span data-ttu-id="a731e-116">Presione "Ejecutar" para ejecutar el código, cámbielo y vuelva a presionar "Ejecutar".</span><span class="sxs-lookup"><span data-stu-id="a731e-116">Press "Run" to run the code, then edit and press "Run" again.</span></span>

-   <span data-ttu-id="a731e-117">un bucle `foreach` típico que muestra el contenido de una matriz de enteros</span><span class="sxs-lookup"><span data-stu-id="a731e-117">a typical `foreach` loop that displays the contents of an array of integers</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L12-L26)]

-   <span data-ttu-id="a731e-118">un bucle [for](../../../csharp/language-reference/keywords/for.md) que hace lo mismo</span><span class="sxs-lookup"><span data-stu-id="a731e-118">a [for](../../../csharp/language-reference/keywords/for.md) loop that does the same thing</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L31-L46)]

-   <span data-ttu-id="a731e-119">un bucle `foreach` que mantiene un recuento del número de elementos de la matriz</span><span class="sxs-lookup"><span data-stu-id="a731e-119">a `foreach` loop that maintains a count of the number of elements in the array</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L51-L69)]
 
## <a name="c-language-specification"></a><span data-ttu-id="a731e-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="a731e-120">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a731e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a731e-121">See Also</span></span>  

[<span data-ttu-id="a731e-122">La instrucción foreach (especificación del lenguaje C#)</span><span class="sxs-lookup"><span data-stu-id="a731e-122">The foreach statement (C# language specification)</span></span>](/dotnet/csharp/language-reference/language-specification/statements#the-foreach-statement)

[<span data-ttu-id="a731e-123">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="a731e-123">C# Reference</span></span>](../index.md)

[<span data-ttu-id="a731e-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a731e-124">C# Programming Guide</span></span>](../../programming-guide/index.md)

[<span data-ttu-id="a731e-125">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="a731e-125">C# Keywords</span></span>](index.md)

[<span data-ttu-id="a731e-126">Instrucciones de iteración</span><span class="sxs-lookup"><span data-stu-id="a731e-126">Iteration Statements</span></span>](iteration-statements.md)

[<span data-ttu-id="a731e-127">for</span><span class="sxs-lookup"><span data-stu-id="a731e-127">for</span></span>](for.md)
