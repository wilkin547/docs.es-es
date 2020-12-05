---
title: Matrices
description: 'Obtenga información sobre cómo crear y usar matrices en el lenguaje de programación F #.'
ms.date: 08/13/2020
ms.openlocfilehash: 96b0d7eaf10d5afcd9a647681d5c2ef2d2fba335
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739756"
---
# <a name="arrays"></a><span data-ttu-id="64e5c-103">Matrices</span><span class="sxs-lookup"><span data-stu-id="64e5c-103">Arrays</span></span>

<span data-ttu-id="64e5c-104">Las matrices son colecciones mutables de tamaño fijo y de base cero de elementos de datos consecutivos que son del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="64e5c-104">Arrays are fixed-size, zero-based, mutable collections of consecutive data elements that are all of the same type.</span></span>

## <a name="create-arrays"></a><span data-ttu-id="64e5c-105">Crear matrices</span><span class="sxs-lookup"><span data-stu-id="64e5c-105">Create arrays</span></span>

<span data-ttu-id="64e5c-106">Puede crear matrices de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="64e5c-106">You can create arrays in several ways.</span></span> <span data-ttu-id="64e5c-107">Puede crear una matriz pequeña enumerando valores consecutivos entre `[|` y `|]` y separados por punto y coma, tal como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="64e5c-107">You can create a small array by listing consecutive values between `[|` and `|]` and separated by semicolons, as shown in the following examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet1.fs)]

<span data-ttu-id="64e5c-108">También puede colocar cada elemento en una línea independiente, en cuyo caso el separador de punto y coma es opcional.</span><span class="sxs-lookup"><span data-stu-id="64e5c-108">You can also put each element on a separate line, in which case the semicolon separator is optional.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet2.fs)]

<span data-ttu-id="64e5c-109">El tipo de los elementos de la matriz se deduce de los literales usados y debe ser coherente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-109">The type of the array elements is inferred from the literals used and must be consistent.</span></span> <span data-ttu-id="64e5c-110">El código siguiente produce un error porque 1,0 es float y 2 y 3 son enteros.</span><span class="sxs-lookup"><span data-stu-id="64e5c-110">The following code causes an error because 1.0 is a float and 2 and 3 are integers.</span></span>

```fsharp
// Causes an error.
// let array2 = [| 1.0; 2; 3 |]
```

<span data-ttu-id="64e5c-111">También puede utilizar expresiones de secuencia para crear matrices.</span><span class="sxs-lookup"><span data-stu-id="64e5c-111">You can also use sequence expressions to create arrays.</span></span> <span data-ttu-id="64e5c-112">A continuación se encuentra un ejemplo que crea una matriz de cuadrados de enteros de 1 a 10.</span><span class="sxs-lookup"><span data-stu-id="64e5c-112">Following is an example that creates an array of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet3.fs)]

<span data-ttu-id="64e5c-113">Para crear una matriz en la que todos los elementos se inicializan en cero, use `Array.zeroCreate` .</span><span class="sxs-lookup"><span data-stu-id="64e5c-113">To create an array in which all the elements are initialized to zero, use `Array.zeroCreate`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet4.fs)]

## <a name="access-elements"></a><span data-ttu-id="64e5c-114">Elementos de acceso</span><span class="sxs-lookup"><span data-stu-id="64e5c-114">Access elements</span></span>

<span data-ttu-id="64e5c-115">Puede tener acceso a los elementos de la matriz mediante un operador punto ( `.` ) y corchetes ( `[` y `]` ).</span><span class="sxs-lookup"><span data-stu-id="64e5c-115">You can access array elements by using a dot operator (`.`) and brackets (`[` and `]`).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet5.fs)]

<span data-ttu-id="64e5c-116">Los índices de matriz comienzan en 0.</span><span class="sxs-lookup"><span data-stu-id="64e5c-116">Array indexes start at 0.</span></span>

<span data-ttu-id="64e5c-117">También puede tener acceso a los elementos de la matriz mediante la notación de segmentación, que permite especificar un subintervalo de la matriz.</span><span class="sxs-lookup"><span data-stu-id="64e5c-117">You can also access array elements by using slice notation, which enables you to specify a subrange of the array.</span></span> <span data-ttu-id="64e5c-118">A continuación se muestran ejemplos de notación de segmentación.</span><span class="sxs-lookup"><span data-stu-id="64e5c-118">Examples of slice notation follow.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet51.fs)]

<span data-ttu-id="64e5c-119">Cuando se usa la notación de segmentos, se crea una nueva copia de la matriz.</span><span class="sxs-lookup"><span data-stu-id="64e5c-119">When slice notation is used, a new copy of the array is created.</span></span>

## <a name="array-types-and-modules"></a><span data-ttu-id="64e5c-120">Tipos de matriz y módulos</span><span class="sxs-lookup"><span data-stu-id="64e5c-120">Array types and modules</span></span>

<span data-ttu-id="64e5c-121">El tipo de todas las matrices de F # es el tipo de .NET Framework <xref:System.Array?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="64e5c-121">The type of all F# arrays is the .NET Framework type <xref:System.Array?displayProperty=nameWithType>.</span></span> <span data-ttu-id="64e5c-122">Por lo tanto, las matrices de F # admiten toda la funcionalidad disponible en <xref:System.Array?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="64e5c-122">Therefore, F# arrays support all the functionality available in <xref:System.Array?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="64e5c-123">El [ `Array` módulo](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html) admite operaciones en matrices unidimensionales.</span><span class="sxs-lookup"><span data-stu-id="64e5c-123">The [`Array` module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html) supports operations on one-dimensional arrays.</span></span> <span data-ttu-id="64e5c-124">Los módulos `Array2D` , `Array3D` y `Array4D` contienen funciones que admiten operaciones en matrices de dos, tres y cuatro dimensiones, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-124">The modules `Array2D`, `Array3D`, and `Array4D` contain functions that support operations on arrays of two, three, and four dimensions, respectively.</span></span> <span data-ttu-id="64e5c-125">Puede crear matrices de rango mayores que cuatro mediante <xref:System.Array?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="64e5c-125">You can create arrays of rank greater than four by using <xref:System.Array?displayProperty=nameWithType>.</span></span>

### <a name="simple-functions"></a><span data-ttu-id="64e5c-126">Funciones simples</span><span class="sxs-lookup"><span data-stu-id="64e5c-126">Simple functions</span></span>

<span data-ttu-id="64e5c-127">[`Array.get`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#get) Obtiene un elemento.</span><span class="sxs-lookup"><span data-stu-id="64e5c-127">[`Array.get`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#get) gets an element.</span></span> <span data-ttu-id="64e5c-128">[`Array.length`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#length) proporciona la longitud de una matriz.</span><span class="sxs-lookup"><span data-stu-id="64e5c-128">[`Array.length`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#length) gives the length of an array.</span></span> <span data-ttu-id="64e5c-129">[`Array.set`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#set) establece un elemento en un valor especificado.</span><span class="sxs-lookup"><span data-stu-id="64e5c-129">[`Array.set`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#set) sets an element to a specified value.</span></span> <span data-ttu-id="64e5c-130">En el ejemplo de código siguiente se muestra el uso de estas funciones.</span><span class="sxs-lookup"><span data-stu-id="64e5c-130">The following code example illustrates the use of these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet9.fs)]

<span data-ttu-id="64e5c-131">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-131">The output is as follows.</span></span>

```console
0 1 2 3 4 5 6 7 8 9
```

### <a name="functions-that-create-arrays"></a><span data-ttu-id="64e5c-132">Funciones que crean matrices</span><span class="sxs-lookup"><span data-stu-id="64e5c-132">Functions that create arrays</span></span>

<span data-ttu-id="64e5c-133">Varias funciones crean matrices sin necesidad de una matriz existente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-133">Several functions create arrays without requiring an existing array.</span></span> <span data-ttu-id="64e5c-134">[`Array.empty`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#empty) crea una nueva matriz que no contiene ningún elemento.</span><span class="sxs-lookup"><span data-stu-id="64e5c-134">[`Array.empty`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#empty) creates a new array that does not contain any elements.</span></span> <span data-ttu-id="64e5c-135">[`Array.create`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#create) crea una matriz de un tamaño especificado y establece todos los elementos en los valores proporcionados.</span><span class="sxs-lookup"><span data-stu-id="64e5c-135">[`Array.create`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#create) creates an array of a specified size and sets all the elements to provided values.</span></span> <span data-ttu-id="64e5c-136">[`Array.init`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#init) crea una matriz, dada una dimensión y una función para generar los elementos.</span><span class="sxs-lookup"><span data-stu-id="64e5c-136">[`Array.init`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#init) creates an array, given a dimension and a function to generate the elements.</span></span> <span data-ttu-id="64e5c-137">[`Array.zeroCreate`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zeroCreate) crea una matriz en la que todos los elementos se inicializan en el valor cero para el tipo de la matriz.</span><span class="sxs-lookup"><span data-stu-id="64e5c-137">[`Array.zeroCreate`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zeroCreate) creates an array in which all the elements are initialized to the zero value for the array's type.</span></span> <span data-ttu-id="64e5c-138">En el código siguiente se muestran estas funciones.</span><span class="sxs-lookup"><span data-stu-id="64e5c-138">The following code demonstrates these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet91.fs)]

<span data-ttu-id="64e5c-139">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-139">The output is as follows.</span></span>

```console
Length of empty array: 0
Area of floats set to 5.0: [|5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0|]
Array of squares: [|0; 1; 4; 9; 16; 25; 36; 49; 64; 81|]
```

<span data-ttu-id="64e5c-140">[`Array.copy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#copy) crea una nueva matriz que contiene los elementos que se copian de una matriz existente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-140">[`Array.copy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#copy) creates a new array that contains elements that are copied from an existing array.</span></span> <span data-ttu-id="64e5c-141">Tenga en cuenta que la copia es una copia superficial, lo que significa que si el tipo de elemento es un tipo de referencia, solo se copia la referencia, no el objeto subyacente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-141">Note that the copy is a shallow copy, which means that if the element type is a reference type, only the reference is copied, not the underlying object.</span></span> <span data-ttu-id="64e5c-142">En el siguiente ejemplo código se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="64e5c-142">The following code example illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet11.fs)]

<span data-ttu-id="64e5c-143">La salida del código anterior es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="64e5c-143">The output of the preceding code is as follows:</span></span>

```console
[|Test1; Test2; |]
[|; Test2; |]
```

<span data-ttu-id="64e5c-144">La cadena `Test1` solo aparece en la primera matriz porque la operación de creación de un nuevo elemento sobrescribe la referencia en `firstArray` pero no afecta a la referencia original a una cadena vacía que todavía está presente en `secondArray` .</span><span class="sxs-lookup"><span data-stu-id="64e5c-144">The string `Test1` appears only in the first array because the operation of creating a new element overwrites the reference in `firstArray` but does not affect the original reference to an empty string that is still present in `secondArray`.</span></span> <span data-ttu-id="64e5c-145">La cadena `Test2` aparece en ambas matrices porque la `Insert` operación en el <xref:System.Text.StringBuilder?displayProperty=nameWithType> tipo afecta al objeto subyacente <xref:System.Text.StringBuilder?displayProperty=nameWithType> , al que se hace referencia en ambas matrices.</span><span class="sxs-lookup"><span data-stu-id="64e5c-145">The string `Test2` appears in both arrays because the `Insert` operation on the <xref:System.Text.StringBuilder?displayProperty=nameWithType> type affects the underlying <xref:System.Text.StringBuilder?displayProperty=nameWithType> object, which is referenced in both arrays.</span></span>

<span data-ttu-id="64e5c-146">[`Array.sub`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sub) genera una nueva matriz a partir de un subintervalo de una matriz.</span><span class="sxs-lookup"><span data-stu-id="64e5c-146">[`Array.sub`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sub) generates a new array from a subrange of an array.</span></span> <span data-ttu-id="64e5c-147">Para especificar el subintervalo, proporcione el índice de inicio y la longitud.</span><span class="sxs-lookup"><span data-stu-id="64e5c-147">You specify the subrange by providing the starting index and the length.</span></span> <span data-ttu-id="64e5c-148">En el código siguiente se muestra cómo usar `Array.sub`.</span><span class="sxs-lookup"><span data-stu-id="64e5c-148">The following code demonstrates the use of `Array.sub`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet12.fs)]

<span data-ttu-id="64e5c-149">La salida muestra que la submatriz comienza en el elemento 5 y contiene 10 elementos.</span><span class="sxs-lookup"><span data-stu-id="64e5c-149">The output shows that the subarray starts at element 5 and contains 10 elements.</span></span>

```console
[|5; 6; 7; 8; 9; 10; 11; 12; 13; 14|]
```

<span data-ttu-id="64e5c-150">[`Array.append`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#append) crea una nueva matriz combinando dos matrices existentes.</span><span class="sxs-lookup"><span data-stu-id="64e5c-150">[`Array.append`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#append) creates a new array by combining two existing arrays.</span></span>

<span data-ttu-id="64e5c-151">En el código siguiente se muestra **array. Append**.</span><span class="sxs-lookup"><span data-stu-id="64e5c-151">The following code demonstrates **Array.append**.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet13.fs)]

<span data-ttu-id="64e5c-152">La salida del código anterior es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-152">The output of the preceding code is as follows.</span></span>

```console
[|1; 2; 3; 4; 5; 6|]
```

<span data-ttu-id="64e5c-153">[`Array.choose`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#choose) selecciona los elementos de una matriz que se van a incluir en una nueva matriz.</span><span class="sxs-lookup"><span data-stu-id="64e5c-153">[`Array.choose`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#choose) selects elements of an array to include in a new array.</span></span> <span data-ttu-id="64e5c-154">En el siguiente código se muestra `Array.choose` .</span><span class="sxs-lookup"><span data-stu-id="64e5c-154">The following code demonstrates `Array.choose`.</span></span> <span data-ttu-id="64e5c-155">Tenga en cuenta que el tipo de elemento de la matriz no tiene que coincidir con el tipo del valor devuelto en el tipo de opción.</span><span class="sxs-lookup"><span data-stu-id="64e5c-155">Note that the element type of the array does not have to match the type of the value returned in the option type.</span></span> <span data-ttu-id="64e5c-156">En este ejemplo, el tipo de elemento es `int` y la opción es el resultado de una función polinómica, `elem*elem - 1` , como un número de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="64e5c-156">In this example, the element type is `int` and the option is the result of a polynomial function, `elem*elem - 1`, as a floating point number.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet14.fs)]

<span data-ttu-id="64e5c-157">La salida del código anterior es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-157">The output of the preceding code is as follows.</span></span>

```console
[|3.0; 15.0; 35.0; 63.0; 99.0|]
```

<span data-ttu-id="64e5c-158">[`Array.collect`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#collect) ejecuta una función especificada en cada elemento de matriz de una matriz existente y, a continuación, recopila los elementos generados por la función y los combina en una nueva matriz.</span><span class="sxs-lookup"><span data-stu-id="64e5c-158">[`Array.collect`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#collect) runs a specified function on each array element of an existing array and then collects the elements generated by the function and combines them into a new array.</span></span> <span data-ttu-id="64e5c-159">En el siguiente código se muestra `Array.collect` .</span><span class="sxs-lookup"><span data-stu-id="64e5c-159">The following code demonstrates `Array.collect`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet15.fs)]

<span data-ttu-id="64e5c-160">La salida del código anterior es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-160">The output of the preceding code is as follows.</span></span>

```console
[|0; 1; 0; 1; 2; 3; 4; 5; 0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10|]
```

<span data-ttu-id="64e5c-161">[`Array.concat`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#concat) toma una secuencia de matrices y las combina en una sola matriz.</span><span class="sxs-lookup"><span data-stu-id="64e5c-161">[`Array.concat`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#concat) takes a sequence of arrays and combines them into a single array.</span></span> <span data-ttu-id="64e5c-162">En el siguiente código se muestra `Array.concat` .</span><span class="sxs-lookup"><span data-stu-id="64e5c-162">The following code demonstrates `Array.concat`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet16.fs)]

<span data-ttu-id="64e5c-163">La salida del código anterior es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-163">The output of the preceding code is as follows.</span></span>

```console
[|(1, 1, 1); (1, 2, 2); (1, 3, 3); (2, 1, 2); (2, 2, 4); (2, 3, 6); (3, 1, 3);
(3, 2, 6); (3, 3, 9)|]
```

<span data-ttu-id="64e5c-164">[`Array.filter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#filter) toma una función de condición booleana y genera una nueva matriz que contiene solo los elementos de la matriz de entrada para los que la condición es true.</span><span class="sxs-lookup"><span data-stu-id="64e5c-164">[`Array.filter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#filter) takes a Boolean condition function and generates a new array that contains only those elements from the input array for which the condition is true.</span></span> <span data-ttu-id="64e5c-165">En el siguiente código se muestra `Array.filter` .</span><span class="sxs-lookup"><span data-stu-id="64e5c-165">The following code demonstrates `Array.filter`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet17.fs)]

<span data-ttu-id="64e5c-166">La salida del código anterior es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-166">The output of the preceding code is as follows.</span></span>

```console
[|2; 4; 6; 8; 10|]
```

<span data-ttu-id="64e5c-167">[`Array.rev`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#rev) genera una nueva matriz invirtiendo el orden de una matriz existente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-167">[`Array.rev`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#rev) generates a new array by reversing the order of an existing array.</span></span> <span data-ttu-id="64e5c-168">En el siguiente código se muestra `Array.rev` .</span><span class="sxs-lookup"><span data-stu-id="64e5c-168">The following code demonstrates `Array.rev`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet18.fs)]

<span data-ttu-id="64e5c-169">La salida del código anterior es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-169">The output of the preceding code is as follows.</span></span>

```console
"Hello world!"
```

<span data-ttu-id="64e5c-170">Puede combinar fácilmente funciones en el módulo de matriz que transforman matrices mediante el operador de canalización ( `|>` ), tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-170">You can easily combine functions in the array module that transform arrays by using the pipeline operator (`|>`), as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet19.fs)]

<span data-ttu-id="64e5c-171">El resultado es</span><span class="sxs-lookup"><span data-stu-id="64e5c-171">The output is</span></span>

```console
[|100; 36; 16; 4|]
```

### <a name="multidimensional-arrays"></a><span data-ttu-id="64e5c-172">Matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="64e5c-172">Multidimensional arrays</span></span>

<span data-ttu-id="64e5c-173">Se puede crear una matriz multidimensional, pero no hay ninguna sintaxis para escribir un literal de matriz multidimensional.</span><span class="sxs-lookup"><span data-stu-id="64e5c-173">A multidimensional array can be created, but there is no syntax for writing a multidimensional array literal.</span></span> <span data-ttu-id="64e5c-174">Use el operador [`array2D`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html) para crear una matriz a partir de una secuencia de secuencias de elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="64e5c-174">Use the operator [`array2D`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html) to create an array from a sequence of sequences of array elements.</span></span> <span data-ttu-id="64e5c-175">Las secuencias pueden ser literales de matriz o lista.</span><span class="sxs-lookup"><span data-stu-id="64e5c-175">The sequences can be array or list literals.</span></span> <span data-ttu-id="64e5c-176">Por ejemplo, el código siguiente crea una matriz bidimensional.</span><span class="sxs-lookup"><span data-stu-id="64e5c-176">For example, the following code creates a two-dimensional array.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet20.fs)]

<span data-ttu-id="64e5c-177">También puede usar la función [`Array2D.init`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html#init) para inicializar matrices de dos dimensiones, y las funciones similares están disponibles para las matrices de tres y cuatro dimensiones.</span><span class="sxs-lookup"><span data-stu-id="64e5c-177">You can also use the function [`Array2D.init`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html#init) to initialize arrays of two dimensions, and similar functions are available for arrays of three and four dimensions.</span></span> <span data-ttu-id="64e5c-178">Estas funciones toman una función que se utiliza para crear los elementos.</span><span class="sxs-lookup"><span data-stu-id="64e5c-178">These functions take a function that is used to create the elements.</span></span> <span data-ttu-id="64e5c-179">Para crear una matriz bidimensional que contenga elementos establecidos en un valor inicial en lugar de especificar una función, use la [`Array2D.create`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html#create) función, que también está disponible para matrices de hasta cuatro dimensiones.</span><span class="sxs-lookup"><span data-stu-id="64e5c-179">To create a two-dimensional array that contains elements set to an initial value instead of specifying a function, use the [`Array2D.create`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html#create) function, which is also available for arrays up to four dimensions.</span></span> <span data-ttu-id="64e5c-180">En el ejemplo de código siguiente se muestra primero cómo crear una matriz de matrices que contienen los elementos deseados y, a continuación, `Array2D.init` se usa para generar la matriz bidimensional deseada.</span><span class="sxs-lookup"><span data-stu-id="64e5c-180">The following code example first shows how to create an array of arrays that contain the desired elements, and then uses `Array2D.init` to generate the desired two-dimensional array.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet21.fs)]

<span data-ttu-id="64e5c-181">La sintaxis de indización y segmentación de matrices es compatible con matrices hasta el rango 4.</span><span class="sxs-lookup"><span data-stu-id="64e5c-181">Array indexing and slicing syntax is supported for arrays up to rank 4.</span></span> <span data-ttu-id="64e5c-182">Cuando se especifica un índice en varias dimensiones, se usan comas para separar los índices, tal y como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-182">When you specify an index in multiple dimensions, you use commas to separate the indexes, as illustrated in the following code example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet22.fs)]

<span data-ttu-id="64e5c-183">El tipo de una matriz bidimensional se escribe como `<type>[,]` (por ejemplo, `int[,]` , `double[,]` ) y el tipo de una matriz tridimensional se escribe como `<type>[,,]` y así sucesivamente para las matrices de dimensiones superiores.</span><span class="sxs-lookup"><span data-stu-id="64e5c-183">The type of a two-dimensional array is written out as `<type>[,]` (for example, `int[,]`, `double[,]`), and the type of a three-dimensional array is written as `<type>[,,]`, and so on for arrays of higher dimensions.</span></span>

<span data-ttu-id="64e5c-184">Solo hay disponible un subconjunto de las funciones disponibles para las matrices unidimensionales para las matrices multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="64e5c-184">Only a subset of the functions available for one-dimensional arrays is also available for multidimensional arrays.</span></span>

### <a name="array-slicing-and-multidimensional-arrays"></a><span data-ttu-id="64e5c-185">Segmentación de matrices y matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="64e5c-185">Array slicing and multidimensional arrays</span></span>

<span data-ttu-id="64e5c-186">En una matriz bidimensional (matriz), puede extraer una submatriz especificando los intervalos y usando un carácter comodín ( `*` ) para especificar filas o columnas completas.</span><span class="sxs-lookup"><span data-stu-id="64e5c-186">In a two-dimensional array (a matrix), you can extract a sub-matrix by specifying ranges and using a wildcard (`*`) character to specify whole rows or columns.</span></span>

```fsharp
// Get rows 1 to N from an NxM matrix (returns a matrix):
matrix.[1.., *]

// Get rows 1 to 3 from a matrix (returns a matrix):
matrix.[1..3, *]

// Get columns 1 to 3 from a matrix (returns a matrix):
matrix.[*, 1..3]

// Get a 3x3 submatrix:
matrix.[1..3, 1..3]
```

<span data-ttu-id="64e5c-187">Puede descomponer una matriz multidimensional en submatrices de la misma dimensión o en una inferior.</span><span class="sxs-lookup"><span data-stu-id="64e5c-187">You can decompose a multidimensional array into subarrays of the same or lower dimension.</span></span> <span data-ttu-id="64e5c-188">Por ejemplo, puede obtener un vector de una matriz especificando una sola fila o columna.</span><span class="sxs-lookup"><span data-stu-id="64e5c-188">For example, you can obtain a vector from a matrix by specifying a single row or column.</span></span>

```fsharp
// Get row 3 from a matrix as a vector:
matrix.[3, *]

// Get column 3 from a matrix as a vector:
matrix.[*, 3]
```

<span data-ttu-id="64e5c-189">Puede utilizar esta sintaxis de segmentación para los tipos que implementan los operadores de acceso a elementos y los métodos sobrecargados `GetSlice` .</span><span class="sxs-lookup"><span data-stu-id="64e5c-189">You can use this slicing syntax for types that implement the element access operators and overloaded `GetSlice` methods.</span></span> <span data-ttu-id="64e5c-190">Por ejemplo, el código siguiente crea un tipo de matriz que contiene la matriz 2D de F #, implementa una propiedad Item para proporcionar compatibilidad con la indización de matrices e implementa tres versiones de `GetSlice` .</span><span class="sxs-lookup"><span data-stu-id="64e5c-190">For example, the following code creates a Matrix type that wraps the F# 2D array, implements an Item property to provide support for array indexing, and implements three versions of `GetSlice`.</span></span> <span data-ttu-id="64e5c-191">Si puede usar este código como plantilla para los tipos de matriz, puede usar todas las operaciones de segmentación que se describen en esta sección.</span><span class="sxs-lookup"><span data-stu-id="64e5c-191">If you can use this code as a template for your matrix types, you can use all the slicing operations that this section describes.</span></span>

```fsharp
type Matrix<'T>(N: int, M: int) =
    let internalArray = Array2D.zeroCreate<'T> N M

    member this.Item
        with get(a: int, b: int) = internalArray.[a, b]
        and set(a: int, b: int) (value:'T) = internalArray.[a, b] <- value

    member this.GetSlice(rowStart: int option, rowFinish : int option, colStart: int option, colFinish : int option) =
        let rowStart =
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        let colStart =
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish =
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[rowStart..rowFinish, colStart..colFinish]

    member this.GetSlice(row: int, colStart: int option, colFinish: int option) =
        let colStart =
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish =
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[row, colStart..colFinish]

    member this.GetSlice(rowStart: int option, rowFinish: int option, col: int) =
        let rowStart =
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        internalArray.[rowStart..rowFinish, col]

module test =
    let generateTestMatrix x y =
        let matrix = new Matrix<float>(3, 3)
        for i in 0..2 do
            for j in 0..2 do
                matrix.[i, j] <- float(i) * x - float(j) * y
        matrix

    let test1 = generateTestMatrix 2.3 1.1
    let submatrix = test1.[0..1, 0..1]
    printfn $"{submatrix}"

    let firstRow = test1.[0,*]
    let secondRow = test1.[1,*]
    let firstCol = test1.[*,0]
    printfn $"{firstCol}"
```

### <a name="boolean-functions-on-arrays"></a><span data-ttu-id="64e5c-192">Funciones booleanas en matrices</span><span class="sxs-lookup"><span data-stu-id="64e5c-192">Boolean functions on arrays</span></span>

<span data-ttu-id="64e5c-193">Las funciones [`Array.exists`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#exists) y [`Array.exists2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#exists2) los elementos de prueba de una o dos matrices, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-193">The functions [`Array.exists`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#exists) and [`Array.exists2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#exists2) test elements in either one or two arrays, respectively.</span></span> <span data-ttu-id="64e5c-194">Estas funciones toman una función de prueba y devuelven `true` si hay un elemento (o par de elementos para `Array.exists2` ) que cumple la condición.</span><span class="sxs-lookup"><span data-stu-id="64e5c-194">These functions take a test function and return `true` if there is an element (or element pair for `Array.exists2`) that satisfies the condition.</span></span>

<span data-ttu-id="64e5c-195">En el código siguiente se muestra el uso de `Array.exists` y `Array.exists2` .</span><span class="sxs-lookup"><span data-stu-id="64e5c-195">The following code demonstrates the use of `Array.exists` and `Array.exists2`.</span></span> <span data-ttu-id="64e5c-196">En estos ejemplos, se crean nuevas funciones aplicando solo uno de los argumentos, en estos casos, el argumento de la función.</span><span class="sxs-lookup"><span data-stu-id="64e5c-196">In these examples, new functions are created by applying only one of the arguments, in these cases, the function argument.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet23.fs)]

<span data-ttu-id="64e5c-197">La salida del código anterior es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-197">The output of the preceding code is as follows.</span></span>

```console
true
false
false
true
```

<span data-ttu-id="64e5c-198">Del mismo modo, la función [`Array.forall`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#forall) prueba una matriz para determinar si todos los elementos satisfacen una condición booleana.</span><span class="sxs-lookup"><span data-stu-id="64e5c-198">Similarly, the function [`Array.forall`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#forall) tests an array to determine whether every element satisfies a Boolean condition.</span></span> <span data-ttu-id="64e5c-199">La variación [`Array.forall2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#forall2) hace lo mismo mediante el uso de una función booleana que implica elementos de dos matrices de igual longitud.</span><span class="sxs-lookup"><span data-stu-id="64e5c-199">The variation [`Array.forall2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#forall2) does the same thing by using a Boolean function that involves elements of two arrays of equal length.</span></span> <span data-ttu-id="64e5c-200">En el código siguiente se muestra el uso de estas funciones.</span><span class="sxs-lookup"><span data-stu-id="64e5c-200">The following code illustrates the use of these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet24.fs)]

<span data-ttu-id="64e5c-201">La salida de estos ejemplos es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-201">The output for these examples is as follows.</span></span>

```console
false
true
true
false
```

### <a name="search-arrays"></a><span data-ttu-id="64e5c-202">Buscar matrices</span><span class="sxs-lookup"><span data-stu-id="64e5c-202">Search arrays</span></span>

<span data-ttu-id="64e5c-203">[`Array.find`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#find) toma una función booleana y devuelve el primer elemento para el que devuelve la función `true` , o produce una <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> si no se encuentra ningún elemento que cumpla la condición.</span><span class="sxs-lookup"><span data-stu-id="64e5c-203">[`Array.find`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#find) takes a Boolean function and returns the first element for which the function returns `true`, or raises a <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> if no element that satisfies the condition is found.</span></span> <span data-ttu-id="64e5c-204">[`Array.findIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#findIndex) es como `Array.find` , excepto que devuelve el índice del elemento en lugar del propio elemento.</span><span class="sxs-lookup"><span data-stu-id="64e5c-204">[`Array.findIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#findIndex) is like `Array.find`, except that it returns the index of the element instead of the element itself.</span></span>

<span data-ttu-id="64e5c-205">En el código siguiente `Array.find` se usa y `Array.findIndex` para buscar un número que sea un cuadrado perfecto y un cubo perfecto.</span><span class="sxs-lookup"><span data-stu-id="64e5c-205">The following code uses `Array.find` and `Array.findIndex` to locate a number that is both a perfect square and perfect cube.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet25.fs)]

<span data-ttu-id="64e5c-206">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-206">The output is as follows.</span></span>

```console
The first element that is both a square and a cube is 64 and its index is 62.
```

<span data-ttu-id="64e5c-207">[`Array.tryFind`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryFind) es como `Array.find` , excepto que su resultado es un tipo de opción y devuelve `None` si no se encuentra ningún elemento.</span><span class="sxs-lookup"><span data-stu-id="64e5c-207">[`Array.tryFind`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryFind) is like `Array.find`, except that its result is an option type, and it returns `None` if no element is found.</span></span> <span data-ttu-id="64e5c-208">`Array.tryFind` se debe usar en lugar de `Array.find` cuando no se sabe si un elemento coincidente está en la matriz.</span><span class="sxs-lookup"><span data-stu-id="64e5c-208">`Array.tryFind` should be used instead of `Array.find` when you do not know whether a matching element is in the array.</span></span> <span data-ttu-id="64e5c-209">Del mismo modo, [`Array.tryFindIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryFindIndex) es como, `Array.findIndex` excepto que el tipo de opción es el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="64e5c-209">Similarly, [`Array.tryFindIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryFindIndex) is like `Array.findIndex` except that the option type is the return value.</span></span> <span data-ttu-id="64e5c-210">Si no se encuentra ningún elemento, la opción es `None` .</span><span class="sxs-lookup"><span data-stu-id="64e5c-210">If no element is found, the option is `None`.</span></span>

<span data-ttu-id="64e5c-211">En el código siguiente se muestra cómo usar `Array.tryFind`.</span><span class="sxs-lookup"><span data-stu-id="64e5c-211">The following code demonstrates the use of `Array.tryFind`.</span></span> <span data-ttu-id="64e5c-212">Este código depende del código anterior.</span><span class="sxs-lookup"><span data-stu-id="64e5c-212">This code depends on the previous code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet26.fs)]

<span data-ttu-id="64e5c-213">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-213">The output is as follows.</span></span>

```console
Found an element: 1
Found an element: 729
Failed to find a matching element.
```

<span data-ttu-id="64e5c-214">Use [`Array.tryPick`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryPick) cuando necesite transformar un elemento además de encontrarlo.</span><span class="sxs-lookup"><span data-stu-id="64e5c-214">Use [`Array.tryPick`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryPick) when you need to transform an element in addition to finding it.</span></span> <span data-ttu-id="64e5c-215">El resultado es el primer elemento para el que la función devuelve el elemento transformado como un valor de opción, o `None` si no se encuentra dicho elemento.</span><span class="sxs-lookup"><span data-stu-id="64e5c-215">The result is the first element for which the function returns the transformed element as an option value, or `None` if no such element is found.</span></span>

<span data-ttu-id="64e5c-216">En el código siguiente se muestra el uso de `Array.tryPick`.</span><span class="sxs-lookup"><span data-stu-id="64e5c-216">The following code shows the use of `Array.tryPick`.</span></span> <span data-ttu-id="64e5c-217">En este caso, en lugar de una expresión lambda, se definen varias funciones auxiliares locales para simplificar el código.</span><span class="sxs-lookup"><span data-stu-id="64e5c-217">In this case, instead of a lambda expression, several local helper functions are defined to simplify the code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet27.fs)]

<span data-ttu-id="64e5c-218">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-218">The output is as follows.</span></span>

```console
Found an element 1 with square root 1 and cube root 1.
Found an element 64 with square root 8 and cube root 4.
Found an element 729 with square root 27 and cube root 9.
Found an element 4096 with square root 64 and cube root 16.
Did not find an element that is both a perfect square and a perfect cube.
```

### <a name="perform-computations-on-arrays"></a><span data-ttu-id="64e5c-219">Realizar cálculos en matrices</span><span class="sxs-lookup"><span data-stu-id="64e5c-219">Perform computations on arrays</span></span>

<span data-ttu-id="64e5c-220">La [`Array.average`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#average) función devuelve el promedio de cada elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="64e5c-220">The [`Array.average`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#average) function returns the average of each element in an array.</span></span> <span data-ttu-id="64e5c-221">Se limita a los tipos de elemento que admiten la división exacta mediante un entero, que incluye los tipos de punto flotante, pero no los tipos enteros.</span><span class="sxs-lookup"><span data-stu-id="64e5c-221">It is limited to element types that support exact division by an integer, which includes floating point types but not integral types.</span></span> <span data-ttu-id="64e5c-222">La [`Array.averageBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#averageBy) función devuelve el promedio de los resultados de llamar a una función en cada elemento.</span><span class="sxs-lookup"><span data-stu-id="64e5c-222">The [`Array.averageBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#averageBy) function returns the average of the results of calling a function on each element.</span></span> <span data-ttu-id="64e5c-223">Para una matriz de tipo entero, puede usar `Array.averageBy` y hacer que la función convierta cada elemento en un tipo de punto flotante para el cálculo.</span><span class="sxs-lookup"><span data-stu-id="64e5c-223">For an array of integral type, you can use `Array.averageBy` and have the function convert each element to a floating point type for the computation.</span></span>

<span data-ttu-id="64e5c-224">Use [`Array.max`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#max) o [`Array.min`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#min) para obtener el elemento máximo o mínimo, si el tipo de elemento lo admite.</span><span class="sxs-lookup"><span data-stu-id="64e5c-224">Use [`Array.max`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#max) or [`Array.min`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#min) to get the maximum or minimum element, if the element type supports it.</span></span> <span data-ttu-id="64e5c-225">De forma similar, [`Array.maxBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#maxBy) y [`Array.minBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#minBy) permiten que una función se ejecute en primer lugar, quizás para realizar la transformación en un tipo que admita la comparación.</span><span class="sxs-lookup"><span data-stu-id="64e5c-225">Similarly, [`Array.maxBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#maxBy) and [`Array.minBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#minBy) allow a function to be executed first, perhaps to transform to a type that supports comparison.</span></span>

<span data-ttu-id="64e5c-226">[`Array.sum`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sum) agrega los elementos de una matriz y [`Array.sumBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sumBy) llama a una función en cada elemento y agrega los resultados juntos.</span><span class="sxs-lookup"><span data-stu-id="64e5c-226">[`Array.sum`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sum) adds the elements of an array, and [`Array.sumBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sumBy) calls a function on each element and adds the results together.</span></span>

<span data-ttu-id="64e5c-227">Para ejecutar una función en cada elemento de una matriz sin almacenar los valores devueltos, use [`Array.iter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iter) .</span><span class="sxs-lookup"><span data-stu-id="64e5c-227">To execute a function on each element in an array without storing the return values, use [`Array.iter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iter).</span></span> <span data-ttu-id="64e5c-228">Para una función que implique dos matrices de igual longitud, use [`Array.iter2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iter2) .</span><span class="sxs-lookup"><span data-stu-id="64e5c-228">For a function involving two arrays of equal length, use [`Array.iter2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iter2).</span></span> <span data-ttu-id="64e5c-229">Si también necesita mantener una matriz de los resultados de la función, use [`Array.map`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#map) o [`Array.map2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#map2) , que opera en dos matrices a la vez.</span><span class="sxs-lookup"><span data-stu-id="64e5c-229">If you also need to keep an array of the results of the function, use [`Array.map`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#map) or [`Array.map2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#map2), which operates on two arrays at a time.</span></span>

<span data-ttu-id="64e5c-230">Las variaciones [`Array.iteri`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iteri) y [`Array.iteri2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iteri2) permiten que el índice del elemento esté implicado en el cálculo; lo mismo sucede con [`Array.mapi`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#mapi) y [`Array.mapi2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#mapi2) .</span><span class="sxs-lookup"><span data-stu-id="64e5c-230">The variations [`Array.iteri`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iteri) and [`Array.iteri2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iteri2) allow the index of the element to be involved in the computation; the same is true for [`Array.mapi`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#mapi) and [`Array.mapi2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#mapi2).</span></span>

<span data-ttu-id="64e5c-231">Las funciones,,,, [`Array.fold`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fold) [`Array.foldBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#foldBack) [`Array.reduce`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#reduce) [`Array.reduceBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#reduceBack) [`Array.scan`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#scan) y [`Array.scanBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#scanBack) ejecutan algoritmos que implican todos los elementos de una matriz.</span><span class="sxs-lookup"><span data-stu-id="64e5c-231">The functions [`Array.fold`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fold), [`Array.foldBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#foldBack), [`Array.reduce`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#reduce), [`Array.reduceBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#reduceBack), [`Array.scan`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#scan), and [`Array.scanBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#scanBack) execute algorithms that involve all the elements of an array.</span></span> <span data-ttu-id="64e5c-232">Del mismo modo, las variaciones [`Array.fold2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fold2) y [`Array.foldBack2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#foldBack2) realizan cálculos en dos matrices.</span><span class="sxs-lookup"><span data-stu-id="64e5c-232">Similarly, the variations [`Array.fold2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fold2) and [`Array.foldBack2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#foldBack2) perform computations on two arrays.</span></span>

<span data-ttu-id="64e5c-233">Estas funciones para realizar cálculos se corresponden con las funciones del mismo nombre en el [módulo de lista](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span><span class="sxs-lookup"><span data-stu-id="64e5c-233">These functions for performing computations correspond to the functions of the same name in the [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span> <span data-ttu-id="64e5c-234">Para obtener ejemplos de uso, vea [listas](lists.md).</span><span class="sxs-lookup"><span data-stu-id="64e5c-234">For usage examples, see [Lists](lists.md).</span></span>

### <a name="modify-arrays"></a><span data-ttu-id="64e5c-235">Modificar matrices</span><span class="sxs-lookup"><span data-stu-id="64e5c-235">Modify arrays</span></span>

<span data-ttu-id="64e5c-236">[`Array.set`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#set) establece un elemento en un valor especificado.</span><span class="sxs-lookup"><span data-stu-id="64e5c-236">[`Array.set`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#set) sets an element to a specified value.</span></span> <span data-ttu-id="64e5c-237">[`Array.fill`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fill) establece un intervalo de elementos de una matriz en un valor especificado.</span><span class="sxs-lookup"><span data-stu-id="64e5c-237">[`Array.fill`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fill) sets a range of elements in an array to a specified value.</span></span> <span data-ttu-id="64e5c-238">En el código siguiente se proporciona un ejemplo de `Array.fill` .</span><span class="sxs-lookup"><span data-stu-id="64e5c-238">The following code provides an example of `Array.fill`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet28.fs)]

<span data-ttu-id="64e5c-239">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="64e5c-239">The output is as follows.</span></span>

```console
[|1; 2; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 23; 24; 25|]
```

<span data-ttu-id="64e5c-240">Puede usar [`Array.blit`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#blit) para copiar una subsección de una matriz en otra matriz.</span><span class="sxs-lookup"><span data-stu-id="64e5c-240">You can use [`Array.blit`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#blit) to copy a subsection of one array to another array.</span></span>

### <a name="convert-to-and-from-other-types"></a><span data-ttu-id="64e5c-241">Conversión a y desde otros tipos</span><span class="sxs-lookup"><span data-stu-id="64e5c-241">Convert to and from other types</span></span>

<span data-ttu-id="64e5c-242">[`Array.ofList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#ofList) crea una matriz a partir de una lista.</span><span class="sxs-lookup"><span data-stu-id="64e5c-242">[`Array.ofList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#ofList) creates an array from a list.</span></span> <span data-ttu-id="64e5c-243">[`Array.ofSeq`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#ofSeq) crea una matriz a partir de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="64e5c-243">[`Array.ofSeq`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#ofSeq) creates an array from a sequence.</span></span> <span data-ttu-id="64e5c-244">[`Array.toList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#toList) y [`Array.toSeq`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#toSeq) se convierten en estos otros tipos de colección del tipo de matriz.</span><span class="sxs-lookup"><span data-stu-id="64e5c-244">[`Array.toList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#toList) and [`Array.toSeq`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#toSeq) convert to these other collection types from the array type.</span></span>

### <a name="sort-arrays"></a><span data-ttu-id="64e5c-245">Ordenar matrices</span><span class="sxs-lookup"><span data-stu-id="64e5c-245">Sort arrays</span></span>

<span data-ttu-id="64e5c-246">Use [`Array.sort`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sort) para ordenar una matriz utilizando la función de comparación genérica.</span><span class="sxs-lookup"><span data-stu-id="64e5c-246">Use [`Array.sort`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sort) to sort an array by using the generic comparison function.</span></span> <span data-ttu-id="64e5c-247">Utilice [`Array.sortBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortBy) para especificar una función que genera un valor, al que se hace referencia como *clave*, para ordenar mediante la función de comparación genérica de la clave.</span><span class="sxs-lookup"><span data-stu-id="64e5c-247">Use [`Array.sortBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortBy) to specify a function that generates a value, referred to as a *key*, to sort by using the generic comparison function on the key.</span></span> <span data-ttu-id="64e5c-248">Use [`Array.sortWith`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortWith) si desea proporcionar una función de comparación personalizada.</span><span class="sxs-lookup"><span data-stu-id="64e5c-248">Use [`Array.sortWith`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortWith) if you want to provide a custom comparison function.</span></span> <span data-ttu-id="64e5c-249">`Array.sort`, `Array.sortBy` y `Array.sortWith` devuelven la matriz ordenada como una nueva matriz.</span><span class="sxs-lookup"><span data-stu-id="64e5c-249">`Array.sort`, `Array.sortBy`, and `Array.sortWith` all return the sorted array as a new array.</span></span> <span data-ttu-id="64e5c-250">Las variaciones [`Array.sortInPlace`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlace) , [`Array.sortInPlaceBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlaceBy) y [`Array.sortInPlaceWith`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlaceWith) modifican la matriz existente en lugar de devolver una nueva.</span><span class="sxs-lookup"><span data-stu-id="64e5c-250">The variations [`Array.sortInPlace`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlace), [`Array.sortInPlaceBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlaceBy), and [`Array.sortInPlaceWith`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlaceWith) modify the existing array instead of returning a new one.</span></span>

### <a name="arrays-and-tuples"></a><span data-ttu-id="64e5c-251">Matrices y tuplas</span><span class="sxs-lookup"><span data-stu-id="64e5c-251">Arrays and tuples</span></span>

<span data-ttu-id="64e5c-252">Las funciones [`Array.zip`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zip) y [`Array.unzip`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#unzip) convierten matrices de pares de tupla en tuplas de matrices y viceversa.</span><span class="sxs-lookup"><span data-stu-id="64e5c-252">The functions [`Array.zip`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zip) and [`Array.unzip`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#unzip) convert arrays of tuple pairs to tuples of arrays and vice versa.</span></span> <span data-ttu-id="64e5c-253">[`Array.zip3`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zip3) y [`Array.unzip3`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#unzip3) son similares, salvo que funcionan con tuplas de tres elementos o tuplas de tres matrices.</span><span class="sxs-lookup"><span data-stu-id="64e5c-253">[`Array.zip3`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zip3) and [`Array.unzip3`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#unzip3) are similar except that they work with tuples of three elements or tuples of three arrays.</span></span>

## <a name="parallel-computations-on-arrays"></a><span data-ttu-id="64e5c-254">Cálculos paralelos en matrices</span><span class="sxs-lookup"><span data-stu-id="64e5c-254">Parallel computations on arrays</span></span>

<span data-ttu-id="64e5c-255">El módulo [`Array.Parallel`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule-parallel.html) contiene funciones para realizar cálculos paralelos en matrices.</span><span class="sxs-lookup"><span data-stu-id="64e5c-255">The module [`Array.Parallel`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule-parallel.html) contains functions for performing parallel computations on arrays.</span></span> <span data-ttu-id="64e5c-256">Este módulo no está disponible en las aplicaciones que tienen como destino versiones de .NET Framework anteriores a la versión 4.</span><span class="sxs-lookup"><span data-stu-id="64e5c-256">This module is not available in applications that target versions of the .NET Framework prior to version 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="64e5c-257">Vea también</span><span class="sxs-lookup"><span data-stu-id="64e5c-257">See also</span></span>

- [<span data-ttu-id="64e5c-258">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="64e5c-258">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="64e5c-259">Tipos en F#</span><span class="sxs-lookup"><span data-stu-id="64e5c-259">F# Types</span></span>](fsharp-types.md)
