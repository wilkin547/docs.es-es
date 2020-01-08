---
title: 'Matrices: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: bbabc84c144e5b3415c19f346b890782e251662c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715058"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="df6a2-102">Matrices (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="df6a2-102">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="df6a2-103">Puede almacenar varias variables del mismo tipo en una estructura de datos de matriz.</span><span class="sxs-lookup"><span data-stu-id="df6a2-103">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="df6a2-104">Puede declarar una matriz mediante la especificación del tipo de sus elementos.</span><span class="sxs-lookup"><span data-stu-id="df6a2-104">You declare an array by specifying the type of its elements.</span></span> <span data-ttu-id="df6a2-105">Si quiere que la matriz almacene elementos de cualquier tipo, puede especificar `object` como su tipo.</span><span class="sxs-lookup"><span data-stu-id="df6a2-105">If you want the array to store elements of any type, you can specify `object` as its type.</span></span> <span data-ttu-id="df6a2-106">En el sistema de tipos unificado de C#, todos los tipos, los predefinidos y los definidos por el usuario, los tipos de referencia y los tipos de valores, heredan directa o indirectamente de <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="df6a2-106">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span>

```csharp
type[] arrayName;
```

## <a name="example"></a><span data-ttu-id="df6a2-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="df6a2-107">Example</span></span>

<span data-ttu-id="df6a2-108">Los ejemplos siguientes crean matrices unidimensionales, multidimensionales y escalonadas:</span><span class="sxs-lookup"><span data-stu-id="df6a2-108">The following example creates single-dimensional, multidimensional, and jagged arrays:</span></span>

[!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]

## <a name="array-overview"></a><span data-ttu-id="df6a2-109">Información general sobre la matriz</span><span class="sxs-lookup"><span data-stu-id="df6a2-109">Array overview</span></span>

<span data-ttu-id="df6a2-110">Una matriz tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="df6a2-110">An array has the following properties:</span></span>

- <span data-ttu-id="df6a2-111">Puede ser una matriz [unidimensional](single-dimensional-arrays.md), [multidimensional](multidimensional-arrays.md) o [escalonada](jagged-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="df6a2-111">An array can be [Single-Dimensional](single-dimensional-arrays.md), [Multidimensional](multidimensional-arrays.md) or [Jagged](jagged-arrays.md).</span></span>
- <span data-ttu-id="df6a2-112">El número de dimensiones y la longitud de cada dimensión se establecen al crear la instancia de matriz.</span><span class="sxs-lookup"><span data-stu-id="df6a2-112">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="df6a2-113">No se pueden cambiar estos valores durante la vigencia de la instancia.</span><span class="sxs-lookup"><span data-stu-id="df6a2-113">These values can't be changed during the lifetime of the instance.</span></span>
- <span data-ttu-id="df6a2-114">Los valores predeterminados de los elementos numéricos de matriz se establecen en cero y los elementos de referencia se establecen en null.</span><span class="sxs-lookup"><span data-stu-id="df6a2-114">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>
- <span data-ttu-id="df6a2-115">Una matriz escalonada es una matriz de matrices y, por consiguiente, sus elementos son tipos de referencia y se inicializan en `null`.</span><span class="sxs-lookup"><span data-stu-id="df6a2-115">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>
- <span data-ttu-id="df6a2-116">Las matrices se indexan con cero: una matriz con `n` elementos se indexa de `0` a `n-1`.</span><span class="sxs-lookup"><span data-stu-id="df6a2-116">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>
- <span data-ttu-id="df6a2-117">Los elementos de una matriz puede ser cualquier tipo, incluido un tipo de matriz.</span><span class="sxs-lookup"><span data-stu-id="df6a2-117">Array elements can be of any type, including an array type.</span></span>
- <span data-ttu-id="df6a2-118">Los tipos de matriz son [tipos de referencia](../../language-reference/keywords/reference-types.md) que proceden del tipo base abstracto <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="df6a2-118">Array types are [reference types](../../language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="df6a2-119">Como este tipo implementa <xref:System.Collections.IEnumerable> y <xref:System.Collections.Generic.IEnumerable%601>, puede usar la iteración [foreach](../../language-reference/keywords/foreach-in.md) en todas las matrices de C#.</span><span class="sxs-lookup"><span data-stu-id="df6a2-119">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>

## <a name="related-sections"></a><span data-ttu-id="df6a2-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="df6a2-120">Related sections</span></span>

- [<span data-ttu-id="df6a2-121">Matrices como objetos</span><span class="sxs-lookup"><span data-stu-id="df6a2-121">Arrays as Objects</span></span>](arrays-as-objects.md)
- [<span data-ttu-id="df6a2-122">Utilizar foreach con matrices</span><span class="sxs-lookup"><span data-stu-id="df6a2-122">Using foreach with Arrays</span></span>](using-foreach-with-arrays.md)
- [<span data-ttu-id="df6a2-123">Pasar matrices como argumentos</span><span class="sxs-lookup"><span data-stu-id="df6a2-123">Passing Arrays as Arguments</span></span>](passing-arrays-as-arguments.md)

## <a name="c-language-specification"></a><span data-ttu-id="df6a2-124">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="df6a2-124">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="df6a2-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="df6a2-125">See also</span></span>

- [<span data-ttu-id="df6a2-126">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="df6a2-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="df6a2-127">Colecciones</span><span class="sxs-lookup"><span data-stu-id="df6a2-127">Collections</span></span>](../concepts/collections.md)
