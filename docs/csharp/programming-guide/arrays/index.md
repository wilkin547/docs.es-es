---
title: 'Matrices: Guía de programación de C#'
description: Puede almacenar varias variables del mismo tipo en una estructura de datos de matriz de C#. Declare una matriz especificando un tipo o especifique un objeto para almacenar cualquier tipo.
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: e302ff2e4c2488c4899c4eb99a666d2d322119ce
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474740"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="cda32-104">Matrices (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="cda32-104">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="cda32-105">Puede almacenar varias variables del mismo tipo en una estructura de datos de matriz.</span><span class="sxs-lookup"><span data-stu-id="cda32-105">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="cda32-106">Puede declarar una matriz mediante la especificación del tipo de sus elementos.</span><span class="sxs-lookup"><span data-stu-id="cda32-106">You declare an array by specifying the type of its elements.</span></span> <span data-ttu-id="cda32-107">Si quiere que la matriz almacene elementos de cualquier tipo, puede especificar `object` como su tipo.</span><span class="sxs-lookup"><span data-stu-id="cda32-107">If you want the array to store elements of any type, you can specify `object` as its type.</span></span> <span data-ttu-id="cda32-108">En el sistema de tipos unificado de C#, todos los tipos, los predefinidos y los definidos por el usuario, los tipos de referencia y los tipos de valores, heredan directa o indirectamente de <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="cda32-108">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span>

```csharp
type[] arrayName;
```

## <a name="example"></a><span data-ttu-id="cda32-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cda32-109">Example</span></span>

<span data-ttu-id="cda32-110">Los ejemplos siguientes crean matrices unidimensionales, multidimensionales y escalonadas:</span><span class="sxs-lookup"><span data-stu-id="cda32-110">The following example creates single-dimensional, multidimensional, and jagged arrays:</span></span>

[!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]

## <a name="array-overview"></a><span data-ttu-id="cda32-111">Información general sobre la matriz</span><span class="sxs-lookup"><span data-stu-id="cda32-111">Array overview</span></span>

<span data-ttu-id="cda32-112">Una matriz tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="cda32-112">An array has the following properties:</span></span>

- <span data-ttu-id="cda32-113">Puede ser una matriz [unidimensional](single-dimensional-arrays.md), [multidimensional](multidimensional-arrays.md) o [escalonada](jagged-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="cda32-113">An array can be [Single-Dimensional](single-dimensional-arrays.md), [Multidimensional](multidimensional-arrays.md) or [Jagged](jagged-arrays.md).</span></span>
- <span data-ttu-id="cda32-114">El número de dimensiones y la longitud de cada dimensión se establecen al crear la instancia de matriz.</span><span class="sxs-lookup"><span data-stu-id="cda32-114">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="cda32-115">No se pueden cambiar estos valores durante la vigencia de la instancia.</span><span class="sxs-lookup"><span data-stu-id="cda32-115">These values can't be changed during the lifetime of the instance.</span></span>
- <span data-ttu-id="cda32-116">Los valores predeterminados de los elementos numéricos de matriz se establecen en cero y los elementos de referencia se establecen en null.</span><span class="sxs-lookup"><span data-stu-id="cda32-116">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>
- <span data-ttu-id="cda32-117">Una matriz escalonada es una matriz de matrices y, por consiguiente, sus elementos son tipos de referencia y se inicializan en `null`.</span><span class="sxs-lookup"><span data-stu-id="cda32-117">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>
- <span data-ttu-id="cda32-118">Las matrices se indexan con cero: una matriz con `n` elementos se indexa de `0` a `n-1`.</span><span class="sxs-lookup"><span data-stu-id="cda32-118">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>
- <span data-ttu-id="cda32-119">Los elementos de una matriz puede ser cualquier tipo, incluido un tipo de matriz.</span><span class="sxs-lookup"><span data-stu-id="cda32-119">Array elements can be of any type, including an array type.</span></span>
- <span data-ttu-id="cda32-120">Los tipos de matriz son [tipos de referencia](../../language-reference/keywords/reference-types.md) que proceden del tipo base abstracto <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="cda32-120">Array types are [reference types](../../language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="cda32-121">Como este tipo implementa <xref:System.Collections.IEnumerable> y <xref:System.Collections.Generic.IEnumerable%601>, puede usar la iteración [foreach](../../language-reference/keywords/foreach-in.md) en todas las matrices de C#.</span><span class="sxs-lookup"><span data-stu-id="cda32-121">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>

## <a name="related-sections"></a><span data-ttu-id="cda32-122">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="cda32-122">Related sections</span></span>

- [<span data-ttu-id="cda32-123">Matrices como objetos</span><span class="sxs-lookup"><span data-stu-id="cda32-123">Arrays as Objects</span></span>](arrays-as-objects.md)
- [<span data-ttu-id="cda32-124">Utilizar foreach con matrices</span><span class="sxs-lookup"><span data-stu-id="cda32-124">Using foreach with Arrays</span></span>](using-foreach-with-arrays.md)
- [<span data-ttu-id="cda32-125">Pasar matrices como argumentos</span><span class="sxs-lookup"><span data-stu-id="cda32-125">Passing Arrays as Arguments</span></span>](passing-arrays-as-arguments.md)

## <a name="c-language-specification"></a><span data-ttu-id="cda32-126">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="cda32-126">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="cda32-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cda32-127">See also</span></span>

- [<span data-ttu-id="cda32-128">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="cda32-128">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="cda32-129">Colecciones</span><span class="sxs-lookup"><span data-stu-id="cda32-129">Collections</span></span>](../concepts/collections.md)
