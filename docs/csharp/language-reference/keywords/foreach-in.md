---
title: foreach, in (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- foreach
- foreach_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
caps.latest.revision: 29
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: aed1d4f086f0b1334df750fd912d20d66326a043
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="c0bfe-102">foreach, in (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c0bfe-102">foreach, in (C# Reference)</span></span>
<span data-ttu-id="c0bfe-103">La instrucción `foreach` repite un grupo de instrucciones insertadas por cada elemento de una matriz o una colección de objetos que implementa la interfaz <xref:System.Collections.IEnumerable?displayProperty=fullName> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="c0bfe-103">The `foreach` statement repeats a group of embedded statements for each element in an array or an object collection that implements the <xref:System.Collections.IEnumerable?displayProperty=fullName> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> interface.</span></span> <span data-ttu-id="c0bfe-104">La instrucción `foreach` se usa para recorrer en iteración la colección para obtener la información deseada, pero no puede usarse para agregar o quitar elementos de la colección de origen para evitar efectos secundarios imprevisibles.</span><span class="sxs-lookup"><span data-stu-id="c0bfe-104">The `foreach` statement is used to iterate through the collection to get the information that you want, but can not be used to add or remove items from the source collection to avoid unpredictable side effects.</span></span> <span data-ttu-id="c0bfe-105">Si se necesitan agregar o quitar elementos de la colección de origen, se usa un bucle [for](../../../csharp/language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="c0bfe-105">If you need to add or remove items from the source collection, use a [for](../../../csharp/language-reference/keywords/for.md) loop.</span></span>  
  
 <span data-ttu-id="c0bfe-106">Las instrucciones incrustadas continúan ejecutándose para cada elemento de la matriz o la colección.</span><span class="sxs-lookup"><span data-stu-id="c0bfe-106">The embedded statements continue to execute for each element in the array or collection.</span></span> <span data-ttu-id="c0bfe-107">Cuando la iteración se completa en todos los elementos de la colección, el control se transfiere a la instrucción que sigue al bloque `foreach`.</span><span class="sxs-lookup"><span data-stu-id="c0bfe-107">After the iteration has been completed for all the elements in the collection, control is transferred to the next statement following the `foreach` block.</span></span>  
  
 <span data-ttu-id="c0bfe-108">En cualquier punto del bloque `foreach`, se puede salir del bucle mediante la palabra clave [break](../../../csharp/language-reference/keywords/break.md), o bien se puede ir a la siguiente iteración del bucle mediante la palabra clave [continue](../../../csharp/language-reference/keywords/continue.md).</span><span class="sxs-lookup"><span data-stu-id="c0bfe-108">At any point within the `foreach` block, you can break out of the loop by using the [break](../../../csharp/language-reference/keywords/break.md) keyword, or step to the next iteration in the loop by using the [continue](../../../csharp/language-reference/keywords/continue.md) keyword.</span></span>  
  
 <span data-ttu-id="c0bfe-109">También se puede salir de un bucle `foreach` mediante las instrucciones [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md).</span><span class="sxs-lookup"><span data-stu-id="c0bfe-109">A `foreach` loop can also be exited by the [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statements.</span></span>  
  
 <span data-ttu-id="c0bfe-110">Para más información sobre la palabra clave `foreach` y obtener ejemplos de código, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="c0bfe-110">For more information about the `foreach` keyword and code samples, see the following topics:</span></span>  
  
 [<span data-ttu-id="c0bfe-111">Utilizar foreach con matrices</span><span class="sxs-lookup"><span data-stu-id="c0bfe-111">Using foreach with Arrays</span></span>](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
 [<span data-ttu-id="c0bfe-112">Cómo: Obtener acceso a una clase de colección mediante Foreach</span><span class="sxs-lookup"><span data-stu-id="c0bfe-112">How to: Access a Collection Class with foreach</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  
  
## <a name="example"></a><span data-ttu-id="c0bfe-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0bfe-113">Example</span></span>  
 <span data-ttu-id="c0bfe-114">En el código siguiente, se muestran tres ejemplos:</span><span class="sxs-lookup"><span data-stu-id="c0bfe-114">The following code shows three examples:</span></span>  
  
-   <span data-ttu-id="c0bfe-115">un bucle `foreach` típico que muestra el contenido de una matriz de enteros</span><span class="sxs-lookup"><span data-stu-id="c0bfe-115">a typical `foreach` loop that displays the contents of an array of integers</span></span>  
  
-   <span data-ttu-id="c0bfe-116">un bucle [for](../../../csharp/language-reference/keywords/for.md) que hace lo mismo</span><span class="sxs-lookup"><span data-stu-id="c0bfe-116">a [for](../../../csharp/language-reference/keywords/for.md) loop that does the same thing</span></span>  
  
-   <span data-ttu-id="c0bfe-117">un bucle `foreach` que mantiene un recuento del número de elementos de la matriz</span><span class="sxs-lookup"><span data-stu-id="c0bfe-117">a `foreach` loop that maintains a count of the number of elements in the array</span></span>  
  
 <span data-ttu-id="c0bfe-118">[!code-cs[csrefKeywordsIteration#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/foreach-in_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0bfe-118">[!code-cs[csrefKeywordsIteration#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/foreach-in_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c0bfe-119">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c0bfe-119">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c0bfe-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0bfe-120">See Also</span></span>  
 <span data-ttu-id="c0bfe-121">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c0bfe-121">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c0bfe-122">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c0bfe-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c0bfe-123">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="c0bfe-123">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="c0bfe-124">[Iteration Statements](../../../csharp/language-reference/keywords/iteration-statements.md)  (Instrucciones de iteración)</span><span class="sxs-lookup"><span data-stu-id="c0bfe-124">[Iteration Statements](../../../csharp/language-reference/keywords/iteration-statements.md) </span></span>  
 [<span data-ttu-id="c0bfe-125">for</span><span class="sxs-lookup"><span data-stu-id="c0bfe-125">for</span></span>](../../../csharp/language-reference/keywords/for.md)

