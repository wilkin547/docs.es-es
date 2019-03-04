---
title: 'Matrices como objetos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: 8500cf508b77a0fa7e348ce0fe6b1f16fd2bab25
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977188"
---
# <a name="arrays-as-objects-c-programming-guide"></a><span data-ttu-id="bd9a6-102">Utilizar matrices como objetos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="bd9a6-102">Arrays as Objects (C# Programming Guide)</span></span>

<span data-ttu-id="bd9a6-103">En C#, las matrices son actualmente objetos, y no simplemente regiones direccionables de memoria contigua como en C y C++.</span><span class="sxs-lookup"><span data-stu-id="bd9a6-103">In C#, arrays are actually objects, and not just addressable regions of contiguous memory as in C and C++.</span></span> <span data-ttu-id="bd9a6-104"><xref:System.Array> es el tipo base abstracto de todos los tipos de matriz.</span><span class="sxs-lookup"><span data-stu-id="bd9a6-104"><xref:System.Array> is the abstract base type of all array types.</span></span> <span data-ttu-id="bd9a6-105">Puede usar las propiedades, y otros miembros de clase, que tiene <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="bd9a6-105">You can use the properties, and other class members, that <xref:System.Array> has.</span></span> <span data-ttu-id="bd9a6-106">Un ejemplo de esto sería usar la propiedad <xref:System.Array.Length%2A> para obtener la longitud de una matriz.</span><span class="sxs-lookup"><span data-stu-id="bd9a6-106">An example of this would be using the <xref:System.Array.Length%2A> property to get the length of an array.</span></span> <span data-ttu-id="bd9a6-107">El código siguiente asigna la longitud de la matriz `numbers`, que es `5`, a una variable denominada `lengthOfNumbers`:</span><span class="sxs-lookup"><span data-stu-id="bd9a6-107">The following code assigns the length of the `numbers` array, which is `5`, to a variable called `lengthOfNumbers`:</span></span>  
  
 [!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]  
  
 <span data-ttu-id="bd9a6-108">La clase <xref:System.Array> proporciona muchos otros métodos útiles y propiedades para ordenar, buscar y copiar matrices.</span><span class="sxs-lookup"><span data-stu-id="bd9a6-108">The <xref:System.Array> class provides many other useful methods and properties for sorting, searching, and copying arrays.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd9a6-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd9a6-109">Example</span></span>

 <span data-ttu-id="bd9a6-110">Este ejemplo usa la propiedad <xref:System.Array.Rank%2A> para mostrar el número de dimensiones de una matriz.</span><span class="sxs-lookup"><span data-stu-id="bd9a6-110">This example uses the <xref:System.Array.Rank%2A> property to display the number of dimensions of an array.</span></span>  
  
 [!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]  
  
## <a name="see-also"></a><span data-ttu-id="bd9a6-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd9a6-111">See also</span></span>

- [<span data-ttu-id="bd9a6-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="bd9a6-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="bd9a6-113">Matrices</span><span class="sxs-lookup"><span data-stu-id="bd9a6-113">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)
- [<span data-ttu-id="bd9a6-114">Matrices unidimensionales</span><span class="sxs-lookup"><span data-stu-id="bd9a6-114">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)
- [<span data-ttu-id="bd9a6-115">Matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="bd9a6-115">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)
- [<span data-ttu-id="bd9a6-116">Matrices escalonadas</span><span class="sxs-lookup"><span data-stu-id="bd9a6-116">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
