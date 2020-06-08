---
title: Patrones activos
description: 'Obtenga información sobre cómo usar patrones activos para definir particiones con nombre que subdividen los datos de entrada en el lenguaje de programación F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 7b6da38baa35f30ae6de8a930be60a4e4fc0fc0d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493898"
---
# <a name="active-patterns"></a><span data-ttu-id="58e94-103">Patrones activos</span><span class="sxs-lookup"><span data-stu-id="58e94-103">Active Patterns</span></span>

<span data-ttu-id="58e94-104">Los *modelos activos* permiten definir particiones con nombre que subdividen los datos de entrada, de modo que puede usar estos nombres en una expresión de coincidencia de patrones de la misma forma que lo haría para una Unión discriminada.</span><span class="sxs-lookup"><span data-stu-id="58e94-104">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="58e94-105">Se pueden usar patrones activos para descomponer los datos de manera personalizada para cada partición.</span><span class="sxs-lookup"><span data-stu-id="58e94-105">You can use active patterns to decompose data in a customized manner for each partition.</span></span>

## <a name="syntax"></a><span data-ttu-id="58e94-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58e94-106">Syntax</span></span>

```fsharp
// Active pattern of one choice.
let (|identifier|) [arguments] valueToMatch = expression

// Active Pattern with multiple choices.
// Uses a FSharp.Core.Choice<_,...,_> based on the number of case names. In F#, the limitation n <= 7 applies.
let (|identifer1|identifier2|...|) valueToMatch = expression

// Partial active pattern definition.
// Uses a FSharp.Core.option<_> to represent if the type is satisfied at the call site.
let (|identifier|_|) [arguments ] valueToMatch = expression
```

## <a name="remarks"></a><span data-ttu-id="58e94-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="58e94-107">Remarks</span></span>

<span data-ttu-id="58e94-108">En la sintaxis anterior, los identificadores son nombres para las particiones de los datos de entrada que se representan mediante *argumentos*o, en otras palabras, nombres para subconjuntos del conjunto de todos los valores de los argumentos.</span><span class="sxs-lookup"><span data-stu-id="58e94-108">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="58e94-109">Puede haber hasta siete particiones en una definición de modelo activo.</span><span class="sxs-lookup"><span data-stu-id="58e94-109">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="58e94-110">La *expresión* describe el formulario en el que se descomponen los datos.</span><span class="sxs-lookup"><span data-stu-id="58e94-110">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="58e94-111">Puede usar una definición de modelo activa para definir las reglas para determinar a qué particiones con nombre se encuentran los valores especificados como argumentos.</span><span class="sxs-lookup"><span data-stu-id="58e94-111">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="58e94-112">Los símbolos (| y |) se conocen como *clips de banana* y la función creada por este tipo de enlace Let se denomina *reconocedor activo*.</span><span class="sxs-lookup"><span data-stu-id="58e94-112">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="58e94-113">Como ejemplo, considere el siguiente patrón activo con un argumento.</span><span class="sxs-lookup"><span data-stu-id="58e94-113">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="58e94-114">Puede usar el modelo activo en una expresión de coincidencia de patrones, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="58e94-114">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="58e94-115">La salida de este programa es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="58e94-115">The output of this program is as follows:</span></span>

```console
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="58e94-116">Otro uso de los patrones activos es descomponer los tipos de datos de varias maneras, por ejemplo, cuando los mismos datos subyacentes tienen varias representaciones posibles.</span><span class="sxs-lookup"><span data-stu-id="58e94-116">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="58e94-117">Por ejemplo, un `Color` objeto se puede descomponer en una representación RGB o en una representación HSB.</span><span class="sxs-lookup"><span data-stu-id="58e94-117">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="58e94-118">La salida del programa anterior es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="58e94-118">The output of the above program is as follows:</span></span>

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

<span data-ttu-id="58e94-119">En combinación, estas dos maneras de utilizar los modelos activos permiten particionar y descomponer los datos en el formulario adecuado y realizar los cálculos adecuados en los datos adecuados en el formulario más conveniente para el cálculo.</span><span class="sxs-lookup"><span data-stu-id="58e94-119">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="58e94-120">Las expresiones de coincidencia de patrones resultantes permiten escribir datos de una manera cómoda que sea muy legible, lo que simplifica considerablemente la bifurcación y el código de análisis de datos potencialmente complejos.</span><span class="sxs-lookup"><span data-stu-id="58e94-120">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>

## <a name="partial-active-patterns"></a><span data-ttu-id="58e94-121">Modelos activos parciales</span><span class="sxs-lookup"><span data-stu-id="58e94-121">Partial Active Patterns</span></span>

<span data-ttu-id="58e94-122">A veces, solo necesita crear particiones de parte del espacio de entrada.</span><span class="sxs-lookup"><span data-stu-id="58e94-122">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="58e94-123">En ese caso, se escribe un conjunto de patrones parciales cada uno de los cuales coinciden con algunas entradas pero no coinciden con otras entradas.</span><span class="sxs-lookup"><span data-stu-id="58e94-123">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="58e94-124">Los modelos activos que no siempre generan un valor se denominan *modelos activos parciales*. tienen un valor devuelto que es un tipo de opción.</span><span class="sxs-lookup"><span data-stu-id="58e94-124">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="58e94-125">Para definir un modelo activo parcial, se usa un carácter comodín ( \_ ) al final de la lista de patrones dentro de los clips de banana.</span><span class="sxs-lookup"><span data-stu-id="58e94-125">To define a partial active pattern, you use a wildcard character (\_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="58e94-126">En el código siguiente se muestra el uso de un modelo activo parcial.</span><span class="sxs-lookup"><span data-stu-id="58e94-126">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="58e94-127">La salida del ejemplo anterior es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="58e94-127">The output of the previous example is as follows:</span></span>

```console
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="58e94-128">Cuando se usan modelos activos parciales, algunas veces las opciones individuales pueden ser disjuntas o excluidas mutuamente, pero no es necesario.</span><span class="sxs-lookup"><span data-stu-id="58e94-128">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="58e94-129">En el ejemplo siguiente, el cuadrado de patrón y el cubo de patrón no están separados, porque algunos números son cuadrados y cubos, como 64.</span><span class="sxs-lookup"><span data-stu-id="58e94-129">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="58e94-130">En el siguiente programa se usa el patrón y para combinar los patrones de cuadrados y de cubo.</span><span class="sxs-lookup"><span data-stu-id="58e94-130">The following program uses the AND pattern to combine the Square and Cube patterns.</span></span> <span data-ttu-id="58e94-131">Imprime todos los enteros hasta 1000 que son cuadrados y cubos, así como aquellos que son solo cubos.</span><span class="sxs-lookup"><span data-stu-id="58e94-131">It prints out all integers up to 1000 that are both squares and cubes, as well as those which are only cubes.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="58e94-132">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="58e94-132">The output is as follows:</span></span>

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

## <a name="parameterized-active-patterns"></a><span data-ttu-id="58e94-133">Modelos activos con parámetros</span><span class="sxs-lookup"><span data-stu-id="58e94-133">Parameterized Active Patterns</span></span>

<span data-ttu-id="58e94-134">Los modelos activos siempre toman al menos un argumento para el elemento que se está coincidentendo, pero también pueden tomar argumentos adicionales, en cuyo caso se aplica el nombre del *modelo activo parametrizado* .</span><span class="sxs-lookup"><span data-stu-id="58e94-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="58e94-135">Los argumentos adicionales permiten que un patrón general esté especializado.</span><span class="sxs-lookup"><span data-stu-id="58e94-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="58e94-136">Por ejemplo, los patrones activos que usan expresiones regulares para analizar cadenas suelen incluir la expresión regular como parámetro adicional, como en el código siguiente, que también usa el modelo activo parcial `Integer` definido en el ejemplo de código anterior.</span><span class="sxs-lookup"><span data-stu-id="58e94-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="58e94-137">En este ejemplo, se proporcionan cadenas que usan expresiones regulares para varios formatos de fecha para personalizar el modelo activo ParseRegex general.</span><span class="sxs-lookup"><span data-stu-id="58e94-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="58e94-138">El modelo activo entero se usa para convertir las cadenas coincidentes en enteros que se pueden pasar al constructor DateTime.</span><span class="sxs-lookup"><span data-stu-id="58e94-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="58e94-139">La salida del código anterior es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="58e94-139">The output of the previous code is as follows:</span></span>

```console
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="58e94-140">Los modelos activos no se limitan solo a las expresiones de coincidencia de patrones, sino que también se pueden usar en los enlaces Let.</span><span class="sxs-lookup"><span data-stu-id="58e94-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="58e94-141">La salida del código anterior es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="58e94-141">The output of the previous code is as follows:</span></span>

```console
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="58e94-142">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="58e94-142">See also</span></span>

- [<span data-ttu-id="58e94-143">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="58e94-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="58e94-144">Expresiones de coincidencia</span><span class="sxs-lookup"><span data-stu-id="58e94-144">Match Expressions</span></span>](match-expressions.md)
