---
title: Instrucciones de formato de código de F#
description: 'Obtenga información sobre las directrices para dar formato a código de F #.'
ms.date: 11/04/2019
ms.openlocfilehash: dc871b0a8461ed93550ab02cc2c66b143285a3e3
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720155"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="2bc5c-103">Instrucciones de formato de código de F#</span><span class="sxs-lookup"><span data-stu-id="2bc5c-103">F# code formatting guidelines</span></span>

<span data-ttu-id="2bc5c-104">En este artículo se proporcionan instrucciones sobre cómo dar formato al código para que el código de F # sea:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="2bc5c-105">Más legible</span><span class="sxs-lookup"><span data-stu-id="2bc5c-105">More legible</span></span>
* <span data-ttu-id="2bc5c-106">De acuerdo con las convenciones aplicadas por las herramientas de formato en Visual Studio y otros editores</span><span class="sxs-lookup"><span data-stu-id="2bc5c-106">In accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="2bc5c-107">Similar a otro código en línea</span><span class="sxs-lookup"><span data-stu-id="2bc5c-107">Similar to other code online</span></span>

<span data-ttu-id="2bc5c-108">Estas instrucciones se basan en [una guía completa de las convenciones de formato de F #](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) por [Anh-estiércol Phan](https://github.com/dungpa).</span><span class="sxs-lookup"><span data-stu-id="2bc5c-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="2bc5c-109">Reglas generales para la sangría</span><span class="sxs-lookup"><span data-stu-id="2bc5c-109">General rules for indentation</span></span>

<span data-ttu-id="2bc5c-110">F # utiliza de forma predeterminada un espacio en blanco significativo.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-110">F# uses significant white space by default.</span></span> <span data-ttu-id="2bc5c-111">Las instrucciones siguientes están pensadas para proporcionar orientación sobre cómo llevar a cabo algunos desafíos que esto puede imponer.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="2bc5c-112">Usar espacios</span><span class="sxs-lookup"><span data-stu-id="2bc5c-112">Using spaces</span></span>

<span data-ttu-id="2bc5c-113">Cuando se requiere la sangría, debe usar espacios, no pestañas.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="2bc5c-114">Se requiere al menos un espacio.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-114">At least one space is required.</span></span> <span data-ttu-id="2bc5c-115">Su organización puede crear estándares de codificación para especificar el número de espacios que se usarán para la sangría; dos, tres o cuatro espacios de sangría en cada nivel en que se produce la sangría es típico.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three, or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="2bc5c-116">**Se recomiendan cuatro espacios por sangría.**</span><span class="sxs-lookup"><span data-stu-id="2bc5c-116">**We recommend four spaces per indentation.**</span></span>

<span data-ttu-id="2bc5c-117">Dicho esto, la sangría de los programas es una cuestión subjetiva.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="2bc5c-118">Las variaciones son correctas, pero la primera regla que debe seguir es la *coherencia de la sangría*.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="2bc5c-119">Elija un estilo de sangría aceptado generalmente y úselo sistemáticamente en el código base.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-white-space"></a><span data-ttu-id="2bc5c-120">Aplicar formato a los espacios en blanco</span><span class="sxs-lookup"><span data-stu-id="2bc5c-120">Formatting white space</span></span>

<span data-ttu-id="2bc5c-121">F # es un espacio en blanco sensible.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-121">F# is white space sensitive.</span></span> <span data-ttu-id="2bc5c-122">Aunque la mayoría de las semánticas de los espacios en blanco se describen mediante una sangría adecuada, hay otros aspectos que hay que tener en cuenta.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-122">Although most semantics from white space are covered by proper indentation, there are some other things to consider.</span></span>

### <a name="formatting-operators-in-arithmetic-expressions"></a><span data-ttu-id="2bc5c-123">Aplicar formato a operadores en expresiones aritméticas</span><span class="sxs-lookup"><span data-stu-id="2bc5c-123">Formatting operators in arithmetic expressions</span></span>

<span data-ttu-id="2bc5c-124">Use siempre el espacio en blanco alrededor de las expresiones aritméticas binarias:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-124">Always use white space around binary arithmetic expressions:</span></span>

```fsharp
let subtractThenAdd x = x - 1 + 3
```

<span data-ttu-id="2bc5c-125">`-`Los operadores unarios siempre deben ir seguidos inmediatamente del valor que están negando:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-125">Unary `-` operators should always be immediately followed by the value they are negating:</span></span>

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

<span data-ttu-id="2bc5c-126">Agregar un carácter de espacio en blanco después del `-` operador puede provocar confusión en otros.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-126">Adding a white-space character after the `-` operator can lead to confusion for others.</span></span>

<span data-ttu-id="2bc5c-127">En Resumen, es importante que siempre:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-127">In summary, it's important to always:</span></span>

* <span data-ttu-id="2bc5c-128">Operadores binarios de envolvente con espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="2bc5c-128">Surround binary operators with white space</span></span>
* <span data-ttu-id="2bc5c-129">Nunca debe haber un espacio en blanco al final después de un operador unario</span><span class="sxs-lookup"><span data-stu-id="2bc5c-129">Never have trailing white space after a unary operator</span></span>

<span data-ttu-id="2bc5c-130">La instrucción del operador aritmético binario es especialmente importante.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-130">The binary arithmetic operator guideline is especially important.</span></span> <span data-ttu-id="2bc5c-131">Si no se rodea un operador binario `-` , cuando se combina con determinadas opciones de formato, podría interpretarlo como unario `-` .</span><span class="sxs-lookup"><span data-stu-id="2bc5c-131">Failing to surround a binary `-` operator, when combined with certain formatting choices, could lead to interpreting it as a unary `-`.</span></span>

### <a name="surround-a-custom-operator-definition-with-white-space"></a><span data-ttu-id="2bc5c-132">Envolver una definición de operador personalizado con espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="2bc5c-132">Surround a custom operator definition with white space</span></span>

<span data-ttu-id="2bc5c-133">Use siempre el espacio en blanco para rodear una definición de operador:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-133">Always use white space to surround an operator definition:</span></span>

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

<span data-ttu-id="2bc5c-134">Para cualquier operador personalizado que empiece por `*` y que tenga más de un carácter, debe agregar un espacio en blanco al principio de la definición para evitar la ambigüedad del compilador.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-134">For any custom operator that starts with `*` and that has more than one character, you need to add a white space to the beginning of the definition to avoid a compiler ambiguity.</span></span> <span data-ttu-id="2bc5c-135">Por este motivo, se recomienda que solo incluya las definiciones de todos los operadores con un solo carácter de espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-135">Because of this, we recommend that you simply surround the definitions of all operators with a single white-space character.</span></span>

### <a name="surround-function-parameter-arrows-with-white-space"></a><span data-ttu-id="2bc5c-136">Flechas de parámetros de función envolvente con espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="2bc5c-136">Surround function parameter arrows with white space</span></span>

<span data-ttu-id="2bc5c-137">Al definir la firma de una función, use el espacio en blanco que rodea el `->` símbolo:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-137">When defining the signature of a function, use white space around the `->` symbol:</span></span>

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a><span data-ttu-id="2bc5c-138">Rodear argumentos de función con espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="2bc5c-138">Surround function arguments with white space</span></span>

<span data-ttu-id="2bc5c-139">Al definir una función, use el espacio en blanco alrededor de cada argumento.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-139">When defining a function, use white space around each argument.</span></span>

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="place-parameters-on-a-new-line-for-long-definitions"></a><span data-ttu-id="2bc5c-140">Colocar parámetros en una línea nueva para definiciones largas</span><span class="sxs-lookup"><span data-stu-id="2bc5c-140">Place parameters on a new line for long definitions</span></span>

<span data-ttu-id="2bc5c-141">Si tiene una definición de función muy larga, coloque los parámetros en nuevas líneas y aplíqueles sangría para que coincidan con el nivel de sangría del parámetro subsiguiente.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-141">If you have a very long function definition, place the parameters on new lines and indent them to match the indentation level of the subsequent parameter.</span></span>

```fsharp
module M =
    let LongFunctionWithLotsOfParameters(aVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                        (aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                        (aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                        =
        // ... the body of the method follows
```

<span data-ttu-id="2bc5c-142">Esto también se aplica a los miembros, constructores y parámetros mediante tuplas:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-142">This also applies to members, constructors, and parameters using tuples:</span></span>

```fsharp
type TM() =
    member _.LongMethodWithLotsOfParameters(aVeryLongParam: AVeryLongTypeThatYouNeedToUse,
                                            aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse,
                                            aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse) =
        // ... the body of the method

type TC(aVeryLongCtorParam: AVeryLongTypeThatYouNeedToUse,
        aSecondVeryLongCtorParam: AVeryLongTypeThatYouNeedToUse,
        aThirdVeryLongCtorParam: AVeryLongTypeThatYouNeedToUse) =
    // ... the body of the class follows
```

<span data-ttu-id="2bc5c-143">Si los parámetros son currified o hay una anotación de tipo de valor devuelto explícita, es preferible colocar el `=` carácter en una nueva línea:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-143">If the parameters are currified or there's an explicit return type annotation, it is preferable to place the `=` character on a new line:</span></span>

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(aVeryLongParam: AVeryLongTypeThatYouNeedToUse,
                                            aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse,
                                            aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                            : AReturnType =
        // ... the body of the method
    member _.LongMethodWithLotsOfCurrifiedParams(aVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                                (aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                                (aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                                =
        // ... the body of the method
```

<span data-ttu-id="2bc5c-144">Se trata de una manera de evitar líneas demasiado largas (en caso de que el tipo de valor devuelto tenga un nombre largo) y tener menos daños en la línea al agregar parámetros.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-144">This is a way to avoid too long lines (in case return type might have long name) and have less line-damage when adding parameters.</span></span>

### <a name="type-annotations"></a><span data-ttu-id="2bc5c-145">Anotaciones de tipo</span><span class="sxs-lookup"><span data-stu-id="2bc5c-145">Type annotations</span></span>

#### <a name="right-pad-function-argument-type-annotations"></a><span data-ttu-id="2bc5c-146">Anotaciones del tipo de argumento de la función del botón secundario</span><span class="sxs-lookup"><span data-stu-id="2bc5c-146">Right-pad function argument type annotations</span></span>

<span data-ttu-id="2bc5c-147">Al definir argumentos con anotaciones de tipo, use el espacio en blanco después del `:` símbolo:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-147">When defining arguments with type annotations, use white space after the `:` symbol:</span></span>

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a><span data-ttu-id="2bc5c-148">Anotaciones de tipo de valor devuelto envolvente con espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="2bc5c-148">Surround return type annotations with white space</span></span>

<span data-ttu-id="2bc5c-149">En una anotación de tipo de valor o función enlazada a (tipo de valor devuelto en el caso de una función), use el espacio en blanco antes y después del `:` símbolo:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-149">In a let-bound function or value type annotation (return type in the case of a function), use white space before and after the `:` symbol:</span></span>

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a><span data-ttu-id="2bc5c-150">Aplicar formato a líneas en blanco</span><span class="sxs-lookup"><span data-stu-id="2bc5c-150">Formatting blank lines</span></span>

* <span data-ttu-id="2bc5c-151">Separe las definiciones de clase y de función de nivel superior con dos líneas en blanco.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-151">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="2bc5c-152">Las definiciones de método dentro de una clase se separan mediante una sola línea en blanco.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-152">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="2bc5c-153">Se pueden usar líneas en blanco adicionales (moderadamente) para separar grupos de funciones relacionadas.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-153">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="2bc5c-154">Es posible que se omitan líneas en blanco entre un grupo de una sola línea relacionada (por ejemplo, un conjunto de implementaciones ficticias).</span><span class="sxs-lookup"><span data-stu-id="2bc5c-154">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="2bc5c-155">Use líneas en blanco en las funciones, con moderación, para indicar secciones lógicas.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-155">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="2bc5c-156">Aplicar formato a comentarios</span><span class="sxs-lookup"><span data-stu-id="2bc5c-156">Formatting comments</span></span>

<span data-ttu-id="2bc5c-157">Normalmente, se prefieren varios comentarios de barra diagonal doble sobre los comentarios de bloque de estilo ML.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-157">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="2bc5c-158">Los comentarios en línea deben poner en mayúscula la primera letra.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-158">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="2bc5c-159">Convenciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="2bc5c-159">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="2bc5c-160">Usar camelCase para funciones y valores enlazados a expresiones y enlazados a un patrón</span><span class="sxs-lookup"><span data-stu-id="2bc5c-160">Use camelCase for class-bound, expression-bound, and pattern-bound values and functions</span></span>

<span data-ttu-id="2bc5c-161">Es común y acepta el estilo F # para usar camelCase para todos los nombres enlazados como variables locales o en coincidencias de patrones y definiciones de función.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-161">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="2bc5c-162">Las funciones enlazadas localmente en clases también deben usar camelCase.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-162">Locally bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="2bc5c-163">Usar camelCase para funciones públicas enlazadas a módulos</span><span class="sxs-lookup"><span data-stu-id="2bc5c-163">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="2bc5c-164">Cuando una función enlazada a un módulo forma parte de una API pública, debe usar camelCase:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-164">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="2bc5c-165">Usar camelCase para funciones y valores enlazados a módulos internos y privados</span><span class="sxs-lookup"><span data-stu-id="2bc5c-165">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="2bc5c-166">Use camelCase para valores enlazados a módulos privados, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-166">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="2bc5c-167">Funciones ad hoc en scripts</span><span class="sxs-lookup"><span data-stu-id="2bc5c-167">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="2bc5c-168">Valores que conforman la implementación interna de un módulo o tipo</span><span class="sxs-lookup"><span data-stu-id="2bc5c-168">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="2bc5c-169">Usar camelCase para los parámetros</span><span class="sxs-lookup"><span data-stu-id="2bc5c-169">Use camelCase for parameters</span></span>

<span data-ttu-id="2bc5c-170">Todos los parámetros deben usar camelCase de acuerdo con las convenciones de nomenclatura de .NET.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-170">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="2bc5c-171">Uso de PascalCase para módulos</span><span class="sxs-lookup"><span data-stu-id="2bc5c-171">Use PascalCase for modules</span></span>

<span data-ttu-id="2bc5c-172">Todos los módulos (de nivel superior, interno, privado, anidado) deben usar PascalCase.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-172">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="2bc5c-173">Usar PascalCase para las declaraciones de tipos, los miembros y las etiquetas</span><span class="sxs-lookup"><span data-stu-id="2bc5c-173">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="2bc5c-174">Todas las clases, interfaces, estructuras, enumeraciones, delegados, registros y uniones discriminadas deben llamarse con PascalCase.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-174">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="2bc5c-175">Los miembros de tipos y etiquetas para registros y uniones discriminadas también deben usar PascalCase.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-175">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

```fsharp
type IMyInterface =
    abstract Something: int

type MyClass() =
    member this.MyMethod(x, y) = x + y

type MyRecord = { IntVal: int; StringVal: string }

type SchoolPerson =
    | Professor
    | Student
    | Advisor
    | Administrator
```

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="2bc5c-176">Uso de PascalCase para construcciones intrínsecas de .NET</span><span class="sxs-lookup"><span data-stu-id="2bc5c-176">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="2bc5c-177">Los espacios de nombres, excepciones, eventos y proyectos/ `.dll` nombres también deben usar PascalCase.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-177">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="2bc5c-178">Esto no solo hace que el consumo de otros lenguajes .NET parezca más natural a los consumidores, sino que también es coherente con las convenciones de nomenclatura de .NET que es probable que encuentre.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-178">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="2bc5c-179">Evitar el carácter de subrayado en los nombres</span><span class="sxs-lookup"><span data-stu-id="2bc5c-179">Avoid underscores in names</span></span>

<span data-ttu-id="2bc5c-180">Históricamente, algunas bibliotecas de F # usaban guiones bajos en los nombres.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-180">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="2bc5c-181">Sin embargo, esto ya no se acepta ampliamente, en parte porque entra en conflicto con las convenciones de nomenclatura de .NET.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-181">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="2bc5c-182">Dicho esto, algunos programadores de F # usan subrayados en gran medida, en parte por motivos históricos, y la tolerancia y el respeto son importantes.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-182">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="2bc5c-183">Sin embargo, tenga en cuenta que el estilo suele estar deshabilitado por otros usuarios que tienen la opción de usarlos.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-183">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="2bc5c-184">Una excepción incluye la interoperabilidad con componentes nativos, donde los guiones bajos son comunes.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-184">One exception includes interoperating with native components, where underscores are common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="2bc5c-185">Usar operadores estándar de F #</span><span class="sxs-lookup"><span data-stu-id="2bc5c-185">Use standard F# operators</span></span>

<span data-ttu-id="2bc5c-186">Los operadores siguientes se definen en la biblioteca estándar de F # y deben usarse en lugar de definir equivalentes.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-186">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="2bc5c-187">Se recomienda usar estos operadores, ya que tiende a hacer que el código sea más legible y idiomático.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-187">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="2bc5c-188">Los desarrolladores con un fondo en OCaml u otro lenguaje de programación funcional pueden estar acostumbrados a diferentes expresiones.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-188">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="2bc5c-189">En la lista siguiente se resumen los operadores de F # recomendados.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-189">The following list summarizes the recommended F# operators.</span></span>

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Discard away a value
x + y // Overloaded addition (including string concatenation)
x - y // Overloaded subtraction
x * y // Overloaded multiplication
x / y // Overloaded division
x % y // Overloaded modulus
x && y // Lazy/short-cut "and"
x || y // Lazy/short-cut "or"
x <<< y // Bitwise left shift
x >>> y // Bitwise right shift
x ||| y // Bitwise or, also for working with “flags” enumeration
x &&& y // Bitwise and, also for working with “flags” enumeration
x ^^^ y // Bitwise xor, also for working with “flags” enumeration
```

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="2bc5c-190">Use la sintaxis de prefijo para genéricos ( `Foo<T>` ) en preferencia a la sintaxis de postfijo ( `T Foo` )</span><span class="sxs-lookup"><span data-stu-id="2bc5c-190">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="2bc5c-191">F # hereda el estilo de ambos postfijos de los tipos genéricos de nomenclatura (por ejemplo,), así `int list` como el estilo de .net de prefijo (por ejemplo, `list<int>` ).</span><span class="sxs-lookup"><span data-stu-id="2bc5c-191">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="2bc5c-192">Prefiera el estilo .NET, excepto para cinco tipos específicos:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-192">Prefer the .NET style, except for five specific types:</span></span>

1. <span data-ttu-id="2bc5c-193">En el caso de las listas de F #, use el formato de postfijo: `int list` en lugar de `list<int>` .</span><span class="sxs-lookup"><span data-stu-id="2bc5c-193">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="2bc5c-194">En el caso de las opciones de F #, use el formato de postfijo: `int option` en lugar de `option<int>` .</span><span class="sxs-lookup"><span data-stu-id="2bc5c-194">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="2bc5c-195">Para las opciones de valor de F #, use el formato de postfijo: `int voption` en lugar de `voption<int>` .</span><span class="sxs-lookup"><span data-stu-id="2bc5c-195">For F# Value Options, use the postfix form: `int voption` rather than `voption<int>`.</span></span>
4. <span data-ttu-id="2bc5c-196">En el caso de las matrices de F #, use el nombre sintáctico `int[]` en lugar de `int array` o `array<int>` .</span><span class="sxs-lookup"><span data-stu-id="2bc5c-196">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
5. <span data-ttu-id="2bc5c-197">En el caso de las celdas de referencia, use `int ref` en lugar de `ref<int>` o `Ref<int>` .</span><span class="sxs-lookup"><span data-stu-id="2bc5c-197">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="2bc5c-198">En el caso de todos los demás tipos, use el formato de prefijo.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-198">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="2bc5c-199">Dar formato a tuplas</span><span class="sxs-lookup"><span data-stu-id="2bc5c-199">Formatting tuples</span></span>

<span data-ttu-id="2bc5c-200">Una creación de instancias de tupla debe ir entre paréntesis y las comas delimitadoras deben ir seguidas de un solo espacio, por ejemplo: `(1, 2)` , `(x, y, z)` .</span><span class="sxs-lookup"><span data-stu-id="2bc5c-200">A tuple instantiation should be parenthesized, and the delimiting commas within it should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="2bc5c-201">Normalmente se acepta para omitir paréntesis en la coincidencia de patrones de tuplas:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-201">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

<span data-ttu-id="2bc5c-202">También se acepta normalmente para omitir los paréntesis si la tupla es el valor devuelto de una función:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-202">It is also commonly accepted to omit parentheses if the tuple is the return value of a function:</span></span>

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

<span data-ttu-id="2bc5c-203">En Resumen, se prefieren las instancias de tupla entre paréntesis, pero cuando se usan tuplas para la coincidencia de patrones o un valor devuelto, se considera adecuado para evitar paréntesis.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-203">In summary, prefer parenthesized tuple instantiations, but when using tuples for pattern matching or a return value, it is considered fine to avoid parentheses.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="2bc5c-204">Dar formato a las declaraciones de Unión discriminadas</span><span class="sxs-lookup"><span data-stu-id="2bc5c-204">Formatting discriminated union declarations</span></span>

<span data-ttu-id="2bc5c-205">Aplicar sangría `|` en la definición de tipo en cuatro espacios:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-205">Indent `|` in type definition by four spaces:</span></span>

```fsharp
// OK
type Volume =
    | Liter of float
    | FluidOunce of float
    | ImperialPint of float

// Not OK
type Volume =
| Liter of float
| USPint of float
| ImperialPint of float
```

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="2bc5c-206">Aplicar formato a uniones discriminadas</span><span class="sxs-lookup"><span data-stu-id="2bc5c-206">Formatting discriminated unions</span></span>

<span data-ttu-id="2bc5c-207">Las uniones discriminadas con instancias que se dividen entre varias líneas deben proporcionar a los datos contenidos un nuevo ámbito con sangría:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-207">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="2bc5c-208">El paréntesis de cierre también puede estar en una nueva línea:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-208">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="2bc5c-209">Dar formato a declaraciones de registro</span><span class="sxs-lookup"><span data-stu-id="2bc5c-209">Formatting record declarations</span></span>

<span data-ttu-id="2bc5c-210">Aplicar sangría `{` en la definición de tipo en cuatro espacios e iniciar la lista de campos en la misma línea:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-210">Indent `{` in type definition by four spaces and start the field list on the same line:</span></span>

```fsharp
// OK
type PostalAddress =
    { Address: string
      City: string
      Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Not OK
type PostalAddress =
  { Address: string
    City: string
    Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Unusual in F#
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
```

<span data-ttu-id="2bc5c-211">Es preferible colocar el token de apertura en una nueva línea y el token de cierre en una nueva línea si se declaran implementaciones de interfaz o miembros en el registro:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-211">Placing the opening token on a new line and the closing token on a new line is preferable if you are declaring interface implementations or members on the record:</span></span>

```fsharp
// Declaring additional members on PostalAddress
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface
```

## <a name="formatting-records"></a><span data-ttu-id="2bc5c-212">Aplicar formato a registros</span><span class="sxs-lookup"><span data-stu-id="2bc5c-212">Formatting records</span></span>

<span data-ttu-id="2bc5c-213">Los registros cortos se pueden escribir en una línea:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-213">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="2bc5c-214">Los registros que son más largas deben usar nuevas líneas para las etiquetas:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-214">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="2bc5c-215">Es preferible colocar el token de apertura en una nueva línea, el contenido con pestañas en un ámbito y el token de cierre en una nueva línea si:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-215">Placing the opening token on a new line, the contents tabbed over one scope, and the closing token on a new line is preferable if you are:</span></span>

* <span data-ttu-id="2bc5c-216">Mover registros en el código con diferentes ámbitos de sangría</span><span class="sxs-lookup"><span data-stu-id="2bc5c-216">Moving records around in code with different indentation scopes</span></span>
* <span data-ttu-id="2bc5c-217">Canalizarlos en una función</span><span class="sxs-lookup"><span data-stu-id="2bc5c-217">Piping them into a function</span></span>

```fsharp
let rainbow =
    {
        Boss1 = "Jeffrey"
        Boss2 = "Jeffrey"
        Boss3 = "Jeffrey"
        Boss4 = "Jeffrey"
        Boss5 = "Jeffrey"
        Boss6 = "Jeffrey"
        Boss7 = "Jeffrey"
        Boss8 = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"]
    }

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface

let foo a =
    a
    |> Option.map (fun x ->
        {
            MyField = x
        })
```

<span data-ttu-id="2bc5c-218">Las mismas reglas se aplican a los elementos de lista y matriz.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-218">The same rules apply for list and array elements.</span></span>

## <a name="formatting-copy-and-update-record-expressions"></a><span data-ttu-id="2bc5c-219">Dar formato a expresiones de registro de copia y actualización</span><span class="sxs-lookup"><span data-stu-id="2bc5c-219">Formatting copy-and-update record expressions</span></span>

<span data-ttu-id="2bc5c-220">Una expresión de registro de copia y actualización sigue siendo un registro, por lo que se aplican instrucciones similares.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-220">A copy-and-update record expression is still a record, so similar guidelines apply.</span></span>

<span data-ttu-id="2bc5c-221">Las expresiones cortas pueden caber en una línea:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-221">Short expressions can fit on one line:</span></span>

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

<span data-ttu-id="2bc5c-222">Las expresiones más largas deben usar nuevas líneas:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-222">Longer expressions should use new lines:</span></span>

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = [ "Zippy"; "George"; "Bungle" ] }
```

<span data-ttu-id="2bc5c-223">Y, al igual que con la guía de registro, puede que desee dedicar líneas independientes a las llaves y aplicar sangría a un ámbito a la derecha con la expresión.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-223">And as with the record guidance, you may want to dedicate separate lines for the braces and indent one scope to the right with the expression.</span></span> <span data-ttu-id="2bc5c-224">En algunos casos especiales, como el ajuste de un valor con un opcional sin paréntesis, puede que tenga que mantener una llave en una línea:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-224">In some special cases, such as wrapping a value with an optional without parentheses, you may need to keep a brace on one line:</span></span>

```fsharp
type S = { F1: int; F2: string }
type State = { F:  S option }

let state = { F = Some { F1 = 1; F2 = "Hello" } }
let newState =
    {
        state with
            F = Some {
                    F1 = 0
                    F2 = ""
                }
    }
```

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="2bc5c-225">Aplicar formato a listas y matrices</span><span class="sxs-lookup"><span data-stu-id="2bc5c-225">Formatting lists and arrays</span></span>

<span data-ttu-id="2bc5c-226">Escribe `x :: l` espacios alrededor del `::` operador ( `::` es un operador infijo, por lo que está rodeado por espacios).</span><span class="sxs-lookup"><span data-stu-id="2bc5c-226">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces).</span></span>

<span data-ttu-id="2bc5c-227">La lista y las matrices declaradas en una sola línea deben tener un espacio después del corchete de apertura y antes del corchete de cierre:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-227">List and arrays declared on a single line should have a space after the opening bracket and before the closing bracket:</span></span>

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

<span data-ttu-id="2bc5c-228">Utilice siempre al menos un espacio entre dos operadores distintivos de tipo llave.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-228">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="2bc5c-229">Por ejemplo, deje un espacio entre `[` y `{` .</span><span class="sxs-lookup"><span data-stu-id="2bc5c-229">For example, leave a space between a `[` and a `{`.</span></span>

```fsharp
// OK
[ { IngredientName = "Green beans"; Quantity = 250 }
  { IngredientName = "Pine nuts"; Quantity = 250 }
  { IngredientName = "Feta cheese"; Quantity = 250 }
  { IngredientName = "Olive oil"; Quantity = 10 }
  { IngredientName = "Lemon"; Quantity = 1 } ]

// Not OK
[{ IngredientName = "Green beans"; Quantity = 250 }
 { IngredientName = "Pine nuts"; Quantity = 250 }
 { IngredientName = "Feta cheese"; Quantity = 250 }
 { IngredientName = "Olive oil"; Quantity = 10 }
 { IngredientName = "Lemon"; Quantity = 1 }]
```

<span data-ttu-id="2bc5c-230">La misma instrucción se aplica a las listas o matrices de tuplas.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-230">The same guideline applies for lists or arrays of tuples.</span></span>

<span data-ttu-id="2bc5c-231">Las listas y matrices que se dividen entre varias líneas siguen una regla similar a la de los registros:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-231">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

```fsharp
let pascalsTriangle =
    [|
        [| 1 |]
        [| 1; 1 |]
        [| 1; 2; 1 |]
        [| 1; 3; 3; 1 |]
        [| 1; 4; 6; 4; 1 |]
        [| 1; 5; 10; 10; 5; 1 |]
        [| 1; 6; 15; 20; 15; 6; 1 |]
        [| 1; 7; 21; 35; 35; 21; 7; 1 |]
        [| 1; 8; 28; 56; 70; 56; 28; 8; 1 |]
    |]
```

<span data-ttu-id="2bc5c-232">Y como con los registros, la declaración de los corchetes de apertura y cierre en su propia línea hará que el código y la canalización en funciones sean más fáciles.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-232">And as with records, declaring the opening and closing brackets on their own line will make moving code around and piping into functions easier.</span></span>

<span data-ttu-id="2bc5c-233">Al generar matrices y listas mediante programación, `->` es preferible `do ... yield` cuando se genera siempre un valor:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-233">When generating arrays and lists programmatically, prefer `->` over `do ... yield` when a value is always generated:</span></span>

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x * x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x * x ]
```

<span data-ttu-id="2bc5c-234">Las versiones anteriores del lenguaje F # requerían especificar en situaciones en las que los `yield` datos se pueden generar de forma condicional, o puede haber expresiones consecutivas que se van a evaluar.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-234">Older versions of the F# language required specifying `yield` in situations where data may be generated conditionally, or there may be consecutive expressions to be evaluated.</span></span> <span data-ttu-id="2bc5c-235">Prefiera omitir estas `yield` palabras clave a menos que deba compilar con una versión anterior del lenguaje F #:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-235">Prefer omitting these `yield` keywords unless you must compile with an older F# language version:</span></span>

```fsharp
// Preferred
let daysOfWeek includeWeekend =
    [
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    ]

// Not preferred
let daysOfWeek' includeWeekend =
    [
        yield "Monday"
        yield "Tuesday"
        yield "Wednesday"
        yield "Thursday"
        yield "Friday"
        if includeWeekend then
            yield "Saturday"
            yield "Sunday"
    ]
```

<span data-ttu-id="2bc5c-236">En algunos casos, `do...yield` puede ayudar a mejorar la legibilidad.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-236">In some cases, `do...yield` may aid in readability.</span></span> <span data-ttu-id="2bc5c-237">Estos casos, aunque subjetiva, deben tenerse en cuenta.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-237">These cases, though subjective, should be taken into consideration.</span></span>

## <a name="formatting-if-expressions"></a><span data-ttu-id="2bc5c-238">Aplicar formato a expresiones if</span><span class="sxs-lookup"><span data-stu-id="2bc5c-238">Formatting if expressions</span></span>

<span data-ttu-id="2bc5c-239">La sangría de los condicionales depende del tamaño de las expresiones que los componen.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-239">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="2bc5c-240">Si `cond` `e1` y `e2` son cortos, simplemente escríbalos en una línea:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-240">If `cond`, `e1` and `e2` are short, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="2bc5c-241">Si `cond` , `e1` o `e2` son más largas, pero no varias líneas:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-241">If either `cond`, `e1` or `e2` are longer, but not multi-line:</span></span>

```fsharp
if cond
then e1
else e2
```

<span data-ttu-id="2bc5c-242">Si alguna de las expresiones es de varias líneas:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-242">If any of the expressions are multi-line:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="2bc5c-243">A varios condicionales con `elif` y `else` se les aplica una sangría en el mismo ámbito que el `if` :</span><span class="sxs-lookup"><span data-stu-id="2bc5c-243">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="2bc5c-244">Construcciones de coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="2bc5c-244">Pattern matching constructs</span></span>

<span data-ttu-id="2bc5c-245">Use una `|` cláusula for each de una coincidencia sin sangría.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-245">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="2bc5c-246">Si la expresión es breve, puede considerar el uso de una sola línea si cada subexpresión también es simple.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-246">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> x
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> x
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

<span data-ttu-id="2bc5c-247">Si la expresión de la derecha de la flecha de coincidencia de patrones es demasiado grande, muévala a la línea siguiente, con una sangría a un paso de `match` / `|` .</span><span class="sxs-lookup"><span data-stu-id="2bc5c-247">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="2bc5c-248">La coincidencia de patrones de funciones anónimas, a partir de `function` , no suele ser una sangría demasiado lejana.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-248">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="2bc5c-249">Por ejemplo, la sangría de un ámbito es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-249">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="2bc5c-250">La coincidencia de patrones en funciones definidas por `let` o `let rec` debe tener una sangría de cuatro espacios después de iniciarse `let` , incluso si `function` se usa la palabra clave:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-250">Pattern matching in functions defined by `let` or `let rec` should be indented four spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="2bc5c-251">No se recomienda alinear las flechas.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-251">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="2bc5c-252">Aplicar formato a expresiones try/with</span><span class="sxs-lookup"><span data-stu-id="2bc5c-252">Formatting try/with expressions</span></span>

<span data-ttu-id="2bc5c-253">Se debe aplicar sangría a la coincidencia de patrones en el tipo de excepción en el mismo nivel que `with` .</span><span class="sxs-lookup"><span data-stu-id="2bc5c-253">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

```fsharp
try
    if System.DateTime.Now.Second % 3 = 0 then
        raise (new System.Exception())
    else
        raise (new System.ApplicationException())
with
| :? System.ApplicationException ->
    printfn "A second that was not a multiple of 3"
| _ ->
    printfn "A second that was a multiple of 3"
```

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="2bc5c-254">Aplicación de formato de parámetros de función</span><span class="sxs-lookup"><span data-stu-id="2bc5c-254">Formatting function parameter application</span></span>

<span data-ttu-id="2bc5c-255">En general, la mayoría de las aplicaciones de parámetros de función se realizan en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-255">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="2bc5c-256">Si desea aplicar parámetros a una función en una nueva línea, aplíqueles sangría en un ámbito.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-256">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

```fsharp
// OK
sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
sprintf
     "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
let printVolumes x =
    printf "Volume in liters = %f, in us pints = %f, in imperial = %f"
        (convertVolumeToLiter x)
        (convertVolumeUSPint x)
        (convertVolumeImperialPint x)
```

<span data-ttu-id="2bc5c-257">Las mismas directrices se aplican a las expresiones lambda como argumentos de función.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-257">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="2bc5c-258">Si el cuerpo de una expresión lambda, el cuerpo puede tener otra línea, con sangría en un ámbito</span><span class="sxs-lookup"><span data-stu-id="2bc5c-258">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

```fsharp
let printListWithOffset a list1 =
    List.iter
        (fun elem -> printfn "%d" (a + elem))
        list1

// OK if lambda body is long enough
let printListWithOffset a list1 =
    List.iter
        (fun elem ->
            printfn "%d" (a + elem))
        list1
```

<span data-ttu-id="2bc5c-259">Sin embargo, si el cuerpo de una expresión lambda tiene más de una línea, considere la posibilidad de factorizarla en una función independiente en lugar de tener una construcción de varias líneas aplicada como un solo argumento a una función.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-259">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="2bc5c-260">Aplicar formato a los operadores de infijo</span><span class="sxs-lookup"><span data-stu-id="2bc5c-260">Formatting infix operators</span></span>

<span data-ttu-id="2bc5c-261">Operadores independientes por espacios.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-261">Separate operators by spaces.</span></span> <span data-ttu-id="2bc5c-262">Las excepciones obvias a esta regla son los `!` `.` operadores y.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-262">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="2bc5c-263">Las expresiones infijas son correctas para la misma columna:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-263">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="2bc5c-264">Operadores de canalización de formato</span><span class="sxs-lookup"><span data-stu-id="2bc5c-264">Formatting pipeline operators</span></span>

<span data-ttu-id="2bc5c-265">`|>`Los operadores de canalización deben ir debajo de las expresiones en las que operan.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-265">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

```fsharp
// Preferred approach
let methods2 =
    System.AppDomain.CurrentDomain.GetAssemblies()
    |> List.ofArray
    |> List.map (fun assm -> assm.GetTypes())
    |> Array.concat
    |> List.ofArray
    |> List.map (fun t -> t.GetMethods())
    |> Array.concat

// Not OK
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
            |> List.ofArray
            |> List.map (fun assm -> assm.GetTypes())
            |> Array.concat
            |> List.ofArray
            |> List.map (fun t -> t.GetMethods())
            |> Array.concat
```

### <a name="formatting-modules"></a><span data-ttu-id="2bc5c-266">Módulos de formato</span><span class="sxs-lookup"><span data-stu-id="2bc5c-266">Formatting modules</span></span>

<span data-ttu-id="2bc5c-267">Se debe aplicar sangría al código de un módulo local en relación con el módulo, pero no se debe aplicar sangría al código de un módulo de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-267">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="2bc5c-268">No es necesario aplicar sangría a los elementos de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-268">Namespace elements do not have to be indented.</span></span>

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a * a + b * b

module A2 =
    let function2 a b = a * a - b * b
```

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="2bc5c-269">Dar formato a expresiones e interfaces de objeto</span><span class="sxs-lookup"><span data-stu-id="2bc5c-269">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="2bc5c-270">Las interfaces y las expresiones de objeto se deben alinear de la misma manera con `member` una sangría después de cuatro espacios.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-270">Object expressions and interfaces should be aligned in the same way with `member` being indented after four spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="2bc5c-271">Aplicar formato a los espacios en blanco en expresiones</span><span class="sxs-lookup"><span data-stu-id="2bc5c-271">Formatting white space in expressions</span></span>

<span data-ttu-id="2bc5c-272">Evite el espacio en blanco extraño en las expresiones de F #.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-272">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="2bc5c-273">Los argumentos con nombre tampoco deben tener espacio alrededor del `=` :</span><span class="sxs-lookup"><span data-stu-id="2bc5c-273">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a><span data-ttu-id="2bc5c-274">Aplicar formato a atributos</span><span class="sxs-lookup"><span data-stu-id="2bc5c-274">Formatting attributes</span></span>

<span data-ttu-id="2bc5c-275">[Los atributos](../language-reference/attributes.md) se colocan sobre una construcción:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-275">[Attributes](../language-reference/attributes.md) are placed above a construct:</span></span>

```fsharp
[<SomeAttribute>]
type MyClass() = ...

[<RequireQualifiedAccess>]
module M =
    let f x = x

[<Struct>]
type MyRecord =
    { Label1: int
      Label2: string }
```

### <a name="formatting-attributes-on-parameters"></a><span data-ttu-id="2bc5c-276">Aplicar formato a atributos en parámetros</span><span class="sxs-lookup"><span data-stu-id="2bc5c-276">Formatting attributes on parameters</span></span>

<span data-ttu-id="2bc5c-277">Los atributos también se pueden colocar en parámetros.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-277">Attributes can also be placed on parameters.</span></span> <span data-ttu-id="2bc5c-278">En este caso, coloque entonces en la misma línea que el parámetro y antes del nombre:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-278">In this case, place then on the same line as the parameter and before the name:</span></span>

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a><span data-ttu-id="2bc5c-279">Aplicar formato a varios atributos</span><span class="sxs-lookup"><span data-stu-id="2bc5c-279">Formatting multiple attributes</span></span>

<span data-ttu-id="2bc5c-280">Cuando se aplican varios atributos a una construcción que no es un parámetro, deben colocarse de forma que haya un atributo por línea:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-280">When multiple attributes are applied to a construct that is not a parameter, they should be placed such that there is one attribute per line:</span></span>

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

<span data-ttu-id="2bc5c-281">Cuando se aplica a un parámetro, deben estar en la misma línea y estar separados por un `;` separador.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-281">When applied to a parameter, they must be on the same line and separated by a `;` separator.</span></span>

## <a name="formatting-literals"></a><span data-ttu-id="2bc5c-282">Aplicar formato a literales</span><span class="sxs-lookup"><span data-stu-id="2bc5c-282">Formatting literals</span></span>

<span data-ttu-id="2bc5c-283">Los [literales de F #](../language-reference/literals.md) que usan el `Literal` atributo deben colocar el atributo en su propia línea y usar PascalCase naming:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-283">[F# literals](../language-reference/literals.md) using the `Literal` attribute should place the attribute on its own line and use PascalCase naming:</span></span>

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

<span data-ttu-id="2bc5c-284">Evite colocar el atributo en la misma línea que el valor.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-284">Avoid placing the attribute on the same line as the value.</span></span>

## <a name="formatting-computation-expression-operations"></a><span data-ttu-id="2bc5c-285">Operaciones de expresiones de cálculo de formato</span><span class="sxs-lookup"><span data-stu-id="2bc5c-285">Formatting computation expression operations</span></span>

<span data-ttu-id="2bc5c-286">Al crear operaciones personalizadas para [expresiones de cálculo](../language-reference/computation-expressions.md) , se recomienda usar la nomenclatura CamelCase:</span><span class="sxs-lookup"><span data-stu-id="2bc5c-286">When creating custom operations for [computation expressions](../language-reference/computation-expressions.md) it is recommended to use camelCase naming:</span></span>

```fsharp
type MathBuilder () =
    member _.Yield _ = 0

    [<CustomOperation("addOne")>]
    member _.AddOne (state: int) =
        state + 1

    [<CustomOperation("subtractOne")>]
    member _.SubtractOne (state: int) =
        state - 1

    [<CustomOperation("divideBy")>]
    member _.DivideBy (state: int, divisor: int) =
        state / divisor

    [<CustomOperation("multiplyBy")>]
    member _.MultiplyBy (state: int, factor: int) =
        state * factor

let math = MathBuilder()

// 10
let myNumber =
    math {
        addOne
        addOne
        addOne

        subtractOne

        divideBy 2

        multiplyBy 10
    }
```

<span data-ttu-id="2bc5c-287">En última instancia, la Convención de nomenclatura utilizada debe estar controlada por el dominio que se está modelando.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-287">The naming convention used should ultimately be driven by the domain being modeled.</span></span>
<span data-ttu-id="2bc5c-288">Si es idiomático usar una Convención diferente, se debe usar esa Convención en su lugar.</span><span class="sxs-lookup"><span data-stu-id="2bc5c-288">If it is idiomatic to use a different convention, that convention should be used instead.</span></span>
