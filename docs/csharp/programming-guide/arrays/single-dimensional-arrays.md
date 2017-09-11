---
title: "Matrices unidimensionales (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
caps.latest.revision: 18
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
ms.openlocfilehash: cc42640715274b89c4c4a12ced8c0ae6af603318
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="bbda1-102">Matrices unidimensionales (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="bbda1-102">Single-Dimensional Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="bbda1-103">Puede declarar una matriz unidimensional de cinco enteros tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bbda1-103">You can declare a single-dimensional array of five integers as shown in the following example:</span></span>  
  
 <span data-ttu-id="bbda1-104">[!code-cs[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bbda1-104">[!code-cs[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_1.cs)]</span></span>  
  
 <span data-ttu-id="bbda1-105">Esta matriz contiene los elementos de `array[0]` a `array[4]`.</span><span class="sxs-lookup"><span data-stu-id="bbda1-105">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="bbda1-106">El operador [new](../../../csharp/language-reference/keywords/new.md) se usa para crear la matriz e inicializar los elementos de matriz con sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="bbda1-106">The [new](../../../csharp/language-reference/keywords/new.md) operator is used to create the array and initialize the array elements to their default values.</span></span> <span data-ttu-id="bbda1-107">En este ejemplo, todos los elementos de matriz se inicializan en cero.</span><span class="sxs-lookup"><span data-stu-id="bbda1-107">In this example, all the array elements are initialized to zero.</span></span>  
  
 <span data-ttu-id="bbda1-108">Una matriz que almacena elementos de cadena se puede declarar de la misma forma.</span><span class="sxs-lookup"><span data-stu-id="bbda1-108">An array that stores string elements can be declared in the same way.</span></span> <span data-ttu-id="bbda1-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbda1-109">For example:</span></span>  
  
 <span data-ttu-id="bbda1-110">[!code-cs[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="bbda1-110">[!code-cs[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_2.cs)]</span></span>  
  
## <a name="array-initialization"></a><span data-ttu-id="bbda1-111">Inicialización de matriz</span><span class="sxs-lookup"><span data-stu-id="bbda1-111">Array Initialization</span></span>  
 <span data-ttu-id="bbda1-112">Es posible inicializar una matriz en la declaración, en cuyo caso, el especificador de rango no es necesario porque ya lo proporciona el número de elementos de la lista de inicialización.</span><span class="sxs-lookup"><span data-stu-id="bbda1-112">It is possible to initialize an array upon declaration, in which case, the rank specifier is not needed because it is already supplied by the number of elements in the initialization list.</span></span> <span data-ttu-id="bbda1-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbda1-113">For example:</span></span>  
  
 <span data-ttu-id="bbda1-114">[!code-cs[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="bbda1-114">[!code-cs[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_3.cs)]</span></span>  
  
 <span data-ttu-id="bbda1-115">Se puede inicializar una matriz de cadenas del mismo modo.</span><span class="sxs-lookup"><span data-stu-id="bbda1-115">A string array can be initialized in the same way.</span></span> <span data-ttu-id="bbda1-116">La siguiente es una declaración de una matriz de cadenas donde cada elemento de la matriz se inicializa mediante un nombre de un día:</span><span class="sxs-lookup"><span data-stu-id="bbda1-116">The following is a declaration of a string array where each array element is initialized by a name of a day:</span></span>  
  
 <span data-ttu-id="bbda1-117">[!code-cs[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="bbda1-117">[!code-cs[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_4.cs)]</span></span>  
  
 <span data-ttu-id="bbda1-118">Al inicializar una matriz en la declaración, puede usar los siguientes métodos abreviados:</span><span class="sxs-lookup"><span data-stu-id="bbda1-118">When you initialize an array upon declaration, you can use the following shortcuts:</span></span>  
  
 <span data-ttu-id="bbda1-119">[!code-cs[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="bbda1-119">[!code-cs[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_5.cs)]</span></span>  
  
 <span data-ttu-id="bbda1-120">Es posible declarar una variable de matriz sin inicializarla, pero debe usar el operador `new` al asignar una matriz a esta variable.</span><span class="sxs-lookup"><span data-stu-id="bbda1-120">It is possible to declare an array variable without initialization, but you must use the `new` operator when you assign an array to this variable.</span></span> <span data-ttu-id="bbda1-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbda1-121">For example:</span></span>  
  
 <span data-ttu-id="bbda1-122">[!code-cs[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="bbda1-122">[!code-cs[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_6.cs)]</span></span>  
  
 <span data-ttu-id="bbda1-123">C# 3.0 presenta matrices con tipo implícito.</span><span class="sxs-lookup"><span data-stu-id="bbda1-123">C# 3.0 introduces implicitly typed arrays.</span></span> <span data-ttu-id="bbda1-124">Para obtener más información, vea [Matrices con asignación implícita de tipos](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="bbda1-124">For more information, see [Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span></span>  
  
## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="bbda1-125">Matrices de tipo de valor y tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="bbda1-125">Value Type and Reference Type Arrays</span></span>  
 <span data-ttu-id="bbda1-126">Tenga en cuenta la siguiente declaración de matriz:</span><span class="sxs-lookup"><span data-stu-id="bbda1-126">Consider the following array declaration:</span></span>  
  
 <span data-ttu-id="bbda1-127">[!code-cs[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="bbda1-127">[!code-cs[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_7.cs)]</span></span>  
  
 <span data-ttu-id="bbda1-128">El resultado de esta instrucción depende de si `SomeType` es un tipo de valor o un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="bbda1-128">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="bbda1-129">Si es un tipo de valor, la instrucción crea una matriz de 10 elementos y cada uno de ellos tiene el tipo `SomeType`.</span><span class="sxs-lookup"><span data-stu-id="bbda1-129">If it is a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="bbda1-130">Si `SomeType` es un tipo de referencia, la instrucción crea una matriz de 10 elementos y cada uno de ellos se inicializa en una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="bbda1-130">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span>  
  
 <span data-ttu-id="bbda1-131">Para obtener más información sobre los tipos de valor y de referencia, consulte [Types](../../../csharp/language-reference/keywords/types.md) (Tipos).</span><span class="sxs-lookup"><span data-stu-id="bbda1-131">For more information about value types and reference types, see [Types](../../../csharp/language-reference/keywords/types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbda1-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbda1-132">See Also</span></span>  
 <span data-ttu-id="bbda1-133"><xref:System.Array></span><span class="sxs-lookup"><span data-stu-id="bbda1-133"><xref:System.Array></span></span>   
 <span data-ttu-id="bbda1-134">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bbda1-134">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="bbda1-135">[Arrays](../../../csharp/programming-guide/arrays/index.md)  (Matrices)</span><span class="sxs-lookup"><span data-stu-id="bbda1-135">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="bbda1-136">[Matrices multidimensionales](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="bbda1-136">[Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span></span>  
 [<span data-ttu-id="bbda1-137">Matrices escalonadas</span><span class="sxs-lookup"><span data-stu-id="bbda1-137">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)

