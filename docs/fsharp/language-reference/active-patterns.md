---
title: Modelos activos (F#)
description: "Obtenga información acerca de cómo usar modelos activos para definir particiones con nombre que subdividen los datos de entrada en el lenguaje de programación de F #."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 11a724ff-f9ff-4056-b5e0-87e9ed986f4a
ms.openlocfilehash: 845184e6150cf0b93393038ca3d39f0e6d898a2e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="active-patterns"></a><span data-ttu-id="4c1b8-104">Patrones activos</span><span class="sxs-lookup"><span data-stu-id="4c1b8-104">Active Patterns</span></span>

<span data-ttu-id="4c1b8-105">*Modelos activos* le permiten definir particiones con nombre que subdividen los datos de entrada, por lo que puede utilizar estos nombres en un patrón de coincidencia de expresión tal como haría con una unión discriminada.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-105">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="4c1b8-106">Se pueden usar patrones activos para descomponer los datos de manera personalizada para cada partición.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-106">You can use active patterns to decompose data in a customized manner for each partition.</span></span>


## <a name="syntax"></a><span data-ttu-id="4c1b8-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4c1b8-107">Syntax</span></span>

```fsharp
// Complete active pattern definition.
let (|identifer1|identifier2|...|) [ arguments ] = expression
// Partial active pattern definition.
let (|identifier|_|) [ arguments ] = expression
```

## <a name="remarks"></a><span data-ttu-id="4c1b8-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4c1b8-108">Remarks</span></span>
<span data-ttu-id="4c1b8-109">En la sintaxis anterior, los identificadores son los nombres para las particiones de los datos de entrada que se representan mediante *argumentos*, o, en otras palabras, los nombres de subconjuntos del conjunto de todos los valores de los argumentos.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-109">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="4c1b8-110">Puede haber hasta siete particiones en una definición de modelo activo.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-110">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="4c1b8-111">El *expresión* describe la forma en la que se recomienda desglosar los datos.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-111">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="4c1b8-112">Puede usar una definición de modelo activo para definir las reglas para determinar cuál de las particiones con nombre de los valores proporcionados como argumentos pertenecen a.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-112">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="4c1b8-113">El (| y |) símbolos se conocen como *clips plátano* y se llama a la función creada por este tipo de enlace permiten un *reconocedor active*.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-113">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="4c1b8-114">Por ejemplo, considere el siguiente patrón activo con un argumento.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-114">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="4c1b8-115">Puede usar el patrón activo en un patrón de coincidencia de expresión, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-115">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="4c1b8-116">El resultado de este programa es como sigue:</span><span class="sxs-lookup"><span data-stu-id="4c1b8-116">The output of this program is as follows:</span></span>

```
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="4c1b8-117">Otro uso de modelos activos consiste en descomponer los tipos de datos de varias maneras, por ejemplo, cuando los mismos datos subyacentes tienen varias representaciones posibles.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-117">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="4c1b8-118">Por ejemplo, un `Color` objeto se puede descomponer en una representación RGB o HSB.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-118">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="4c1b8-119">La salida del programa anterior es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c1b8-119">The output of the above program is as follows:</span></span>

```
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

<span data-ttu-id="4c1b8-120">En combinación, estas dos formas de usar modelos activos permiten a la partición y descomponen los datos en el formulario de adecuado y realizan los cálculos adecuados en los datos apropiados en la forma más conveniente para el cálculo.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-120">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="4c1b8-121">Las expresiones de búsqueda de coincidencias de patrón resultante habilitar datos se escriban en una manera cómoda de bifurcación potencialmente compleja muy legibles, lo que simplifica en gran medida y el código de análisis de datos.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-121">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>


## <a name="partial-active-patterns"></a><span data-ttu-id="4c1b8-122">Modelos activos parciales</span><span class="sxs-lookup"><span data-stu-id="4c1b8-122">Partial Active Patterns</span></span>
<span data-ttu-id="4c1b8-123">A veces, debe crear particiones solo una parte del espacio de entrada.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-123">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="4c1b8-124">En ese caso, escribe un conjunto de modelos parciales, cada que coinciden con algunas entradas pero no coincide con otras entradas.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-124">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="4c1b8-125">Modelos activos que no siempre generan un valor se denominan *modelos activos parciales*; tienen un valor devuelto que es un tipo de opción.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-125">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="4c1b8-126">Para definir un modelo activo parcial, usa un carácter comodín (_) al final de la lista de patrones en los clips plátano.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-126">To define a partial active pattern, you use a wildcard character (_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="4c1b8-127">El código siguiente muestra el uso de un modelo activo parcial.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-127">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="4c1b8-128">La salida del ejemplo anterior es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c1b8-128">The output of the previous example is as follows:</span></span>

```
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="4c1b8-129">Al utilizar modelos activos parciales, las opciones individuales pueden ser unas veces separados o mutuamente excluyente, pero no tienen que ser.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-129">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="4c1b8-130">En el ejemplo siguiente, el modelo Square y el modelo del cubo no son separados, porque algunos números son cuadrados y cubos, como 64.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-130">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="4c1b8-131">El siguiente programa imprime todos los enteros hasta 1000000 que son cuadrados y cubos.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-131">The following program prints out all integers up to 1000000 that are both squares and cubes.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="4c1b8-132">La salida es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c1b8-132">The output is as follows:</span></span>

```
1
64
729
4096
15625
46656
117649
262144
531441
1000000
```

## <a name="parameterized-active-patterns"></a><span data-ttu-id="4c1b8-133">Modelos activos con parámetros</span><span class="sxs-lookup"><span data-stu-id="4c1b8-133">Parameterized Active Patterns</span></span>
<span data-ttu-id="4c1b8-134">Modelos activos siempre tienen al menos un argumento para el elemento que se buscan coincidencias, pero puede aceptar argumentos adicionales, en cuyo caso el nombre *modelo activo parametrizado* se aplica.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="4c1b8-135">Argumentos adicionales permiten que un patrón general especializadas.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="4c1b8-136">Por ejemplo, los modelos activos que utilizan expresiones regulares para analizar cadenas suelen incluyen la expresión regular como un parámetro adicional, como se muestra en el código siguiente, que también utiliza el modelo activo parcial `Integer` definido en el ejemplo de código anterior.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="4c1b8-137">En este ejemplo, las cadenas que utilizan expresiones regulares para diversos formatos de fecha se proporcionan para personalizar el activo ParseRegex general.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="4c1b8-138">El modelo activo de entero se utiliza para convertir las cadenas coincidentes en enteros que se pueden pasar al constructor de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="4c1b8-139">La salida del código anterior es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c1b8-139">The output of the previous code is as follows:</span></span>

```
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="4c1b8-140">Modelos activos no están restringidos únicamente a expresiones de coincidencia de patrón, también puede utilizar en enlaces let.</span><span class="sxs-lookup"><span data-stu-id="4c1b8-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="4c1b8-141">La salida del código anterior es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c1b8-141">The output of the previous code is as follows:</span></span>

```
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="4c1b8-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c1b8-142">See Also</span></span>
[<span data-ttu-id="4c1b8-143">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="4c1b8-143">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="4c1b8-144">Expresiones de coincidencia</span><span class="sxs-lookup"><span data-stu-id="4c1b8-144">Match Expressions</span></span>](match-expressions.md)

