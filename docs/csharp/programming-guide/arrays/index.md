---
title: "Matrices (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
caps.latest.revision: 33
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
ms.openlocfilehash: 1035caae15b64d1311305cfe4c1f1a74c80ed19a
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="4e0bb-102">Matrices (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="4e0bb-102">Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="4e0bb-103">Puede almacenar varias variables del mismo tipo en una estructura de datos de matriz.</span><span class="sxs-lookup"><span data-stu-id="4e0bb-103">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="4e0bb-104">Puede declarar una matriz mediante la especificación del tipo de sus elementos.</span><span class="sxs-lookup"><span data-stu-id="4e0bb-104">You declare an array by specifying the type of its elements.</span></span>  
  
 `type[] arrayName;`  
  
 <span data-ttu-id="4e0bb-105">Los ejemplos siguientes crean matrices unidimensionales, multidimensionales y escalonadas:</span><span class="sxs-lookup"><span data-stu-id="4e0bb-105">The following examples create single-dimensional, multidimensional, and jagged arrays:</span></span>  
  
 <span data-ttu-id="4e0bb-106">[!code-cs[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4e0bb-106">[!code-cs[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]</span></span>  
  
## <a name="array-overview"></a><span data-ttu-id="4e0bb-107">Información general de las matrices</span><span class="sxs-lookup"><span data-stu-id="4e0bb-107">Array Overview</span></span>  
 <span data-ttu-id="4e0bb-108">Una matriz tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="4e0bb-108">An array has the following properties:</span></span>  
  
-   <span data-ttu-id="4e0bb-109">Puede ser una matriz [unidimensional](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [multidimensional](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) o [escalonada](../../../csharp/programming-guide/arrays/jagged-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="4e0bb-109">An array can be [Single-Dimensional](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [Multidimensional](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) or [Jagged](../../../csharp/programming-guide/arrays/jagged-arrays.md).</span></span>  
  
-   <span data-ttu-id="4e0bb-110">El número de dimensiones y la longitud de cada dimensión se establecen al crear la instancia de matriz.</span><span class="sxs-lookup"><span data-stu-id="4e0bb-110">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="4e0bb-111">No se pueden cambiar estos valores durante la vigencia de la instancia.</span><span class="sxs-lookup"><span data-stu-id="4e0bb-111">These values can't be changed during the lifetime of the instance.</span></span>  
  
-   <span data-ttu-id="4e0bb-112">Los valores predeterminados de los elementos numéricos de matriz se establecen en cero y los elementos de referencia se establecen en null.</span><span class="sxs-lookup"><span data-stu-id="4e0bb-112">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>  
  
-   <span data-ttu-id="4e0bb-113">Una matriz escalonada es una matriz de matrices y, por consiguiente, sus elementos son tipos de referencia y se inicializan en `null`.</span><span class="sxs-lookup"><span data-stu-id="4e0bb-113">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
-   <span data-ttu-id="4e0bb-114">Las matrices se indexan con cero: una matriz con `n` elementos se indexa de `0` a `n-1`.</span><span class="sxs-lookup"><span data-stu-id="4e0bb-114">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>  
  
-   <span data-ttu-id="4e0bb-115">Los elementos de una matriz puede ser cualquier tipo, incluido un tipo de matriz.</span><span class="sxs-lookup"><span data-stu-id="4e0bb-115">Array elements can be of any type, including an array type.</span></span>  
  
-   <span data-ttu-id="4e0bb-116">Los tipos de matriz son [tipos de referencia](../../../csharp/language-reference/keywords/reference-types.md) que proceden del tipo base abstracto <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="4e0bb-116">Array types are [reference types](../../../csharp/language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="4e0bb-117">Como este tipo implementa <xref:System.Collections.IEnumerable> y <xref:System.Collections.Generic.IEnumerable%601>, puede usar la iteración [foreach](../../../csharp/language-reference/keywords/foreach-in.md) en todas las matrices de C#.</span><span class="sxs-lookup"><span data-stu-id="4e0bb-117">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../../csharp/language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4e0bb-118">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="4e0bb-118">Related Sections</span></span>  
  
-   [<span data-ttu-id="4e0bb-119">Matrices como objetos</span><span class="sxs-lookup"><span data-stu-id="4e0bb-119">Arrays as Objects</span></span>](../../../csharp/programming-guide/arrays/arrays-as-objects.md)  
  
-   [<span data-ttu-id="4e0bb-120">Utilizar foreach con matrices</span><span class="sxs-lookup"><span data-stu-id="4e0bb-120">Using foreach with Arrays</span></span>](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
-   [<span data-ttu-id="4e0bb-121">Pasar matrices como argumentos</span><span class="sxs-lookup"><span data-stu-id="4e0bb-121">Passing Arrays as Arguments</span></span>](../../../csharp/programming-guide/arrays/passing-arrays-as-arguments.md)  
  
-   [<span data-ttu-id="4e0bb-122">Pasar matrices mediante Ref y Out</span><span class="sxs-lookup"><span data-stu-id="4e0bb-122">Passing Arrays Using ref and out</span></span>](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)   
  
## <a name="c-language-specification"></a><span data-ttu-id="4e0bb-123">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="4e0bb-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4e0bb-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e0bb-124">See Also</span></span>  
 <span data-ttu-id="4e0bb-125">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4e0bb-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4e0bb-126">[Colecciones](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b) </span><span class="sxs-lookup"><span data-stu-id="4e0bb-126">[Collections](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b) </span></span>  
 [<span data-ttu-id="4e0bb-127">Tipo de colección de matrices</span><span class="sxs-lookup"><span data-stu-id="4e0bb-127">Array Collection Type</span></span>](http://msdn.microsoft.com/en-us/8a9964de-8941-47b1-a3cf-a01bc88db9e8)

