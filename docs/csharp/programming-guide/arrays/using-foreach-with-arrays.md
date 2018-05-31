---
title: Utilizar foreach con matrices (Guía de programación de C#)
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: b858f35167e24390a729769487ce98908a3d349f
ms.sourcegitcommit: 54231aa56fca059e9297888a96fbca1d4cf3746c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2018
ms.locfileid: "34549460"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a><span data-ttu-id="87d86-102">Utilizar foreach con matrices (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="87d86-102">Using foreach with Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="87d86-103">La instrucción [foreach](../../language-reference/keywords/foreach-in.md) ofrece una manera sencilla y limpia de iterar los elementos de una matriz.</span><span class="sxs-lookup"><span data-stu-id="87d86-103">The [foreach](../../language-reference/keywords/foreach-in.md) statement provides a simple, clean way to iterate through the elements of an array.</span></span>

<span data-ttu-id="87d86-104">Para matrices unidimensionales, la instrucción `foreach` procesa los elementos en orden creciente de índice, comenzando con el índice 0 y terminando con el índice `Length - 1`:</span><span class="sxs-lookup"><span data-stu-id="87d86-104">For single-dimensional arrays, the `foreach` statement processes elements in increasing index order, starting with index 0 and ending with index `Length - 1`:</span></span>

[!code-csharp[csProgGuideArrays#28](./codesnippet/CSharp/using-foreach-with-arrays_1.cs)]

<span data-ttu-id="87d86-105">En el caso de matrices multidimensionales, los elementos se recorren de tal manera que primero se incrementan los índices de la dimensión más a la derecha, luego la siguiente dimensión a la izquierda, y así sucesivamente a la izquierda:</span><span class="sxs-lookup"><span data-stu-id="87d86-105">For multi-dimensional arrays, elements are traversed such that the indices of the rightmost dimension are increased first, then the next left dimension, and so on to the left:</span></span>

[!code-csharp[csProgGuideArrays#29](./codesnippet/CSharp/using-foreach-with-arrays_2.cs)]

<span data-ttu-id="87d86-106">En cambio, con las matrices multidimensionales, usar un bucle [for](../../language-reference/keywords/for.md) anidado ofrece un mayor control sobre el orden en el que se procesan los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="87d86-106">However, with multidimensional arrays, using a nested [for](../../language-reference/keywords/for.md) loop gives you more control over the order in which to process the array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="87d86-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="87d86-107">See also</span></span>  
 <xref:System.Array>  
 [<span data-ttu-id="87d86-108">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="87d86-108">C# Programming Guide</span></span>](../index.md)  
 [<span data-ttu-id="87d86-109">Matrices</span><span class="sxs-lookup"><span data-stu-id="87d86-109">Arrays</span></span>](index.md)  
 [<span data-ttu-id="87d86-110">Matrices unidimensionales</span><span class="sxs-lookup"><span data-stu-id="87d86-110">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)  
 [<span data-ttu-id="87d86-111">Matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="87d86-111">Multidimensional Arrays</span></span>](multidimensional-arrays.md)  
 [<span data-ttu-id="87d86-112">Matrices escalonadas</span><span class="sxs-lookup"><span data-stu-id="87d86-112">Jagged Arrays</span></span>](jagged-arrays.md)
