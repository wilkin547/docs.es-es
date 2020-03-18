---
title: 'Matrices de C#: un paseo por el lenguaje C#'
description: Las matrices son el tipo más básico de colección en el lenguaje C#.
ms.date: 02/27/2020
ms.assetid: a440704c-9e88-4c75-97dd-bfe30ca0fb97
ms.openlocfilehash: 3e045c0933a21beab6958c7851546ba6e0b55ef9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78159200"
---
# <a name="arrays"></a><span data-ttu-id="0f577-103">Matrices</span><span class="sxs-lookup"><span data-stu-id="0f577-103">Arrays</span></span>

<span data-ttu-id="0f577-104">Una ***matriz*** es una estructura de datos que contiene un número de variables a las que se accede mediante índices calculados.</span><span class="sxs-lookup"><span data-stu-id="0f577-104">An ***array*** is a data structure that contains a number of variables that are accessed through computed indices.</span></span> <span data-ttu-id="0f577-105">Las variables contenidas en una matriz, denominadas también ***elementos*** de la matriz, son todas del mismo tipo y este tipo se conoce como ***tipo de elemento*** de la matriz.</span><span class="sxs-lookup"><span data-stu-id="0f577-105">The variables contained in an array, also called the ***elements*** of the array, are all of the same type, and this type is called the ***element type*** of the array.</span></span>

<span data-ttu-id="0f577-106">Los tipos de matriz son tipos de referencia, y la declaración de una variable de matriz simplemente establece un espacio reservado para una referencia a una instancia de matriz.</span><span class="sxs-lookup"><span data-stu-id="0f577-106">Array types are reference types, and the declaration of an array variable simply sets aside space for a reference to an array instance.</span></span> <span data-ttu-id="0f577-107">Las instancias de matriz reales se crean dinámicamente en tiempo de ejecución mediante el operador `new`.</span><span class="sxs-lookup"><span data-stu-id="0f577-107">Actual array instances are created dynamically at runtime using the new operator.</span></span> <span data-ttu-id="0f577-108">La nueva operación especifica la ***longitud*** de la nueva instancia de matriz, que luego se fija para la vigencia de la instancia.</span><span class="sxs-lookup"><span data-stu-id="0f577-108">The new operation specifies the ***length*** of the new array instance, which is then fixed for the lifetime of the instance.</span></span> <span data-ttu-id="0f577-109">Los índices de los elementos de una matriz van de `0` a `Length - 1`.</span><span class="sxs-lookup"><span data-stu-id="0f577-109">The indices of the elements of an array range from `0` to `Length - 1`.</span></span> <span data-ttu-id="0f577-110">El operador `new` inicializa automáticamente los elementos de una matriz a su valor predeterminado, que, por ejemplo, es cero para todos los tipos numéricos y `null` para todos los tipos de referencias.</span><span class="sxs-lookup"><span data-stu-id="0f577-110">The `new` operator automatically initializes the elements of an array to their default value, which, for example, is zero for all numeric types and `null` for all reference types.</span></span>

<span data-ttu-id="0f577-111">En el ejemplo siguiente se crea una matriz de elementos `int`, se inicializa la matriz y se imprime el contenido de la matriz.</span><span class="sxs-lookup"><span data-stu-id="0f577-111">The following example creates an array of `int` elements, initializes the array, and prints out the contents of the array.</span></span>

[!code-csharp[ArraySample](../../../samples/snippets/csharp/tour/arrays/Program.cs#L3-L18)]

<span data-ttu-id="0f577-112">Este ejemplo se crea y se pone en funcionamiento en una ***matriz unidimensional***.</span><span class="sxs-lookup"><span data-stu-id="0f577-112">This example creates and operates on a ***single-dimensional array***.</span></span> <span data-ttu-id="0f577-113">C# también admite ***matrices multidimensionales***.</span><span class="sxs-lookup"><span data-stu-id="0f577-113">C# also supports ***multi-dimensional arrays***.</span></span> <span data-ttu-id="0f577-114">El número de dimensiones de un tipo de matriz, conocido también como ***rango*** del tipo de matriz, es una más el número de comas escritas entre los corchetes del tipo de matriz.</span><span class="sxs-lookup"><span data-stu-id="0f577-114">The number of dimensions of an array type, also known as the ***rank*** of the array type, is one plus the number of commas written between the square brackets of the array type.</span></span> <span data-ttu-id="0f577-115">En el ejemplo siguiente se asignan una matriz unidimensional, bidimensional y tridimensional, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="0f577-115">The following example allocates a single-dimensional, a two-dimensional, and a three-dimensional array, respectively.</span></span>

[!code-csharp[ArrayRank](../../../samples/snippets/csharp/tour/arrays/Program.cs#L24-L26)]

<span data-ttu-id="0f577-116">La matriz `a1` contiene 10 elementos, la matriz `a2` 50 (10 × 5) elementos y la matriz `a3` 100 (10 × 5 × 2) elementos.</span><span class="sxs-lookup"><span data-stu-id="0f577-116">The `a1` array contains 10 elements, the `a2` array contains 50 (10 × 5) elements, and the `a3` array contains 100 (10 × 5 × 2) elements.</span></span>
<span data-ttu-id="0f577-117">El tipo de elemento de una matriz puede ser cualquiera, incluido un tipo de matriz.</span><span class="sxs-lookup"><span data-stu-id="0f577-117">The element type of an array can be any type, including an array type.</span></span> <span data-ttu-id="0f577-118">Una matriz con elementos de un tipo de matriz a veces se conoce como ***matriz escalonada*** porque las longitudes de las matrices de elementos no tienen que ser iguales.</span><span class="sxs-lookup"><span data-stu-id="0f577-118">An array with elements of an array type is sometimes called a ***jagged array*** because the lengths of the element arrays don't all have to be the same.</span></span> <span data-ttu-id="0f577-119">En el ejemplo siguiente se asigna una matriz de matrices de `int`:</span><span class="sxs-lookup"><span data-stu-id="0f577-119">The following example allocates an array of arrays of `int`:</span></span>

[!code-csharp[ArrayAllocation](../../../samples/snippets/csharp/tour/arrays/Program.cs#L31-L34)]

<span data-ttu-id="0f577-120">La primera línea crea una matriz con tres elementos, cada uno de tipo `int[]` y cada uno con un valor inicial de `null`.</span><span class="sxs-lookup"><span data-stu-id="0f577-120">The first line creates an array with three elements, each of type `int[]` and each with an initial value of `null`.</span></span> <span data-ttu-id="0f577-121">Las líneas posteriores inicializan entonces los tres elementos con referencias a instancias de matriz individuales de longitud variable.</span><span class="sxs-lookup"><span data-stu-id="0f577-121">The subsequent lines then initialize the three elements with references to individual array instances of varying lengths.</span></span>

<span data-ttu-id="0f577-122">El nuevo operador permite especificar los valores iniciales de los elementos de matriz mediante un ***inicializador de matriz***, que es una lista de las expresiones escritas entre los delimitadores `{` y `}`.</span><span class="sxs-lookup"><span data-stu-id="0f577-122">The new operator permits the initial values of the array elements to be specified using an ***array initializer***, which is a list of expressions written between the delimiters `{` and `}`.</span></span> <span data-ttu-id="0f577-123">En el ejemplo siguiente se asigna e inicializa un tipo `int[]` con tres elementos.</span><span class="sxs-lookup"><span data-stu-id="0f577-123">The following example allocates and initializes an `int[]` with three elements.</span></span>

[!code-csharp[ArrayInitialization](../../../samples/snippets/csharp/tour/arrays/Program.cs#L39-L39)]

<span data-ttu-id="0f577-124">La longitud de la matriz se deduce del número de expresiones entre { y }.</span><span class="sxs-lookup"><span data-stu-id="0f577-124">The length of the array is inferred from the number of expressions between { and }.</span></span> <span data-ttu-id="0f577-125">Las declaraciones de variable local y campo se pueden acortar más para que así no sea necesario reformular el tipo de matriz.</span><span class="sxs-lookup"><span data-stu-id="0f577-125">Local variable and field declarations can be shortened further such that the array type does not have to be restated.</span></span>

[!code-csharp[ArrayInitialization](../../../samples/snippets/csharp/tour/arrays/Program.cs#L44-L44)]

<span data-ttu-id="0f577-126">Los dos ejemplos anteriores son equivalentes al código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0f577-126">Both of the previous examples are equivalent to the following code:</span></span>

[!code-csharp[ArrayAssignment](../../../samples/snippets/csharp/tour/arrays/Program.cs#L49-L53)]

>[!div class="step-by-step"]
><span data-ttu-id="0f577-127">[Anterior](classes-and-objects.md)
>[Siguiente](interfaces.md)</span><span class="sxs-lookup"><span data-stu-id="0f577-127">[Previous](classes-and-objects.md)
[Next](interfaces.md)</span></span>
