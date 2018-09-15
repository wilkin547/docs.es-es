---
title: Matrices (F#)
description: 'Obtenga información sobre cómo crear y usar matrices en el lenguaje de programación F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 27b73efc900ac2efc813fe66f81baa2e9ae1e843
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2018
ms.locfileid: "45591846"
---
# <a name="arrays"></a><span data-ttu-id="eab37-103">Matrices</span><span class="sxs-lookup"><span data-stu-id="eab37-103">Arrays</span></span>

> [!NOTE]
<span data-ttu-id="eab37-104">El vínculo de la referencia de API le llevará a MSDN.</span><span class="sxs-lookup"><span data-stu-id="eab37-104">The API reference link will take you to MSDN.</span></span>  <span data-ttu-id="eab37-105">La referencia de API de docs.microsoft.com no está completa.</span><span class="sxs-lookup"><span data-stu-id="eab37-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="eab37-106">Las matrices son colecciones de tamaño fijo, basado en cero, mutables de elementos de datos consecutivos que son todas del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="eab37-106">Arrays are fixed-size, zero-based, mutable collections of consecutive data elements that are all of the same type.</span></span>

## <a name="creating-arrays"></a><span data-ttu-id="eab37-107">Creación de matrices</span><span class="sxs-lookup"><span data-stu-id="eab37-107">Creating Arrays</span></span>

<span data-ttu-id="eab37-108">Puede crear matrices de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="eab37-108">You can create arrays in several ways.</span></span> <span data-ttu-id="eab37-109">Puede crear una matriz pequeña con una lista de valores consecutivos entre `[|` y `|]` y separados por punto y coma, como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="eab37-109">You can create a small array by listing consecutive values between `[|` and `|]` and separated by semicolons, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet1.fs)]

<span data-ttu-id="eab37-110">También puede colocar cada elemento en una línea independiente, en cuyo caso el separador de punto y coma es opcional.</span><span class="sxs-lookup"><span data-stu-id="eab37-110">You can also put each element on a separate line, in which case the semicolon separator is optional.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet2.fs)]

<span data-ttu-id="eab37-111">El tipo de los elementos de matriz se deduce de los literales utilizados y debe ser coherente.</span><span class="sxs-lookup"><span data-stu-id="eab37-111">The type of the array elements is inferred from the literals used and must be consistent.</span></span> <span data-ttu-id="eab37-112">El código siguiente produce un error porque 1.0 es un valor float y 2 y 3 son enteros.</span><span class="sxs-lookup"><span data-stu-id="eab37-112">The following code causes an error because 1.0 is a float and 2 and 3 are integers.</span></span>

```fsharp
// Causes an error.
// let array2 = [| 1.0; 2; 3 |]
```

<span data-ttu-id="eab37-113">También puede usar las expresiones de secuencia para crear matrices.</span><span class="sxs-lookup"><span data-stu-id="eab37-113">You can also use sequence expressions to create arrays.</span></span> <span data-ttu-id="eab37-114">La siguiente es un ejemplo que crea una matriz de los cuadrados de enteros del 1 al 10.</span><span class="sxs-lookup"><span data-stu-id="eab37-114">Following is an example that creates an array of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet3.fs)]

<span data-ttu-id="eab37-115">Para crear una matriz en la que todos los elementos se inicializan a cero, se utiliza `Array.zeroCreate`.</span><span class="sxs-lookup"><span data-stu-id="eab37-115">To create an array in which all the elements are initialized to zero, use `Array.zeroCreate`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet4.fs)]

## <a name="accessing-elements"></a><span data-ttu-id="eab37-116">Tener acceso a elementos</span><span class="sxs-lookup"><span data-stu-id="eab37-116">Accessing Elements</span></span>

<span data-ttu-id="eab37-117">Puede tener acceso a los elementos de matriz mediante el operador punto (`.`) y corchetes (`[` y `]`).</span><span class="sxs-lookup"><span data-stu-id="eab37-117">You can access array elements by using a dot operator (`.`) and brackets (`[` and `]`).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet5.fs)]

<span data-ttu-id="eab37-118">Los índices de matriz empiezan en 0.</span><span class="sxs-lookup"><span data-stu-id="eab37-118">Array indexes start at 0.</span></span>

<span data-ttu-id="eab37-119">También puede tener acceso a los elementos de matriz utilizando la notación de segmentos, que le permite especificar un subrango de la matriz.</span><span class="sxs-lookup"><span data-stu-id="eab37-119">You can also access array elements by using slice notation, which enables you to specify a subrange of the array.</span></span> <span data-ttu-id="eab37-120">Se presentan ejemplos de notación de segmentos.</span><span class="sxs-lookup"><span data-stu-id="eab37-120">Examples of slice notation follow.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet51.fs)]

<span data-ttu-id="eab37-121">Cuando se usa la notación de segmentos, se crea una nueva copia de la matriz.</span><span class="sxs-lookup"><span data-stu-id="eab37-121">When slice notation is used, a new copy of the array is created.</span></span>

## <a name="array-types-and-modules"></a><span data-ttu-id="eab37-122">Los módulos y tipos de matriz</span><span class="sxs-lookup"><span data-stu-id="eab37-122">Array Types and Modules</span></span>

<span data-ttu-id="eab37-123">El tipo de todas las matrices de F # es el tipo de .NET Framework <xref:System.Array?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="eab37-123">The type of all F# arrays is the .NET Framework type <xref:System.Array?displayProperty=nameWithType>.</span></span> <span data-ttu-id="eab37-124">Por lo tanto, las matrices de F # admiten toda la funcionalidad disponible en <xref:System.Array?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="eab37-124">Therefore, F# arrays support all the functionality available in <xref:System.Array?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="eab37-125">El módulo de biblioteca [ `Microsoft.FSharp.Collections.Array` ](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1) admite operaciones en matrices unidimensionales.</span><span class="sxs-lookup"><span data-stu-id="eab37-125">The library module [`Microsoft.FSharp.Collections.Array`](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1) supports operations on one-dimensional arrays.</span></span> <span data-ttu-id="eab37-126">Los módulos `Array2D`, `Array3D`, y `Array4D` contienen funciones que admiten las operaciones en las matrices de dos, tres y cuatro dimensiones, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="eab37-126">The modules `Array2D`, `Array3D`, and `Array4D` contain functions that support operations on arrays of two, three, and four dimensions, respectively.</span></span> <span data-ttu-id="eab37-127">Puede crear matrices de clasificación superior a 4 mediante el uso de <xref:System.Array?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="eab37-127">You can create arrays of rank greater than four by using <xref:System.Array?displayProperty=nameWithType>.</span></span>

### <a name="simple-functions"></a><span data-ttu-id="eab37-128">Funciones simples</span><span class="sxs-lookup"><span data-stu-id="eab37-128">Simple Functions</span></span>

<span data-ttu-id="eab37-129">[`Array.get`](https://msdn.microsoft.com/library/dd93e85d-7e80-4d76-8de0-b6d45bcf07bc) Obtiene un elemento.</span><span class="sxs-lookup"><span data-stu-id="eab37-129">[`Array.get`](https://msdn.microsoft.com/library/dd93e85d-7e80-4d76-8de0-b6d45bcf07bc) gets an element.</span></span> <span data-ttu-id="eab37-130">[`Array.length`](https://msdn.microsoft.com/library/0d775b6a-4a8f-4bd1-83e5-843b3251725f) indica la longitud de la matriz.</span><span class="sxs-lookup"><span data-stu-id="eab37-130">[`Array.length`](https://msdn.microsoft.com/library/0d775b6a-4a8f-4bd1-83e5-843b3251725f) gives the length of an array.</span></span> <span data-ttu-id="eab37-131">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) establece un elemento en un valor especificado.</span><span class="sxs-lookup"><span data-stu-id="eab37-131">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) sets an element to a specified value.</span></span> <span data-ttu-id="eab37-132">El ejemplo de código siguiente muestra el uso de estas funciones.</span><span class="sxs-lookup"><span data-stu-id="eab37-132">The following code example illustrates the use of these functions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet9.fs)]

<span data-ttu-id="eab37-133">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="eab37-133">The output is as follows.</span></span>

```
0 1 2 3 4 5 6 7 8 9
```

### <a name="functions-that-create-arrays"></a><span data-ttu-id="eab37-134">Funciones que crean matrices</span><span class="sxs-lookup"><span data-stu-id="eab37-134">Functions That Create Arrays</span></span>

<span data-ttu-id="eab37-135">Varias funciones que crean matrices sin necesidad de una matriz existente.</span><span class="sxs-lookup"><span data-stu-id="eab37-135">Several functions create arrays without requiring an existing array.</span></span> <span data-ttu-id="eab37-136">[`Array.empty`](https://msdn.microsoft.com/library/c3694b92-1c16-4c54-9bf2-fe398fadce32) crea una nueva matriz que no contiene ningún elemento.</span><span class="sxs-lookup"><span data-stu-id="eab37-136">[`Array.empty`](https://msdn.microsoft.com/library/c3694b92-1c16-4c54-9bf2-fe398fadce32) creates a new array that does not contain any elements.</span></span> <span data-ttu-id="eab37-137">[`Array.create`](https://msdn.microsoft.com/library/e848c8d6-1142-4080-9727-8dacc26066be) crea una matriz de un tamaño especificado y establece todos los elementos con valores proporcionados.</span><span class="sxs-lookup"><span data-stu-id="eab37-137">[`Array.create`](https://msdn.microsoft.com/library/e848c8d6-1142-4080-9727-8dacc26066be) creates an array of a specified size and sets all the elements to provided values.</span></span> <span data-ttu-id="eab37-138">[`Array.init`](https://msdn.microsoft.com/library/ee898089-63b0-40aa-910c-5ae7e32f6665) crea una matriz, dada una dimensión y una función para generar los elementos.</span><span class="sxs-lookup"><span data-stu-id="eab37-138">[`Array.init`](https://msdn.microsoft.com/library/ee898089-63b0-40aa-910c-5ae7e32f6665) creates an array, given a dimension and a function to generate the elements.</span></span> <span data-ttu-id="eab37-139">[`Array.zeroCreate`](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2) crea una matriz en la que todos los elementos se inicializan en el valor cero para el tipo de la matriz.</span><span class="sxs-lookup"><span data-stu-id="eab37-139">[`Array.zeroCreate`](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2) creates an array in which all the elements are initialized to the zero value for the array's type.</span></span> <span data-ttu-id="eab37-140">El código siguiente muestra estas funciones.</span><span class="sxs-lookup"><span data-stu-id="eab37-140">The following code demonstrates these functions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet91.fs)]

<span data-ttu-id="eab37-141">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="eab37-141">The output is as follows.</span></span>

```
Length of empty array: 0
Area of floats set to 5.0: [|5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0|]
Array of squares: [|0; 1; 4; 9; 16; 25; 36; 49; 64; 81|]
```

<span data-ttu-id="eab37-142">[`Array.copy`](https://msdn.microsoft.com/library/9d0202f1-1ea0-475e-9d66-4f8ccc3c5b5f) crea una nueva matriz que contiene elementos que se copian de una matriz existente.</span><span class="sxs-lookup"><span data-stu-id="eab37-142">[`Array.copy`](https://msdn.microsoft.com/library/9d0202f1-1ea0-475e-9d66-4f8ccc3c5b5f) creates a new array that contains elements that are copied from an existing array.</span></span> <span data-ttu-id="eab37-143">Tenga en cuenta que la copia es una copia superficial, lo que significa que si el tipo de elemento es un tipo de referencia, se copia únicamente la referencia, no el objeto subyacente.</span><span class="sxs-lookup"><span data-stu-id="eab37-143">Note that the copy is a shallow copy, which means that if the element type is a reference type, only the reference is copied, not the underlying object.</span></span> <span data-ttu-id="eab37-144">En el siguiente ejemplo código se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="eab37-144">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet11.fs)]

<span data-ttu-id="eab37-145">La salida del código anterior es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="eab37-145">The output of the preceding code is as follows:</span></span>

```
[|Test1; Test2; |]
[|; Test2; |]
```

<span data-ttu-id="eab37-146">La cadena `Test1` sólo aparece en la primera matriz porque la operación de creación de un nuevo elemento sobrescribe la referencia en `firstArray` pero no afecta a la referencia original a una cadena vacía que aún se encuentra en `secondArray`.</span><span class="sxs-lookup"><span data-stu-id="eab37-146">The string `Test1` appears only in the first array because the operation of creating a new element overwrites the reference in `firstArray` but does not affect the original reference to an empty string that is still present in `secondArray`.</span></span> <span data-ttu-id="eab37-147">La cadena `Test2` aparece en ambas matrices porque la `Insert` operación en el <xref:System.Text.StringBuilder?displayProperty=nameWithType> tipo afecta subyacente <xref:System.Text.StringBuilder?displayProperty=nameWithType> objeto, que se hace referencia en ambas matrices.</span><span class="sxs-lookup"><span data-stu-id="eab37-147">The string `Test2` appears in both arrays because the `Insert` operation on the <xref:System.Text.StringBuilder?displayProperty=nameWithType> type affects the underlying <xref:System.Text.StringBuilder?displayProperty=nameWithType> object, which is referenced in both arrays.</span></span>

<span data-ttu-id="eab37-148">[`Array.sub`](https://msdn.microsoft.com/library/40fb12ba-41d7-4ef0-b33a-56727deeef9d) genera una nueva matriz a partir de un subrango de una matriz.</span><span class="sxs-lookup"><span data-stu-id="eab37-148">[`Array.sub`](https://msdn.microsoft.com/library/40fb12ba-41d7-4ef0-b33a-56727deeef9d) generates a new array from a subrange of an array.</span></span> <span data-ttu-id="eab37-149">Especificar el subrango proporcionando el índice de inicio y la longitud.</span><span class="sxs-lookup"><span data-stu-id="eab37-149">You specify the subrange by providing the starting index and the length.</span></span> <span data-ttu-id="eab37-150">En el código siguiente se muestra cómo usar `Array.sub`.</span><span class="sxs-lookup"><span data-stu-id="eab37-150">The following code demonstrates the use of `Array.sub`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet12.fs)]

<span data-ttu-id="eab37-151">El resultado muestra que la submatriz comienza en el elemento 5 y contiene 10 elementos.</span><span class="sxs-lookup"><span data-stu-id="eab37-151">The output shows that the subarray starts at element 5 and contains 10 elements.</span></span>

```
[|5; 6; 7; 8; 9; 10; 11; 12; 13; 14|]
```
<span data-ttu-id="eab37-152">[`Array.append`](https://msdn.microsoft.com/library/08836310-5036-4474-b9a2-2c73e2293911) crea una nueva matriz combinando dos matrices existentes.</span><span class="sxs-lookup"><span data-stu-id="eab37-152">[`Array.append`](https://msdn.microsoft.com/library/08836310-5036-4474-b9a2-2c73e2293911) creates a new array by combining two existing arrays.</span></span>

<span data-ttu-id="eab37-153">El siguiente código muestra **Array.append**.</span><span class="sxs-lookup"><span data-stu-id="eab37-153">The following code demonstrates **Array.append**.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet13.fs)]

<span data-ttu-id="eab37-154">La salida del código anterior es como sigue.</span><span class="sxs-lookup"><span data-stu-id="eab37-154">The output of the preceding code is as follows.</span></span>

```
[|1; 2; 3; 4; 5; 6|]
```

<span data-ttu-id="eab37-155">[`Array.choose`](https://msdn.microsoft.com/library/f5c8a5e2-637f-44d4-b35c-be96a6618b09) selecciona los elementos de una matriz que se va a incluir en una nueva matriz.</span><span class="sxs-lookup"><span data-stu-id="eab37-155">[`Array.choose`](https://msdn.microsoft.com/library/f5c8a5e2-637f-44d4-b35c-be96a6618b09) selects elements of an array to include in a new array.</span></span> <span data-ttu-id="eab37-156">El siguiente código muestra `Array.choose`.</span><span class="sxs-lookup"><span data-stu-id="eab37-156">The following code demonstrates `Array.choose`.</span></span> <span data-ttu-id="eab37-157">Tenga en cuenta que el tipo de elemento de la matriz no tiene que coincidir con el tipo de valor devuelto en el tipo de opción.</span><span class="sxs-lookup"><span data-stu-id="eab37-157">Note that the element type of the array does not have to match the type of the value returned in the option type.</span></span> <span data-ttu-id="eab37-158">En este ejemplo, el tipo de elemento es `int` y la opción es el resultado de una función polinómica, `elem*elem - 1`, un flotante como número de punto.</span><span class="sxs-lookup"><span data-stu-id="eab37-158">In this example, the element type is `int` and the option is the result of a polynomial function, `elem*elem - 1`, as a floating point number.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet14.fs)]

<span data-ttu-id="eab37-159">La salida del código anterior es como sigue.</span><span class="sxs-lookup"><span data-stu-id="eab37-159">The output of the preceding code is as follows.</span></span>

```
[|3.0; 15.0; 35.0; 63.0; 99.0|]
```

<span data-ttu-id="eab37-160">[`Array.collect`](https://msdn.microsoft.com/library/c3b60c3b-9455-48c9-bc2b-e88f0434342a) ejecuta una función especificada en cada elemento de matriz de una matriz existente y, a continuación, recopila los elementos generados por la función y las combina en una nueva matriz.</span><span class="sxs-lookup"><span data-stu-id="eab37-160">[`Array.collect`](https://msdn.microsoft.com/library/c3b60c3b-9455-48c9-bc2b-e88f0434342a) runs a specified function on each array element of an existing array and then collects the elements generated by the function and combines them into a new array.</span></span> <span data-ttu-id="eab37-161">El siguiente código muestra `Array.collect`.</span><span class="sxs-lookup"><span data-stu-id="eab37-161">The following code demonstrates `Array.collect`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet15.fs)]

<span data-ttu-id="eab37-162">La salida del código anterior es como sigue.</span><span class="sxs-lookup"><span data-stu-id="eab37-162">The output of the preceding code is as follows.</span></span>

```
[|0; 1; 0; 1; 2; 3; 4; 5; 0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10|]
```

<span data-ttu-id="eab37-163">[`Array.concat`](https://msdn.microsoft.com/library/f7219b79-1ec8-4a25-96b1-edbedb358302) toma una secuencia de matrices y las combina en una sola matriz.</span><span class="sxs-lookup"><span data-stu-id="eab37-163">[`Array.concat`](https://msdn.microsoft.com/library/f7219b79-1ec8-4a25-96b1-edbedb358302) takes a sequence of arrays and combines them into a single array.</span></span> <span data-ttu-id="eab37-164">El siguiente código muestra `Array.concat`.</span><span class="sxs-lookup"><span data-stu-id="eab37-164">The following code demonstrates `Array.concat`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet16.fs)]

<span data-ttu-id="eab37-165">La salida del código anterior es como sigue.</span><span class="sxs-lookup"><span data-stu-id="eab37-165">The output of the preceding code is as follows.</span></span>

```
[|(1, 1, 1); (1, 2, 2); (1, 3, 3); (2, 1, 2); (2, 2, 4); (2, 3, 6); (3, 1, 3);
(3, 2, 6); (3, 3, 9)|]
```

<span data-ttu-id="eab37-166">[`Array.filter`](https://msdn.microsoft.com/library/b885b214-47fc-4639-9664-b8c183a39ede) toma una función de condición booleana y genera una nueva matriz que contiene únicamente los elementos de la matriz de entrada para el que la condición es verdadera.</span><span class="sxs-lookup"><span data-stu-id="eab37-166">[`Array.filter`](https://msdn.microsoft.com/library/b885b214-47fc-4639-9664-b8c183a39ede) takes a Boolean condition function and generates a new array that contains only those elements from the input array for which the condition is true.</span></span> <span data-ttu-id="eab37-167">El siguiente código muestra `Array.filter`.</span><span class="sxs-lookup"><span data-stu-id="eab37-167">The following code demonstrates `Array.filter`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet17.fs)]

<span data-ttu-id="eab37-168">La salida del código anterior es como sigue.</span><span class="sxs-lookup"><span data-stu-id="eab37-168">The output of the preceding code is as follows.</span></span>

```
[|2; 4; 6; 8; 10|]
```

<span data-ttu-id="eab37-169">[`Array.rev`](https://msdn.microsoft.com/library/1bbf822c-763b-4794-af21-97d2e48ef709) genera una nueva matriz invirtiendo el orden de una matriz existente.</span><span class="sxs-lookup"><span data-stu-id="eab37-169">[`Array.rev`](https://msdn.microsoft.com/library/1bbf822c-763b-4794-af21-97d2e48ef709) generates a new array by reversing the order of an existing array.</span></span> <span data-ttu-id="eab37-170">El siguiente código muestra `Array.rev`.</span><span class="sxs-lookup"><span data-stu-id="eab37-170">The following code demonstrates `Array.rev`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet18.fs)]  

<span data-ttu-id="eab37-171">La salida del código anterior es como sigue.</span><span class="sxs-lookup"><span data-stu-id="eab37-171">The output of the preceding code is as follows.</span></span>

```
"Hello world!"
```

<span data-ttu-id="eab37-172">Se pueden combinar fácilmente funciones del módulo array que transforman las matrices mediante el operador de canalización (`|>`), como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="eab37-172">You can easily combine functions in the array module that transform arrays by using the pipeline operator (`|>`), as shown in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet19.fs)]

<span data-ttu-id="eab37-173">El resultado es</span><span class="sxs-lookup"><span data-stu-id="eab37-173">The output is</span></span>

```
[|100; 36; 16; 4|]
```

### <a name="multidimensional-arrays"></a><span data-ttu-id="eab37-174">Matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="eab37-174">Multidimensional Arrays</span></span>

<span data-ttu-id="eab37-175">Se puede crear una matriz multidimensional, pero no hay ninguna sintaxis para escribir un literal de matriz multidimensional.</span><span class="sxs-lookup"><span data-stu-id="eab37-175">A multidimensional array can be created, but there is no syntax for writing a multidimensional array literal.</span></span> <span data-ttu-id="eab37-176">Utilice el operador [ `array2D` ](https://msdn.microsoft.com/library/1d52503d-2990-49fc-8fd3-6b0e508aa236) para crear una matriz desde una secuencia de secuencias de elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="eab37-176">Use the operator [`array2D`](https://msdn.microsoft.com/library/1d52503d-2990-49fc-8fd3-6b0e508aa236) to create an array from a sequence of sequences of array elements.</span></span> <span data-ttu-id="eab37-177">Las secuencias pueden ser literales de matriz o lista.</span><span class="sxs-lookup"><span data-stu-id="eab37-177">The sequences can be array or list literals.</span></span> <span data-ttu-id="eab37-178">Por ejemplo, el código siguiente crea una matriz bidimensional.</span><span class="sxs-lookup"><span data-stu-id="eab37-178">For example, the following code creates a two-dimensional array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet20.fs)]

<span data-ttu-id="eab37-179">También puede usar la función [ `Array2D.init` ](https://msdn.microsoft.com/library/9de07e95-bc21-4927-b5b4-08fdec882c7b) para inicializar las matrices de dos dimensiones y otros similares funciones están disponibles para las matrices de tres y cuatro dimensiones.</span><span class="sxs-lookup"><span data-stu-id="eab37-179">You can also use the function [`Array2D.init`](https://msdn.microsoft.com/library/9de07e95-bc21-4927-b5b4-08fdec882c7b) to initialize arrays of two dimensions, and similar functions are available for arrays of three and four dimensions.</span></span> <span data-ttu-id="eab37-180">Estas funciones toman una función que se usa para crear los elementos.</span><span class="sxs-lookup"><span data-stu-id="eab37-180">These functions take a function that is used to create the elements.</span></span> <span data-ttu-id="eab37-181">Para crear una matriz bidimensional que contiene elementos establecidos en un valor inicial en lugar de especificar una función, utilice el [ `Array2D.create` ](https://msdn.microsoft.com/library/36c9d980-b241-4a20-bc64-bcfa0205d804) función, que también está disponible para las matrices de hasta cuatro dimensiones.</span><span class="sxs-lookup"><span data-stu-id="eab37-181">To create a two-dimensional array that contains elements set to an initial value instead of specifying a function, use the [`Array2D.create`](https://msdn.microsoft.com/library/36c9d980-b241-4a20-bc64-bcfa0205d804) function, which is also available for arrays up to four dimensions.</span></span> <span data-ttu-id="eab37-182">El ejemplo de código siguiente se muestra primero cómo crear una matriz de matrices que contienen los elementos deseados y, a continuación, usa `Array2D.init` para generar la matriz bidimensional deseada.</span><span class="sxs-lookup"><span data-stu-id="eab37-182">The following code example first shows how to create an array of arrays that contain the desired elements, and then uses `Array2D.init` to generate the desired two-dimensional array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet21.fs)]

<span data-ttu-id="eab37-183">Se admite la indexación y la segmentación de sintaxis de matriz para matrices con un rango 4.</span><span class="sxs-lookup"><span data-stu-id="eab37-183">Array indexing and slicing syntax is supported for arrays up to rank 4.</span></span> <span data-ttu-id="eab37-184">Cuando se especifica un índice en varias dimensiones, use comas para separar los índices, como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="eab37-184">When you specify an index in multiple dimensions, you use commas to separate the indexes, as illustrated in the following code example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet22.fs)]

<span data-ttu-id="eab37-185">El tipo de una matriz bidimensional se escribe como `<type>[,]` (por ejemplo, `int[,]`, `double[,]`), y el tipo de una matriz tridimensional se escribe como `<type>[,,]`, y así sucesivamente para las matrices de más dimensiones.</span><span class="sxs-lookup"><span data-stu-id="eab37-185">The type of a two-dimensional array is written out as `<type>[,]` (for example, `int[,]`, `double[,]`), and the type of a three-dimensional array is written as `<type>[,,]`, and so on for arrays of higher dimensions.</span></span>

<span data-ttu-id="eab37-186">Solo un subconjunto de las funciones disponibles para las matrices unidimensionales también está disponible para las matrices multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="eab37-186">Only a subset of the functions available for one-dimensional arrays is also available for multidimensional arrays.</span></span> <span data-ttu-id="eab37-187">Para obtener más información, consulte [ `Collections.Array Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array-module-%5bfsharp%5d), [ `Collections.Array2D Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array2d-module-%5bfsharp%5d), [ `Collections.Array3D Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array3d-module-%5bfsharp%5d), y [ `Collections.Array4D Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array4d-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="eab37-187">For more information, see [`Collections.Array Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array-module-%5bfsharp%5d), [`Collections.Array2D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array2d-module-%5bfsharp%5d), [`Collections.Array3D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array3d-module-%5bfsharp%5d), and [`Collections.Array4D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array4d-module-%5bfsharp%5d).</span></span>

### <a name="array-slicing-and-multidimensional-arrays"></a><span data-ttu-id="eab37-188">Fragmentación de matriz y las matrices multidimensionales</span><span class="sxs-lookup"><span data-stu-id="eab37-188">Array Slicing and Multidimensional Arrays</span></span>

<span data-ttu-id="eab37-189">En una matriz bidimensional (una matriz), puede extraer una matriz más especificando intervalos y utilizando un carácter comodín (`*`) para especificar filas o columnas completas.</span><span class="sxs-lookup"><span data-stu-id="eab37-189">In a two-dimensional array (a matrix), you can extract a sub-matrix by specifying ranges and using a wildcard (`*`) character to specify whole rows or columns.</span></span>

```fsharp
/ Get rows 1 to N from an NxM matrix (returns a matrix):
matrix.[1.., *]

// Get rows 1 to 3 from a matrix (returns a matrix):
matrix.[1..3, *]

// Get columns 1 to 3 from a matrix (returns a matrix):
matrix.[*, 1..3]

// Get a 3x3 submatrix:
matrix.[1..3, 1..3]
```

<span data-ttu-id="eab37-190">A partir de F # 3.1, puede descomponer una matriz multidimensional en submatrices de la dimensión igual o inferior.</span><span class="sxs-lookup"><span data-stu-id="eab37-190">As of F# 3.1, you can decompose a multidimensional array into subarrays of the same or lower dimension.</span></span> <span data-ttu-id="eab37-191">Por ejemplo, puede obtener un vector de una matriz mediante la especificación de una sola fila o columna.</span><span class="sxs-lookup"><span data-stu-id="eab37-191">For example, you can obtain a vector from a matrix by specifying a single row or column.</span></span>

```fsharp
// Get row 3 from a matrix as a vector:
matrix.[3, *]

// Get column 3 from a matrix as a vector:
matrix.[*, 3]
```

<span data-ttu-id="eab37-192">Puede utilizar esta sintaxis de fragmentación para tipos que implementan los operadores de acceso de elemento y sobrecargado `GetSlice` métodos.</span><span class="sxs-lookup"><span data-stu-id="eab37-192">You can use this slicing syntax for types that implement the element access operators and overloaded `GetSlice` methods.</span></span> <span data-ttu-id="eab37-193">Por ejemplo, el código siguiente crea un tipo de matriz que contiene la matriz 2D de F #, implementa una propiedad de elemento para proporcionar compatibilidad para la indización de matrices e implementa tres versiones de `GetSlice`.</span><span class="sxs-lookup"><span data-stu-id="eab37-193">For example, the following code creates a Matrix type that wraps the F# 2D array, implements an Item property to provide support for array indexing, and implements three versions of `GetSlice`.</span></span> <span data-ttu-id="eab37-194">Si este código puede usar como plantilla para los tipos de matriz, puede usar todas las operaciones de segmentación que se describe en esta sección.</span><span class="sxs-lookup"><span data-stu-id="eab37-194">If you can use this code as a template for your matrix types, you can use all the slicing operations that this section describes.</span></span>

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
    printfn "%A" submatrix

    let firstRow = test1.[0,*]
    let secondRow = test1.[1,*]
    let firstCol = test1.[*,0]
    printfn "%A" firstCol
```

### <a name="boolean-functions-on-arrays"></a><span data-ttu-id="eab37-195">Funciones booleanas para matrices</span><span class="sxs-lookup"><span data-stu-id="eab37-195">Boolean Functions on Arrays</span></span>

<span data-ttu-id="eab37-196">Las funciones [ `Array.exists` ](https://msdn.microsoft.com/library/8e47ad6c-c065-4876-8cb4-ec960ec3e5c9) y [ `Array.exists2` ](https://msdn.microsoft.com/library/2e384a6a-f99d-4e23-b677-250ffbc1dd8e) comprueban los elementos de uno o dos matrices, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="eab37-196">The functions [`Array.exists`](https://msdn.microsoft.com/library/8e47ad6c-c065-4876-8cb4-ec960ec3e5c9) and [`Array.exists2`](https://msdn.microsoft.com/library/2e384a6a-f99d-4e23-b677-250ffbc1dd8e) test elements in either one or two arrays, respectively.</span></span> <span data-ttu-id="eab37-197">Estas funciones toman una función de prueba y devuelven `true` si hay un elemento (o par de elementos para `Array.exists2`) que cumple la condición.</span><span class="sxs-lookup"><span data-stu-id="eab37-197">These functions take a test function and return `true` if there is an element (or element pair for `Array.exists2`) that satisfies the condition.</span></span>

<span data-ttu-id="eab37-198">El código siguiente muestra el uso de `Array.exists` y `Array.exists2`.</span><span class="sxs-lookup"><span data-stu-id="eab37-198">The following code demonstrates the use of `Array.exists` and `Array.exists2`.</span></span> <span data-ttu-id="eab37-199">En estos ejemplos, se crean nuevas funciones aplicando solo uno de los argumentos, en estos casos, el argumento de función.</span><span class="sxs-lookup"><span data-stu-id="eab37-199">In these examples, new functions are created by applying only one of the arguments, in these cases, the function argument.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet23.fs)]

<span data-ttu-id="eab37-200">La salida del código anterior es como sigue.</span><span class="sxs-lookup"><span data-stu-id="eab37-200">The output of the preceding code is as follows.</span></span>

```
true
false
false
true
```

<span data-ttu-id="eab37-201">De forma similar, la función [ `Array.forall` ](https://msdn.microsoft.com/library/d88f2cd0-fa7f-45cf-ac15-31eae9086cc4) comprueba una matriz para determinar si cada elemento satisface una condición booleana.</span><span class="sxs-lookup"><span data-stu-id="eab37-201">Similarly, the function [`Array.forall`](https://msdn.microsoft.com/library/d88f2cd0-fa7f-45cf-ac15-31eae9086cc4) tests an array to determine whether every element satisfies a Boolean condition.</span></span> <span data-ttu-id="eab37-202">La variación [ `Array.forall2` ](https://msdn.microsoft.com/library/c68f61a1-030c-4024-b705-c4768b6c96b9) hace lo mismo mediante el uso de una función booleana que implica a los elementos de dos matrices de igual longitud.</span><span class="sxs-lookup"><span data-stu-id="eab37-202">The variation [`Array.forall2`](https://msdn.microsoft.com/library/c68f61a1-030c-4024-b705-c4768b6c96b9) does the same thing by using a Boolean function that involves elements of two arrays of equal length.</span></span> <span data-ttu-id="eab37-203">El código siguiente muestra el uso de estas funciones.</span><span class="sxs-lookup"><span data-stu-id="eab37-203">The following code illustrates the use of these functions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet24.fs)]

<span data-ttu-id="eab37-204">La salida de estos ejemplos es como sigue.</span><span class="sxs-lookup"><span data-stu-id="eab37-204">The output for these examples is as follows.</span></span>

```
false
true
true
false
```

### <a name="searching-arrays"></a><span data-ttu-id="eab37-205">Buscar en las matrices</span><span class="sxs-lookup"><span data-stu-id="eab37-205">Searching Arrays</span></span>

<span data-ttu-id="eab37-206">[`Array.find`](https://msdn.microsoft.com/library/db6d920a-de19-4520-85a4-d83de77c1b33) toma una función booleana y devuelve el primer elemento para el cual la función devuelve `true`, o se produce un <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> si se encuentra ningún elemento que satisface la condición.</span><span class="sxs-lookup"><span data-stu-id="eab37-206">[`Array.find`](https://msdn.microsoft.com/library/db6d920a-de19-4520-85a4-d83de77c1b33) takes a Boolean function and returns the first element for which the function returns `true`, or raises a <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> if no element that satisfies the condition is found.</span></span> <span data-ttu-id="eab37-207">[`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) es similar a `Array.find`, excepto en que devuelve el índice del elemento en lugar del propio elemento.</span><span class="sxs-lookup"><span data-stu-id="eab37-207">[`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) is like `Array.find`, except that it returns the index of the element instead of the element itself.</span></span>

<span data-ttu-id="eab37-208">El siguiente código utiliza `Array.find` y `Array.findIndex` para buscar un número que es un cuadrado perfecto y un cubo perfecto.</span><span class="sxs-lookup"><span data-stu-id="eab37-208">The following code uses `Array.find` and `Array.findIndex` to locate a number that is both a perfect square and perfect cube.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet25.fs)]

<span data-ttu-id="eab37-209">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="eab37-209">The output is as follows.</span></span>

```
The first element that is both a square and a cube is 64 and its index is 62.
```

<span data-ttu-id="eab37-210">[`Array.tryFind`](https://msdn.microsoft.com/library/7bd65f6c-df77-454c-ac3a-6f7baecec9d9) es similar a `Array.find`, salvo que su resultado es un tipo de opción y devuelve `None` si se encuentra ningún elemento.</span><span class="sxs-lookup"><span data-stu-id="eab37-210">[`Array.tryFind`](https://msdn.microsoft.com/library/7bd65f6c-df77-454c-ac3a-6f7baecec9d9) is like `Array.find`, except that its result is an option type, and it returns `None` if no element is found.</span></span> <span data-ttu-id="eab37-211">`Array.tryFind` debe usarse en lugar de `Array.find` cuando no se sabe si es un elemento coincidente en la matriz.</span><span class="sxs-lookup"><span data-stu-id="eab37-211">`Array.tryFind` should be used instead of `Array.find` when you do not know whether a matching element is in the array.</span></span> <span data-ttu-id="eab37-212">De forma similar, [ `Array.tryFindIndex` ](https://msdn.microsoft.com/library/da82f7fe-95e9-4fd5-a924-cd3c9d10618a) es similar a [ `Array.findIndex` ](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) , salvo que el tipo de opción es el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="eab37-212">Similarly, [`Array.tryFindIndex`](https://msdn.microsoft.com/library/da82f7fe-95e9-4fd5-a924-cd3c9d10618a) is like [`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) except that the option type is the return value.</span></span> <span data-ttu-id="eab37-213">Si se encuentra ningún elemento, la opción es `None`.</span><span class="sxs-lookup"><span data-stu-id="eab37-213">If no element is found, the option is `None`.</span></span>

<span data-ttu-id="eab37-214">En el código siguiente se muestra cómo usar `Array.tryFind`.</span><span class="sxs-lookup"><span data-stu-id="eab37-214">The following code demonstrates the use of `Array.tryFind`.</span></span> <span data-ttu-id="eab37-215">Este código depende del código anterior.</span><span class="sxs-lookup"><span data-stu-id="eab37-215">This code depends on the previous code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet26.fs)]

<span data-ttu-id="eab37-216">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="eab37-216">The output is as follows.</span></span>

```
Found an element: 1
Found an element: 729
```

<span data-ttu-id="eab37-217">Use [ `Array.tryPick` ](https://msdn.microsoft.com/library/72d45f85-037b-43a9-97fd-17239f72713e) cuando se necesita transformar un elemento además de buscarlo.</span><span class="sxs-lookup"><span data-stu-id="eab37-217">Use [`Array.tryPick`](https://msdn.microsoft.com/library/72d45f85-037b-43a9-97fd-17239f72713e) when you need to transform an element in addition to finding it.</span></span> <span data-ttu-id="eab37-218">El resultado es el primer elemento para el que la función devuelve el elemento transformado como un valor de opción o `None` si no se encuentra ningún elemento.</span><span class="sxs-lookup"><span data-stu-id="eab37-218">The result is the first element for which the function returns the transformed element as an option value, or `None` if no such element is found.</span></span>

<span data-ttu-id="eab37-219">En el código siguiente se muestra el uso de `Array.tryPick`.</span><span class="sxs-lookup"><span data-stu-id="eab37-219">The following code shows the use of `Array.tryPick`.</span></span> <span data-ttu-id="eab37-220">En este caso, en lugar de una expresión lambda, se definen varias funciones auxiliares locales para simplificar el código.</span><span class="sxs-lookup"><span data-stu-id="eab37-220">In this case, instead of a lambda expression, several local helper functions are defined to simplify the code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet27.fs)]

<span data-ttu-id="eab37-221">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="eab37-221">The output is as follows.</span></span>

```
Found an element 1 with square root 1 and cube root 1.
Found an element 64 with square root 8 and cube root 4.
Found an element 729 with square root 27 and cube root 9.
Found an element 4096 with square root 64 and cube root 16.
```

### <a name="performing-computations-on-arrays"></a><span data-ttu-id="eab37-222">Realizar cálculos con matrices</span><span class="sxs-lookup"><span data-stu-id="eab37-222">Performing Computations on Arrays</span></span>

<span data-ttu-id="eab37-223">El [ `Array.average` ](https://msdn.microsoft.com/library/7029f2b9-91ea-41cb-be1b-466a5a0db20e) función devuelve el promedio de cada elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="eab37-223">The [`Array.average`](https://msdn.microsoft.com/library/7029f2b9-91ea-41cb-be1b-466a5a0db20e) function returns the average of each element in an array.</span></span> <span data-ttu-id="eab37-224">Se limita a los tipos de elemento que admiten la división exacta por un entero, que incluye los tipos de punto flotante, pero los tipos enteros.</span><span class="sxs-lookup"><span data-stu-id="eab37-224">It is limited to element types that support exact division by an integer, which includes floating point types but not integral types.</span></span> <span data-ttu-id="eab37-225">El [ `Array.averageBy` ](https://msdn.microsoft.com/library/e9d64609-06a3-48f0-bc07-226ab0f85c54) función devuelve el promedio de los resultados de llamar a una función en cada elemento.</span><span class="sxs-lookup"><span data-stu-id="eab37-225">The [`Array.averageBy`](https://msdn.microsoft.com/library/e9d64609-06a3-48f0-bc07-226ab0f85c54) function returns the average of the results of calling a function on each element.</span></span> <span data-ttu-id="eab37-226">Para una matriz de tipo entero, puede usar `Array.averageBy` y hacer que la función flotante convertir cada elemento de tipo para el cálculo de punto.</span><span class="sxs-lookup"><span data-stu-id="eab37-226">For an array of integral type, you can use `Array.averageBy` and have the function convert each element to a floating point type for the computation.</span></span>

<span data-ttu-id="eab37-227">Use [ `Array.max` ](https://msdn.microsoft.com/library/f03fbda0-fce6-40e2-a85d-79c9d81f710b) o [ `Array.min` ](https://msdn.microsoft.com/library/d6b3da5f-bac0-4355-9846-4b72d95bc3fd) para obtener el elemento máximo o mínimo, si lo admite el tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="eab37-227">Use [`Array.max`](https://msdn.microsoft.com/library/f03fbda0-fce6-40e2-a85d-79c9d81f710b) or [`Array.min`](https://msdn.microsoft.com/library/d6b3da5f-bac0-4355-9846-4b72d95bc3fd) to get the maximum or minimum element, if the element type supports it.</span></span> <span data-ttu-id="eab37-228">De forma similar, [ `Array.maxBy` ](https://msdn.microsoft.com/library/18dbe7c5-482e-4766-8e01-12a76f847045) y [ `Array.minBy` ](https://msdn.microsoft.com/library/24091583-be78-4cc9-9fab-de6d7506af4f) permiten que una función que se va a ejecutar en primer lugar, quizás para transformar un tipo que admite la comparación.</span><span class="sxs-lookup"><span data-stu-id="eab37-228">Similarly, [`Array.maxBy`](https://msdn.microsoft.com/library/18dbe7c5-482e-4766-8e01-12a76f847045) and [`Array.minBy`](https://msdn.microsoft.com/library/24091583-be78-4cc9-9fab-de6d7506af4f) allow a function to be executed first, perhaps to transform to a type that supports comparison.</span></span>

<span data-ttu-id="eab37-229">[`Array.sum`](https://msdn.microsoft.com/library/4ffdb8c8-cd94-4b0b-9e5c-a7c9c17963c2) Agrega los elementos de una matriz, y [ `Array.sumBy` ](https://msdn.microsoft.com/library/41698ba6-1adc-4169-8cc5-7a0e3f8de56b) llama a una función en cada elemento y suma los resultados.</span><span class="sxs-lookup"><span data-stu-id="eab37-229">[`Array.sum`](https://msdn.microsoft.com/library/4ffdb8c8-cd94-4b0b-9e5c-a7c9c17963c2) adds the elements of an array, and [`Array.sumBy`](https://msdn.microsoft.com/library/41698ba6-1adc-4169-8cc5-7a0e3f8de56b) calls a function on each element and adds the results together.</span></span>

<span data-ttu-id="eab37-230">Para ejecutar una función en cada elemento de una matriz sin almacenar los valores devueltos, utilice [ `Array.iter` ](https://msdn.microsoft.com/library/94eba0f1-ecd7-459f-b89f-ed2a2923e516).</span><span class="sxs-lookup"><span data-stu-id="eab37-230">To execute a function on each element in an array without storing the return values, use [`Array.iter`](https://msdn.microsoft.com/library/94eba0f1-ecd7-459f-b89f-ed2a2923e516).</span></span> <span data-ttu-id="eab37-231">Para usar una función de que impliquen dos matrices de igual longitud [ `Array.iter2` ](https://msdn.microsoft.com/library/018aa9b9-f186-4142-be8a-a62462794fdc).</span><span class="sxs-lookup"><span data-stu-id="eab37-231">For a function involving two arrays of equal length, use [`Array.iter2`](https://msdn.microsoft.com/library/018aa9b9-f186-4142-be8a-a62462794fdc).</span></span> <span data-ttu-id="eab37-232">Si también tiene que mantener una matriz de los resultados de la función, utilice [ `Array.map` ](https://msdn.microsoft.com/library/38cbe824-0480-47be-85fd-df3afdd97a45) o [ `Array.map2` ](https://msdn.microsoft.com/library/bb7aafe8-4a1f-45b9-92fc-1af9eafbea5c), que actúa sobre dos matrices a la vez.</span><span class="sxs-lookup"><span data-stu-id="eab37-232">If you also need to keep an array of the results of the function, use [`Array.map`](https://msdn.microsoft.com/library/38cbe824-0480-47be-85fd-df3afdd97a45) or [`Array.map2`](https://msdn.microsoft.com/library/bb7aafe8-4a1f-45b9-92fc-1af9eafbea5c), which operates on two arrays at a time.</span></span>

<span data-ttu-id="eab37-233">Las variaciones [ `Array.iteri` ](https://msdn.microsoft.com/library/8bbe2ed4-ada7-4906-ac3e-cb09f9db6486) y [ `Array.iteri2` ](https://msdn.microsoft.com/library/c041b91f-6080-45b7-867b-2ed983a90405) permite que el índice del elemento que se va a participar en el cálculo; lo mismo puede decirse de [ `Array.mapi` ](https://msdn.microsoft.com/library/f7e45994-b0a1-49e6-8fb5-5641cea8fde4) y [ `Array.mapi2` ](https://msdn.microsoft.com/library/5edb33d2-47da-44e1-9290-40c00c47d5b0).</span><span class="sxs-lookup"><span data-stu-id="eab37-233">The variations [`Array.iteri`](https://msdn.microsoft.com/library/8bbe2ed4-ada7-4906-ac3e-cb09f9db6486) and [`Array.iteri2`](https://msdn.microsoft.com/library/c041b91f-6080-45b7-867b-2ed983a90405) allow the index of the element to be involved in the computation; the same is true for [`Array.mapi`](https://msdn.microsoft.com/library/f7e45994-b0a1-49e6-8fb5-5641cea8fde4) and [`Array.mapi2`](https://msdn.microsoft.com/library/5edb33d2-47da-44e1-9290-40c00c47d5b0).</span></span>

<span data-ttu-id="eab37-234">Las funciones [ `Array.fold` ](https://msdn.microsoft.com/library/5ed9dd3b-3694-4567-94d0-fd9a24474e09), [ `Array.foldBack` ](https://msdn.microsoft.com/library/1121a453-dead-4711-a0ca-cc147752989c), [ `Array.reduce` ](https://msdn.microsoft.com/library/fd62a985-89fe-4f49-a9d4-0c808ac6749d), [ `Array.reduceBack` ](https://msdn.microsoft.com/library/4fdd4cbe-2238-4c5c-b286-597a7e9036f9), [ `Array.scan` ](https://msdn.microsoft.com/library/f6893608-9146-450d-9ebb-a0016803fbb0), y [ `Array.scanBack` ](https://msdn.microsoft.com/library/7610f406-7a5c-41db-a0ca-8e2a2a4826ad) ejecutar algoritmos que usan todos los elementos de una matriz.</span><span class="sxs-lookup"><span data-stu-id="eab37-234">The functions [`Array.fold`](https://msdn.microsoft.com/library/5ed9dd3b-3694-4567-94d0-fd9a24474e09), [`Array.foldBack`](https://msdn.microsoft.com/library/1121a453-dead-4711-a0ca-cc147752989c), [`Array.reduce`](https://msdn.microsoft.com/library/fd62a985-89fe-4f49-a9d4-0c808ac6749d), [`Array.reduceBack`](https://msdn.microsoft.com/library/4fdd4cbe-2238-4c5c-b286-597a7e9036f9), [`Array.scan`](https://msdn.microsoft.com/library/f6893608-9146-450d-9ebb-a0016803fbb0), and [`Array.scanBack`](https://msdn.microsoft.com/library/7610f406-7a5c-41db-a0ca-8e2a2a4826ad) execute algorithms that involve all the elements of an array.</span></span> <span data-ttu-id="eab37-235">De forma similar, las variaciones [ `Array.fold2` ](https://msdn.microsoft.com/library/5c845087-d041-476e-8cc4-53ae6849ef79) y [ `Array.foldBack2` ](https://msdn.microsoft.com/library/aa51b405-df20-4c51-9998-a6530f7db862) realizar cálculos sobre dos matrices.</span><span class="sxs-lookup"><span data-stu-id="eab37-235">Similarly, the variations [`Array.fold2`](https://msdn.microsoft.com/library/5c845087-d041-476e-8cc4-53ae6849ef79) and [`Array.foldBack2`](https://msdn.microsoft.com/library/aa51b405-df20-4c51-9998-a6530f7db862) perform computations on two arrays.</span></span>

<span data-ttu-id="eab37-236">Estas funciones para realizar cálculos se corresponden con las funciones del mismo nombre en el [List (módulo)](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span><span class="sxs-lookup"><span data-stu-id="eab37-236">These functions for performing computations correspond to the functions of the same name in the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span> <span data-ttu-id="eab37-237">Para obtener ejemplos de uso, consulte [enumera](lists.md).</span><span class="sxs-lookup"><span data-stu-id="eab37-237">For usage examples, see [Lists](lists.md).</span></span>

### <a name="modifying-arrays"></a><span data-ttu-id="eab37-238">Modificar matrices</span><span class="sxs-lookup"><span data-stu-id="eab37-238">Modifying Arrays</span></span>

<span data-ttu-id="eab37-239">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) establece un elemento en un valor especificado.</span><span class="sxs-lookup"><span data-stu-id="eab37-239">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) sets an element to a specified value.</span></span> <span data-ttu-id="eab37-240">[`Array.fill`](https://msdn.microsoft.com/library/c83c9886-81d9-44f9-a195-61c7b87f7df2) establece un intervalo de elementos de una matriz en un valor especificado.</span><span class="sxs-lookup"><span data-stu-id="eab37-240">[`Array.fill`](https://msdn.microsoft.com/library/c83c9886-81d9-44f9-a195-61c7b87f7df2) sets a range of elements in an array to a specified value.</span></span> <span data-ttu-id="eab37-241">El código siguiente proporciona un ejemplo de `Array.fill`.</span><span class="sxs-lookup"><span data-stu-id="eab37-241">The following code provides an example of `Array.fill`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet28.fs)]

<span data-ttu-id="eab37-242">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="eab37-242">The output is as follows.</span></span>

```
[|1; 2; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 23; 24; 25|]
```

<span data-ttu-id="eab37-243">Puede usar [ `Array.blit` ](https://msdn.microsoft.com/library/675e13e4-7fb9-4e0d-a5be-a112830de667) para copiar una subsección de una matriz en otra matriz.</span><span class="sxs-lookup"><span data-stu-id="eab37-243">You can use [`Array.blit`](https://msdn.microsoft.com/library/675e13e4-7fb9-4e0d-a5be-a112830de667) to copy a subsection of one array to another array.</span></span>

### <a name="converting-to-and-from-other-types"></a><span data-ttu-id="eab37-244">Convertir a y desde otros tipos</span><span class="sxs-lookup"><span data-stu-id="eab37-244">Converting to and from Other Types</span></span>

<span data-ttu-id="eab37-245">[`Array.ofList`](https://msdn.microsoft.com/library/e7225239-f561-45a4-b0b5-69a1cdcae78b) crea una matriz de una lista.</span><span class="sxs-lookup"><span data-stu-id="eab37-245">[`Array.ofList`](https://msdn.microsoft.com/library/e7225239-f561-45a4-b0b5-69a1cdcae78b) creates an array from a list.</span></span> <span data-ttu-id="eab37-246">[`Array.ofSeq`](https://msdn.microsoft.com/library/6bedf5e0-4b22-46da-b09c-6aa09eff220c) crea una matriz a partir de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="eab37-246">[`Array.ofSeq`](https://msdn.microsoft.com/library/6bedf5e0-4b22-46da-b09c-6aa09eff220c) creates an array from a sequence.</span></span> <span data-ttu-id="eab37-247">[`Array.toList`](https://msdn.microsoft.com/library/4deff724-0be4-4688-92e7-9d67a1097786) y [ `Array.toSeq` ](https://msdn.microsoft.com/library/ac28dbab-406c-4fe0-ab08-c1ce5e247af4) convertir a estos otros tipos de colección del tipo de matriz.</span><span class="sxs-lookup"><span data-stu-id="eab37-247">[`Array.toList`](https://msdn.microsoft.com/library/4deff724-0be4-4688-92e7-9d67a1097786) and [`Array.toSeq`](https://msdn.microsoft.com/library/ac28dbab-406c-4fe0-ab08-c1ce5e247af4) convert to these other collection types from the array type.</span></span>

### <a name="sorting-arrays"></a><span data-ttu-id="eab37-248">Ordenar matrices</span><span class="sxs-lookup"><span data-stu-id="eab37-248">Sorting Arrays</span></span>

<span data-ttu-id="eab37-249">Use [ `Array.sort` ](https://msdn.microsoft.com/library/c6679075-e7eb-463c-9be5-c89be140c312) para ordenar una matriz mediante la función de comparación genérica.</span><span class="sxs-lookup"><span data-stu-id="eab37-249">Use [`Array.sort`](https://msdn.microsoft.com/library/c6679075-e7eb-463c-9be5-c89be140c312) to sort an array by using the generic comparison function.</span></span> <span data-ttu-id="eab37-250">Use [ `Array.sortBy` ](https://msdn.microsoft.com/library/144498dc-091d-4575-a229-c0bcbd61426b) especificar una función que genera un valor, conoce como un *clave*, para ordenar mediante la función de comparación genérica en la clave.</span><span class="sxs-lookup"><span data-stu-id="eab37-250">Use [`Array.sortBy`](https://msdn.microsoft.com/library/144498dc-091d-4575-a229-c0bcbd61426b) to specify a function that generates a value, referred to as a *key*, to sort by using the generic comparison function on the key.</span></span> <span data-ttu-id="eab37-251">Use [ `Array.sortWith` ](https://msdn.microsoft.com/library/699d3638-4244-4f42-8496-45f53d43ce95) si desea proporcionar una función de comparación personalizada.</span><span class="sxs-lookup"><span data-stu-id="eab37-251">Use [`Array.sortWith`](https://msdn.microsoft.com/library/699d3638-4244-4f42-8496-45f53d43ce95) if you want to provide a custom comparison function.</span></span> <span data-ttu-id="eab37-252">`Array.sort`, `Array.sortBy`, y `Array.sortWith` todas devuelven la matriz ordenada como una nueva matriz.</span><span class="sxs-lookup"><span data-stu-id="eab37-252">`Array.sort`, `Array.sortBy`, and `Array.sortWith` all return the sorted array as a new array.</span></span> <span data-ttu-id="eab37-253">Las variaciones [ `Array.sortInPlace` ](https://msdn.microsoft.com/library/36f39947-8a88-4823-9e9b-e9d838d292e0), [ `Array.sortInPlaceBy` ](https://msdn.microsoft.com/library/7fb9d2dd-d461-4c67-8b43-b5c59fc12c3f), y [ `Array.sortInPlaceWith` ](https://msdn.microsoft.com/library/454f9e11-972d-47a6-a854-8031cb0c7b0b) modifican la matriz existente en lugar de devolver una nueva.</span><span class="sxs-lookup"><span data-stu-id="eab37-253">The variations [`Array.sortInPlace`](https://msdn.microsoft.com/library/36f39947-8a88-4823-9e9b-e9d838d292e0), [`Array.sortInPlaceBy`](https://msdn.microsoft.com/library/7fb9d2dd-d461-4c67-8b43-b5c59fc12c3f), and [`Array.sortInPlaceWith`](https://msdn.microsoft.com/library/454f9e11-972d-47a6-a854-8031cb0c7b0b) modify the existing array instead of returning a new one.</span></span>

### <a name="arrays-and-tuples"></a><span data-ttu-id="eab37-254">Matrices y tuplas</span><span class="sxs-lookup"><span data-stu-id="eab37-254">Arrays and Tuples</span></span>

<span data-ttu-id="eab37-255">Las funciones [ `Array.zip` ](https://msdn.microsoft.com/library/23e086b8-b266-4db2-8b68-e88e6a8e2187) y [ `Array.unzip` ](https://msdn.microsoft.com/library/a529b47c-2e2b-4f79-ad44-c578432d2f48) convertir matrices de tuplas de dos elementos en tuplas de matrices y viceversa.</span><span class="sxs-lookup"><span data-stu-id="eab37-255">The functions [`Array.zip`](https://msdn.microsoft.com/library/23e086b8-b266-4db2-8b68-e88e6a8e2187) and [`Array.unzip`](https://msdn.microsoft.com/library/a529b47c-2e2b-4f79-ad44-c578432d2f48) convert arrays of tuple pairs to tuples of arrays and vice versa.</span></span> <span data-ttu-id="eab37-256">[`Array.zip3`](https://msdn.microsoft.com/library/1745744a-d2ca-4c3e-b825-3f15d9f4000d) y [ `Array.unzip3` ](https://msdn.microsoft.com/library/bc3e6db0-f334-444f-8c30-813942880677) son similares, salvo que funcionan con tuplas de tres elementos o tuplas de tres matrices.</span><span class="sxs-lookup"><span data-stu-id="eab37-256">[`Array.zip3`](https://msdn.microsoft.com/library/1745744a-d2ca-4c3e-b825-3f15d9f4000d) and [`Array.unzip3`](https://msdn.microsoft.com/library/bc3e6db0-f334-444f-8c30-813942880677) are similar except that they work with tuples of three elements or tuples of three arrays.</span></span>

## <a name="parallel-computations-on-arrays"></a><span data-ttu-id="eab37-257">Cálculos en paralelo en las matrices</span><span class="sxs-lookup"><span data-stu-id="eab37-257">Parallel Computations on Arrays</span></span>

<span data-ttu-id="eab37-258">El módulo [ `Array.Parallel` ](https://msdn.microsoft.com/library/60f30b77-5af4-4050-9a5c-bcdb3f5cbb09) contiene funciones para realizar cálculos en paralelo en las matrices.</span><span class="sxs-lookup"><span data-stu-id="eab37-258">The module [`Array.Parallel`](https://msdn.microsoft.com/library/60f30b77-5af4-4050-9a5c-bcdb3f5cbb09) contains functions for performing parallel computations on arrays.</span></span> <span data-ttu-id="eab37-259">Este módulo no está disponible en las aplicaciones que tienen como destino versiones de .NET Framework anteriores a la versión 4.</span><span class="sxs-lookup"><span data-stu-id="eab37-259">This module is not available in applications that target versions of the .NET Framework prior to version 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="eab37-260">Vea también</span><span class="sxs-lookup"><span data-stu-id="eab37-260">See also</span></span>

- [<span data-ttu-id="eab37-261">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="eab37-261">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="eab37-262">F # Tipos de</span><span class="sxs-lookup"><span data-stu-id="eab37-262">F#; Types</span></span>](fsharp-types.md)
