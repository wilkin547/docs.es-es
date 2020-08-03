---
title: 'Matrices escalonadas: Guía de programación de C#'
description: Una matriz escalonada de C# es una matriz cuyos elementos son matrices de diferentes dimensiones y tamaños. Aprenda a declarar y inicializar matrices escalonadas, así como a acceder a ellas.
ms.date: 07/20/2015
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
ms.openlocfilehash: 40da9fbda34aef4e69ebf2ae20485e883b79f871
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474688"
---
# <a name="jagged-arrays-c-programming-guide"></a><span data-ttu-id="6fa96-104">Matrices escalonadas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="6fa96-104">Jagged Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="6fa96-105">Una matriz escalonada es una matriz cuyos elementos son matrices.</span><span class="sxs-lookup"><span data-stu-id="6fa96-105">A jagged array is an array whose elements are arrays.</span></span> <span data-ttu-id="6fa96-106">Los elementos de una matriz escalonada pueden ser de diferentes dimensiones y tamaños.</span><span class="sxs-lookup"><span data-stu-id="6fa96-106">The elements of a jagged array can be of different dimensions and sizes.</span></span> <span data-ttu-id="6fa96-107">Una matriz escalonada se denomina a veces "matriz de matrices".</span><span class="sxs-lookup"><span data-stu-id="6fa96-107">A jagged array is sometimes called an "array of arrays."</span></span> <span data-ttu-id="6fa96-108">En los ejemplos siguientes, se muestra cómo declarar, inicializar y acceder a matrices escalonadas.</span><span class="sxs-lookup"><span data-stu-id="6fa96-108">The following examples show how to declare, initialize, and access jagged arrays.</span></span>  
  
 <span data-ttu-id="6fa96-109">La siguiente es una declaración de una matriz unidimensional que tiene tres elementos, cada uno de los cuales es una matriz unidimensional de enteros:</span><span class="sxs-lookup"><span data-stu-id="6fa96-109">The following is a declaration of a single-dimensional array that has three elements, each of which is a single-dimensional array of integers:</span></span>  
  
 [!code-csharp[csProgGuideArrays#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#19)]  
  
 <span data-ttu-id="6fa96-110">Para poder usar `jaggedArray`, se deben inicializar sus elementos.</span><span class="sxs-lookup"><span data-stu-id="6fa96-110">Before you can use `jaggedArray`, its elements must be initialized.</span></span> <span data-ttu-id="6fa96-111">Puede inicializar los elementos de esta forma:</span><span class="sxs-lookup"><span data-stu-id="6fa96-111">You can initialize the elements like this:</span></span>  
  
 [!code-csharp[csProgGuideArrays#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#20)]  
  
 <span data-ttu-id="6fa96-112">Cada uno de los elementos es una matriz unidimensional de enteros.</span><span class="sxs-lookup"><span data-stu-id="6fa96-112">Each of the elements is a single-dimensional array of integers.</span></span> <span data-ttu-id="6fa96-113">El primer elemento es una matriz de 5 enteros, el segundo es una matriz de 4 enteros y el tercero es una matriz de 2 enteros.</span><span class="sxs-lookup"><span data-stu-id="6fa96-113">The first element is an array of 5 integers, the second is an array of 4 integers, and the third is an array of 2 integers.</span></span>  
  
 <span data-ttu-id="6fa96-114">También es posible usar inicializadores para rellenar los elementos de matriz con valores, en cuyo caso no es necesario el tamaño de la matriz.</span><span class="sxs-lookup"><span data-stu-id="6fa96-114">It is also possible to use initializers to fill the array elements with values, in which case you do not need the array size.</span></span> <span data-ttu-id="6fa96-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6fa96-115">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#21)]  
  
 <span data-ttu-id="6fa96-116">También puede inicializar la matriz en la declaración de esta forma:</span><span class="sxs-lookup"><span data-stu-id="6fa96-116">You can also initialize the array upon declaration like this:</span></span>  
  
 [!code-csharp[csProgGuideArrays#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#22)]  
  
 <span data-ttu-id="6fa96-117">Puede usar la siguiente forma abreviada.</span><span class="sxs-lookup"><span data-stu-id="6fa96-117">You can use the following shorthand form.</span></span> <span data-ttu-id="6fa96-118">Tenga en cuenta que no puede omitir el operador `new` de la inicialización de elementos porque no hay ninguna inicialización predeterminada para los elementos:</span><span class="sxs-lookup"><span data-stu-id="6fa96-118">Notice that you cannot omit the `new` operator from the elements initialization because there is no default initialization for the elements:</span></span>  
  
 [!code-csharp[csProgGuideArrays#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#23)]  
  
 <span data-ttu-id="6fa96-119">Una matriz escalonada es una matriz de matrices y, por consiguiente, sus elementos son tipos de referencia y se inicializan en `null`.</span><span class="sxs-lookup"><span data-stu-id="6fa96-119">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
 <span data-ttu-id="6fa96-120">Puede tener acceso a elementos individuales de la matriz como en estos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="6fa96-120">You can access individual array elements like these examples:</span></span>  
  
 [!code-csharp[csProgGuideArrays#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#24)]  
  
 <span data-ttu-id="6fa96-121">Es posible mezclar matrices multidimensionales y escalonadas.</span><span class="sxs-lookup"><span data-stu-id="6fa96-121">It is possible to mix jagged and multidimensional arrays.</span></span> <span data-ttu-id="6fa96-122">La siguiente es una declaración e inicialización de una matriz escalonada unidimensional que contiene tres elementos de matriz bidimensional de tamaños diferentes.</span><span class="sxs-lookup"><span data-stu-id="6fa96-122">The following is a declaration and initialization of a single-dimensional jagged array that contains three two-dimensional array elements of different sizes.</span></span> <span data-ttu-id="6fa96-123">Para obtener más información sobre las matrices bidimensionales, vea [Matrices multidimensionales](./multidimensional-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="6fa96-123">For more information about two-dimensional arrays, see [Multidimensional Arrays](./multidimensional-arrays.md).</span></span>  
  
 [!code-csharp[csProgGuideArrays#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#25)]  
  
 <span data-ttu-id="6fa96-124">Puede tener acceso a los elementos individuales como se muestra en este ejemplo, que muestra el valor del elemento `[1,0]` de la primera matriz (valor `5`):</span><span class="sxs-lookup"><span data-stu-id="6fa96-124">You can access individual elements as shown in this example, which displays the value of the element `[1,0]` of the first array (value `5`):</span></span>  
  
 [!code-csharp[csProgGuideArrays#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#26)]  
  
 <span data-ttu-id="6fa96-125">El método `Length` devuelve el número de matrices contenidos en la matriz escalonada.</span><span class="sxs-lookup"><span data-stu-id="6fa96-125">The method `Length` returns the number of arrays contained in the jagged array.</span></span> <span data-ttu-id="6fa96-126">Por ejemplo, suponiendo que ha declarado la matriz anterior, esta línea:</span><span class="sxs-lookup"><span data-stu-id="6fa96-126">For example, assuming you have declared the previous array, this line:</span></span>  
  
 [!code-csharp[csProgGuideArrays#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#27)]  
  
 <span data-ttu-id="6fa96-127">devuelve un valor de 3.</span><span class="sxs-lookup"><span data-stu-id="6fa96-127">returns a value of 3.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fa96-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6fa96-128">Example</span></span>

 <span data-ttu-id="6fa96-129">En este ejemplo, se crea una matriz cuyos elementos son matrices.</span><span class="sxs-lookup"><span data-stu-id="6fa96-129">This example builds an array whose elements are themselves arrays.</span></span> <span data-ttu-id="6fa96-130">Cada uno de los elementos de matriz tiene un tamaño diferente.</span><span class="sxs-lookup"><span data-stu-id="6fa96-130">Each one of the array elements has a different size.</span></span>  
  
 [!code-csharp[csProgGuideArrays#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#18)]  
  
## <a name="see-also"></a><span data-ttu-id="6fa96-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="6fa96-131">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="6fa96-132">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6fa96-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6fa96-133">Matrices</span><span class="sxs-lookup"><span data-stu-id="6fa96-133">Arrays</span></span>](./index.md)
- [<span data-ttu-id="6fa96-134">Matrices unidimensionales</span><span class="sxs-lookup"><span data-stu-id="6fa96-134">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="6fa96-135">Matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="6fa96-135">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
