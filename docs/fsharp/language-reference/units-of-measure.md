---
title: Unidades de medida (F#)
description: 'Obtenga información acerca de punto flotante cómo y valores enteros con signo en F # pueden tener asociadas unidades de medida, que se usan normalmente para indicar la longitud, el volumen y masa.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 336a1e04426fb39f5ceb98e06a06cd7eadc36e85
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="units-of-measure"></a><span data-ttu-id="0e110-103">Unidades de medida</span><span class="sxs-lookup"><span data-stu-id="0e110-103">Units of Measure</span></span>

<span data-ttu-id="0e110-104">Punto flotante y valores enteros con signo en F # puede tener asociadas unidades de medida, que se usan normalmente para indicar la longitud, el volumen, masa, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="0e110-104">Floating point and signed integer values in F# can have associated units of measure, which are typically used to indicate length, volume, mass, and so on.</span></span> <span data-ttu-id="0e110-105">Al usar cantidades con unidades, se habilita al compilador comprobar que las relaciones aritméticas tienen las unidades correctas, lo que ayuda a evitar errores de programación.</span><span class="sxs-lookup"><span data-stu-id="0e110-105">By using quantities with units, you enable the compiler to verify that arithmetic relationships have the correct units, which helps prevent programming errors.</span></span>


## <a name="syntax"></a><span data-ttu-id="0e110-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e110-106">Syntax</span></span>

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a><span data-ttu-id="0e110-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0e110-107">Remarks</span></span>
<span data-ttu-id="0e110-108">Define la sintaxis anterior *nombre de la unidad* como una unidad de medida.</span><span class="sxs-lookup"><span data-stu-id="0e110-108">The previous syntax defines *unit-name* as a unit of measure.</span></span> <span data-ttu-id="0e110-109">La parte opcional se utiliza para definir una nueva medida en términos de unidades definidos previamente.</span><span class="sxs-lookup"><span data-stu-id="0e110-109">The optional part is used to define a new measure in terms of previously defined units.</span></span> <span data-ttu-id="0e110-110">Por ejemplo, la línea siguiente define la medida `cm` (cm).</span><span class="sxs-lookup"><span data-stu-id="0e110-110">For example, the following line defines the measure `cm` (centimeter).</span></span>

```fsharp
[<Measure>] type cm
```

<span data-ttu-id="0e110-111">La línea siguiente define la medida `ml` (mililitro) un como centímetro cúbico (`cm^3`).</span><span class="sxs-lookup"><span data-stu-id="0e110-111">The following line defines the measure `ml` (milliliter) as a cubic centimeter (`cm^3`).</span></span>

```fsharp
[<Measure>] type ml = cm^3
```

<span data-ttu-id="0e110-112">En la sintaxis anterior, *medida* es una fórmula que implica unidades.</span><span class="sxs-lookup"><span data-stu-id="0e110-112">In the previous syntax, *measure* is a formula that involves units.</span></span> <span data-ttu-id="0e110-113">En las fórmulas que requieren unidades, se admiten potencias enteras (positivas y negativas), espacios entre unidades indican un producto de las dos unidades, `*` también indica un producto de unidades, y `/` indica un cociente de unidades.</span><span class="sxs-lookup"><span data-stu-id="0e110-113">In formulas that involve units, integral powers are supported (positive and negative), spaces between units indicate a product of the two units, `*` also indicates a product of units, and `/` indicates a quotient of units.</span></span> <span data-ttu-id="0e110-114">Para una unidad recíproca, puede usar una potencia de entero negativo o una `/` que indica una separación entre el numerador y el denominador de una fórmula de la unidad.</span><span class="sxs-lookup"><span data-stu-id="0e110-114">For a reciprocal unit, you can either use a negative integer power or a `/` that indicates a separation between the numerator and denominator of a unit formula.</span></span> <span data-ttu-id="0e110-115">Varias unidades en el denominador deben ir entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="0e110-115">Multiple units in the denominator should be surrounded by parentheses.</span></span> <span data-ttu-id="0e110-116">Unidades separan por espacios después de un `/` se interpretan como parte del denominador, pero las unidades después de un `*` se interpretan como parte del numerador.</span><span class="sxs-lookup"><span data-stu-id="0e110-116">Units separated by spaces after a `/` are interpreted as being part of the denominator, but any units following a `*` are interpreted as being part of the numerator.</span></span>

<span data-ttu-id="0e110-117">Puede usar 1 en las expresiones de unidad, ya sea por sí solo para indicar una cantidad sin dimensiones, o junto con otras unidades, como se muestra en el numerador.</span><span class="sxs-lookup"><span data-stu-id="0e110-117">You can use 1 in unit expressions, either alone to indicate a dimensionless quantity, or together with other units, such as in the numerator.</span></span> <span data-ttu-id="0e110-118">Por ejemplo, las unidades para una velocidad se escribiría como `1/s`, donde `s` indica los segundos.</span><span class="sxs-lookup"><span data-stu-id="0e110-118">For example, the units for a rate would be written as `1/s`, where `s` indicates seconds.</span></span> <span data-ttu-id="0e110-119">No se emplean paréntesis en las fórmulas de la unidad.</span><span class="sxs-lookup"><span data-stu-id="0e110-119">Parentheses are not used in unit formulas.</span></span> <span data-ttu-id="0e110-120">No especificar constantes de conversión numérica en las fórmulas de unidades; Sin embargo, puede definir constantes de conversión con unidades por separado y utilizarlos en cálculos con comprobación de unidad.</span><span class="sxs-lookup"><span data-stu-id="0e110-120">You do not specify numeric conversion constants in the unit formulas; however, you can define conversion constants with units separately and use them in unit-checked computations.</span></span>

<span data-ttu-id="0e110-121">Fórmulas de unidades que significan lo mismo pueden escribirse de diferentes formas equivalentes.</span><span class="sxs-lookup"><span data-stu-id="0e110-121">Unit formulas that mean the same thing can be written in various equivalent ways.</span></span> <span data-ttu-id="0e110-122">Por lo tanto, el compilador convierte fórmulas de unidades en un formato coherente, que convierte potencias negativas recíprocos, unidades se agrupan en un solo numerador y denominador y se ordenan alfabéticamente las unidades en el numerador y el denominador.</span><span class="sxs-lookup"><span data-stu-id="0e110-122">Therefore, the compiler converts unit formulas into a consistent form, which converts negative powers to reciprocals, groups units into a single numerator and a denominator, and alphabetizes the units in the numerator and denominator.</span></span>

<span data-ttu-id="0e110-123">Por ejemplo, las fórmulas de unidades `kg m s^-2` y `m /s s * kg` se convierten en `kg m/s^2`.</span><span class="sxs-lookup"><span data-stu-id="0e110-123">For example, the unit formulas `kg m s^-2` and `m /s s * kg` are both converted to `kg m/s^2`.</span></span>

<span data-ttu-id="0e110-124">Usar unidades de medida en expresiones de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="0e110-124">You use units of measure in floating point expressions.</span></span> <span data-ttu-id="0e110-125">Uso de números de punto flotante junto con asociados unidades de medida agrega otro nivel de seguridad de tipos y ayuda a evita los errores de falta de coincidencia de unidad que se pueden producir en las fórmulas cuando se utiliza con tipos débiles números de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="0e110-125">Using floating point numbers together with associated units of measure adds another level of type safety and helps avoid the unit mismatch errors that can occur in formulas when you use weakly typed floating point numbers.</span></span> <span data-ttu-id="0e110-126">Si escribe un flotante expresión de punto que utiliza unidades, las unidades en la expresión deben coincidir.</span><span class="sxs-lookup"><span data-stu-id="0e110-126">If you write a floating point expression that uses units, the units in the expression must match.</span></span>

<span data-ttu-id="0e110-127">Puede anotar literales con una fórmula de unidad en corchetes angulares, tal como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="0e110-127">You can annotate literals with a unit formula in angle brackets, as shown in the following examples.</span></span>

```fsharp
1.0<cm>
55.0<miles/hour>
```

<span data-ttu-id="0e110-128">No incluir un espacio entre el número y el corchete angular de cierre; Sin embargo, puede incluir un sufijo literal como `f`, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0e110-128">You do not put a space between the number and the angle bracket; however, you can include a literal suffix such as `f`, as in the following example.</span></span>

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

<span data-ttu-id="0e110-129">Este tipo de anotación cambia el tipo del literal desde su tipo primitivo (como `float`) a un tipo con dimensiones, como `float<cm>` o, en este caso, `float<miles/hour>`.</span><span class="sxs-lookup"><span data-stu-id="0e110-129">Such an annotation changes the type of the literal from its primitive type (such as `float`) to a dimensioned type, such as `float<cm>` or, in this case, `float<miles/hour>`.</span></span> <span data-ttu-id="0e110-130">La anotación de unidad `<1>` indica una cantidad sin dimensiones y su tipo es equivalente al tipo primitivo sin un parámetro de unidad.</span><span class="sxs-lookup"><span data-stu-id="0e110-130">A unit annotation of `<1>` indicates a dimensionless quantity, and its type is equivalent to the primitive type without a unit parameter.</span></span>

<span data-ttu-id="0e110-131">El tipo de una unidad de medida es un punto flotante o tipo entero con signo junto con una anotación de unidad adicional, indicada entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="0e110-131">The type of a unit of measure is a floating point or signed integral type together with an extra unit annotation, indicated in brackets.</span></span> <span data-ttu-id="0e110-132">Por lo tanto, al escribir el tipo de conversión de `g` (g) a `kg` (kilogramos), se describen los tipos como sigue.</span><span class="sxs-lookup"><span data-stu-id="0e110-132">Thus, when you write the type of a conversion from `g` (grams) to `kg` (kilograms), you describe the types as follows.</span></span>

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

<span data-ttu-id="0e110-133">Unidades de medida que se usan para la comprobación de unidades en tiempo de compilación pero no se conservan en el entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0e110-133">Units of measure are used for compile-time unit checking but are not persisted in the run-time environment.</span></span> <span data-ttu-id="0e110-134">Por lo tanto, no afectan al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0e110-134">Therefore, they do not affect performance.</span></span>

<span data-ttu-id="0e110-135">Unidades de medida se pueden aplicar a cualquier tipo, no solo los tipos de punto; flotante Sin embargo, solo los tipos de punto flotante, firma tipos enteros y tipos decimales admiten cantidades con dimensiones.</span><span class="sxs-lookup"><span data-stu-id="0e110-135">Units of measure can be applied to any type, not just floating point types; however, only floating point types, signed integral types, and decimal types support dimensioned quantities.</span></span> <span data-ttu-id="0e110-136">Por lo tanto, solo tiene sentido utilizar unidades de medida en los tipos primitivos y los agregados que contengan estos tipos primitivos.</span><span class="sxs-lookup"><span data-stu-id="0e110-136">Therefore, it only makes sense to use units of measure on the primitive types and on aggregates that contain these primitive types.</span></span>

<span data-ttu-id="0e110-137">En el ejemplo siguiente se muestra el uso de unidades de medida.</span><span class="sxs-lookup"><span data-stu-id="0e110-137">The following example illustrates the use of units of measure.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]
    
<span data-ttu-id="0e110-138">En el ejemplo de código siguiente se muestra cómo convertir un número de punto flotante sin dimensiones en un valor de punto flotante con dimensiones.</span><span class="sxs-lookup"><span data-stu-id="0e110-138">The following code example illustrates how to convert from a dimensionless floating point number to a dimensioned floating point value.</span></span> <span data-ttu-id="0e110-139">Solo multiplique por 1,0, aplicar las dimensiones a la versión 1.0.</span><span class="sxs-lookup"><span data-stu-id="0e110-139">You just multiply by 1.0, applying the dimensions to the 1.0.</span></span> <span data-ttu-id="0e110-140">Esto se puede abstraer en una función como `degreesFahrenheit`.</span><span class="sxs-lookup"><span data-stu-id="0e110-140">You can abstract this into a function like `degreesFahrenheit`.</span></span>

<span data-ttu-id="0e110-141">Además, al pasar valores con dimensiones a funciones que esperan números de punto flotante sin dimensiones, debe anular las unidades o convertir a `float` utilizando el `float` operador.</span><span class="sxs-lookup"><span data-stu-id="0e110-141">Also, when you pass dimensioned values to functions that expect dimensionless floating point numbers, you must cancel out the units or cast to `float` by using the `float` operator.</span></span> <span data-ttu-id="0e110-142">En este ejemplo, se divide por `1.0<degC>` para los argumentos con `printf` porque `printf` espera cantidades sin dimensiones.</span><span class="sxs-lookup"><span data-stu-id="0e110-142">In this example, you divide by `1.0<degC>` for the arguments to `printf` because `printf` expects dimensionless quantities.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

<span data-ttu-id="0e110-143">La sesión de ejemplo siguiente muestra las entradas y salidas de a este código.</span><span class="sxs-lookup"><span data-stu-id="0e110-143">The following example session shows the outputs from and inputs to this code.</span></span>

```
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a><span data-ttu-id="0e110-144">Usar unidades genéricas</span><span class="sxs-lookup"><span data-stu-id="0e110-144">Using Generic Units</span></span>
<span data-ttu-id="0e110-145">Puede escribir funciones genéricas que funcionan con datos que tienen una unidad de medida asociada.</span><span class="sxs-lookup"><span data-stu-id="0e110-145">You can write generic functions that operate on data that has an associated unit of measure.</span></span> <span data-ttu-id="0e110-146">Para ello, especificando un tipo junto con una unidad genérica como un parámetro de tipo, como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="0e110-146">You do this by specifying a type together with a generic unit as a type parameter, as shown in the following code example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]
    
## <a name="creating-aggregate-types-with-generic-units"></a><span data-ttu-id="0e110-147">Crear tipos agregados con unidades genéricas</span><span class="sxs-lookup"><span data-stu-id="0e110-147">Creating Aggregate Types with Generic Units</span></span>
<span data-ttu-id="0e110-148">El código siguiente muestra cómo crear un tipo agregado que consta de valores de punto flotante individuales que tienen unidades que son genéricas.</span><span class="sxs-lookup"><span data-stu-id="0e110-148">The following code shows how to create an aggregate type that consists of individual floating point values that have units that are generic.</span></span> <span data-ttu-id="0e110-149">Esto permite que un tipo único al crearse que funciona con una variedad de unidades.</span><span class="sxs-lookup"><span data-stu-id="0e110-149">This enables a single type to be created that works with a variety of units.</span></span> <span data-ttu-id="0e110-150">Además, unidades genéricas conservan la seguridad de tipos al garantizar que un tipo genérico que tiene un conjunto de unidades es un tipo diferente que el mismo tipo genérico con un conjunto diferente de unidades.</span><span class="sxs-lookup"><span data-stu-id="0e110-150">Also, generic units preserve type safety by ensuring that a generic type that has one set of units is a different type than the same generic type with a different set of units.</span></span> <span data-ttu-id="0e110-151">La base de esta técnica es que la `Measure` atributo se puede aplicar al parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="0e110-151">The basis of this technique is that the `Measure` attribute can be applied to the type parameter.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]
    
## <a name="units-at-runtime"></a><span data-ttu-id="0e110-152">Unidades en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="0e110-152">Units at Runtime</span></span>
<span data-ttu-id="0e110-153">Unidades de medida se utilizan para la comprobación de tipos estáticos.</span><span class="sxs-lookup"><span data-stu-id="0e110-153">Units of measure are used for static type checking.</span></span> <span data-ttu-id="0e110-154">Cuando se compilan los valores de punto flotante, se eliminan las unidades de medida, por lo que las unidades se pierden en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0e110-154">When floating point values are compiled, the units of measure are eliminated, so the units are lost at run time.</span></span> <span data-ttu-id="0e110-155">Por lo tanto, cualquier intento de implementar la funcionalidad que depende de la comprobación de las unidades en tiempo de ejecución no es posible.</span><span class="sxs-lookup"><span data-stu-id="0e110-155">Therefore, any attempt to implement functionality that depends on checking the units at run time is not possible.</span></span> <span data-ttu-id="0e110-156">Por ejemplo, implementar un `ToString` función para imprimir las unidades no es posible.</span><span class="sxs-lookup"><span data-stu-id="0e110-156">For example, implementing a `ToString` function to print out the units is not possible.</span></span>


## <a name="conversions"></a><span data-ttu-id="0e110-157">Conversiones</span><span class="sxs-lookup"><span data-stu-id="0e110-157">Conversions</span></span>
<span data-ttu-id="0e110-158">Para convertir un tipo que tiene unidades (por ejemplo, `float<'u>`) a un tipo que no tiene unidades, puede utilizar la función de conversión estándar.</span><span class="sxs-lookup"><span data-stu-id="0e110-158">To convert a type that has units (for example, `float<'u>`) to a type that does not have units, you can use the standard conversion function.</span></span> <span data-ttu-id="0e110-159">Por ejemplo, puede usar `float` para convertir en un `float` valor que no tiene unidades, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="0e110-159">For example, you can use `float` to convert to a `float` value that does not have units, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

<span data-ttu-id="0e110-160">Para convertir un valor sin unidades en un valor que contiene unidades, puede multiplicar por un valor de 1 ó 1,0 que se anota con las unidades correspondientes.</span><span class="sxs-lookup"><span data-stu-id="0e110-160">To convert a unitless value to a value that has units, you can multiply by a 1 or 1.0 value that is annotated with the appropriate units.</span></span> <span data-ttu-id="0e110-161">Sin embargo, para escribir niveles de interoperabilidad, también hay algunas funciones explícitas que puede utilizar para convertir los valores sin unidades en valores con unidades.</span><span class="sxs-lookup"><span data-stu-id="0e110-161">However, for writing interoperability layers, there are also some explicit functions that you can use to convert unitless values to values with units.</span></span> <span data-ttu-id="0e110-162">Se trata de la [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) módulo.</span><span class="sxs-lookup"><span data-stu-id="0e110-162">These are in the [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) module.</span></span> <span data-ttu-id="0e110-163">Por ejemplo, para convertir de una sin unidades `float` a una `float<cm>`, use [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="0e110-163">For example, to convert from a unitless `float` to a `float<cm>`, use [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]
    
## <a name="units-of-measure-in-the-f-power-pack"></a><span data-ttu-id="0e110-164">Unidades de medida en el módulo de F # Power</span><span class="sxs-lookup"><span data-stu-id="0e110-164">Units of Measure in the F# Power Pack</span></span>
<span data-ttu-id="0e110-165">Una biblioteca de unidades está disponible en F # PowerPack.</span><span class="sxs-lookup"><span data-stu-id="0e110-165">A unit library is available in the F# PowerPack.</span></span> <span data-ttu-id="0e110-166">La biblioteca de unidad incluye las unidades y constantes físicas.</span><span class="sxs-lookup"><span data-stu-id="0e110-166">The unit library includes SI units and physical constants.</span></span>


## <a name="see-also"></a><span data-ttu-id="0e110-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e110-167">See Also</span></span>
[<span data-ttu-id="0e110-168">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="0e110-168">F# Language Reference</span></span>](index.md)
