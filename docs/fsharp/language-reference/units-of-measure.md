---
title: Unidades de medida
description: 'Obtenga información sobre cómo los valores de punto flotante y entero con signo en F # pueden tener asociadas unidades de medida, que se suelen usar para indicar la longitud, el volumen y la masa.'
ms.date: 08/15/2020
ms.openlocfilehash: 0262f89e80697dd86161c93fe37381122972b56f
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811579"
---
# <a name="units-of-measure"></a><span data-ttu-id="e3513-103">Unidades de medida</span><span class="sxs-lookup"><span data-stu-id="e3513-103">Units of Measure</span></span>

<span data-ttu-id="e3513-104">Los valores de punto flotante y entero con signo en F # pueden tener asociadas unidades de medida, que se suelen usar para indicar la longitud, el volumen, la masa, etc.</span><span class="sxs-lookup"><span data-stu-id="e3513-104">Floating point and signed integer values in F# can have associated units of measure, which are typically used to indicate length, volume, mass, and so on.</span></span> <span data-ttu-id="e3513-105">Mediante el uso de cantidades con unidades, se habilita el compilador para comprobar que las relaciones aritméticas tienen las unidades correctas, lo que ayuda a evitar errores de programación.</span><span class="sxs-lookup"><span data-stu-id="e3513-105">By using quantities with units, you enable the compiler to verify that arithmetic relationships have the correct units, which helps prevent programming errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="e3513-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3513-106">Syntax</span></span>

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a><span data-ttu-id="e3513-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e3513-107">Remarks</span></span>

<span data-ttu-id="e3513-108">La sintaxis anterior define el *nombre de unidad* como unidad de medida.</span><span class="sxs-lookup"><span data-stu-id="e3513-108">The previous syntax defines *unit-name* as a unit of measure.</span></span> <span data-ttu-id="e3513-109">El elemento opcional se utiliza para definir una nueva medida en términos de unidades definidas previamente.</span><span class="sxs-lookup"><span data-stu-id="e3513-109">The optional part is used to define a new measure in terms of previously defined units.</span></span> <span data-ttu-id="e3513-110">Por ejemplo, la línea siguiente define la medida `cm` (centímetro).</span><span class="sxs-lookup"><span data-stu-id="e3513-110">For example, the following line defines the measure `cm` (centimeter).</span></span>

```fsharp
[<Measure>] type cm
```

<span data-ttu-id="e3513-111">En la línea siguiente se define la medida `ml` (milliliter) como un centímetro cúbico ( `cm^3` ).</span><span class="sxs-lookup"><span data-stu-id="e3513-111">The following line defines the measure `ml` (milliliter) as a cubic centimeter (`cm^3`).</span></span>

```fsharp
[<Measure>] type ml = cm^3
```

<span data-ttu-id="e3513-112">En la sintaxis anterior, *Measure* es una fórmula que implica unidades.</span><span class="sxs-lookup"><span data-stu-id="e3513-112">In the previous syntax, *measure* is a formula that involves units.</span></span> <span data-ttu-id="e3513-113">En las fórmulas que implican unidades, se admiten las potencias enteras (positivas y negativas), los espacios entre las unidades indican un producto de las dos unidades, `*` también indica un producto de unidades e `/` indica un cociente de unidades.</span><span class="sxs-lookup"><span data-stu-id="e3513-113">In formulas that involve units, integral powers are supported (positive and negative), spaces between units indicate a product of the two units, `*` also indicates a product of units, and `/` indicates a quotient of units.</span></span> <span data-ttu-id="e3513-114">En el caso de una unidad recíproca, puede usar una potencia entera negativa o una `/` que indique una separación entre el numerador y el denominador de una fórmula de unidad.</span><span class="sxs-lookup"><span data-stu-id="e3513-114">For a reciprocal unit, you can either use a negative integer power or a `/` that indicates a separation between the numerator and denominator of a unit formula.</span></span> <span data-ttu-id="e3513-115">Varias unidades del denominador deben ir entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="e3513-115">Multiple units in the denominator should be surrounded by parentheses.</span></span> <span data-ttu-id="e3513-116">Las unidades separadas por espacios después de un `/` se interpretan como parte del denominador, pero las unidades que siguen a un `*` se interpretan como parte del numerador.</span><span class="sxs-lookup"><span data-stu-id="e3513-116">Units separated by spaces after a `/` are interpreted as being part of the denominator, but any units following a `*` are interpreted as being part of the numerator.</span></span>

<span data-ttu-id="e3513-117">Puede usar 1 en expresiones unitarias, ya sea solo para indicar una cantidad sin dimensiones, o junto con otras unidades, como en el numerador.</span><span class="sxs-lookup"><span data-stu-id="e3513-117">You can use 1 in unit expressions, either alone to indicate a dimensionless quantity, or together with other units, such as in the numerator.</span></span> <span data-ttu-id="e3513-118">Por ejemplo, las unidades de una tasa se escribirían como `1/s` , donde `s` indica segundos.</span><span class="sxs-lookup"><span data-stu-id="e3513-118">For example, the units for a rate would be written as `1/s`, where `s` indicates seconds.</span></span> <span data-ttu-id="e3513-119">No se usan paréntesis en las fórmulas unitarias.</span><span class="sxs-lookup"><span data-stu-id="e3513-119">Parentheses are not used in unit formulas.</span></span> <span data-ttu-id="e3513-120">No se especifican constantes de conversión numéricas en las fórmulas unitarias; sin embargo, puede definir constantes de conversión con unidades por separado y usarlas en cálculos con comprobación unitaria.</span><span class="sxs-lookup"><span data-stu-id="e3513-120">You do not specify numeric conversion constants in the unit formulas; however, you can define conversion constants with units separately and use them in unit-checked computations.</span></span>

<span data-ttu-id="e3513-121">Las fórmulas de unidad que significan lo mismo pueden escribirse de varias formas equivalentes.</span><span class="sxs-lookup"><span data-stu-id="e3513-121">Unit formulas that mean the same thing can be written in various equivalent ways.</span></span> <span data-ttu-id="e3513-122">Por lo tanto, el compilador convierte las fórmulas unitarias en un formato coherente, que convierte las potencias negativas en recíprocos, agrupa las unidades en un solo numerador y un denominador, y alphabetizes las unidades en el numerador y el denominador.</span><span class="sxs-lookup"><span data-stu-id="e3513-122">Therefore, the compiler converts unit formulas into a consistent form, which converts negative powers to reciprocals, groups units into a single numerator and a denominator, and alphabetizes the units in the numerator and denominator.</span></span>

<span data-ttu-id="e3513-123">Por ejemplo, las fórmulas de unidad `kg m s^-2` y `m /s s * kg` se convierten en `kg m/s^2` .</span><span class="sxs-lookup"><span data-stu-id="e3513-123">For example, the unit formulas `kg m s^-2` and `m /s s * kg` are both converted to `kg m/s^2`.</span></span>

<span data-ttu-id="e3513-124">En las expresiones de punto flotante se usan unidades de medida.</span><span class="sxs-lookup"><span data-stu-id="e3513-124">You use units of measure in floating point expressions.</span></span> <span data-ttu-id="e3513-125">El uso de números de punto flotante junto con unidades de medida asociadas agrega otro nivel de seguridad de tipos y ayuda a evitar los errores de no coincidencia de unidad que se pueden producir en las fórmulas cuando se utilizan números de punto flotante débilmente tipados.</span><span class="sxs-lookup"><span data-stu-id="e3513-125">Using floating point numbers together with associated units of measure adds another level of type safety and helps avoid the unit mismatch errors that can occur in formulas when you use weakly typed floating point numbers.</span></span> <span data-ttu-id="e3513-126">Si escribe una expresión de punto flotante que utiliza unidades, las unidades de la expresión deben coincidir.</span><span class="sxs-lookup"><span data-stu-id="e3513-126">If you write a floating point expression that uses units, the units in the expression must match.</span></span>

<span data-ttu-id="e3513-127">Puede anotar literales con una fórmula de unidad entre corchetes angulares, tal como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="e3513-127">You can annotate literals with a unit formula in angle brackets, as shown in the following examples.</span></span>

```fsharp
1.0<cm>
55.0<miles/hour>
```

<span data-ttu-id="e3513-128">No se coloca un espacio entre el número y el corchete angular; sin embargo, puede incluir un sufijo literal como `f` , como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e3513-128">You do not put a space between the number and the angle bracket; however, you can include a literal suffix such as `f`, as in the following example.</span></span>

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

<span data-ttu-id="e3513-129">Esta anotación cambia el tipo del literal de su tipo primitivo (como `float` ) a un tipo de dimensión, como `float<cm>` o, en este caso, `float<miles/hour>` .</span><span class="sxs-lookup"><span data-stu-id="e3513-129">Such an annotation changes the type of the literal from its primitive type (such as `float`) to a dimensioned type, such as `float<cm>` or, in this case, `float<miles/hour>`.</span></span> <span data-ttu-id="e3513-130">Una anotación de unidad de `<1>` indica una cantidad sin dimensiones y su tipo es equivalente al tipo primitivo sin un parámetro de unidad.</span><span class="sxs-lookup"><span data-stu-id="e3513-130">A unit annotation of `<1>` indicates a dimensionless quantity, and its type is equivalent to the primitive type without a unit parameter.</span></span>

<span data-ttu-id="e3513-131">El tipo de una unidad de medida es un tipo de punto flotante o entero con signo junto con una anotación de unidad adicional, indicado entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="e3513-131">The type of a unit of measure is a floating point or signed integral type together with an extra unit annotation, indicated in brackets.</span></span> <span data-ttu-id="e3513-132">Por lo tanto, al escribir el tipo de una conversión de `g` (gramos) a `kg` (kilogramos), se describen los tipos de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="e3513-132">Thus, when you write the type of a conversion from `g` (grams) to `kg` (kilograms), you describe the types as follows.</span></span>

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

<span data-ttu-id="e3513-133">Las unidades de medida se utilizan para la comprobación unitaria en tiempo de compilación pero no se conservan en el entorno en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e3513-133">Units of measure are used for compile-time unit checking but are not persisted in the run-time environment.</span></span> <span data-ttu-id="e3513-134">Por lo tanto, no afectan al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="e3513-134">Therefore, they do not affect performance.</span></span>

<span data-ttu-id="e3513-135">Las unidades de medida se pueden aplicar a cualquier tipo, no solo a los tipos de punto flotante; sin embargo, solo los tipos de punto flotante, los tipos enteros con signo y los tipos decimales admiten cantidades dimensionales.</span><span class="sxs-lookup"><span data-stu-id="e3513-135">Units of measure can be applied to any type, not just floating point types; however, only floating point types, signed integral types, and decimal types support dimensioned quantities.</span></span> <span data-ttu-id="e3513-136">Por lo tanto, solo tiene sentido utilizar unidades de medida en los tipos primitivos y en los agregados que contienen estos tipos primitivos.</span><span class="sxs-lookup"><span data-stu-id="e3513-136">Therefore, it only makes sense to use units of measure on the primitive types and on aggregates that contain these primitive types.</span></span>

<span data-ttu-id="e3513-137">En el ejemplo siguiente se muestra el uso de unidades de medida.</span><span class="sxs-lookup"><span data-stu-id="e3513-137">The following example illustrates the use of units of measure.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]

<span data-ttu-id="e3513-138">En el ejemplo de código siguiente se muestra cómo convertir un número de punto flotante no dimensional en un valor de punto flotante de dimensión.</span><span class="sxs-lookup"><span data-stu-id="e3513-138">The following code example illustrates how to convert from a dimensionless floating point number to a dimensioned floating point value.</span></span> <span data-ttu-id="e3513-139">Solo tiene que multiplicar por 1,0 y aplicar las dimensiones a 1,0.</span><span class="sxs-lookup"><span data-stu-id="e3513-139">You just multiply by 1.0, applying the dimensions to the 1.0.</span></span> <span data-ttu-id="e3513-140">Puede abstraerlo en una función como `degreesFahrenheit` .</span><span class="sxs-lookup"><span data-stu-id="e3513-140">You can abstract this into a function like `degreesFahrenheit`.</span></span>

<span data-ttu-id="e3513-141">Además, cuando pase valores con dimensiones a funciones que esperan números de punto flotante sin dimensiones, debe cancelar las unidades o convertirlos en `float` mediante el `float` operador.</span><span class="sxs-lookup"><span data-stu-id="e3513-141">Also, when you pass dimensioned values to functions that expect dimensionless floating point numbers, you must cancel out the units or cast to `float` by using the `float` operator.</span></span> <span data-ttu-id="e3513-142">En este ejemplo, se divide por `1.0<degC>` para los argumentos en `printf` porque `printf` espera cantidades no dimensionales.</span><span class="sxs-lookup"><span data-stu-id="e3513-142">In this example, you divide by `1.0<degC>` for the arguments to `printf` because `printf` expects dimensionless quantities.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

<span data-ttu-id="e3513-143">En la sesión de ejemplo siguiente se muestran los resultados de las entradas y en este código.</span><span class="sxs-lookup"><span data-stu-id="e3513-143">The following example session shows the outputs from and inputs to this code.</span></span>

```console
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a><span data-ttu-id="e3513-144">Uso de unidades genéricas</span><span class="sxs-lookup"><span data-stu-id="e3513-144">Using Generic Units</span></span>

<span data-ttu-id="e3513-145">Puede escribir funciones genéricas que operan en datos que tienen una unidad de medida asociada.</span><span class="sxs-lookup"><span data-stu-id="e3513-145">You can write generic functions that operate on data that has an associated unit of measure.</span></span> <span data-ttu-id="e3513-146">Para ello, especifique un tipo junto con una unidad genérica como parámetro de tipo, tal y como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="e3513-146">You do this by specifying a type together with a generic unit as a type parameter, as shown in the following code example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]

## <a name="creating-aggregate-types-with-generic-units"></a><span data-ttu-id="e3513-147">Crear tipos de agregado con unidades genéricas</span><span class="sxs-lookup"><span data-stu-id="e3513-147">Creating Aggregate Types with Generic Units</span></span>

<span data-ttu-id="e3513-148">En el código siguiente se muestra cómo crear un tipo de agregado que consta de valores de punto flotante individuales que tienen unidades que son genéricas.</span><span class="sxs-lookup"><span data-stu-id="e3513-148">The following code shows how to create an aggregate type that consists of individual floating point values that have units that are generic.</span></span> <span data-ttu-id="e3513-149">Esto permite crear un único tipo que funciona con una variedad de unidades.</span><span class="sxs-lookup"><span data-stu-id="e3513-149">This enables a single type to be created that works with a variety of units.</span></span> <span data-ttu-id="e3513-150">Además, las unidades genéricas conservan la seguridad de tipos asegurándose de que un tipo genérico que tiene un conjunto de unidades es un tipo diferente del mismo tipo genérico con un conjunto de unidades diferente.</span><span class="sxs-lookup"><span data-stu-id="e3513-150">Also, generic units preserve type safety by ensuring that a generic type that has one set of units is a different type than the same generic type with a different set of units.</span></span> <span data-ttu-id="e3513-151">La base de esta técnica es que el `Measure` atributo se puede aplicar al parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="e3513-151">The basis of this technique is that the `Measure` attribute can be applied to the type parameter.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]

## <a name="units-at-runtime"></a><span data-ttu-id="e3513-152">Unidades en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="e3513-152">Units at Runtime</span></span>

<span data-ttu-id="e3513-153">Las unidades de medida se utilizan para la comprobación de tipos estáticos.</span><span class="sxs-lookup"><span data-stu-id="e3513-153">Units of measure are used for static type checking.</span></span> <span data-ttu-id="e3513-154">Cuando se compilan los valores de punto flotante, se eliminan las unidades de medida, por lo que las unidades se pierden en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e3513-154">When floating point values are compiled, the units of measure are eliminated, so the units are lost at run time.</span></span> <span data-ttu-id="e3513-155">Por lo tanto, no es posible cualquier intento de implementar la funcionalidad que depende de la comprobación de las unidades en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e3513-155">Therefore, any attempt to implement functionality that depends on checking the units at run time is not possible.</span></span> <span data-ttu-id="e3513-156">Por ejemplo, `ToString` no es posible implementar una función para imprimir las unidades.</span><span class="sxs-lookup"><span data-stu-id="e3513-156">For example, implementing a `ToString` function to print out the units is not possible.</span></span>

## <a name="conversions"></a><span data-ttu-id="e3513-157">Conversiones</span><span class="sxs-lookup"><span data-stu-id="e3513-157">Conversions</span></span>

<span data-ttu-id="e3513-158">Para convertir un tipo que tiene unidades (por ejemplo, `float<'u>` ) en un tipo que no tiene unidades, puede usar la función de conversión estándar.</span><span class="sxs-lookup"><span data-stu-id="e3513-158">To convert a type that has units (for example, `float<'u>`) to a type that does not have units, you can use the standard conversion function.</span></span> <span data-ttu-id="e3513-159">Por ejemplo, puede usar `float` para convertir en un `float` valor que no tiene unidades, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="e3513-159">For example, you can use `float` to convert to a `float` value that does not have units, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

<span data-ttu-id="e3513-160">Para convertir un valor sin unidades en un valor que tiene unidades, puede multiplicar por un valor 1 o 1,0 anotado con las unidades adecuadas.</span><span class="sxs-lookup"><span data-stu-id="e3513-160">To convert a unitless value to a value that has units, you can multiply by a 1 or 1.0 value that is annotated with the appropriate units.</span></span> <span data-ttu-id="e3513-161">Sin embargo, para escribir capas de interoperabilidad, también hay algunas funciones explícitas que puede usar para convertir valores sin unidades en valores con unidades.</span><span class="sxs-lookup"><span data-stu-id="e3513-161">However, for writing interoperability layers, there are also some explicit functions that you can use to convert unitless values to values with units.</span></span> <span data-ttu-id="e3513-162">Se encuentran en el módulo [FSharp. Core. LanguagePrimitives](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-languageprimitives.html) .</span><span class="sxs-lookup"><span data-stu-id="e3513-162">These are in the [FSharp.Core.LanguagePrimitives](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-languageprimitives.html) module.</span></span> <span data-ttu-id="e3513-163">Por ejemplo, para convertir de una unidad `float` a una `float<cm>` , use [floatwithmeasure (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-languageprimitives.html#FloatWithMeasure), tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="e3513-163">For example, to convert from a unitless `float` to a `float<cm>`, use [FloatWithMeasure](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-languageprimitives.html#FloatWithMeasure), as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]

## <a name="units-of-measure-in-the-f-core-library"></a><span data-ttu-id="e3513-164">Unidades de medida en la biblioteca básica de F #</span><span class="sxs-lookup"><span data-stu-id="e3513-164">Units of Measure in the F# Core library</span></span>

<span data-ttu-id="e3513-165">Una biblioteca de unidades está disponible en el `FSharp.Data.UnitSystems.SI` espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e3513-165">A unit library is available in the `FSharp.Data.UnitSystems.SI` namespace.</span></span> <span data-ttu-id="e3513-166">Incluye las unidades SI en su forma de símbolo (como `m` para el medidor) en el `UnitSymbols` subespacio de nombres y su nombre completo (como `meter` para el medidor) en el `UnitNames` subespacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e3513-166">It includes SI units in both their symbol form (like `m` for meter) in the `UnitSymbols` sub-namespace, and their full name (like `meter` for meter) in the `UnitNames` sub-namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3513-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3513-167">See also</span></span>

- [<span data-ttu-id="e3513-168">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="e3513-168">F# Language Reference</span></span>](index.md)
