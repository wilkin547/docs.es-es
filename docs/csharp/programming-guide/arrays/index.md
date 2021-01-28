---
title: 'Matrices: Guía de programación de C#'
description: Puede almacenar varias variables del mismo tipo en una estructura de datos de matriz de C#. Declare una matriz especificando un tipo o especifique un objeto para almacenar cualquier tipo.
ms.date: 01/22/2021
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: 203d8b86da4e74d8c5397132a0ba68618eedf348
ms.sourcegitcommit: 4d5e25a46aa7cd0d29b4b9227b92987354d444c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98794764"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="27eba-104">Matrices (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="27eba-104">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="27eba-105">Puede almacenar varias variables del mismo tipo en una estructura de datos de matriz.</span><span class="sxs-lookup"><span data-stu-id="27eba-105">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="27eba-106">Puede declarar una matriz mediante la especificación del tipo de sus elementos.</span><span class="sxs-lookup"><span data-stu-id="27eba-106">You declare an array by specifying the type of its elements.</span></span> <span data-ttu-id="27eba-107">Si quiere que la matriz almacene elementos de cualquier tipo, puede especificar `object` como su tipo.</span><span class="sxs-lookup"><span data-stu-id="27eba-107">If you want the array to store elements of any type, you can specify `object` as its type.</span></span> <span data-ttu-id="27eba-108">En el sistema de tipos unificado de C#, todos los tipos, los predefinidos y los definidos por el usuario, los tipos de referencia y los tipos de valores, heredan directa o indirectamente de <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="27eba-108">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span>

```csharp
type[] arrayName;
```

## <a name="example"></a><span data-ttu-id="27eba-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="27eba-109">Example</span></span>

<span data-ttu-id="27eba-110">Los ejemplos siguientes crean matrices unidimensionales, multidimensionales y escalonadas:</span><span class="sxs-lookup"><span data-stu-id="27eba-110">The following example creates single-dimensional, multidimensional, and jagged arrays:</span></span>

[!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]

## <a name="array-overview"></a><span data-ttu-id="27eba-111">Información general sobre la matriz</span><span class="sxs-lookup"><span data-stu-id="27eba-111">Array overview</span></span>

<span data-ttu-id="27eba-112">Una matriz tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="27eba-112">An array has the following properties:</span></span>

- <span data-ttu-id="27eba-113">Puede ser una matriz [unidimensional](single-dimensional-arrays.md), [multidimensional](multidimensional-arrays.md) o [escalonada](jagged-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="27eba-113">An array can be [single-dimensional](single-dimensional-arrays.md), [multidimensional](multidimensional-arrays.md) or [jagged](jagged-arrays.md).</span></span>
- <span data-ttu-id="27eba-114">El número de dimensiones y la longitud de cada dimensión se establecen al crear la instancia de matriz.</span><span class="sxs-lookup"><span data-stu-id="27eba-114">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="27eba-115">No se pueden cambiar estos valores durante la vigencia de la instancia.</span><span class="sxs-lookup"><span data-stu-id="27eba-115">These values can't be changed during the lifetime of the instance.</span></span>
- <span data-ttu-id="27eba-116">Los valores predeterminados de los elementos numéricos de matriz se establecen en cero y los elementos de referencia se establecen en null.</span><span class="sxs-lookup"><span data-stu-id="27eba-116">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>
- <span data-ttu-id="27eba-117">Una matriz escalonada es una matriz de matrices y, por consiguiente, sus elementos son tipos de referencia y se inicializan en `null`.</span><span class="sxs-lookup"><span data-stu-id="27eba-117">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>
- <span data-ttu-id="27eba-118">Las matrices se indexan con cero: una matriz con `n` elementos se indexa de `0` a `n-1`.</span><span class="sxs-lookup"><span data-stu-id="27eba-118">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>
- <span data-ttu-id="27eba-119">Los elementos de una matriz puede ser cualquier tipo, incluido un tipo de matriz.</span><span class="sxs-lookup"><span data-stu-id="27eba-119">Array elements can be of any type, including an array type.</span></span>
- <span data-ttu-id="27eba-120">Los tipos de matriz son [tipos de referencia](../../language-reference/keywords/reference-types.md) que proceden del tipo base abstracto <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="27eba-120">Array types are [reference types](../../language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="27eba-121">Como este tipo implementa <xref:System.Collections.IEnumerable> y <xref:System.Collections.Generic.IEnumerable%601>, puede usar la iteración [foreach](../../language-reference/keywords/foreach-in.md) en todas las matrices de C#.</span><span class="sxs-lookup"><span data-stu-id="27eba-121">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>

### <a name="arrays-as-objects"></a><span data-ttu-id="27eba-122">Matrices como objetos</span><span class="sxs-lookup"><span data-stu-id="27eba-122">Arrays as Objects</span></span>

<span data-ttu-id="27eba-123">En C#, las matrices son actualmente objetos, y no simplemente regiones direccionables de memoria contigua como en C y C++.</span><span class="sxs-lookup"><span data-stu-id="27eba-123">In C#, arrays are actually objects, and not just addressable regions of contiguous memory as in C and C++.</span></span> <span data-ttu-id="27eba-124"><xref:System.Array> es el tipo base abstracto de todos los tipos de matriz.</span><span class="sxs-lookup"><span data-stu-id="27eba-124"><xref:System.Array> is the abstract base type of all array types.</span></span> <span data-ttu-id="27eba-125">Puede usar las propiedades, y otros miembros de clase, que tiene <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="27eba-125">You can use the properties and other class members that <xref:System.Array> has.</span></span> <span data-ttu-id="27eba-126">Un ejemplo de esto sería usar la propiedad <xref:System.Array.Length%2A> para obtener la longitud de una matriz.</span><span class="sxs-lookup"><span data-stu-id="27eba-126">An example of this is using the <xref:System.Array.Length%2A> property to get the length of an array.</span></span> <span data-ttu-id="27eba-127">El código siguiente asigna la longitud de la matriz `numbers`, que es `5`, a una variable denominada `lengthOfNumbers`:</span><span class="sxs-lookup"><span data-stu-id="27eba-127">The following code assigns the length of the `numbers` array, which is `5`, to a variable called `lengthOfNumbers`:</span></span>

[!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]

<span data-ttu-id="27eba-128">La clase <xref:System.Array> proporciona muchos otros métodos útiles y propiedades para ordenar, buscar y copiar matrices.</span><span class="sxs-lookup"><span data-stu-id="27eba-128">The <xref:System.Array> class provides many other useful methods and properties for sorting, searching, and copying arrays.</span></span> <span data-ttu-id="27eba-129">En los ejemplos siguientes se usa la propiedad <xref:System.Array.Rank%2A> para mostrar el número de dimensiones de una matriz.</span><span class="sxs-lookup"><span data-stu-id="27eba-129">The following example uses the <xref:System.Array.Rank%2A> property to display the number of dimensions of an array.</span></span>

[!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]

## <a name="see-also"></a><span data-ttu-id="27eba-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="27eba-130">See also</span></span>

- [<span data-ttu-id="27eba-131">Uso de matrices unidimensionales</span><span class="sxs-lookup"><span data-stu-id="27eba-131">How to use single-dimensional arrays</span></span>](single-dimensional-arrays.md)
- [<span data-ttu-id="27eba-132">Uso de matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="27eba-132">How to use multi-dimensional arrays</span></span>](multidimensional-arrays.md)
- [<span data-ttu-id="27eba-133">Uso de matrices escalonadas</span><span class="sxs-lookup"><span data-stu-id="27eba-133">How to use jagged arrays</span></span>](jagged-arrays.md)
- [<span data-ttu-id="27eba-134">Utilizar foreach con matrices</span><span class="sxs-lookup"><span data-stu-id="27eba-134">Using foreach with arrays</span></span>](using-foreach-with-arrays.md)
- [<span data-ttu-id="27eba-135">Pasar matrices como argumentos</span><span class="sxs-lookup"><span data-stu-id="27eba-135">Passing arrays as arguments</span></span>](passing-arrays-as-arguments.md)
- [<span data-ttu-id="27eba-136">Matrices con tipo implícito</span><span class="sxs-lookup"><span data-stu-id="27eba-136">Implicitly typed arrays</span></span>](implicitly-typed-arrays.md)
- [<span data-ttu-id="27eba-137">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="27eba-137">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="27eba-138">Colecciones</span><span class="sxs-lookup"><span data-stu-id="27eba-138">Collections</span></span>](../concepts/collections.md)

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]
