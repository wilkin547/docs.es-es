---
title: 'Matrices como objetos: Guía de programación de C#'
description: Las matrices de C# son objetos del tipo base abstracto Array. Puede usar las propiedades y otros miembros de clase de Array, como la propiedad Length.
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: 984def3ef74b07d7099fae6cae6d6f8ce7e03e12
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474727"
---
# <a name="arrays-as-objects-c-programming-guide"></a><span data-ttu-id="c9797-104">Utilizar matrices como objetos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="c9797-104">Arrays as Objects (C# Programming Guide)</span></span>

<span data-ttu-id="c9797-105">En C#, las matrices son actualmente objetos, y no simplemente regiones direccionables de memoria contigua como en C y C++.</span><span class="sxs-lookup"><span data-stu-id="c9797-105">In C#, arrays are actually objects, and not just addressable regions of contiguous memory as in C and C++.</span></span> <span data-ttu-id="c9797-106"><xref:System.Array> es el tipo base abstracto de todos los tipos de matriz.</span><span class="sxs-lookup"><span data-stu-id="c9797-106"><xref:System.Array> is the abstract base type of all array types.</span></span> <span data-ttu-id="c9797-107">Puede usar las propiedades, y otros miembros de clase, que tiene <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="c9797-107">You can use the properties and other class members that <xref:System.Array> has.</span></span> <span data-ttu-id="c9797-108">Un ejemplo de esto sería usar la propiedad <xref:System.Array.Length%2A> para obtener la longitud de una matriz.</span><span class="sxs-lookup"><span data-stu-id="c9797-108">An example of this is using the <xref:System.Array.Length%2A> property to get the length of an array.</span></span> <span data-ttu-id="c9797-109">El código siguiente asigna la longitud de la matriz `numbers`, que es `5`, a una variable denominada `lengthOfNumbers`:</span><span class="sxs-lookup"><span data-stu-id="c9797-109">The following code assigns the length of the `numbers` array, which is `5`, to a variable called `lengthOfNumbers`:</span></span>

[!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]

<span data-ttu-id="c9797-110">La clase <xref:System.Array> proporciona muchos otros métodos útiles y propiedades para ordenar, buscar y copiar matrices.</span><span class="sxs-lookup"><span data-stu-id="c9797-110">The <xref:System.Array> class provides many other useful methods and properties for sorting, searching, and copying arrays.</span></span>

## <a name="example"></a><span data-ttu-id="c9797-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c9797-111">Example</span></span>

<span data-ttu-id="c9797-112">Este ejemplo usa la propiedad <xref:System.Array.Rank%2A> para mostrar el número de dimensiones de una matriz.</span><span class="sxs-lookup"><span data-stu-id="c9797-112">This example uses the <xref:System.Array.Rank%2A> property to display the number of dimensions of an array.</span></span>

[!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]

## <a name="see-also"></a><span data-ttu-id="c9797-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9797-113">See also</span></span>

- [<span data-ttu-id="c9797-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c9797-114">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c9797-115">Matrices</span><span class="sxs-lookup"><span data-stu-id="c9797-115">Arrays</span></span>](./index.md)
- [<span data-ttu-id="c9797-116">Matrices unidimensionales</span><span class="sxs-lookup"><span data-stu-id="c9797-116">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="c9797-117">Matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="c9797-117">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="c9797-118">Matrices escalonadas</span><span class="sxs-lookup"><span data-stu-id="c9797-118">Jagged Arrays</span></span>](./jagged-arrays.md)
