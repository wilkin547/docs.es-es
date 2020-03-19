---
title: Patrones activos
description: Aprenda a utilizar patrones activos para definir particiones con nombre que subdividen los datos de entrada en el lenguaje de programación de F .
ms.date: 05/16/2016
ms.openlocfilehash: 898ef201369683bfd49d53e863e86f919f5837fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187059"
---
# <a name="active-patterns"></a><span data-ttu-id="5c89f-103">Patrones activos</span><span class="sxs-lookup"><span data-stu-id="5c89f-103">Active Patterns</span></span>

<span data-ttu-id="5c89f-104">*Los patrones activos* le permiten definir particiones con nombre que subdividen los datos de entrada, de modo que pueda usar estos nombres en una expresión de coincidencia de patrones tal como lo haría para una unión discriminada.</span><span class="sxs-lookup"><span data-stu-id="5c89f-104">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="5c89f-105">Se pueden usar patrones activos para descomponer los datos de manera personalizada para cada partición.</span><span class="sxs-lookup"><span data-stu-id="5c89f-105">You can use active patterns to decompose data in a customized manner for each partition.</span></span>

## <a name="syntax"></a><span data-ttu-id="5c89f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c89f-106">Syntax</span></span>

```fsharp
// Active pattern of one choice.
let (|identifier|) [arguments] valueToMatch= expression

// Active Pattern with multiple choices.
// Uses a FSharp.Core.Choice<_,...,_> based on the number of case names. In F#, the limitation n <= 7 applies.
let (|identifer1|identifier2|...|) valueToMatch = expression

// Partial active pattern definition.
// Uses a FSharp.Core.option<_> to represent if the type is satisfied at the call site.
let (|identifier|_|) [arguments ] valueToMatch = expression
```

## <a name="remarks"></a><span data-ttu-id="5c89f-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5c89f-107">Remarks</span></span>

<span data-ttu-id="5c89f-108">En la sintaxis anterior, los identificadores son nombres para las particiones de los datos de entrada representados por argumentos o, en otras *palabras,* nombres para subconjuntos del conjunto de todos los valores de los argumentos.</span><span class="sxs-lookup"><span data-stu-id="5c89f-108">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="5c89f-109">Puede haber hasta siete particiones en una definición de patrón activo.</span><span class="sxs-lookup"><span data-stu-id="5c89f-109">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="5c89f-110">La *expresión* describe el formulario en el que se descomponen los datos.</span><span class="sxs-lookup"><span data-stu-id="5c89f-110">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="5c89f-111">Puede utilizar una definición de patrón activa para definir las reglas para determinar a cuál de las particiones con nombre pertenecen los valores dados como argumentos.</span><span class="sxs-lookup"><span data-stu-id="5c89f-111">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="5c89f-112">Los símbolos (a) se conocen como clips de *plátano* y la función creada por este tipo de enlace let se denomina *reconocedor activo.*</span><span class="sxs-lookup"><span data-stu-id="5c89f-112">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="5c89f-113">Por ejemplo, considere el siguiente patrón activo con un argumento.</span><span class="sxs-lookup"><span data-stu-id="5c89f-113">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="5c89f-114">Puede utilizar el patrón activo en una expresión de coincidencia de patrones, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5c89f-114">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="5c89f-115">La salida de este programa es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c89f-115">The output of this program is as follows:</span></span>

```console
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="5c89f-116">Otro uso de patrones activos es descomponer los tipos de datos de varias maneras, como cuando los mismos datos subyacentes tienen varias representaciones posibles.</span><span class="sxs-lookup"><span data-stu-id="5c89f-116">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="5c89f-117">Por ejemplo, `Color` un objeto podría descomponerse en una representación RGB o una representación HSB.</span><span class="sxs-lookup"><span data-stu-id="5c89f-117">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="5c89f-118">La salida del programa anterior es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c89f-118">The output of the above program is as follows:</span></span>

```console
Red
 Red: 255 Green: 0 Blue: 0
 Hue: 360.000000 Saturation: 1.000000 Brightness: 0.500000
Black
 Red: 0 Green: 0 Blue: 0
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.000000
White
 Red: 255 Green: 255 Blue: 255
 Hue: 0.000000 Saturation: 0.000000 Brightness: 1.000000
Gray
 Red: 128 Green: 128 Blue: 128
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.501961
BlanchedAlmond
 Red: 255 Green: 235 Blue: 205
 Hue: 36.000000 Saturation: 1.000000 Brightness: 0.901961
```

<span data-ttu-id="5c89f-119">En combinación, estas dos formas de usar patrones activos le permiten particionar y descomponer datos en solo el formulario adecuado y realizar los cálculos adecuados en los datos adecuados en la forma más conveniente para el cálculo.</span><span class="sxs-lookup"><span data-stu-id="5c89f-119">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="5c89f-120">Las expresiones de coincidencia de patrones resultantes permiten que los datos se escriban de una manera conveniente que sea muy legible, lo que simplifica en gran medida el código de bifurcación y análisis de datos potencialmente complejo.</span><span class="sxs-lookup"><span data-stu-id="5c89f-120">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>

## <a name="partial-active-patterns"></a><span data-ttu-id="5c89f-121">Patrones activos parciales</span><span class="sxs-lookup"><span data-stu-id="5c89f-121">Partial Active Patterns</span></span>

<span data-ttu-id="5c89f-122">A veces, solo necesita particionar una parte del espacio de entrada.</span><span class="sxs-lookup"><span data-stu-id="5c89f-122">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="5c89f-123">En ese caso, se escribe un conjunto de patrones parciales cada uno de los cuales coincide con algunas entradas, pero no coinciden con otras entradas.</span><span class="sxs-lookup"><span data-stu-id="5c89f-123">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="5c89f-124">Los patrones activos que no siempre producen un valor se denominan *patrones activos parciales;* tienen un valor devuelto que es un tipo de opción.</span><span class="sxs-lookup"><span data-stu-id="5c89f-124">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="5c89f-125">Para definir un patrón activo parcial,\_utilice un carácter comodín ( ) al final de la lista de patrones dentro de los clips de plátano.</span><span class="sxs-lookup"><span data-stu-id="5c89f-125">To define a partial active pattern, you use a wildcard character (\_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="5c89f-126">El código siguiente ilustra el uso de un patrón activo parcial.</span><span class="sxs-lookup"><span data-stu-id="5c89f-126">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="5c89f-127">La salida del ejemplo anterior es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c89f-127">The output of the previous example is as follows:</span></span>

```console
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="5c89f-128">Cuando se utilizan patrones activos parciales, a veces las opciones individuales pueden ser desarticuladas o mutuamente excluyentes, pero no es necesario que lo sean.</span><span class="sxs-lookup"><span data-stu-id="5c89f-128">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="5c89f-129">En el ejemplo siguiente, el patrón Square y el patrón Cube no están desarticulados, porque algunos números son cuadrados y cubos, como 64.</span><span class="sxs-lookup"><span data-stu-id="5c89f-129">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="5c89f-130">El siguiente programa utiliza el patrón AND para combinar los patrones Square y Cube.</span><span class="sxs-lookup"><span data-stu-id="5c89f-130">The following program uses the AND pattern to combine the Square and Cube patterns.</span></span> <span data-ttu-id="5c89f-131">Imprime todos los enteros de hasta 1000 que son cuadrados y cubos, así como los que son solo cubos.</span><span class="sxs-lookup"><span data-stu-id="5c89f-131">It prints out all integers up to 1000 that are both squares and cubes, as well as those which are only cubes.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="5c89f-132">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="5c89f-132">The output is as follows:</span></span>

```console
1 is a cube and a square
8 is a cube
27 is a cube
64 is a cube and a square
125 is a cube
216 is a cube
343 is a cube
512 is a cube
729 is a cube and a square
1000 is a cube
```

## <a name="parameterized-active-patterns"></a><span data-ttu-id="5c89f-133">Patrones activos parametrizados</span><span class="sxs-lookup"><span data-stu-id="5c89f-133">Parameterized Active Patterns</span></span>

<span data-ttu-id="5c89f-134">Los patrones activos siempre toman al menos un argumento para el elemento que se va a coincidir, pero también pueden tomar argumentos adicionales, en cuyo caso se aplica el *patrón activo con parámetros* de nombre.</span><span class="sxs-lookup"><span data-stu-id="5c89f-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="5c89f-135">Los argumentos adicionales permiten especializar un patrón general.</span><span class="sxs-lookup"><span data-stu-id="5c89f-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="5c89f-136">Por ejemplo, los patrones activos que usan expresiones regulares para analizar cadenas a menudo incluyen la `Integer` expresión regular como un parámetro adicional, como en el código siguiente, que también usa el patrón activo parcial definido en el ejemplo de código anterior.</span><span class="sxs-lookup"><span data-stu-id="5c89f-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="5c89f-137">En este ejemplo, se proporcionan cadenas que utilizan expresiones regulares para varios formatos de fecha para personalizar el patrón activo general de ParseRegex.</span><span class="sxs-lookup"><span data-stu-id="5c89f-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="5c89f-138">El patrón activo entero se utiliza para convertir las cadenas coincidentes en enteros que se pueden pasar al constructor DateTime.</span><span class="sxs-lookup"><span data-stu-id="5c89f-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="5c89f-139">La salida del código anterior es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c89f-139">The output of the previous code is as follows:</span></span>

```console
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="5c89f-140">Los patrones activos no están restringidos solo a las expresiones de coincidencia de patrones, también puede usarlos en enlaces let.</span><span class="sxs-lookup"><span data-stu-id="5c89f-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="5c89f-141">La salida del código anterior es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c89f-141">The output of the previous code is as follows:</span></span>

```console
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="5c89f-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5c89f-142">See also</span></span>

- [<span data-ttu-id="5c89f-143">Referencia del lenguaje f</span><span class="sxs-lookup"><span data-stu-id="5c89f-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="5c89f-144">Expresiones de coincidencia</span><span class="sxs-lookup"><span data-stu-id="5c89f-144">Match Expressions</span></span>](match-expressions.md)
