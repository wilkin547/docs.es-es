---
title: Matrices (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: 1469336bf034fd22c9d7355b2f8dd8be32721fdf
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510643"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="dec3c-102">Matrices (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="dec3c-102">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="dec3c-103">Puede almacenar varias variables del mismo tipo en una estructura de datos de matriz.</span><span class="sxs-lookup"><span data-stu-id="dec3c-103">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="dec3c-104">Puede declarar una matriz mediante la especificación del tipo de sus elementos.</span><span class="sxs-lookup"><span data-stu-id="dec3c-104">You declare an array by specifying the type of its elements.</span></span>  
  
 `type[] arrayName;`  
  
 <span data-ttu-id="dec3c-105">Los ejemplos siguientes crean matrices unidimensionales, multidimensionales y escalonadas:</span><span class="sxs-lookup"><span data-stu-id="dec3c-105">The following examples create single-dimensional, multidimensional, and jagged arrays:</span></span>  
  
 [!code-csharp[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]  
  
## <a name="array-overview"></a><span data-ttu-id="dec3c-106">Información general de las matrices</span><span class="sxs-lookup"><span data-stu-id="dec3c-106">Array Overview</span></span>

 <span data-ttu-id="dec3c-107">Una matriz tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="dec3c-107">An array has the following properties:</span></span>  
  
-   <span data-ttu-id="dec3c-108">Puede ser una matriz [unidimensional](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [multidimensional](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) o [escalonada](../../../csharp/programming-guide/arrays/jagged-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="dec3c-108">An array can be [Single-Dimensional](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [Multidimensional](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) or [Jagged](../../../csharp/programming-guide/arrays/jagged-arrays.md).</span></span>  
  
-   <span data-ttu-id="dec3c-109">El número de dimensiones y la longitud de cada dimensión se establecen al crear la instancia de matriz.</span><span class="sxs-lookup"><span data-stu-id="dec3c-109">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="dec3c-110">No se pueden cambiar estos valores durante la vigencia de la instancia.</span><span class="sxs-lookup"><span data-stu-id="dec3c-110">These values can't be changed during the lifetime of the instance.</span></span>  
  
-   <span data-ttu-id="dec3c-111">Los valores predeterminados de los elementos numéricos de matriz se establecen en cero y los elementos de referencia se establecen en null.</span><span class="sxs-lookup"><span data-stu-id="dec3c-111">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>  
  
-   <span data-ttu-id="dec3c-112">Una matriz escalonada es una matriz de matrices y, por consiguiente, sus elementos son tipos de referencia y se inicializan en `null`.</span><span class="sxs-lookup"><span data-stu-id="dec3c-112">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
-   <span data-ttu-id="dec3c-113">Las matrices se indexan con cero: una matriz con `n` elementos se indexa de `0` a `n-1`.</span><span class="sxs-lookup"><span data-stu-id="dec3c-113">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>  
  
-   <span data-ttu-id="dec3c-114">Los elementos de una matriz puede ser cualquier tipo, incluido un tipo de matriz.</span><span class="sxs-lookup"><span data-stu-id="dec3c-114">Array elements can be of any type, including an array type.</span></span>  
  
-   <span data-ttu-id="dec3c-115">Los tipos de matriz son [tipos de referencia](../../../csharp/language-reference/keywords/reference-types.md) que proceden del tipo base abstracto <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="dec3c-115">Array types are [reference types](../../../csharp/language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="dec3c-116">Como este tipo implementa <xref:System.Collections.IEnumerable> y <xref:System.Collections.Generic.IEnumerable%601>, puede usar la iteración [foreach](../../../csharp/language-reference/keywords/foreach-in.md) en todas las matrices de C#.</span><span class="sxs-lookup"><span data-stu-id="dec3c-116">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../../csharp/language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="dec3c-117">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="dec3c-117">Related Sections</span></span>  
  
-   [<span data-ttu-id="dec3c-118">Matrices como objetos</span><span class="sxs-lookup"><span data-stu-id="dec3c-118">Arrays as Objects</span></span>](../../../csharp/programming-guide/arrays/arrays-as-objects.md)  
  
-   [<span data-ttu-id="dec3c-119">Utilizar foreach con matrices</span><span class="sxs-lookup"><span data-stu-id="dec3c-119">Using foreach with Arrays</span></span>](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
-   [<span data-ttu-id="dec3c-120">Pasar matrices como argumentos</span><span class="sxs-lookup"><span data-stu-id="dec3c-120">Passing Arrays as Arguments</span></span>](../../../csharp/programming-guide/arrays/passing-arrays-as-arguments.md)  
  
-   [<span data-ttu-id="dec3c-121">Pasar matrices mediante Ref y Out</span><span class="sxs-lookup"><span data-stu-id="dec3c-121">Passing Arrays Using ref and out</span></span>](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)   
  
## <a name="c-language-specification"></a><span data-ttu-id="dec3c-122">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="dec3c-122">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dec3c-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="dec3c-123">See Also</span></span>

- [<span data-ttu-id="dec3c-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="dec3c-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="dec3c-125">Colecciones</span><span class="sxs-lookup"><span data-stu-id="dec3c-125">Collections</span></span>](https://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)  
- [<span data-ttu-id="dec3c-126">Tipo de colección de matrices</span><span class="sxs-lookup"><span data-stu-id="dec3c-126">Array Collection Type</span></span>](https://msdn.microsoft.com/library/8a9964de-8941-47b1-a3cf-a01bc88db9e8)
