---
title: "Matrices escalonadas (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f74eaf5334e8e2198f7a058717a4eb2ff0c1e775
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="jagged-arrays-c-programming-guide"></a><span data-ttu-id="4a3f8-102">Matrices escalonadas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="4a3f8-102">Jagged Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="4a3f8-103">Una matriz escalonada es una matriz cuyos elementos son matrices.</span><span class="sxs-lookup"><span data-stu-id="4a3f8-103">A jagged array is an array whose elements are arrays.</span></span> <span data-ttu-id="4a3f8-104">Los elementos de una matriz escalonada pueden ser de diferentes dimensiones y tamaños.</span><span class="sxs-lookup"><span data-stu-id="4a3f8-104">The elements of a jagged array can be of different dimensions and sizes.</span></span> <span data-ttu-id="4a3f8-105">Una matriz escalonada se denomina a veces "matriz de matrices".</span><span class="sxs-lookup"><span data-stu-id="4a3f8-105">A jagged array is sometimes called an "array of arrays."</span></span> <span data-ttu-id="4a3f8-106">En los ejemplos siguientes, se muestra cómo declarar, inicializar y acceder a matrices escalonadas.</span><span class="sxs-lookup"><span data-stu-id="4a3f8-106">The following examples show how to declare, initialize, and access jagged arrays.</span></span>  
  
 <span data-ttu-id="4a3f8-107">La siguiente es una declaración de una matriz unidimensional que tiene tres elementos, cada uno de los cuales es una matriz unidimensional de enteros:</span><span class="sxs-lookup"><span data-stu-id="4a3f8-107">The following is a declaration of a single-dimensional array that has three elements, each of which is a single-dimensional array of integers:</span></span>  
  
 [!code-csharp[csProgGuideArrays#19](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_1.cs)]  
  
 <span data-ttu-id="4a3f8-108">Para poder usar `jaggedArray`, se deben inicializar sus elementos.</span><span class="sxs-lookup"><span data-stu-id="4a3f8-108">Before you can use `jaggedArray`, its elements must be initialized.</span></span> <span data-ttu-id="4a3f8-109">Puede inicializar los elementos de esta forma:</span><span class="sxs-lookup"><span data-stu-id="4a3f8-109">You can initialize the elements like this:</span></span>  
  
 [!code-csharp[csProgGuideArrays#20](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_2.cs)]  
  
 <span data-ttu-id="4a3f8-110">Cada uno de los elementos es una matriz unidimensional de enteros.</span><span class="sxs-lookup"><span data-stu-id="4a3f8-110">Each of the elements is a single-dimensional array of integers.</span></span> <span data-ttu-id="4a3f8-111">El primer elemento es una matriz de 5 enteros, el segundo es una matriz de 4 enteros y el tercero es una matriz de 2 enteros.</span><span class="sxs-lookup"><span data-stu-id="4a3f8-111">The first element is an array of 5 integers, the second is an array of 4 integers, and the third is an array of 2 integers.</span></span>  
  
 <span data-ttu-id="4a3f8-112">También es posible usar inicializadores para rellenar los elementos de matriz con valores, en cuyo caso no es necesario el tamaño de la matriz.</span><span class="sxs-lookup"><span data-stu-id="4a3f8-112">It is also possible to use initializers to fill the array elements with values, in which case you do not need the array size.</span></span> <span data-ttu-id="4a3f8-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4a3f8-113">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#21](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_3.cs)]  
  
 <span data-ttu-id="4a3f8-114">También puede inicializar la matriz en la declaración de esta forma:</span><span class="sxs-lookup"><span data-stu-id="4a3f8-114">You can also initialize the array upon declaration like this:</span></span>  
  
 [!code-csharp[csProgGuideArrays#22](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_4.cs)]  
  
 <span data-ttu-id="4a3f8-115">Puede usar la siguiente forma abreviada.</span><span class="sxs-lookup"><span data-stu-id="4a3f8-115">You can use the following shorthand form.</span></span> <span data-ttu-id="4a3f8-116">Tenga en cuenta que no puede omitir el operador `new` de la inicialización de elementos porque no hay ninguna inicialización predeterminada para los elementos:</span><span class="sxs-lookup"><span data-stu-id="4a3f8-116">Notice that you cannot omit the `new` operator from the elements initialization because there is no default initialization for the elements:</span></span>  
  
 [!code-csharp[csProgGuideArrays#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_5.cs)]  
  
 <span data-ttu-id="4a3f8-117">Una matriz escalonada es una matriz de matrices y, por consiguiente, sus elementos son tipos de referencia y se inicializan en `null`.</span><span class="sxs-lookup"><span data-stu-id="4a3f8-117">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
 <span data-ttu-id="4a3f8-118">Puede tener acceso a elementos individuales de la matriz como en estos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="4a3f8-118">You can access individual array elements like these examples:</span></span>  
  
 [!code-csharp[csProgGuideArrays#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_6.cs)]  
  
 <span data-ttu-id="4a3f8-119">Es posible mezclar matrices multidimensionales y escalonadas.</span><span class="sxs-lookup"><span data-stu-id="4a3f8-119">It is possible to mix jagged and multidimensional arrays.</span></span> <span data-ttu-id="4a3f8-120">La siguiente es una declaración e inicialización de una matriz escalonada unidimensional que contiene tres elementos de matriz bidimensional de tamaños diferentes.</span><span class="sxs-lookup"><span data-stu-id="4a3f8-120">The following is a declaration and initialization of a single-dimensional jagged array that contains three two-dimensional array elements of different sizes.</span></span> <span data-ttu-id="4a3f8-121">Para obtener más información sobre las matrices bidimensionales, vea [Matrices multidimensionales](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="4a3f8-121">For more information about two-dimensional arrays, see [Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).</span></span>  
  
 [!code-csharp[csProgGuideArrays#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_7.cs)]  
  
 <span data-ttu-id="4a3f8-122">Puede tener acceso a los elementos individuales como se muestra en este ejemplo, que muestra el valor del elemento `[1,0]` de la primera matriz (valor `5`):</span><span class="sxs-lookup"><span data-stu-id="4a3f8-122">You can access individual elements as shown in this example, which displays the value of the element `[1,0]` of the first array (value `5`):</span></span>  
  
 [!code-csharp[csProgGuideArrays#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_8.cs)]  
  
 <span data-ttu-id="4a3f8-123">El método `Length` devuelve el número de matrices contenidos en la matriz escalonada.</span><span class="sxs-lookup"><span data-stu-id="4a3f8-123">The method `Length` returns the number of arrays contained in the jagged array.</span></span> <span data-ttu-id="4a3f8-124">Por ejemplo, suponiendo que ha declarado la matriz anterior, esta línea:</span><span class="sxs-lookup"><span data-stu-id="4a3f8-124">For example, assuming you have declared the previous array, this line:</span></span>  
  
 [!code-csharp[csProgGuideArrays#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_9.cs)]  
  
 <span data-ttu-id="4a3f8-125">devuelve un valor de 3.</span><span class="sxs-lookup"><span data-stu-id="4a3f8-125">returns a value of 3.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a3f8-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4a3f8-126">Example</span></span>  
 <span data-ttu-id="4a3f8-127">En este ejemplo, se crea una matriz cuyos elementos son matrices.</span><span class="sxs-lookup"><span data-stu-id="4a3f8-127">This example builds an array whose elements are themselves arrays.</span></span> <span data-ttu-id="4a3f8-128">Cada uno de los elementos de matriz tiene un tamaño diferente.</span><span class="sxs-lookup"><span data-stu-id="4a3f8-128">Each one of the array elements has a different size.</span></span>  
  
 [!code-csharp[csProgGuideArrays#18](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_10.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="4a3f8-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a3f8-129">See Also</span></span>  
 <xref:System.Array>  
 [<span data-ttu-id="4a3f8-130">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="4a3f8-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4a3f8-131">Matrices</span><span class="sxs-lookup"><span data-stu-id="4a3f8-131">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="4a3f8-132">Matrices unidimensionales</span><span class="sxs-lookup"><span data-stu-id="4a3f8-132">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="4a3f8-133">Matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="4a3f8-133">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)
