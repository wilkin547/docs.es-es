---
title: 'Matrices unidimensionales: Guía de programación de C#'
ms.date: 06/03/2020
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: e189253eedc21fa2d51e16407f04b034610bb57b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410249"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="70dcc-102">Matrices unidimensionales (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="70dcc-102">Single-Dimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="70dcc-103">Cree una matriz unidimensional mediante el operador [new](../../language-reference/operators/new-operator.md); para ello, especifique el tipo de elemento de matriz y el número de elementos.</span><span class="sxs-lookup"><span data-stu-id="70dcc-103">You create a single-dimensional array using the [new](../../language-reference/operators/new-operator.md) operator specifying the array element type and the number of elements.</span></span> <span data-ttu-id="70dcc-104">En el ejemplo siguiente se declara una matriz de cinco enteros:</span><span class="sxs-lookup"><span data-stu-id="70dcc-104">The following example declares an array of five integers:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntDeclaration":::

<span data-ttu-id="70dcc-105">Esta matriz contiene los elementos de `array[0]` a `array[4]`.</span><span class="sxs-lookup"><span data-stu-id="70dcc-105">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="70dcc-106">Los elementos de la matriz se inicializan en el valor predeterminado del tipo de elemento, `0` para los enteros.</span><span class="sxs-lookup"><span data-stu-id="70dcc-106">The elements of the array are initialized to the default value of the element type, `0` for integers.</span></span>

<span data-ttu-id="70dcc-107">Las matrices pueden almacenar cualquier tipo de elemento que se especifique, como en el ejemplo siguiente, en el que se declara una matriz de cadenas:</span><span class="sxs-lookup"><span data-stu-id="70dcc-107">Arrays can store any element type you specify, such as the following example that declares an array of strings:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringDeclaration":::

## <a name="array-initialization"></a><span data-ttu-id="70dcc-108">Inicialización de matriz</span><span class="sxs-lookup"><span data-stu-id="70dcc-108">Array Initialization</span></span>

<span data-ttu-id="70dcc-109">Puede inicializar los elementos de una matriz al declararla.</span><span class="sxs-lookup"><span data-stu-id="70dcc-109">You can initialize the elements of an array when you declare the array.</span></span> <span data-ttu-id="70dcc-110">El especificador de longitud no es necesario porque la medida se infiere a partir del número de elementos de la lista de inicialización.</span><span class="sxs-lookup"><span data-stu-id="70dcc-110">The length specifier isn't needed because it's inferred by the number of elements in the initialization list.</span></span> <span data-ttu-id="70dcc-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="70dcc-111">For example:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntInitialization":::

<span data-ttu-id="70dcc-112">En el código siguiente se muestra una declaración de una matriz de cadenas donde cada elemento de la matriz se inicializa mediante el nombre de un día:</span><span class="sxs-lookup"><span data-stu-id="70dcc-112">The following code shows a declaration of a string array where each array element is initialized by a name of a day:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringInitialization":::
  
<span data-ttu-id="70dcc-113">Puede evitar la expresión `new` y el tipo de matriz al inicializar una matriz en la declaración, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="70dcc-113">You can avoid the `new` expression and the array type when you initialize an array upon declaration, as shown in the following code.</span></span> <span data-ttu-id="70dcc-114">Esto se conoce como [matriz con tipo implícito](implicitly-typed-arrays.md):</span><span class="sxs-lookup"><span data-stu-id="70dcc-114">This is called an [implicitly typed array](implicitly-typed-arrays.md):</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="ShorthandInitialization":::

<span data-ttu-id="70dcc-115">Puede declarar una variable de matriz sin crearla, pero debe usar el operador `new` cuando asigne una nueva matriz a esta variable.</span><span class="sxs-lookup"><span data-stu-id="70dcc-115">You can declare an array variable without creating it, but you must use the `new` operator when you assign a new array to this variable.</span></span> <span data-ttu-id="70dcc-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="70dcc-116">For example:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="DeclareAllocate":::

## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="70dcc-117">Matrices de tipo de valor y tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="70dcc-117">Value Type and Reference Type Arrays</span></span>

<span data-ttu-id="70dcc-118">Tenga en cuenta la siguiente declaración de matriz:</span><span class="sxs-lookup"><span data-stu-id="70dcc-118">Consider the following array declaration:</span></span>  

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="FinalInstantiation":::

<span data-ttu-id="70dcc-119">El resultado de esta instrucción depende de si `SomeType` es un tipo de valor o un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="70dcc-119">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="70dcc-120">Si es un tipo de valor, la instrucción crea una matriz de 10 elementos, y cada uno de ellos tiene el tipo `SomeType`.</span><span class="sxs-lookup"><span data-stu-id="70dcc-120">If it's a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="70dcc-121">Si `SomeType` es un tipo de referencia, la instrucción crea una matriz de 10 elementos y cada uno de ellos se inicializa en una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="70dcc-121">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span> <span data-ttu-id="70dcc-122">En ambas instancias, los elementos se inicializan en el valor predeterminado para el tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="70dcc-122">In both instances, the elements are initialized to the default value for the element type.</span></span> <span data-ttu-id="70dcc-123">Para obtener más información sobre los tipos de valor y de referencia, consulte [Tipos de valor ](../../language-reference/builtin-types/value-types.md) y [Tipos de referencia](../../language-reference/keywords/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="70dcc-123">For more information about value types and reference types, see [Value types](../../language-reference/builtin-types/value-types.md) and [Reference types](../../language-reference/keywords/reference-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="70dcc-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="70dcc-124">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="70dcc-125">Matrices</span><span class="sxs-lookup"><span data-stu-id="70dcc-125">Arrays</span></span>](./index.md)
- [<span data-ttu-id="70dcc-126">Matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="70dcc-126">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="70dcc-127">Matrices escalonadas</span><span class="sxs-lookup"><span data-stu-id="70dcc-127">Jagged Arrays</span></span>](./jagged-arrays.md)
