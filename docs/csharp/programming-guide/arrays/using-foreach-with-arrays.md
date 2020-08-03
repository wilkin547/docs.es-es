---
title: Uso de foreach con matrices - Guía de programación de C#
description: La instrucción foreach de C# itera por los elementos de una matriz. En el caso de las matrices unidimensionales, foreach procesa los elementos en orden de índice creciente.
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: d924a3ef3351cbb30b809a1542f35314ee721852
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474545"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a><span data-ttu-id="10654-104">Uso de foreach con matrices (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="10654-104">Using foreach with arrays (C# Programming Guide)</span></span>

<span data-ttu-id="10654-105">La instrucción [foreach](../../language-reference/keywords/foreach-in.md) ofrece una manera sencilla y limpia de iterar los elementos de una matriz.</span><span class="sxs-lookup"><span data-stu-id="10654-105">The [foreach](../../language-reference/keywords/foreach-in.md) statement provides a simple, clean way to iterate through the elements of an array.</span></span>

<span data-ttu-id="10654-106">Para matrices unidimensionales, la instrucción `foreach` procesa los elementos en orden creciente de índice, comenzando con el índice 0 y terminando con el índice `Length - 1`:</span><span class="sxs-lookup"><span data-stu-id="10654-106">For single-dimensional arrays, the `foreach` statement processes elements in increasing index order, starting with index 0 and ending with index `Length - 1`:</span></span>

 [!code-csharp[csProgGuideArrays#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#28)]

<span data-ttu-id="10654-107">En el caso de matrices multidimensionales, los elementos se recorren de tal manera que primero se incrementan los índices de la dimensión más a la derecha, luego la siguiente dimensión a la izquierda, y así sucesivamente a la izquierda:</span><span class="sxs-lookup"><span data-stu-id="10654-107">For multi-dimensional arrays, elements are traversed such that the indices of the rightmost dimension are increased first, then the next left dimension, and so on to the left:</span></span>

 [!code-csharp[csProgGuideArrays#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#29)]

<span data-ttu-id="10654-108">En cambio, con las matrices multidimensionales, usar un bucle [for](../../language-reference/keywords/for.md) anidado ofrece un mayor control sobre el orden en el que se procesan los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="10654-108">However, with multidimensional arrays, using a nested [for](../../language-reference/keywords/for.md) loop gives you more control over the order in which to process the array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="10654-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="10654-109">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="10654-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="10654-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="10654-111">Matrices</span><span class="sxs-lookup"><span data-stu-id="10654-111">Arrays</span></span>](index.md)
- [<span data-ttu-id="10654-112">Matrices unidimensionales</span><span class="sxs-lookup"><span data-stu-id="10654-112">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)
- [<span data-ttu-id="10654-113">Matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="10654-113">Multidimensional Arrays</span></span>](multidimensional-arrays.md)
- [<span data-ttu-id="10654-114">Matrices escalonadas</span><span class="sxs-lookup"><span data-stu-id="10654-114">Jagged Arrays</span></span>](jagged-arrays.md)
