---
title: 'Matrices unidimensionales: Guía de programación de C#'
description: Cree una matriz unidimensional en C# mediante el operador new; para ello, especifique el tipo de elemento de matriz y el número de elementos.
ms.date: 06/03/2020
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: ada01262d57cbfebc8bfa1a5fee0639a10db5a4b
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474597"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="be9cc-103">Matrices unidimensionales (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="be9cc-103">Single-Dimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="be9cc-104">Cree una matriz unidimensional mediante el operador [new](../../language-reference/operators/new-operator.md); para ello, especifique el tipo de elemento de matriz y el número de elementos.</span><span class="sxs-lookup"><span data-stu-id="be9cc-104">You create a single-dimensional array using the [new](../../language-reference/operators/new-operator.md) operator specifying the array element type and the number of elements.</span></span> <span data-ttu-id="be9cc-105">En el ejemplo siguiente se declara una matriz de cinco enteros:</span><span class="sxs-lookup"><span data-stu-id="be9cc-105">The following example declares an array of five integers:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntDeclaration":::

<span data-ttu-id="be9cc-106">Esta matriz contiene los elementos de `array[0]` a `array[4]`.</span><span class="sxs-lookup"><span data-stu-id="be9cc-106">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="be9cc-107">Los elementos de la matriz se inicializan en el valor predeterminado del tipo de elemento, `0` para los enteros.</span><span class="sxs-lookup"><span data-stu-id="be9cc-107">The elements of the array are initialized to the default value of the element type, `0` for integers.</span></span>

<span data-ttu-id="be9cc-108">Las matrices pueden almacenar cualquier tipo de elemento que se especifique, como en el ejemplo siguiente, en el que se declara una matriz de cadenas:</span><span class="sxs-lookup"><span data-stu-id="be9cc-108">Arrays can store any element type you specify, such as the following example that declares an array of strings:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringDeclaration":::

## <a name="array-initialization"></a><span data-ttu-id="be9cc-109">Inicialización de matriz</span><span class="sxs-lookup"><span data-stu-id="be9cc-109">Array Initialization</span></span>

<span data-ttu-id="be9cc-110">Puede inicializar los elementos de una matriz al declararla.</span><span class="sxs-lookup"><span data-stu-id="be9cc-110">You can initialize the elements of an array when you declare the array.</span></span> <span data-ttu-id="be9cc-111">El especificador de longitud no es necesario porque la medida se infiere a partir del número de elementos de la lista de inicialización.</span><span class="sxs-lookup"><span data-stu-id="be9cc-111">The length specifier isn't needed because it's inferred by the number of elements in the initialization list.</span></span> <span data-ttu-id="be9cc-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="be9cc-112">For example:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntInitialization":::

<span data-ttu-id="be9cc-113">En el código siguiente se muestra una declaración de una matriz de cadenas donde cada elemento de la matriz se inicializa mediante el nombre de un día:</span><span class="sxs-lookup"><span data-stu-id="be9cc-113">The following code shows a declaration of a string array where each array element is initialized by a name of a day:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringInitialization":::
  
<span data-ttu-id="be9cc-114">Puede evitar la expresión `new` y el tipo de matriz al inicializar una matriz en la declaración, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="be9cc-114">You can avoid the `new` expression and the array type when you initialize an array upon declaration, as shown in the following code.</span></span> <span data-ttu-id="be9cc-115">Esto se conoce como [matriz con tipo implícito](implicitly-typed-arrays.md):</span><span class="sxs-lookup"><span data-stu-id="be9cc-115">This is called an [implicitly typed array](implicitly-typed-arrays.md):</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="ShorthandInitialization":::

<span data-ttu-id="be9cc-116">Puede declarar una variable de matriz sin crearla, pero debe usar el operador `new` cuando asigne una nueva matriz a esta variable.</span><span class="sxs-lookup"><span data-stu-id="be9cc-116">You can declare an array variable without creating it, but you must use the `new` operator when you assign a new array to this variable.</span></span> <span data-ttu-id="be9cc-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="be9cc-117">For example:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="DeclareAllocate":::

## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="be9cc-118">Matrices de tipo de valor y tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="be9cc-118">Value Type and Reference Type Arrays</span></span>

<span data-ttu-id="be9cc-119">Tenga en cuenta la siguiente declaración de matriz:</span><span class="sxs-lookup"><span data-stu-id="be9cc-119">Consider the following array declaration:</span></span>  

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="FinalInstantiation":::

<span data-ttu-id="be9cc-120">El resultado de esta instrucción depende de si `SomeType` es un tipo de valor o un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="be9cc-120">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="be9cc-121">Si es un tipo de valor, la instrucción crea una matriz de 10 elementos, y cada uno de ellos tiene el tipo `SomeType`.</span><span class="sxs-lookup"><span data-stu-id="be9cc-121">If it's a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="be9cc-122">Si `SomeType` es un tipo de referencia, la instrucción crea una matriz de 10 elementos y cada uno de ellos se inicializa en una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="be9cc-122">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span> <span data-ttu-id="be9cc-123">En ambas instancias, los elementos se inicializan en el valor predeterminado para el tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="be9cc-123">In both instances, the elements are initialized to the default value for the element type.</span></span> <span data-ttu-id="be9cc-124">Para obtener más información sobre los tipos de valor y de referencia, consulte [Tipos de valor ](../../language-reference/builtin-types/value-types.md) y [Tipos de referencia](../../language-reference/keywords/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="be9cc-124">For more information about value types and reference types, see [Value types](../../language-reference/builtin-types/value-types.md) and [Reference types](../../language-reference/keywords/reference-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="be9cc-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="be9cc-125">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="be9cc-126">Matrices</span><span class="sxs-lookup"><span data-stu-id="be9cc-126">Arrays</span></span>](./index.md)
- [<span data-ttu-id="be9cc-127">Matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="be9cc-127">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="be9cc-128">Matrices escalonadas</span><span class="sxs-lookup"><span data-stu-id="be9cc-128">Jagged Arrays</span></span>](./jagged-arrays.md)
