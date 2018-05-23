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
ms.openlocfilehash: f00ae873e615f653d3e760f82b157a57fdaef6ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="f7a9b-102">foreach, in (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f7a9b-102">foreach, in (C# Reference)</span></span>
<span data-ttu-id="f7a9b-103">La instrucción `foreach` repite un grupo de instrucciones insertadas por cada elemento de una matriz o una colección de objetos que implementa la interfaz <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f7a9b-103">The `foreach` statement repeats a group of embedded statements for each element in an array or an object collection that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="f7a9b-104">La instrucción `foreach` se usa para recorrer en iteración la colección para obtener la información deseada, pero no puede usarse para agregar o quitar elementos de la colección de origen para evitar efectos secundarios imprevisibles.</span><span class="sxs-lookup"><span data-stu-id="f7a9b-104">The `foreach` statement is used to iterate through the collection to get the information that you want, but can not be used to add or remove items from the source collection to avoid unpredictable side effects.</span></span> <span data-ttu-id="f7a9b-105">Si se necesitan agregar o quitar elementos de la colección de origen, se usa un bucle [for](for.md).</span><span class="sxs-lookup"><span data-stu-id="f7a9b-105">If you need to add or remove items from the source collection, use a [for](for.md) loop.</span></span>
  
 <span data-ttu-id="f7a9b-106">Las instrucciones incrustadas continúan ejecutándose para cada elemento de la matriz o la colección.</span><span class="sxs-lookup"><span data-stu-id="f7a9b-106">The embedded statements continue to execute for each element in the array or collection.</span></span> <span data-ttu-id="f7a9b-107">Cuando la iteración se completa en todos los elementos de la colección, el control se transfiere a la instrucción que sigue al bloque `foreach`.</span><span class="sxs-lookup"><span data-stu-id="f7a9b-107">After the iteration has been completed for all the elements in the collection, control is transferred to the next statement following the `foreach` block.</span></span>
  
 <span data-ttu-id="f7a9b-108">En cualquier punto del bloque `foreach`, se puede salir del bucle mediante la palabra clave [break](break.md), o bien se puede ir a la siguiente iteración del bucle mediante la palabra clave [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="f7a9b-108">At any point within the `foreach` block, you can break out of the loop by using the [break](break.md) keyword, or step to the next iteration in the loop by using the [continue](continue.md) keyword.</span></span>

 <span data-ttu-id="f7a9b-109">También se puede salir de un bucle `foreach` mediante las instrucciones [goto](goto.md), [return](return.md) o [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="f7a9b-109">A `foreach` loop can also be exited by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

 <span data-ttu-id="f7a9b-110">Para más información sobre la palabra clave `foreach` y obtener ejemplos de código, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f7a9b-110">For more information about the `foreach` keyword and code samples, see the following topics:</span></span>  

 [<span data-ttu-id="f7a9b-111">Utilizar foreach con matrices</span><span class="sxs-lookup"><span data-stu-id="f7a9b-111">Using foreach with Arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)  

 [<span data-ttu-id="f7a9b-112">Cómo: Obtener acceso a una clase de colección mediante Foreach</span><span class="sxs-lookup"><span data-stu-id="f7a9b-112">How to: Access a Collection Class with foreach</span></span>](../../programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  

## <a name="example"></a><span data-ttu-id="f7a9b-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f7a9b-113">Example</span></span>
 <span data-ttu-id="f7a9b-114">En el siguiente código se muestran tres ejemplos.</span><span class="sxs-lookup"><span data-stu-id="f7a9b-114">The following code shows three examples.</span></span>

> [!TIP]
> <span data-ttu-id="f7a9b-115">Puede modificar los ejemplos para probar la sintaxis y tantear distintos usos que se acerquen más a su caso particular.</span><span class="sxs-lookup"><span data-stu-id="f7a9b-115">You can modify the examples to experiment with the syntax and try different usages that are more similar to your use case.</span></span> <span data-ttu-id="f7a9b-116">Presione "Ejecutar" para ejecutar el código, cámbielo y vuelva a presionar "Ejecutar".</span><span class="sxs-lookup"><span data-stu-id="f7a9b-116">Press "Run" to run the code, then edit and press "Run" again.</span></span>

-   <span data-ttu-id="f7a9b-117">un bucle `foreach` típico que muestra el contenido de una matriz de enteros</span><span class="sxs-lookup"><span data-stu-id="f7a9b-117">a typical `foreach` loop that displays the contents of an array of integers</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L12-L26)]

-   <span data-ttu-id="f7a9b-118">un bucle [for](../../../csharp/language-reference/keywords/for.md) que hace lo mismo</span><span class="sxs-lookup"><span data-stu-id="f7a9b-118">a [for](../../../csharp/language-reference/keywords/for.md) loop that does the same thing</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L31-L46)]

-   <span data-ttu-id="f7a9b-119">un bucle `foreach` que mantiene un recuento del número de elementos de la matriz</span><span class="sxs-lookup"><span data-stu-id="f7a9b-119">a `foreach` loop that maintains a count of the number of elements in the array</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L51-L69)]
 
## <a name="c-language-specification"></a><span data-ttu-id="f7a9b-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f7a9b-120">C# Language Specification</span></span>
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f7a9b-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7a9b-121">See Also</span></span>  

[<span data-ttu-id="f7a9b-122">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f7a9b-122">C# Reference</span></span>](../index.md)

[<span data-ttu-id="f7a9b-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f7a9b-123">C# Programming Guide</span></span>](../../programming-guide/index.md)

[<span data-ttu-id="f7a9b-124">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="f7a9b-124">C# Keywords</span></span>](index.md)

[<span data-ttu-id="f7a9b-125">Instrucciones de iteración</span><span class="sxs-lookup"><span data-stu-id="f7a9b-125">Iteration Statements</span></span>](iteration-statements.md)

[<span data-ttu-id="f7a9b-126">for</span><span class="sxs-lookup"><span data-stu-id="f7a9b-126">for</span></span>](for.md)
