---
title: 'Matrices escalonadas: Guía de programación de C#'
description: Una matriz escalonada de C# es una matriz cuyos elementos son matrices de diferentes tamaños. Aprenda a declarar y inicializar matrices escalonadas, así como a acceder a ellas.
ms.date: 12/18/2020
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
ms.openlocfilehash: 6d4fb939fb6594c7644a80eb688ea852ddf8a5c5
ms.sourcegitcommit: c3093e9d106d8ca87cc86eef1f2ae4ecfb392118
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2020
ms.locfileid: "97737286"
---
# <a name="jagged-arrays-c-programming-guide"></a><span data-ttu-id="b5f99-104">Matrices escalonadas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="b5f99-104">Jagged Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="b5f99-105">Una matriz escalonada es una matriz cuyos elementos son matrices, posiblemente de diferentes tamaños.</span><span class="sxs-lookup"><span data-stu-id="b5f99-105">A jagged array is an array whose elements are arrays, possibly of different sizes.</span></span> <span data-ttu-id="b5f99-106">Una matriz escalonada se denomina a veces "matriz de matrices".</span><span class="sxs-lookup"><span data-stu-id="b5f99-106">A jagged array is sometimes called an "array of arrays."</span></span> <span data-ttu-id="b5f99-107">En los ejemplos siguientes, se muestra cómo declarar, inicializar y acceder a matrices escalonadas.</span><span class="sxs-lookup"><span data-stu-id="b5f99-107">The following examples show how to declare, initialize, and access jagged arrays.</span></span>

 <span data-ttu-id="b5f99-108">La siguiente es una declaración de una matriz unidimensional que tiene tres elementos, cada uno de los cuales es una matriz unidimensional de enteros:</span><span class="sxs-lookup"><span data-stu-id="b5f99-108">The following is a declaration of a single-dimensional array that has three elements, each of which is a single-dimensional array of integers:</span></span>

 [!code-csharp[csProgGuideArrays#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#19)]

 <span data-ttu-id="b5f99-109">Para poder usar `jaggedArray`, se deben inicializar sus elementos.</span><span class="sxs-lookup"><span data-stu-id="b5f99-109">Before you can use `jaggedArray`, its elements must be initialized.</span></span> <span data-ttu-id="b5f99-110">Puede inicializar los elementos de esta forma:</span><span class="sxs-lookup"><span data-stu-id="b5f99-110">You can initialize the elements like this:</span></span>

 [!code-csharp[csProgGuideArrays#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#20)]

 <span data-ttu-id="b5f99-111">Cada uno de los elementos es una matriz unidimensional de enteros.</span><span class="sxs-lookup"><span data-stu-id="b5f99-111">Each of the elements is a single-dimensional array of integers.</span></span> <span data-ttu-id="b5f99-112">El primer elemento es una matriz de 5 enteros, el segundo es una matriz de 4 enteros y el tercero es una matriz de 2 enteros.</span><span class="sxs-lookup"><span data-stu-id="b5f99-112">The first element is an array of 5 integers, the second is an array of 4 integers, and the third is an array of 2 integers.</span></span>

 <span data-ttu-id="b5f99-113">También es posible usar inicializadores para rellenar los elementos de matriz con valores, en cuyo caso no es necesario el tamaño de la matriz.</span><span class="sxs-lookup"><span data-stu-id="b5f99-113">It is also possible to use initializers to fill the array elements with values, in which case you do not need the array size.</span></span> <span data-ttu-id="b5f99-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b5f99-114">For example:</span></span>

 [!code-csharp[csProgGuideArrays#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#21)]

 <span data-ttu-id="b5f99-115">También puede inicializar la matriz en la declaración de esta forma:</span><span class="sxs-lookup"><span data-stu-id="b5f99-115">You can also initialize the array upon declaration like this:</span></span>

 [!code-csharp[csProgGuideArrays#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#22)]

 <span data-ttu-id="b5f99-116">Puede usar la siguiente forma abreviada.</span><span class="sxs-lookup"><span data-stu-id="b5f99-116">You can use the following shorthand form.</span></span> <span data-ttu-id="b5f99-117">Tenga en cuenta que no puede omitir el operador `new` de la inicialización de elementos porque no hay ninguna inicialización predeterminada para los elementos:</span><span class="sxs-lookup"><span data-stu-id="b5f99-117">Notice that you cannot omit the `new` operator from the elements initialization because there is no default initialization for the elements:</span></span>

 [!code-csharp[csProgGuideArrays#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#23)]

 <span data-ttu-id="b5f99-118">Una matriz escalonada es una matriz de matrices y, por consiguiente, sus elementos son tipos de referencia y se inicializan en `null`.</span><span class="sxs-lookup"><span data-stu-id="b5f99-118">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>

 <span data-ttu-id="b5f99-119">Puede tener acceso a elementos individuales de la matriz como en estos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="b5f99-119">You can access individual array elements like these examples:</span></span>

 [!code-csharp[csProgGuideArrays#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#24)]

 <span data-ttu-id="b5f99-120">Es posible mezclar matrices multidimensionales y escalonadas.</span><span class="sxs-lookup"><span data-stu-id="b5f99-120">It's possible to mix jagged and multidimensional arrays.</span></span> <span data-ttu-id="b5f99-121">La siguiente es una declaración e inicialización de una matriz escalonada unidimensional que contiene tres elementos de matriz bidimensional de tamaños diferentes.</span><span class="sxs-lookup"><span data-stu-id="b5f99-121">The following is a declaration and initialization of a single-dimensional jagged array that contains three two-dimensional array elements of different sizes.</span></span> <span data-ttu-id="b5f99-122">Para obtener más información, vea [Matrices multidimensionales](./multidimensional-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="b5f99-122">For more information, see [Multidimensional Arrays](./multidimensional-arrays.md).</span></span>

 [!code-csharp[csProgGuideArrays#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#25)]

 <span data-ttu-id="b5f99-123">Puede tener acceso a los elementos individuales como se muestra en este ejemplo, que muestra el valor del elemento `[1,0]` de la primera matriz (valor `5`):</span><span class="sxs-lookup"><span data-stu-id="b5f99-123">You can access individual elements as shown in this example, which displays the value of the element `[1,0]` of the first array (value `5`):</span></span>

 [!code-csharp[csProgGuideArrays#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#26)]

 <span data-ttu-id="b5f99-124">El método `Length` devuelve el número de matrices contenidos en la matriz escalonada.</span><span class="sxs-lookup"><span data-stu-id="b5f99-124">The method `Length` returns the number of arrays contained in the jagged array.</span></span> <span data-ttu-id="b5f99-125">Por ejemplo, suponiendo que ha declarado la matriz anterior, esta línea:</span><span class="sxs-lookup"><span data-stu-id="b5f99-125">For example, assuming you have declared the previous array, this line:</span></span>

 [!code-csharp[csProgGuideArrays#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#27)]

 <span data-ttu-id="b5f99-126">devuelve un valor de 3.</span><span class="sxs-lookup"><span data-stu-id="b5f99-126">returns a value of 3.</span></span>

## <a name="example"></a><span data-ttu-id="b5f99-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b5f99-127">Example</span></span>

 <span data-ttu-id="b5f99-128">En este ejemplo, se crea una matriz cuyos elementos son matrices.</span><span class="sxs-lookup"><span data-stu-id="b5f99-128">This example builds an array whose elements are themselves arrays.</span></span> <span data-ttu-id="b5f99-129">Cada uno de los elementos de matriz tiene un tamaño diferente.</span><span class="sxs-lookup"><span data-stu-id="b5f99-129">Each one of the array elements has a different size.</span></span>

 [!code-csharp[csProgGuideArrays#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#18)]

## <a name="see-also"></a><span data-ttu-id="b5f99-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5f99-130">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="b5f99-131">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b5f99-131">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b5f99-132">Matrices</span><span class="sxs-lookup"><span data-stu-id="b5f99-132">Arrays</span></span>](./index.md)
- [<span data-ttu-id="b5f99-133">Matrices unidimensionales</span><span class="sxs-lookup"><span data-stu-id="b5f99-133">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="b5f99-134">Matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="b5f99-134">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
