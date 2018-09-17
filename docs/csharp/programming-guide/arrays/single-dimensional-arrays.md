---
title: Matrices unidimensionales (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: c2f26fd74a596ada21eef578e58c9cd8e0305d6c
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45616226"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="bd2ad-102">Matrices unidimensionales (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="bd2ad-102">Single-Dimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="bd2ad-103">Puede declarar una matriz unidimensional de cinco enteros tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bd2ad-103">You can declare a single-dimensional array of five integers as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_1.cs)]  
  
 <span data-ttu-id="bd2ad-104">Esta matriz contiene los elementos de `array[0]` a `array[4]`.</span><span class="sxs-lookup"><span data-stu-id="bd2ad-104">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="bd2ad-105">El operador [new](../../../csharp/language-reference/keywords/new.md) se usa para crear la matriz e inicializar los elementos de matriz con sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="bd2ad-105">The [new](../../../csharp/language-reference/keywords/new.md) operator is used to create the array and initialize the array elements to their default values.</span></span> <span data-ttu-id="bd2ad-106">En este ejemplo, todos los elementos de matriz se inicializan en cero.</span><span class="sxs-lookup"><span data-stu-id="bd2ad-106">In this example, all the array elements are initialized to zero.</span></span>  
  
 <span data-ttu-id="bd2ad-107">Una matriz que almacena elementos de cadena se puede declarar de la misma forma.</span><span class="sxs-lookup"><span data-stu-id="bd2ad-107">An array that stores string elements can be declared in the same way.</span></span> <span data-ttu-id="bd2ad-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bd2ad-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_2.cs)]  
  
## <a name="array-initialization"></a><span data-ttu-id="bd2ad-109">Inicialización de matriz</span><span class="sxs-lookup"><span data-stu-id="bd2ad-109">Array Initialization</span></span>

 <span data-ttu-id="bd2ad-110">Es posible inicializar una matriz en la declaración, en cuyo caso, el especificador de rango no es necesario porque ya lo proporciona el número de elementos de la lista de inicialización.</span><span class="sxs-lookup"><span data-stu-id="bd2ad-110">It is possible to initialize an array upon declaration, in which case, the rank specifier is not needed because it is already supplied by the number of elements in the initialization list.</span></span> <span data-ttu-id="bd2ad-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bd2ad-111">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_3.cs)]  
  
 <span data-ttu-id="bd2ad-112">Se puede inicializar una matriz de cadenas del mismo modo.</span><span class="sxs-lookup"><span data-stu-id="bd2ad-112">A string array can be initialized in the same way.</span></span> <span data-ttu-id="bd2ad-113">La siguiente es una declaración de una matriz de cadenas donde cada elemento de la matriz se inicializa mediante un nombre de un día:</span><span class="sxs-lookup"><span data-stu-id="bd2ad-113">The following is a declaration of a string array where each array element is initialized by a name of a day:</span></span>  
  
 [!code-csharp[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_4.cs)]  
  
 <span data-ttu-id="bd2ad-114">Al inicializar una matriz en la declaración, puede usar los siguientes métodos abreviados:</span><span class="sxs-lookup"><span data-stu-id="bd2ad-114">When you initialize an array upon declaration, you can use the following shortcuts:</span></span>  
  
 [!code-csharp[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_5.cs)]  
  
 <span data-ttu-id="bd2ad-115">Es posible declarar una variable de matriz sin inicializarla, pero debe usar el operador `new` al asignar una matriz a esta variable.</span><span class="sxs-lookup"><span data-stu-id="bd2ad-115">It is possible to declare an array variable without initialization, but you must use the `new` operator when you assign an array to this variable.</span></span> <span data-ttu-id="bd2ad-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bd2ad-116">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_6.cs)]  
  
 <span data-ttu-id="bd2ad-117">C# 3.0 presenta matrices con tipo implícito.</span><span class="sxs-lookup"><span data-stu-id="bd2ad-117">C# 3.0 introduces implicitly typed arrays.</span></span> <span data-ttu-id="bd2ad-118">Para obtener más información, vea [Matrices con asignación implícita de tipos](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="bd2ad-118">For more information, see [Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span></span>  
  
## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="bd2ad-119">Matrices de tipo de valor y tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="bd2ad-119">Value Type and Reference Type Arrays</span></span>

 <span data-ttu-id="bd2ad-120">Tenga en cuenta la siguiente declaración de matriz:</span><span class="sxs-lookup"><span data-stu-id="bd2ad-120">Consider the following array declaration:</span></span>  
  
 [!code-csharp[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_7.cs)]  
  
 <span data-ttu-id="bd2ad-121">El resultado de esta instrucción depende de si `SomeType` es un tipo de valor o un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="bd2ad-121">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="bd2ad-122">Si es un tipo de valor, la instrucción crea una matriz de 10 elementos y cada uno de ellos tiene el tipo `SomeType`.</span><span class="sxs-lookup"><span data-stu-id="bd2ad-122">If it is a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="bd2ad-123">Si `SomeType` es un tipo de referencia, la instrucción crea una matriz de 10 elementos y cada uno de ellos se inicializa en una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="bd2ad-123">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span>  
  
 <span data-ttu-id="bd2ad-124">Para obtener más información sobre los tipos de valor y de referencia, consulte [Types](../../../csharp/language-reference/keywords/types.md) (Tipos).</span><span class="sxs-lookup"><span data-stu-id="bd2ad-124">For more information about value types and reference types, see [Types](../../../csharp/language-reference/keywords/types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd2ad-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd2ad-125">See Also</span></span>

- <xref:System.Array>  
- [<span data-ttu-id="bd2ad-126">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="bd2ad-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="bd2ad-127">Matrices</span><span class="sxs-lookup"><span data-stu-id="bd2ad-127">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
- [<span data-ttu-id="bd2ad-128">Matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="bd2ad-128">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
- [<span data-ttu-id="bd2ad-129">Matrices escalonadas</span><span class="sxs-lookup"><span data-stu-id="bd2ad-129">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
