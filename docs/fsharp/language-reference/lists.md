---
title: Listas
description: 'Obtenga información sobre las listas de F #, una serie ordenada e inmutable de elementos del mismo tipo.'
ms.date: 08/13/2020
ms.openlocfilehash: 16d7195039d25cf63630f5cc3be6563b1bf45c44
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559172"
---
# <a name="lists"></a><span data-ttu-id="3ec92-103">Listas</span><span class="sxs-lookup"><span data-stu-id="3ec92-103">Lists</span></span>

<span data-ttu-id="3ec92-104">En F#, una lista es una serie ordenada e inmutable de elementos del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="3ec92-104">A list in F# is an ordered, immutable series of elements of the same type.</span></span> <span data-ttu-id="3ec92-105">Para realizar operaciones básicas en listas, use las funciones del [módulo de lista](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span><span class="sxs-lookup"><span data-stu-id="3ec92-105">To perform basic operations on lists, use the functions in the [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span>

## <a name="creating-and-initializing-lists"></a><span data-ttu-id="3ec92-106">Crear e inicializar listas</span><span class="sxs-lookup"><span data-stu-id="3ec92-106">Creating and Initializing Lists</span></span>

<span data-ttu-id="3ec92-107">Para definir una lista, puede enumerar explícitamente los elementos, separados por punto y coma y escritos entre corchetes, tal y como se muestra en la línea de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="3ec92-107">You can define a list by explicitly listing out the elements, separated by semicolons and enclosed in square brackets, as shown in the following line of code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1301.fs)]

<span data-ttu-id="3ec92-108">También puede insertar saltos de línea entre los elementos, en cuyo caso el signo de punto y coma es opcional.</span><span class="sxs-lookup"><span data-stu-id="3ec92-108">You can also put line breaks between elements, in which case the semicolons are optional.</span></span> <span data-ttu-id="3ec92-109">La última sintaxis produce un código más legible cuando las expresiones de inicialización de elementos son más largas o si quiere incluir un comentario para cada elemento.</span><span class="sxs-lookup"><span data-stu-id="3ec92-109">The latter syntax can result in more readable code when the element initialization expressions are longer, or when you want to include a comment for each element.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13011.fs)]

<span data-ttu-id="3ec92-110">Normalmente, todos los elementos de lista deben ser del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="3ec92-110">Normally, all list elements must be the same type.</span></span> <span data-ttu-id="3ec92-111">Una excepción es que una lista en la cual los elementos se han especificado para que sean de un tipo base puede tener elementos que sean de tipos derivados.</span><span class="sxs-lookup"><span data-stu-id="3ec92-111">An exception is that a list in which the elements are specified to be a base type can have elements that are derived types.</span></span> <span data-ttu-id="3ec92-112">Por lo tanto, lo siguiente es aceptable, porque tanto `Button` como `CheckBox` derivan de `Control`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-112">Thus the following is acceptable, because both `Button` and `CheckBox` derive from `Control`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13012.fs)]

<span data-ttu-id="3ec92-113">También puede definir elementos de lista usando un intervalo indicado por enteros separados por el operador de intervalo (`..`), tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="3ec92-113">You can also define list elements by using a range indicated by integers separated by the range operator (`..`), as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1302.fs)]

<span data-ttu-id="3ec92-114">Una lista vacía se especifica por un par de corchetes con nada entre ellos.</span><span class="sxs-lookup"><span data-stu-id="3ec92-114">An empty list is specified by a pair of square brackets with nothing in between them.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1304.fs)]

<span data-ttu-id="3ec92-115">También puede usar una expresión de secuencia para crear una lista.</span><span class="sxs-lookup"><span data-stu-id="3ec92-115">You can also use a sequence expression to create a list.</span></span> <span data-ttu-id="3ec92-116">Vea [expresiones de secuencia](sequences.md#sequence-expressions) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3ec92-116">See [Sequence Expressions](sequences.md#sequence-expressions) for more information.</span></span> <span data-ttu-id="3ec92-117">Por ejemplo, el código siguiente crea una lista de cuadrados de enteros, de 1 a 10.</span><span class="sxs-lookup"><span data-stu-id="3ec92-117">For example, the following code creates a list of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1303.fs)]

## <a name="operators-for-working-with-lists"></a><span data-ttu-id="3ec92-118">Operadores para trabajar con listas</span><span class="sxs-lookup"><span data-stu-id="3ec92-118">Operators for Working with Lists</span></span>

<span data-ttu-id="3ec92-119">Puede asociar elementos a una lista usando el operador `::` (cons).</span><span class="sxs-lookup"><span data-stu-id="3ec92-119">You can attach elements to a list by using the `::` (cons) operator.</span></span> <span data-ttu-id="3ec92-120">Si `list1` es `[2; 3; 4]`, el código siguiente crea `list2` como `[100; 2; 3; 4]`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-120">If `list1` is `[2; 3; 4]`, the following code creates `list2` as `[100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1305.fs)]

<span data-ttu-id="3ec92-121">Para concatenar listas que tengan tipos compatibles, puede usar el operador `@`, como en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="3ec92-121">You can concatenate lists that have compatible types by using the `@` operator, as in the following code.</span></span> <span data-ttu-id="3ec92-122">Si `list1` es `[2; 3; 4]` y `list2` es `[100; 2; 3; 4]`, este código crea `list3` como `[2; 3; 4; 100; 2; 3; 4]`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-122">If `list1` is `[2; 3; 4]` and `list2` is `[100; 2; 3; 4]`, this code creates `list3` as `[2; 3; 4; 100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1306.fs)]

<span data-ttu-id="3ec92-123">Las funciones para realizar operaciones en listas están disponibles en el [módulo de lista](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span><span class="sxs-lookup"><span data-stu-id="3ec92-123">Functions for performing operations on lists are available in the [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span>

<span data-ttu-id="3ec92-124">Como en F# las listas son inmutables, las operaciones de modificación generan nuevas listas en lugar de modificar las existentes.</span><span class="sxs-lookup"><span data-stu-id="3ec92-124">Because lists in F# are immutable, any modifying operations generate new lists instead of modifying existing lists.</span></span>

<span data-ttu-id="3ec92-125">Las listas de F # se implementan como listas vinculadas individualmente, lo que significa que las operaciones que tienen acceso solo al encabezado de la lista son O (1) y el acceso a los elementos es O (*n*).</span><span class="sxs-lookup"><span data-stu-id="3ec92-125">Lists in F# are implemented as singly linked lists, which means that operations that access only the head of the list are O(1), and element access is O(*n*).</span></span>

## <a name="properties"></a><span data-ttu-id="3ec92-126">Propiedades</span><span class="sxs-lookup"><span data-stu-id="3ec92-126">Properties</span></span>

<span data-ttu-id="3ec92-127">El tipo de lista admite las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="3ec92-127">The list type supports the following properties:</span></span>

|<span data-ttu-id="3ec92-128">Propiedad</span><span class="sxs-lookup"><span data-stu-id="3ec92-128">Property</span></span>|<span data-ttu-id="3ec92-129">Tipo</span><span class="sxs-lookup"><span data-stu-id="3ec92-129">Type</span></span>|<span data-ttu-id="3ec92-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ec92-130">Description</span></span>|
|--------|----|-----------|
|[<span data-ttu-id="3ec92-131">Head</span><span class="sxs-lookup"><span data-stu-id="3ec92-131">Head</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head)|`'T`|<span data-ttu-id="3ec92-132">El primer elemento.</span><span class="sxs-lookup"><span data-stu-id="3ec92-132">The first element.</span></span>|
|[<span data-ttu-id="3ec92-133">Vacía</span><span class="sxs-lookup"><span data-stu-id="3ec92-133">Empty</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Empty)|`'T list`|<span data-ttu-id="3ec92-134">Propiedad estática que devuelve una lista vacía del tipo apropiado.</span><span class="sxs-lookup"><span data-stu-id="3ec92-134">A static property that returns an empty list of the appropriate type.</span></span>|
|[<span data-ttu-id="3ec92-135">IsEmpty</span><span class="sxs-lookup"><span data-stu-id="3ec92-135">IsEmpty</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#IsEmpty)|`bool`|<span data-ttu-id="3ec92-136">`true` si la lista no tiene ningún elemento.</span><span class="sxs-lookup"><span data-stu-id="3ec92-136">`true` if the list has no elements.</span></span>|
|[<span data-ttu-id="3ec92-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="3ec92-137">Item</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Item)|`'T`|<span data-ttu-id="3ec92-138">Elemento en el índice especificado (base cero).</span><span class="sxs-lookup"><span data-stu-id="3ec92-138">The element at the specified index (zero-based).</span></span>|
|[<span data-ttu-id="3ec92-139">Longitud</span><span class="sxs-lookup"><span data-stu-id="3ec92-139">Length</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Length)|`int`|<span data-ttu-id="3ec92-140">Número de elementos.</span><span class="sxs-lookup"><span data-stu-id="3ec92-140">The number of elements.</span></span>|
|[<span data-ttu-id="3ec92-141">Tail</span><span class="sxs-lookup"><span data-stu-id="3ec92-141">Tail</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail)|`'T list`|<span data-ttu-id="3ec92-142">La lista sin el primer elemento.</span><span class="sxs-lookup"><span data-stu-id="3ec92-142">The list without the first element.</span></span>|

<span data-ttu-id="3ec92-143">Los siguientes son algunos ejemplos de cómo usar estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="3ec92-143">Following are some examples of using these properties.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1307.fs)]

## <a name="using-lists"></a><span data-ttu-id="3ec92-144">Usar listas</span><span class="sxs-lookup"><span data-stu-id="3ec92-144">Using Lists</span></span>

<span data-ttu-id="3ec92-145">Programar con listas permite realizar operaciones complejas con una pequeña cantidad de código.</span><span class="sxs-lookup"><span data-stu-id="3ec92-145">Programming with lists enables you to perform complex operations with a small amount of code.</span></span> <span data-ttu-id="3ec92-146">En esta sección se describen las operaciones comunes en las listas que son importantes para la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="3ec92-146">This section describes common operations on lists that are important to functional programming.</span></span>

### <a name="recursion-with-lists"></a><span data-ttu-id="3ec92-147">Recursión con listas</span><span class="sxs-lookup"><span data-stu-id="3ec92-147">Recursion with Lists</span></span>

<span data-ttu-id="3ec92-148">Las listas están especialmente indicadas para las técnicas de programación recursiva.</span><span class="sxs-lookup"><span data-stu-id="3ec92-148">Lists are uniquely suited to recursive programming techniques.</span></span> <span data-ttu-id="3ec92-149">Tomemos una operación que deba realizarse en todos los elementos de una lista.</span><span class="sxs-lookup"><span data-stu-id="3ec92-149">Consider an operation that must be performed on every element of a list.</span></span> <span data-ttu-id="3ec92-150">Puede hacerlo recursivamente ejecutando una operación en el encabezado de la lista y, después, devolviendo la cola de la lista (que es una lista más pequeña formada por la lista original sin el primer elemento) de nuevo al siguiente nivel de recursión.</span><span class="sxs-lookup"><span data-stu-id="3ec92-150">You can do this recursively by operating on the head of the list and then passing the tail of the list, which is a smaller list that consists of the original list without the first element, back again to the next level of recursion.</span></span>

<span data-ttu-id="3ec92-151">Para escribir una función recursiva de este estilo, se usa el operador cons (`::`) en coincidencia de patrones, lo que permite separar el encabezado de una lista de la cola.</span><span class="sxs-lookup"><span data-stu-id="3ec92-151">To write such a recursive function, you use the cons operator (`::`) in pattern matching, which enables you to separate the head of a list from the tail.</span></span>

<span data-ttu-id="3ec92-152">En el ejemplo de código siguiente se muestra cómo usar la coincidencia de patrones para implementar una función recursiva que realice operaciones en una lista.</span><span class="sxs-lookup"><span data-stu-id="3ec92-152">The following code example shows how to use pattern matching to implement a recursive function that performs operations on a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13071.fs)]

<span data-ttu-id="3ec92-153">El código anterior funciona bien para listas pequeñas, pero en listas mayores podría desbordar la pila.</span><span class="sxs-lookup"><span data-stu-id="3ec92-153">The previous code works well for small lists, but for larger lists, it could overflow the stack.</span></span> <span data-ttu-id="3ec92-154">El código siguiente mejora este código usando un argumento acumulador, una técnica estándar para trabajar con funciones recursivas.</span><span class="sxs-lookup"><span data-stu-id="3ec92-154">The following code improves on this code by using an accumulator argument, a standard technique for working with recursive functions.</span></span> <span data-ttu-id="3ec92-155">El uso del argumento acumulador hace que la función sea recursiva en la cola, lo que ahorra espacio en la pila.</span><span class="sxs-lookup"><span data-stu-id="3ec92-155">The use of the accumulator argument makes the function tail recursive, which saves stack space.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13072.fs)]

<span data-ttu-id="3ec92-156">La función `RemoveAllMultiples` es una función recursiva que toma dos listas.</span><span class="sxs-lookup"><span data-stu-id="3ec92-156">The function `RemoveAllMultiples` is a recursive function that takes two lists.</span></span> <span data-ttu-id="3ec92-157">La primera lista contiene los números cuyos múltiplos se van a quitar, y la segunda es la lista de la que se van a quitar los números.</span><span class="sxs-lookup"><span data-stu-id="3ec92-157">The first list contains the numbers whose multiples will be removed, and the second list is the list from which to remove the numbers.</span></span> <span data-ttu-id="3ec92-158">El código del ejemplo siguiente usa esta función recursiva para eliminar de una lista todos los números que no sean primos, dejando como resultado una lista de números primos.</span><span class="sxs-lookup"><span data-stu-id="3ec92-158">The code in the following example uses this recursive function to eliminate all the non-prime numbers from a list, leaving a list of prime numbers as the result.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1308.fs)]

<span data-ttu-id="3ec92-159">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ec92-159">The output is as follows:</span></span>

```console
Primes Up To 100:
[2; 3; 5; 7; 11; 13; 17; 19; 23; 29; 31; 37; 41; 43; 47; 53; 59; 61; 67; 71; 73; 79; 83; 89; 97]
```

## <a name="module-functions"></a><span data-ttu-id="3ec92-160">Funciones del módulo</span><span class="sxs-lookup"><span data-stu-id="3ec92-160">Module Functions</span></span>

<span data-ttu-id="3ec92-161">El [módulo de lista](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html) proporciona funciones que tienen acceso a los elementos de una lista.</span><span class="sxs-lookup"><span data-stu-id="3ec92-161">The [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html) provides functions that access the elements of a list.</span></span> <span data-ttu-id="3ec92-162">El elemento de encabezado es la manera más rápida y sencilla de acceder.</span><span class="sxs-lookup"><span data-stu-id="3ec92-162">The head element is the fastest and easiest to access.</span></span> <span data-ttu-id="3ec92-163">Use el [encabezado](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head) de propiedad o la función de módulo [List. Head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#head).</span><span class="sxs-lookup"><span data-stu-id="3ec92-163">Use the property [Head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head) or the module function [List.head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#head).</span></span> <span data-ttu-id="3ec92-164">Puede tener acceso al final de una lista mediante la propiedad [tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail) o la función [List. tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tail) .</span><span class="sxs-lookup"><span data-stu-id="3ec92-164">You can access the tail of a list by using the [Tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail) property or the [List.tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tail) function.</span></span> <span data-ttu-id="3ec92-165">Para buscar un elemento por índice, use la función [List. nth](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#nth) .</span><span class="sxs-lookup"><span data-stu-id="3ec92-165">To find an element by index, use the [List.nth](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#nth) function.</span></span> <span data-ttu-id="3ec92-166">`List.nth` atraviesa la lista.</span><span class="sxs-lookup"><span data-stu-id="3ec92-166">`List.nth` traverses the list.</span></span> <span data-ttu-id="3ec92-167">Por lo tanto, es O (*n*).</span><span class="sxs-lookup"><span data-stu-id="3ec92-167">Therefore, it is O(*n*).</span></span> <span data-ttu-id="3ec92-168">Si su código usa `List.nth` con frecuencia, quizás quiera considerar la posibilidad de usar una matriz en lugar de una lista.</span><span class="sxs-lookup"><span data-stu-id="3ec92-168">If your code uses `List.nth` frequently, you might want to consider using an array instead of a list.</span></span> <span data-ttu-id="3ec92-169">El acceso a elementos en las matrices es O(1).</span><span class="sxs-lookup"><span data-stu-id="3ec92-169">Element access in arrays is O(1).</span></span>

### <a name="boolean-operations-on-lists"></a><span data-ttu-id="3ec92-170">Operaciones booleanas en listas</span><span class="sxs-lookup"><span data-stu-id="3ec92-170">Boolean Operations on Lists</span></span>

<span data-ttu-id="3ec92-171">La función [List. IsEmpty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#isEmpty) determina si una lista tiene elementos.</span><span class="sxs-lookup"><span data-stu-id="3ec92-171">The [List.isEmpty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#isEmpty) function determines whether a list has any elements.</span></span>

<span data-ttu-id="3ec92-172">La función [List. exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists) aplica una prueba booleana a los elementos de una lista y devuelve `true` si algún elemento cumple la prueba.</span><span class="sxs-lookup"><span data-stu-id="3ec92-172">The [List.exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists) function applies a Boolean test to elements of a list and returns `true` if any element satisfies the test.</span></span> <span data-ttu-id="3ec92-173">[List. exists2 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists2) es similar pero funciona en pares sucesivos de elementos de dos listas.</span><span class="sxs-lookup"><span data-stu-id="3ec92-173">[List.exists2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists2) is similar but operates on successive pairs of elements in two lists.</span></span>

<span data-ttu-id="3ec92-174">En el código siguiente se muestra cómo usar `List.exists`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-174">The following code demonstrates the use of `List.exists`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet1.fs)]

<span data-ttu-id="3ec92-175">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ec92-175">The output is as follows:</span></span>

```console
For list [0; 1; 2; 3], contains zero is true
```

<span data-ttu-id="3ec92-176">El siguiente ejemplo muestra el uso de `List.exists2`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-176">The following example demonstrates the use of `List.exists2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet2.fs)]

<span data-ttu-id="3ec92-177">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ec92-177">The output is as follows:</span></span>

```console
Lists [1; 2; 3; 4; 5] and [5; 4; 3; 2; 1] have at least one equal element at the same position.
```

<span data-ttu-id="3ec92-178">Puede usar [List. ForAll](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall) si desea comprobar si todos los elementos de una lista cumplen una condición.</span><span class="sxs-lookup"><span data-stu-id="3ec92-178">You can use [List.forall](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall) if you want to test whether all the elements of a list meet a condition.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet3.fs)]

<span data-ttu-id="3ec92-179">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ec92-179">The output is as follows:</span></span>

```console
true
false
```

<span data-ttu-id="3ec92-180">De forma similar, [List. forall2 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall2) determina si todos los elementos de las posiciones correspondientes de dos listas satisfacen una expresión booleana que implica cada par de elementos.</span><span class="sxs-lookup"><span data-stu-id="3ec92-180">Similarly, [List.forall2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall2) determines whether all elements in the corresponding positions in two lists satisfy a Boolean expression that involves each pair of elements.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet4.fs)]

<span data-ttu-id="3ec92-181">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ec92-181">The output is as follows:</span></span>

```console
true
false
```

### <a name="sort-operations-on-lists"></a><span data-ttu-id="3ec92-182">Operaciones de ordenación en listas</span><span class="sxs-lookup"><span data-stu-id="3ec92-182">Sort Operations on Lists</span></span>

<span data-ttu-id="3ec92-183">Las funciones [List. Sort](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sort), [List. sortBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortBy)y [List. sortWith (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortWith) ordenan las listas.</span><span class="sxs-lookup"><span data-stu-id="3ec92-183">The [List.sort](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sort), [List.sortBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortBy), and [List.sortWith](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortWith) functions sort lists.</span></span> <span data-ttu-id="3ec92-184">La función de ordenación determina cuál de estas tres funciones se usará.</span><span class="sxs-lookup"><span data-stu-id="3ec92-184">The sorting function determines which of these three functions to use.</span></span> <span data-ttu-id="3ec92-185">`List.sort` usa una comparación genérica predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3ec92-185">`List.sort` uses default generic comparison.</span></span> <span data-ttu-id="3ec92-186">La comparación genérica usa operadores globales basados en la función de comparación genérica para comparar valores.</span><span class="sxs-lookup"><span data-stu-id="3ec92-186">Generic comparison uses global operators based on the generic compare function to compare values.</span></span> <span data-ttu-id="3ec92-187">Funciona de forma eficaz con una amplia variedad de tipos de elemento, como tipos numéricos simples, tuplas, registros, uniones discriminadas, listas, matrices y cualquier tipo que implemente `System.IComparable`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-187">It works efficiently with a wide variety of element types, such as simple numeric types, tuples, records, discriminated unions, lists, arrays, and any type that implements `System.IComparable`.</span></span> <span data-ttu-id="3ec92-188">Para los tipos que implementan `System.IComparable`, la comparación genérica usa la función `System.IComparable.CompareTo()`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-188">For types that implement `System.IComparable`, generic comparison uses the `System.IComparable.CompareTo()` function.</span></span> <span data-ttu-id="3ec92-189">La comparación genérica también trabaja con cadenas, pero usa una ordenación independiente de la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="3ec92-189">Generic comparison also works with strings, but uses a culture-independent sorting order.</span></span> <span data-ttu-id="3ec92-190">La comparación genérica no se debe usar en tipos no admitidos, como los tipos de función.</span><span class="sxs-lookup"><span data-stu-id="3ec92-190">Generic comparison should not be used on unsupported types, such as function types.</span></span> <span data-ttu-id="3ec92-191">Además, el rendimiento de la comparación genérica predeterminada es mejor para tipos estructurados pequeños; para los tipos estructurados mayores que deben compararse y ordenarse con frecuencia, considere la posibilidad de implementar `System.IComparable` y de proporcionar una implementación eficaz del método `System.IComparable.CompareTo()`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-191">Also, the performance of the default generic comparison is best for small structured types; for larger structured types that need to be compared and sorted frequently, consider implementing `System.IComparable` and providing an efficient implementation of the `System.IComparable.CompareTo()` method.</span></span>

<span data-ttu-id="3ec92-192">`List.sortBy` toma una función que devuelve un valor que se usa como criterio de ordenación, y `List.sortWith` toma una función de comparación como argumento.</span><span class="sxs-lookup"><span data-stu-id="3ec92-192">`List.sortBy` takes a function that returns a value that is used as the sort criterion, and `List.sortWith` takes a comparison function as an argument.</span></span> <span data-ttu-id="3ec92-193">Estas dos últimas funciones son útiles cuando se trabaja con tipos que no permiten la comparación, o cuando la comparación requiere semánticas de comparación más complejas, como es el caso de las cadenas que tienen en cuenta la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="3ec92-193">These latter two functions are useful when you are working with types that do not support comparison, or when the comparison requires more complex comparison semantics, as in the case of culture-aware strings.</span></span>

<span data-ttu-id="3ec92-194">El siguiente ejemplo muestra el uso de `List.sort`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-194">The following example demonstrates the use of `List.sort`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet5.fs)]

<span data-ttu-id="3ec92-195">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ec92-195">The output is as follows:</span></span>

```console
[-2; 1; 4; 5; 8]
```

<span data-ttu-id="3ec92-196">El siguiente ejemplo muestra el uso de `List.sortBy`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-196">The following example demonstrates the use of `List.sortBy`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet6.fs)]

<span data-ttu-id="3ec92-197">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ec92-197">The output is as follows:</span></span>

```console
[1; -2; 4; 5; 8]
```

<span data-ttu-id="3ec92-198">El siguiente ejemplo muestra el uso de `List.sortWith`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-198">The next example demonstrates the use of `List.sortWith`.</span></span> <span data-ttu-id="3ec92-199">En este ejemplo, la función de comparación personalizada `compareWidgets` se usa para comparar primero un campo de un tipo personalizado, y después otro cuando los valores del primer campo son iguales.</span><span class="sxs-lookup"><span data-stu-id="3ec92-199">In this example, the custom comparison function `compareWidgets` is used to first compare one field of a custom type, and then another when the values of the first field are equal.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet7.fs)]

<span data-ttu-id="3ec92-200">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ec92-200">The output is as follows:</span></span>

```console
[{ID = 92;
Rev = 1;}; {ID = 92;
Rev = 1;}; {ID = 100;
Rev = 2;}; {ID = 100;
Rev = 5;}; {ID = 110;
Rev = 1;}]
```

### <a name="search-operations-on-lists"></a><span data-ttu-id="3ec92-201">Operaciones de búsqueda en listas</span><span class="sxs-lookup"><span data-stu-id="3ec92-201">Search Operations on Lists</span></span>

<span data-ttu-id="3ec92-202">Se admiten numerosas operaciones de búsqueda en las listas.</span><span class="sxs-lookup"><span data-stu-id="3ec92-202">Numerous search operations are supported for lists.</span></span> <span data-ttu-id="3ec92-203">La más sencilla, [List. Find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#find), permite buscar el primer elemento que coincide con una condición determinada.</span><span class="sxs-lookup"><span data-stu-id="3ec92-203">The simplest, [List.find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#find), enables you to find the first element that matches a given condition.</span></span>

<span data-ttu-id="3ec92-204">El ejemplo de código siguiente muestra el uso de `List.find` para buscar el primer número que es divisible por 5 en una lista.</span><span class="sxs-lookup"><span data-stu-id="3ec92-204">The following code example demonstrates the use of `List.find` to find the first number that is divisible by 5 in a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet8.fs)]

<span data-ttu-id="3ec92-205">El resultado es 5.</span><span class="sxs-lookup"><span data-stu-id="3ec92-205">The result is 5.</span></span>

<span data-ttu-id="3ec92-206">Si los elementos se deben transformar primero, llame a [List. Pick](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#pick), que toma una función que devuelve una opción y busca el primer valor de opción que sea `Some(x)` .</span><span class="sxs-lookup"><span data-stu-id="3ec92-206">If the elements must be transformed first, call [List.pick](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#pick), which takes a function that returns an option, and looks for the first option value that is `Some(x)`.</span></span> <span data-ttu-id="3ec92-207">En lugar de devolver el elemento, `List.pick` devuelve el resultado `x`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-207">Instead of returning the element, `List.pick` returns the result `x`.</span></span> <span data-ttu-id="3ec92-208">Si no se encuentra ningún elemento coincidente, `List.pick` activa `System.Collections.Generic.KeyNotFoundException`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-208">If no matching element is found, `List.pick` throws `System.Collections.Generic.KeyNotFoundException`.</span></span> <span data-ttu-id="3ec92-209">En el código siguiente se muestra el uso de `List.pick`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-209">The following code shows the use of `List.pick`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet9.fs)]

<span data-ttu-id="3ec92-210">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ec92-210">The output is as follows:</span></span>

```console
"b"
```

<span data-ttu-id="3ec92-211">Otro grupo de operaciones de búsqueda, [List. tryFind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFind) y funciones relacionadas, devuelven un valor de opción.</span><span class="sxs-lookup"><span data-stu-id="3ec92-211">Another group of search operations, [List.tryFind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFind) and related functions, return an option value.</span></span> <span data-ttu-id="3ec92-212">La función `List.tryFind` devuelve el primer elemento de una lista que cumple una condición si ese elemento existe, pero el valor de opción `None` si no.</span><span class="sxs-lookup"><span data-stu-id="3ec92-212">The `List.tryFind` function returns the first element of a list that satisfies a condition if such an element exists, but the option value `None` if not.</span></span> <span data-ttu-id="3ec92-213">La variación [List. tryfindindex (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFindIndex) devuelve el índice del elemento, si se encuentra uno, en lugar del propio elemento.</span><span class="sxs-lookup"><span data-stu-id="3ec92-213">The variation [List.tryFindIndex](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFindIndex) returns the index of the element, if one is found, rather than the element itself.</span></span> <span data-ttu-id="3ec92-214">Estas funciones quedan reflejadas en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="3ec92-214">These functions are illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet10.fs)]

<span data-ttu-id="3ec92-215">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ec92-215">The output is as follows:</span></span>

```console
The first even value is 22.
The first even value is at position 8.
```

### <a name="arithmetic-operations-on-lists"></a><span data-ttu-id="3ec92-216">Operaciones aritméticas en listas</span><span class="sxs-lookup"><span data-stu-id="3ec92-216">Arithmetic Operations on Lists</span></span>

<span data-ttu-id="3ec92-217">Las operaciones aritméticas comunes, como SUM y Average, se integran en el [módulo List](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span><span class="sxs-lookup"><span data-stu-id="3ec92-217">Common arithmetic operations such as sum and average are built into the [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span> <span data-ttu-id="3ec92-218">Para trabajar con [List. SUM](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sum), el tipo de elemento de lista debe admitir el `+` operador y tener un valor de cero.</span><span class="sxs-lookup"><span data-stu-id="3ec92-218">To work with [List.sum](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sum), the list element type must support the `+` operator and have a zero value.</span></span> <span data-ttu-id="3ec92-219">Todos los tipos aritmético integrados cumplen estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="3ec92-219">All built-in arithmetic types satisfy these conditions.</span></span> <span data-ttu-id="3ec92-220">Para trabajar con [List. Average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#average), el tipo de elemento debe admitir la división sin resto, lo que excluye los tipos enteros, pero permite tipos de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="3ec92-220">To work with [List.average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#average), the element type must support division without a remainder, which excludes integral types but allows for floating point types.</span></span> <span data-ttu-id="3ec92-221">Las funciones [List. sumBy (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sumBy) y [List. averageBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#averageBy) toman una función como parámetro, y los resultados de esta función se usan para calcular los valores de la suma o el promedio.</span><span class="sxs-lookup"><span data-stu-id="3ec92-221">The [List.sumBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sumBy) and [List.averageBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#averageBy) functions take a function as a parameter, and this function's results are used to calculate the values for the sum or average.</span></span>

<span data-ttu-id="3ec92-222">En el código siguiente se muestra cómo usar `List.sum`, `List.sumBy` y `List.average`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-222">The following code demonstrates the use of `List.sum`, `List.sumBy`, and `List.average`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet11.fs)]

<span data-ttu-id="3ec92-223">El resultado es `1.000000`</span><span class="sxs-lookup"><span data-stu-id="3ec92-223">The output is `1.000000`.</span></span>

<span data-ttu-id="3ec92-224">En el código siguiente se muestra el uso de `List.averageBy`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-224">The following code shows the use of `List.averageBy`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet12.fs)]

<span data-ttu-id="3ec92-225">El resultado es `5.5`</span><span class="sxs-lookup"><span data-stu-id="3ec92-225">The output is `5.5`.</span></span>

### <a name="lists-and-tuples"></a><span data-ttu-id="3ec92-226">Listas y tuplas</span><span class="sxs-lookup"><span data-stu-id="3ec92-226">Lists and Tuples</span></span>

<span data-ttu-id="3ec92-227">Las listas que contienen tuplas se pueden manipular con las funciones zip y unzip.</span><span class="sxs-lookup"><span data-stu-id="3ec92-227">Lists that contain tuples can be manipulated by zip and unzip functions.</span></span> <span data-ttu-id="3ec92-228">Estas funciones combinan dos listas de valores únicos en una lista de tuplas o separan una lista de tuplas en dos listas de valores únicos.</span><span class="sxs-lookup"><span data-stu-id="3ec92-228">These functions combine two lists of single values into one list of tuples or separate one list of tuples into two lists of single values.</span></span> <span data-ttu-id="3ec92-229">La función [List.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip) más sencilla toma dos listas de elementos únicos y genera una sola lista de pares de tupla.</span><span class="sxs-lookup"><span data-stu-id="3ec92-229">The simplest [List.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip) function takes two lists of single elements and produces a single list of tuple pairs.</span></span> <span data-ttu-id="3ec92-230">Otra versión, [List.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip3), toma tres listas de elementos únicos y genera una sola lista de tuplas que tienen tres elementos.</span><span class="sxs-lookup"><span data-stu-id="3ec92-230">Another version, [List.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip3), takes three lists of single elements and produces a single list of tuples that have three elements.</span></span> <span data-ttu-id="3ec92-231">En el siguiente ejemplo de código se muestra el uso de `List.zip`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-231">The following code example demonstrates the use of `List.zip`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet13.fs)]

<span data-ttu-id="3ec92-232">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ec92-232">The output is as follows:</span></span>

```console
[(1, -1); (2, -2); (3; -3)]
```

<span data-ttu-id="3ec92-233">En el siguiente ejemplo de código se muestra el uso de `List.zip3`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-233">The following code example demonstrates the use of `List.zip3`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet14.fs)]

<span data-ttu-id="3ec92-234">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ec92-234">The output is as follows:</span></span>

```console
[(1, -1, 0); (2, -2, 0); (3, -3, 0)]
```

<span data-ttu-id="3ec92-235">Las versiones de unzip correspondientes, [List. unzip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip) y [List. unzip3 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3), toman listas de tuplas y devuelven listas en una tupla, donde la primera lista contiene todos los elementos que estaban en primer lugar en cada tupla, y la segunda lista contiene el segundo elemento de cada tupla, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="3ec92-235">The corresponding unzip versions, [List.unzip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip) and [List.unzip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3), take lists of tuples and return lists in a tuple, where the first list contains all the elements that were first in each tuple, and the second list contains the second element of each tuple, and so on.</span></span>

<span data-ttu-id="3ec92-236">En el ejemplo de código siguiente se muestra el uso de [List. unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).</span><span class="sxs-lookup"><span data-stu-id="3ec92-236">The following code example demonstrates the use of [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet15.fs)]

<span data-ttu-id="3ec92-237">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ec92-237">The output is as follows:</span></span>

```console
([1; 3], [2; 4])
[1; 3] [2; 4]
```

<span data-ttu-id="3ec92-238">En el ejemplo de código siguiente se muestra el uso de [List. unzip3 (](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4).</span><span class="sxs-lookup"><span data-stu-id="3ec92-238">The following code example demonstrates the use of [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet16.fs)]

<span data-ttu-id="3ec92-239">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ec92-239">The output is as follows:</span></span>

```console
([1; 4], [2; 5], [3; 6])
```

### <a name="operating-on-list-elements"></a><span data-ttu-id="3ec92-240">Operar en elementos de lista</span><span class="sxs-lookup"><span data-stu-id="3ec92-240">Operating on List Elements</span></span>

<span data-ttu-id="3ec92-241">F# admite diferentes operaciones en los elementos de lista.</span><span class="sxs-lookup"><span data-stu-id="3ec92-241">F# supports a variety of operations on list elements.</span></span> <span data-ttu-id="3ec92-242">La más sencilla es [List. ITER](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter), que le permite llamar a una función en cada elemento de una lista.</span><span class="sxs-lookup"><span data-stu-id="3ec92-242">The simplest is [List.iter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter), which enables you to call a function on every element of a list.</span></span> <span data-ttu-id="3ec92-243">Las variaciones incluyen [List. iter2 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter2), que permite realizar una operación en elementos de dos listas, [List. ITERI](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri), que es como, a `List.iter` excepción de que el índice de cada elemento se pasa como argumento a la función a la que se llama para cada elemento y [List. iteri2 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri2), que es una combinación de la funcionalidad de `List.iter2` y `List.iteri` .</span><span class="sxs-lookup"><span data-stu-id="3ec92-243">Variations include [List.iter2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter2), which enables you to perform an operation on elements of two lists, [List.iteri](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri), which is like `List.iter` except that the index of each element is passed as an argument to the function that is called for each element, and [List.iteri2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri2), which is a combination of the functionality of `List.iter2` and `List.iteri`.</span></span> <span data-ttu-id="3ec92-244">En el siguiente ejemplo de código se muestran estas funciones.</span><span class="sxs-lookup"><span data-stu-id="3ec92-244">The following code example illustrates these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet17.fs)]

<span data-ttu-id="3ec92-245">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ec92-245">The output is as follows:</span></span>

```console
List.iter: element is 1
List.iter: element is 2
List.iter: element is 3
List.iteri: element 0 is 1
List.iteri: element 1 is 2
List.iteri: element 2 is 3
List.iter2: elements are 1 4
List.iter2: elements are 2 5
List.iter2: elements are 3 6
List.iteri2: element 0 of list1 is 1; element 0 of list2 is 4
List.iteri2: element 1 of list1 is 2; element 1 of list2 is 5
List.iteri2: element 2 of list1 is 3; element 2 of list2 is 6
```

<span data-ttu-id="3ec92-246">Otra función que se usa con frecuencia que transforma elementos de lista es [List. map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map), que permite aplicar una función a cada elemento de una lista y colocar todos los resultados en una nueva lista.</span><span class="sxs-lookup"><span data-stu-id="3ec92-246">Another frequently used function that transforms list elements is [List.map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map), which enables you to apply a function to each element of a list and put all the results into a new list.</span></span> <span data-ttu-id="3ec92-247">[List. MAP2 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map2) y [List. map3 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map3) son variaciones que toman varias listas.</span><span class="sxs-lookup"><span data-stu-id="3ec92-247">[List.map2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map2) and [List.map3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map3) are variations that take multiple lists.</span></span> <span data-ttu-id="3ec92-248">También puede usar [List. MAPI](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi) y [List. mapi2 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi2)si, además del elemento, la función debe pasar el índice de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="3ec92-248">You can also use [List.mapi](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi) and [List.mapi2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi2), if, in addition to the element, the function needs to be passed the index of each element.</span></span> <span data-ttu-id="3ec92-249">La única diferencia entre `List.mapi2` y `List.mapi` es que `List.mapi2` trabaja con dos listas.</span><span class="sxs-lookup"><span data-stu-id="3ec92-249">The only difference between `List.mapi2` and `List.mapi` is that `List.mapi2` works with two lists.</span></span> <span data-ttu-id="3ec92-250">En el ejemplo siguiente se muestra [List. map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map).</span><span class="sxs-lookup"><span data-stu-id="3ec92-250">The following example illustrates [List.map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet18.fs)]

<span data-ttu-id="3ec92-251">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ec92-251">The output is as follows:</span></span>

```console
[2; 3; 4]
```

<span data-ttu-id="3ec92-252">En el siguiente ejemplo se muestra el uso de `List.map2`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-252">The following example shows the use of `List.map2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet19.fs)]

<span data-ttu-id="3ec92-253">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ec92-253">The output is as follows:</span></span>

```console
[5; 7; 9]
```

<span data-ttu-id="3ec92-254">En el siguiente ejemplo se muestra el uso de `List.map3`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-254">The following example shows the use of `List.map3`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet20.fs)]

<span data-ttu-id="3ec92-255">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ec92-255">The output is as follows:</span></span>

```console
[7; 10; 13]
```

<span data-ttu-id="3ec92-256">En el siguiente ejemplo se muestra el uso de `List.mapi`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-256">The following example shows the use of `List.mapi`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet21.fs)]

<span data-ttu-id="3ec92-257">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ec92-257">The output is as follows:</span></span>

```console
[1; 3; 5]
```

<span data-ttu-id="3ec92-258">En el siguiente ejemplo se muestra el uso de `List.mapi2`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-258">The following example shows the use of `List.mapi2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet22.fs)]

<span data-ttu-id="3ec92-259">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ec92-259">The output is as follows:</span></span>

```console
[0; 7; 18]
```

<span data-ttu-id="3ec92-260">[List. Collect](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#collect) es como `List.map` , salvo que cada elemento genera una lista y todas estas listas se concatenan en una lista final.</span><span class="sxs-lookup"><span data-stu-id="3ec92-260">[List.collect](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#collect) is like `List.map`, except that each element produces a list and all these lists are concatenated into a final list.</span></span> <span data-ttu-id="3ec92-261">En el código siguiente, cada elemento de la lista genera tres números.</span><span class="sxs-lookup"><span data-stu-id="3ec92-261">In the following code, each element of the list generates three numbers.</span></span> <span data-ttu-id="3ec92-262">Todos ellos se recopilan en una lista.</span><span class="sxs-lookup"><span data-stu-id="3ec92-262">These are all collected into one list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet23.fs)]

<span data-ttu-id="3ec92-263">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ec92-263">The output is as follows:</span></span>

```console
[1; 2; 3; 2; 4; 6; 3; 6; 9]
```

<span data-ttu-id="3ec92-264">También puede usar [List. Filter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#filter), que toma una condición booleana y genera una nueva lista que solo consta de los elementos que satisfacen la condición especificada.</span><span class="sxs-lookup"><span data-stu-id="3ec92-264">You can also use [List.filter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#filter), which takes a Boolean condition and produces a new list that consists only of elements that satisfy the given condition.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet24.fs)]

<span data-ttu-id="3ec92-265">La lista resultante es `[2; 4; 6]`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-265">The resulting list is `[2; 4; 6]`.</span></span>

<span data-ttu-id="3ec92-266">Una combinación de asignación y filtro, [List. Choose](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#choose) permite transformar y seleccionar elementos al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="3ec92-266">A combination of map and filter, [List.choose](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#choose) enables you to transform and select elements at the same time.</span></span> <span data-ttu-id="3ec92-267">`List.choose` aplica una función que devuelve una opción a cada elemento de una lista, y devuelve una nueva lista de resultados de elementos cuando la función devuelve el valor de opción `Some`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-267">`List.choose` applies a function that returns an option to each element of a list, and returns a new list of the results for elements when the function returns the option value `Some`.</span></span>

<span data-ttu-id="3ec92-268">El código siguiente muestra cómo usar `List.choose` para seleccionar las palabras en mayúsculas de una lista de palabras.</span><span class="sxs-lookup"><span data-stu-id="3ec92-268">The following code demonstrates the use of `List.choose` to select capitalized words out of a list of words.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet25.fs)]

<span data-ttu-id="3ec92-269">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3ec92-269">The output is as follows:</span></span>

```console
["Rome's"; "Bob's"]
```

### <a name="operating-on-multiple-lists"></a><span data-ttu-id="3ec92-270">Operar en varias listas</span><span class="sxs-lookup"><span data-stu-id="3ec92-270">Operating on Multiple Lists</span></span>

<span data-ttu-id="3ec92-271">Las listas se pueden unir entre sí.</span><span class="sxs-lookup"><span data-stu-id="3ec92-271">Lists can be joined together.</span></span> <span data-ttu-id="3ec92-272">Para combinar dos listas en una, use [List. Append](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#append).</span><span class="sxs-lookup"><span data-stu-id="3ec92-272">To join two lists into one, use [List.append](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#append).</span></span> <span data-ttu-id="3ec92-273">Para combinar más de dos listas, use [List. concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#concat).</span><span class="sxs-lookup"><span data-stu-id="3ec92-273">To join more than two lists, use [List.concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#concat).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet26.fs)]

### <a name="fold-and-scan-operations"></a><span data-ttu-id="3ec92-274">Operaciones de plegamiento y exploración</span><span class="sxs-lookup"><span data-stu-id="3ec92-274">Fold and Scan Operations</span></span>

<span data-ttu-id="3ec92-275">Algunas operaciones de lista implican interdependencias entre todos los elementos de lista.</span><span class="sxs-lookup"><span data-stu-id="3ec92-275">Some list operations involve interdependencies between all of the list elements.</span></span> <span data-ttu-id="3ec92-276">Las operaciones de plegamiento y de recorrido son como `List.iter` y `List.map` , en el caso de que se invoque una función en cada elemento, pero estas operaciones proporcionan un parámetro adicional denominado el *acumulador* que lleva información a través del cálculo.</span><span class="sxs-lookup"><span data-stu-id="3ec92-276">The fold and scan operations are like `List.iter` and `List.map` in that you invoke a function on each element, but these operations provide an additional parameter called the *accumulator* that carries information through the computation.</span></span>

<span data-ttu-id="3ec92-277">Use `List.fold` para realizar un cálculo en una lista.</span><span class="sxs-lookup"><span data-stu-id="3ec92-277">Use `List.fold` to perform a calculation on a list.</span></span>

<span data-ttu-id="3ec92-278">En el ejemplo de código siguiente se muestra el uso de [List. Fold](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold) para realizar varias operaciones.</span><span class="sxs-lookup"><span data-stu-id="3ec92-278">The following code example demonstrates the use of [List.fold](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold) to perform various operations.</span></span>

<span data-ttu-id="3ec92-279">La lista se atraviesa; el acumulador `acc` es un valor que va pasando mientras se realiza el cálculo.</span><span class="sxs-lookup"><span data-stu-id="3ec92-279">The list is traversed; the accumulator `acc` is a value that is passed along as the calculation proceeds.</span></span> <span data-ttu-id="3ec92-280">El primer argumento toma el acumulador y el elemento de lista y devuelve el resultado provisional del cálculo para ese elemento de lista.</span><span class="sxs-lookup"><span data-stu-id="3ec92-280">The first argument takes the accumulator and the list element, and returns the interim result of the calculation for that list element.</span></span> <span data-ttu-id="3ec92-281">El segundo argumento es el valor inicial del acumulador.</span><span class="sxs-lookup"><span data-stu-id="3ec92-281">The second argument is the initial value of the accumulator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet27.fs)]

<span data-ttu-id="3ec92-282">Las versiones de estas funciones que tienen un dígito en el nombre de la función operan en más de una lista.</span><span class="sxs-lookup"><span data-stu-id="3ec92-282">The versions of these functions that have a digit in the function name operate on more than one list.</span></span> <span data-ttu-id="3ec92-283">Por ejemplo, [List. fold2 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) realiza cálculos en dos listas.</span><span class="sxs-lookup"><span data-stu-id="3ec92-283">For example, [List.fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) performs computations on two lists.</span></span>

<span data-ttu-id="3ec92-284">El siguiente ejemplo muestra el uso de `List.fold2`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-284">The following example demonstrates the use of `List.fold2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet28.fs)]

<span data-ttu-id="3ec92-285">`List.fold` y [List. Scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#scan) difiere en que `List.fold` devuelve el valor final del parámetro adicional, pero `List.scan` devuelve la lista de los valores intermedios (junto con el valor final) del parámetro adicional.</span><span class="sxs-lookup"><span data-stu-id="3ec92-285">`List.fold` and [List.scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#scan) differ in that `List.fold` returns the final value of the extra parameter, but `List.scan` returns the list of the intermediate values (along with the final value) of the extra parameter.</span></span>

<span data-ttu-id="3ec92-286">Cada una de estas funciones incluye una variación inversa, por ejemplo, [List. foldBack](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack), que difiere en el orden en el que se recorre la lista y el orden de los argumentos.</span><span class="sxs-lookup"><span data-stu-id="3ec92-286">Each of these functions includes a reverse variation, for example, [List.foldBack](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack), which differs in the order in which the list is traversed and the order of the arguments.</span></span> <span data-ttu-id="3ec92-287">Además, `List.fold` y `List.foldBack` tienen variaciones, [List. fold2 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) y [List. foldBack2 (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack2), que toman dos listas de la misma longitud.</span><span class="sxs-lookup"><span data-stu-id="3ec92-287">Also, `List.fold` and `List.foldBack` have variations, [List.fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) and [List.foldBack2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack2), that take two lists of equal length.</span></span> <span data-ttu-id="3ec92-288">La función que se ejecuta en cada elemento puede usar los elementos correspondientes de ambas listas para realizar alguna acción.</span><span class="sxs-lookup"><span data-stu-id="3ec92-288">The function that executes on each element can use corresponding elements of both lists to perform some action.</span></span> <span data-ttu-id="3ec92-289">Los tipos de elemento de las dos listas pueden ser diferentes, como en el ejemplo siguiente, en el que una lista contiene los importes de las transacciones de una cuenta bancaria y la otra lista contiene el tipo de transacción: ingreso o retirada.</span><span class="sxs-lookup"><span data-stu-id="3ec92-289">The element types of the two lists can be different, as in the following example, in which one list contains transaction amounts for a bank account, and the other list contains the type of transaction: deposit or withdrawal.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet29.fs)]

<span data-ttu-id="3ec92-290">Para un cálculo como la suma, `List.fold` y `List.foldBack` tiene el mismo efecto porque el resultado no depende del orden del recorrido.</span><span class="sxs-lookup"><span data-stu-id="3ec92-290">For a calculation like summation, `List.fold` and `List.foldBack` have the same effect because the result does not depend on the order of traversal.</span></span> <span data-ttu-id="3ec92-291">En el ejemplo siguientes, se usa `List.foldBack` para sumar los elementos de una lista.</span><span class="sxs-lookup"><span data-stu-id="3ec92-291">In the following example, `List.foldBack` is used to add the elements in a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet30.fs)]

<span data-ttu-id="3ec92-292">El ejemplo siguiente vuelve al ejemplo de la cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="3ec92-292">The following example returns to the bank account example.</span></span> <span data-ttu-id="3ec92-293">Esta vez se agrega un nuevo tipo de transacción: un cálculo de interés.</span><span class="sxs-lookup"><span data-stu-id="3ec92-293">This time a new transaction type is added: an interest calculation.</span></span> <span data-ttu-id="3ec92-294">El saldo final depende ahora del orden de las transacciones.</span><span class="sxs-lookup"><span data-stu-id="3ec92-294">The ending balance now depends on the order of transactions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet34.fs)]

<span data-ttu-id="3ec92-295">La lista de funciones [. reduce](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#reduce) es similar a `List.fold` y `List.scan` , salvo que, en lugar de pasar un acumulador independiente, `List.reduce` toma una función que toma dos argumentos del tipo de elemento en lugar de uno solo, y uno de esos argumentos actúa como el acumulador, lo que significa que almacena el resultado intermedio del cálculo.</span><span class="sxs-lookup"><span data-stu-id="3ec92-295">The function [List.reduce](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#reduce) is somewhat like `List.fold` and `List.scan`, except that instead of passing around a separate accumulator, `List.reduce` takes a function that takes two arguments of the element type instead of just one, and one of those arguments acts as the accumulator, meaning that it stores the intermediate result of the computation.</span></span> <span data-ttu-id="3ec92-296">`List.reduce` comienza por operar en los dos primeros elementos y, después, usa el resultado de la operación con el siguiente elemento.</span><span class="sxs-lookup"><span data-stu-id="3ec92-296">`List.reduce` starts by operating on the first two list elements, and then uses the result of the operation along with the next element.</span></span> <span data-ttu-id="3ec92-297">Como no hay un acumulador diferente que tenga su propio tipo, se puede usar `List.reduce` en lugar de `List.fold` solo cuando el acumulador y el elemento sean del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="3ec92-297">Because there is not a separate accumulator that has its own type, `List.reduce` can be used in place of `List.fold` only when the accumulator and the element type have the same type.</span></span> <span data-ttu-id="3ec92-298">En el código siguiente se muestra cómo usar `List.reduce`.</span><span class="sxs-lookup"><span data-stu-id="3ec92-298">The following code demonstrates the use of `List.reduce`.</span></span> <span data-ttu-id="3ec92-299">`List.reduce` activa una excepción si la lista proporciona no tiene elementos.</span><span class="sxs-lookup"><span data-stu-id="3ec92-299">`List.reduce` throws an exception if the list provided has no elements.</span></span>

<span data-ttu-id="3ec92-300">En el código siguiente, en la primera llamada a la expresión lambda se proporcionan los argumentos 2 y 4, y devuelve 6; en la siguiente llamada se proporcionan los argumentos 6 y 10, por lo que el resultado es 16.</span><span class="sxs-lookup"><span data-stu-id="3ec92-300">In the following code, the first call to the lambda expression is given the arguments 2 and 4, and returns 6, and the next call is given the arguments 6 and 10, so the result is 16.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet33.fs)]

### <a name="converting-between-lists-and-other-collection-types"></a><span data-ttu-id="3ec92-301">Convertir entre listas y otros tipos de colecciones</span><span class="sxs-lookup"><span data-stu-id="3ec92-301">Converting Between Lists and Other Collection Types</span></span>

<span data-ttu-id="3ec92-302">El módulo `List` proporciona funciones para convertir desde y hacia secuencias y matrices.</span><span class="sxs-lookup"><span data-stu-id="3ec92-302">The `List` module provides functions for converting to and from both sequences and arrays.</span></span> <span data-ttu-id="3ec92-303">Para convertir a o desde una secuencia, use [List. toseq (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toSeq) o [List. ofSeq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofSeq).</span><span class="sxs-lookup"><span data-stu-id="3ec92-303">To convert to or from a sequence, use [List.toSeq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toSeq) or [List.ofSeq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofSeq).</span></span> <span data-ttu-id="3ec92-304">Para realizar la conversión a o desde una matriz, use [List. toArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toArray) o [List. myArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofArray).</span><span class="sxs-lookup"><span data-stu-id="3ec92-304">To convert to or from an array, use [List.toArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toArray) or [List.ofArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofArray).</span></span>

### <a name="additional-operations"></a><span data-ttu-id="3ec92-305">Otras operaciones</span><span class="sxs-lookup"><span data-stu-id="3ec92-305">Additional Operations</span></span>

<span data-ttu-id="3ec92-306">Para obtener información sobre otras operaciones en listas, vea el módulo de [lista](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)de temas de referencia de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="3ec92-306">For information about additional operations on lists, see the library reference topic [List Module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span>

## <a name="see-also"></a><span data-ttu-id="3ec92-307">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ec92-307">See also</span></span>

- [<span data-ttu-id="3ec92-308">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="3ec92-308">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="3ec92-309">Tipos en F#</span><span class="sxs-lookup"><span data-stu-id="3ec92-309">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="3ec92-310">Secuencias</span><span class="sxs-lookup"><span data-stu-id="3ec92-310">Sequences</span></span>](sequences.md)
- [<span data-ttu-id="3ec92-311">Matrices</span><span class="sxs-lookup"><span data-stu-id="3ec92-311">Arrays</span></span>](arrays.md)
- [<span data-ttu-id="3ec92-312">Opciones</span><span class="sxs-lookup"><span data-stu-id="3ec92-312">Options</span></span>](options.md)
