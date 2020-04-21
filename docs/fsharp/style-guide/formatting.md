---
title: Instrucciones de formato de código de F#
description: Obtenga información sobre las directrices para dar formato al código de F.
ms.date: 11/04/2019
ms.openlocfilehash: b8be70dd29a04e71614308164e541b99a1724305
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739553"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="02c58-103">Instrucciones de formato de código de F#</span><span class="sxs-lookup"><span data-stu-id="02c58-103">F# code formatting guidelines</span></span>

<span data-ttu-id="02c58-104">En este artículo se ofrecen directrices sobre cómo dar formato al código para que el código de F es:</span><span class="sxs-lookup"><span data-stu-id="02c58-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="02c58-105">Más legible</span><span class="sxs-lookup"><span data-stu-id="02c58-105">More legible</span></span>
* <span data-ttu-id="02c58-106">De acuerdo con las convenciones aplicadas por las herramientas de formato en Visual Studio y otros editores</span><span class="sxs-lookup"><span data-stu-id="02c58-106">In accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="02c58-107">Similar a otro código en línea</span><span class="sxs-lookup"><span data-stu-id="02c58-107">Similar to other code online</span></span>

<span data-ttu-id="02c58-108">Estas directrices se basan en una guía completa de las [convenciones](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) de formato de F de [Anh-Dung Phan](https://github.com/dungpa).</span><span class="sxs-lookup"><span data-stu-id="02c58-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="02c58-109">Reglas generales para la sangría</span><span class="sxs-lookup"><span data-stu-id="02c58-109">General rules for indentation</span></span>

<span data-ttu-id="02c58-110">De forma predeterminada, F- utiliza espacios en blanco significativos.</span><span class="sxs-lookup"><span data-stu-id="02c58-110">F# uses significant white space by default.</span></span> <span data-ttu-id="02c58-111">Las siguientes pautas están destinadas a proporcionar orientación sobre cómo hacer malabares con algunos desafíos que esto puede imponer.</span><span class="sxs-lookup"><span data-stu-id="02c58-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="02c58-112">Uso de espacios</span><span class="sxs-lookup"><span data-stu-id="02c58-112">Using spaces</span></span>

<span data-ttu-id="02c58-113">Cuando se requiere sangría, debe utilizar espacios, no tabulaciones.</span><span class="sxs-lookup"><span data-stu-id="02c58-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="02c58-114">Se requiere al menos un espacio.</span><span class="sxs-lookup"><span data-stu-id="02c58-114">At least one space is required.</span></span> <span data-ttu-id="02c58-115">Su organización puede crear estándares de codificación para especificar el número de espacios que se utilizarán para la sangría; dos, tres o cuatro espacios de sangría en cada nivel donde se produce la sangría es típico.</span><span class="sxs-lookup"><span data-stu-id="02c58-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three, or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="02c58-116">**Recomendamos cuatro espacios por sangría.**</span><span class="sxs-lookup"><span data-stu-id="02c58-116">**We recommend four spaces per indentation.**</span></span>

<span data-ttu-id="02c58-117">Dicho esto, la sangría de los programas es un asunto subjetivo.</span><span class="sxs-lookup"><span data-stu-id="02c58-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="02c58-118">Las variaciones están bien, pero la primera regla que debe seguir es la coherencia de la *sangría.*</span><span class="sxs-lookup"><span data-stu-id="02c58-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="02c58-119">Elija un estilo de sangría generalmente aceptado y utilícelo sistemáticamente en todo el código base.</span><span class="sxs-lookup"><span data-stu-id="02c58-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-white-space"></a><span data-ttu-id="02c58-120">Formato de espacios en blanco</span><span class="sxs-lookup"><span data-stu-id="02c58-120">Formatting white space</span></span>

<span data-ttu-id="02c58-121">F es sensible al espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="02c58-121">F# is white space sensitive.</span></span> <span data-ttu-id="02c58-122">Aunque la mayoría de la semántica del espacio en blanco está cubierta por una sangría adecuada, hay algunas otras cosas a considerar.</span><span class="sxs-lookup"><span data-stu-id="02c58-122">Although most semantics from white space are covered by proper indentation, there are some other things to consider.</span></span>

### <a name="formatting-operators-in-arithmetic-expressions"></a><span data-ttu-id="02c58-123">Operadores de formato en expresiones aritméticas</span><span class="sxs-lookup"><span data-stu-id="02c58-123">Formatting operators in arithmetic expressions</span></span>

<span data-ttu-id="02c58-124">Utilice siempre espacios en blanco alrededor de expresiones aritméticas binarias:</span><span class="sxs-lookup"><span data-stu-id="02c58-124">Always use white space around binary arithmetic expressions:</span></span>

```fsharp
let subtractThenAdd x = x - 1 + 3
```

<span data-ttu-id="02c58-125">Los `-` operadores unarios siempre deben ir seguidos inmediatamente por el valor que están negando:</span><span class="sxs-lookup"><span data-stu-id="02c58-125">Unary `-` operators should always be immediately followed by the value they are negating:</span></span>

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

<span data-ttu-id="02c58-126">Agregar un carácter de `-` espacio en blanco después del operador puede llevar a confusión para otros.</span><span class="sxs-lookup"><span data-stu-id="02c58-126">Adding a white-space character after the `-` operator can lead to confusion for others.</span></span>

<span data-ttu-id="02c58-127">En resumen, es importante:</span><span class="sxs-lookup"><span data-stu-id="02c58-127">In summary, it's important to always:</span></span>

* <span data-ttu-id="02c58-128">Operadores binarios envolventes con espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="02c58-128">Surround binary operators with white space</span></span>
* <span data-ttu-id="02c58-129">Nunca tenga un espacio en blanco final después de un operador unario</span><span class="sxs-lookup"><span data-stu-id="02c58-129">Never have trailing white space after a unary operator</span></span>

<span data-ttu-id="02c58-130">La directriz del operador aritmético binario es especialmente importante.</span><span class="sxs-lookup"><span data-stu-id="02c58-130">The binary arithmetic operator guideline is especially important.</span></span> <span data-ttu-id="02c58-131">Si no se `-` rodea un operador binario, cuando se combina con ciertas opciones de formato, podría conducir a interpretarlo como unario `-`.</span><span class="sxs-lookup"><span data-stu-id="02c58-131">Failing to surround a binary `-` operator, when combined with certain formatting choices, could lead to interpreting it as a unary `-`.</span></span>

### <a name="surround-a-custom-operator-definition-with-white-space"></a><span data-ttu-id="02c58-132">Rodee una definición de operador personalizada con espacios en blanco</span><span class="sxs-lookup"><span data-stu-id="02c58-132">Surround a custom operator definition with white space</span></span>

<span data-ttu-id="02c58-133">Utilice siempre espacios en blanco para rodear una definición de operador:</span><span class="sxs-lookup"><span data-stu-id="02c58-133">Always use white space to surround an operator definition:</span></span>

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

<span data-ttu-id="02c58-134">Para cualquier operador personalizado `*` que comience con y que tenga más de un carácter, debe agregar un espacio en blanco al principio de la definición para evitar una ambiguedad del compilador.</span><span class="sxs-lookup"><span data-stu-id="02c58-134">For any custom operator that starts with `*` and that has more than one character, you need to add a white space to the beginning of the definition to avoid a compiler ambiguity.</span></span> <span data-ttu-id="02c58-135">Por este caso, se recomienda simplemente rodear las definiciones de todos los operadores con un único carácter de espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="02c58-135">Because of this, we recommend that you simply surround the definitions of all operators with a single white-space character.</span></span>

### <a name="surround-function-parameter-arrows-with-white-space"></a><span data-ttu-id="02c58-136">Flechas de parámetros de función envolvente con espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="02c58-136">Surround function parameter arrows with white space</span></span>

<span data-ttu-id="02c58-137">Al definir la firma de una función, utilice un espacio en blanco alrededor del `->` símbolo:</span><span class="sxs-lookup"><span data-stu-id="02c58-137">When defining the signature of a function, use white space around the `->` symbol:</span></span>

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a><span data-ttu-id="02c58-138">Argumentos de función envolvente con espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="02c58-138">Surround function arguments with white space</span></span>

<span data-ttu-id="02c58-139">Al definir una función, utilice espacios en blanco alrededor de cada argumento.</span><span class="sxs-lookup"><span data-stu-id="02c58-139">When defining a function, use white space around each argument.</span></span>

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="place-parameters-on-a-new-line-for-long-member-definitions"></a><span data-ttu-id="02c58-140">Coloque los parámetros en una nueva línea para las definiciones de miembros largos</span><span class="sxs-lookup"><span data-stu-id="02c58-140">Place parameters on a new line for long member definitions</span></span>

<span data-ttu-id="02c58-141">Si tiene una definición de miembro muy larga, coloque los parámetros en nuevas líneas y indentelas un ámbito.</span><span class="sxs-lookup"><span data-stu-id="02c58-141">If you have a very long member definition, place the parameters on new lines and indent them one scope.</span></span>

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(
        aVeryLongType: AVeryLongTypeThatYouNeedToUse
        aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
        aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
        // ... the body of the method follows
```

<span data-ttu-id="02c58-142">Esto también se aplica a los constructores:</span><span class="sxs-lookup"><span data-stu-id="02c58-142">This also applies to constructors:</span></span>

```fsharp
type C(
    aVeryLongType: AVeryLongTypeThatYouNeedToUse
    aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
    aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
    // ... the body of the class follows
```

### <a name="type-annotations"></a><span data-ttu-id="02c58-143">Anotaciones de tipo</span><span class="sxs-lookup"><span data-stu-id="02c58-143">Type annotations</span></span>

#### <a name="right-pad-function-argument-type-annotations"></a><span data-ttu-id="02c58-144">Anotaciones de tipo de argumento de función del botón derecho</span><span class="sxs-lookup"><span data-stu-id="02c58-144">Right-pad function argument type annotations</span></span>

<span data-ttu-id="02c58-145">Al definir argumentos con anotaciones de `:` tipo, utilice el espacio en blanco después del símbolo:</span><span class="sxs-lookup"><span data-stu-id="02c58-145">When defining arguments with type annotations, use white space after the `:` symbol:</span></span>

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a><span data-ttu-id="02c58-146">Anotaciones de tipo de valor devuelto envolvente con espacio en blanco</span><span class="sxs-lookup"><span data-stu-id="02c58-146">Surround return type annotations with white space</span></span>

<span data-ttu-id="02c58-147">En una función enlazada a let o anotación de tipo de valor `:` (tipo de valor devuelto en el caso de una función), utilice el espacio en blanco antes y después del símbolo:</span><span class="sxs-lookup"><span data-stu-id="02c58-147">In a let-bound function or value type annotation (return type in the case of a function), use white space before and after the `:` symbol:</span></span>

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a><span data-ttu-id="02c58-148">Formato de líneas en blanco</span><span class="sxs-lookup"><span data-stu-id="02c58-148">Formatting blank lines</span></span>

* <span data-ttu-id="02c58-149">Separe las definiciones de clase y función de nivel superior con dos líneas en blanco.</span><span class="sxs-lookup"><span data-stu-id="02c58-149">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="02c58-150">Las definiciones de método dentro de una clase están separadas por una sola línea en blanco.</span><span class="sxs-lookup"><span data-stu-id="02c58-150">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="02c58-151">Se pueden utilizar líneas en blanco adicionales (con moderación) para separar grupos de funciones relacionadas.</span><span class="sxs-lookup"><span data-stu-id="02c58-151">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="02c58-152">Las líneas en blanco se pueden omitir entre un montón de líneas de una (por ejemplo, un conjunto de implementaciones ficticias).</span><span class="sxs-lookup"><span data-stu-id="02c58-152">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="02c58-153">Utilice líneas en blanco en las funciones, con moderación, para indicar secciones lógicas.</span><span class="sxs-lookup"><span data-stu-id="02c58-153">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="02c58-154">Formato de comentarios</span><span class="sxs-lookup"><span data-stu-id="02c58-154">Formatting comments</span></span>

<span data-ttu-id="02c58-155">Por lo general, prefiere varios comentarios de doble barra diagonal a los comentarios de bloque de estilo ML.</span><span class="sxs-lookup"><span data-stu-id="02c58-155">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="02c58-156">Los comentarios en línea deben capitalizar la primera letra.</span><span class="sxs-lookup"><span data-stu-id="02c58-156">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="02c58-157">Convenciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="02c58-157">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="02c58-158">Utilice camelCase para funciones y valores enlazados a clases, enlazados a expresiones y enlazados a patrones</span><span class="sxs-lookup"><span data-stu-id="02c58-158">Use camelCase for class-bound, expression-bound, and pattern-bound values and functions</span></span>

<span data-ttu-id="02c58-159">Es común y aceptado estilo de F - para usar camelCase para todos los nombres enlazados como variables locales o en coincidencias de patrones y definiciones de función.</span><span class="sxs-lookup"><span data-stu-id="02c58-159">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="02c58-160">Las funciones enlazadas localmente en las clases también deben usar camelCase.</span><span class="sxs-lookup"><span data-stu-id="02c58-160">Locally bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="02c58-161">Utilice camelCase para funciones públicas enlazadas a módulos</span><span class="sxs-lookup"><span data-stu-id="02c58-161">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="02c58-162">Cuando una función enlazada a un módulo forma parte de una API pública, debe utilizar camelCase:</span><span class="sxs-lookup"><span data-stu-id="02c58-162">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="02c58-163">Utilice camelCase para funciones y valores internos y privados enlazados a módulos</span><span class="sxs-lookup"><span data-stu-id="02c58-163">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="02c58-164">Utilice camelCase para valores enlazados a módulos privados, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="02c58-164">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="02c58-165">Funciones ad hoc en scripts</span><span class="sxs-lookup"><span data-stu-id="02c58-165">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="02c58-166">Valores que componen la implementación interna de un módulo o tipo</span><span class="sxs-lookup"><span data-stu-id="02c58-166">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="02c58-167">Utilice camelCase para los parámetros</span><span class="sxs-lookup"><span data-stu-id="02c58-167">Use camelCase for parameters</span></span>

<span data-ttu-id="02c58-168">Todos los parámetros deben usar camelCase de acuerdo con las convenciones de nomenclatura de .NET.</span><span class="sxs-lookup"><span data-stu-id="02c58-168">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="02c58-169">Utilice PascalCase para módulos</span><span class="sxs-lookup"><span data-stu-id="02c58-169">Use PascalCase for modules</span></span>

<span data-ttu-id="02c58-170">Todos los módulos (de nivel superior, internos, privados, anidados) deben utilizar PascalCase.</span><span class="sxs-lookup"><span data-stu-id="02c58-170">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="02c58-171">Utilice PascalCase para declaraciones de tipo, miembros y etiquetas</span><span class="sxs-lookup"><span data-stu-id="02c58-171">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="02c58-172">Las clases, interfaces, estructuras, enumeraciones, delegados, registros y uniones discriminadas deben denominarse con PascalCase.</span><span class="sxs-lookup"><span data-stu-id="02c58-172">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="02c58-173">Los miembros dentro de tipos y etiquetas para registros y uniones discriminadas también deben usar PascalCase.</span><span class="sxs-lookup"><span data-stu-id="02c58-173">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="02c58-174">Utilice PascalCase para construcciones intrínsecas a .NET</span><span class="sxs-lookup"><span data-stu-id="02c58-174">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="02c58-175">Los espacios de nombres, excepciones, eventos y nombres de proyecto/proyectos`.dll` también deben usar PascalCase.</span><span class="sxs-lookup"><span data-stu-id="02c58-175">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="02c58-176">Esto no solo hace que el consumo de otros lenguajes .NET se sienta más natural para los consumidores, sino que también es coherente con las convenciones de nomenclatura de .NET que es probable que encuentre.</span><span class="sxs-lookup"><span data-stu-id="02c58-176">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="02c58-177">Evite los guiones bajos en los nombres</span><span class="sxs-lookup"><span data-stu-id="02c58-177">Avoid underscores in names</span></span>

<span data-ttu-id="02c58-178">Históricamente, algunas bibliotecas de F - han utilizado guiones bajos en los nombres.</span><span class="sxs-lookup"><span data-stu-id="02c58-178">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="02c58-179">Sin embargo, esto ya no se acepta ampliamente, en parte porque entra en conflicto con las convenciones de nomenclatura de .NET.</span><span class="sxs-lookup"><span data-stu-id="02c58-179">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="02c58-180">Dicho esto, algunos programadores de F - utilizan subrayados en gran medida, en parte por razones históricas, y la tolerancia y el respeto es importante.</span><span class="sxs-lookup"><span data-stu-id="02c58-180">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="02c58-181">Sin embargo, ten en cuenta que el estilo a menudo no es del agrado por otros que tienen la opción de usarlo.</span><span class="sxs-lookup"><span data-stu-id="02c58-181">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="02c58-182">Una excepción incluye la interoperación con componentes nativos, donde los guiones bajos son comunes.</span><span class="sxs-lookup"><span data-stu-id="02c58-182">One exception includes interoperating with native components, where underscores are common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="02c58-183">Utilice operadores estándar de F -</span><span class="sxs-lookup"><span data-stu-id="02c58-183">Use standard F# operators</span></span>

<span data-ttu-id="02c58-184">Los siguientes operadores se definen en la biblioteca estándar de F y se deben usar en lugar de definir equivalentes.</span><span class="sxs-lookup"><span data-stu-id="02c58-184">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="02c58-185">Se recomienda el uso de estos operadores, ya que tiende a hacer que el código sea más legible e idiomático.</span><span class="sxs-lookup"><span data-stu-id="02c58-185">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="02c58-186">Los desarrolladores con experiencia en OCaml u otro lenguaje de programación funcional pueden estar acostumbrados a diferentes modismos.</span><span class="sxs-lookup"><span data-stu-id="02c58-186">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="02c58-187">En la lista siguiente se resumen los operadores de F.</span><span class="sxs-lookup"><span data-stu-id="02c58-187">The following list summarizes the recommended F# operators.</span></span>

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="02c58-188">Utilice la sintaxis`Foo<T>`de prefijo para genéricos`T Foo`( ) en preferencia a la sintaxis de postfijo ( )</span><span class="sxs-lookup"><span data-stu-id="02c58-188">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="02c58-189">El estilo de valor de ML de postfijo de `int list`los tipos genéricos de patrón `list<int>`(por ejemplo, ) como el estilo de .NET del prefijo (por ejemplo, ).</span><span class="sxs-lookup"><span data-stu-id="02c58-189">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="02c58-190">Prefiere el estilo .NET, excepto para cinco tipos específicos:</span><span class="sxs-lookup"><span data-stu-id="02c58-190">Prefer the .NET style, except for five specific types:</span></span>

1. <span data-ttu-id="02c58-191">Para las listas de F, `int list` utilice `list<int>`el formulario de postfijo: en lugar de .</span><span class="sxs-lookup"><span data-stu-id="02c58-191">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="02c58-192">Para Opciones de F, utilice `int option` el `option<int>`formulario de postfijo: en lugar de .</span><span class="sxs-lookup"><span data-stu-id="02c58-192">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="02c58-193">Para Opciones de valor de F, `int voption` utilice `voption<int>`el formulario de postfijo: en lugar de .</span><span class="sxs-lookup"><span data-stu-id="02c58-193">For F# Value Options, use the postfix form: `int voption` rather than `voption<int>`.</span></span>
4. <span data-ttu-id="02c58-194">Para las matrices de F, utilice `int[]` el `int array` `array<int>`nombre sintáctico en lugar de o .</span><span class="sxs-lookup"><span data-stu-id="02c58-194">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
5. <span data-ttu-id="02c58-195">Para Celdas `int ref` de `ref<int>` referencia, utilice en lugar de o `Ref<int>`.</span><span class="sxs-lookup"><span data-stu-id="02c58-195">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="02c58-196">Para todos los demás tipos, utilice el formulario de prefijo.</span><span class="sxs-lookup"><span data-stu-id="02c58-196">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="02c58-197">Tuplas de formato</span><span class="sxs-lookup"><span data-stu-id="02c58-197">Formatting tuples</span></span>

<span data-ttu-id="02c58-198">Una creación de instancias de tupla debe ser entreparénte, y las comas delimitadoras dentro de ella deben ir seguidas de un único espacio, por ejemplo: `(1, 2)`, `(x, y, z)`.</span><span class="sxs-lookup"><span data-stu-id="02c58-198">A tuple instantiation should be parenthesized, and the delimiting commas within it should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="02c58-199">Se acepta comúnmente para omitir paréntesis en la coincidencia de patrones de tuplas:</span><span class="sxs-lookup"><span data-stu-id="02c58-199">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

<span data-ttu-id="02c58-200">También se acepta comúnmente para omitir paréntesis si la tupla es el valor devuelto de una función:</span><span class="sxs-lookup"><span data-stu-id="02c58-200">It is also commonly accepted to omit parentheses if the tuple is the return value of a function:</span></span>

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

<span data-ttu-id="02c58-201">En resumen, prefiere las instancias de tupla entre paréntesis, pero cuando se usan tuplas para la coincidencia de patrones o un valor devuelto, se considera fino evitar paréntesis.</span><span class="sxs-lookup"><span data-stu-id="02c58-201">In summary, prefer parenthesized tuple instantiations, but when using tuples for pattern matching or a return value, it is considered fine to avoid parentheses.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="02c58-202">Formato de declaraciones sindicales discriminadas</span><span class="sxs-lookup"><span data-stu-id="02c58-202">Formatting discriminated union declarations</span></span>

<span data-ttu-id="02c58-203">Sangría `|` en la definición de tipo por cuatro espacios:</span><span class="sxs-lookup"><span data-stu-id="02c58-203">Indent `|` in type definition by four spaces:</span></span>

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

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="02c58-204">Formato de uniones discriminadas</span><span class="sxs-lookup"><span data-stu-id="02c58-204">Formatting discriminated unions</span></span>

<span data-ttu-id="02c58-205">Las uniones discriminadas con instancias que se dividen en varias líneas deben proporcionar a los datos contenidos un nuevo ámbito con sangría:</span><span class="sxs-lookup"><span data-stu-id="02c58-205">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="02c58-206">El paréntesis de cierre también puede estar en una nueva línea:</span><span class="sxs-lookup"><span data-stu-id="02c58-206">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="02c58-207">Formato de declaraciones de registros</span><span class="sxs-lookup"><span data-stu-id="02c58-207">Formatting record declarations</span></span>

<span data-ttu-id="02c58-208">Sangra `{` en la definición de tipo por cuatro espacios e inicia la lista de campos en la misma línea:</span><span class="sxs-lookup"><span data-stu-id="02c58-208">Indent `{` in type definition by four spaces and start the field list on the same line:</span></span>

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

<span data-ttu-id="02c58-209">Colocar el token de apertura en una nueva línea y el token de cierre en una nueva línea es preferible si está declarando implementaciones de interfaz o miembros en el registro:</span><span class="sxs-lookup"><span data-stu-id="02c58-209">Placing the opening token on a new line and the closing token on a new line is preferable if you are declaring interface implementations or members on the record:</span></span>

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

## <a name="formatting-records"></a><span data-ttu-id="02c58-210">Formato de registros</span><span class="sxs-lookup"><span data-stu-id="02c58-210">Formatting records</span></span>

<span data-ttu-id="02c58-211">Los registros cortos se pueden escribir en una línea:</span><span class="sxs-lookup"><span data-stu-id="02c58-211">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="02c58-212">Los registros que son más largos deben usar nuevas líneas para las etiquetas:</span><span class="sxs-lookup"><span data-stu-id="02c58-212">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="02c58-213">Colocar el token de apertura en una nueva línea, el contenido tabulado sobre un ámbito y el token de cierre en una nueva línea es preferible si:</span><span class="sxs-lookup"><span data-stu-id="02c58-213">Placing the opening token on a new line, the contents tabbed over one scope, and the closing token on a new line is preferable if you are:</span></span>

* <span data-ttu-id="02c58-214">Mover registros en código con diferentes ámbitos de sangría</span><span class="sxs-lookup"><span data-stu-id="02c58-214">Moving records around in code with different indentation scopes</span></span>
* <span data-ttu-id="02c58-215">Convertirlos en una función</span><span class="sxs-lookup"><span data-stu-id="02c58-215">Piping them into a function</span></span>

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

<span data-ttu-id="02c58-216">Se aplican las mismas reglas para los elementos de lista y matriz.</span><span class="sxs-lookup"><span data-stu-id="02c58-216">The same rules apply for list and array elements.</span></span>

## <a name="formatting-copy-and-update-record-expressions"></a><span data-ttu-id="02c58-217">Formato de expresiones de registro de copia y actualización</span><span class="sxs-lookup"><span data-stu-id="02c58-217">Formatting copy-and-update record expressions</span></span>

<span data-ttu-id="02c58-218">Una expresión de registro de copia y actualización sigue siendo un registro, por lo que se aplican directrices similares.</span><span class="sxs-lookup"><span data-stu-id="02c58-218">A copy-and-update record expression is still a record, so similar guidelines apply.</span></span>

<span data-ttu-id="02c58-219">Las expresiones cortas pueden caber en una línea:</span><span class="sxs-lookup"><span data-stu-id="02c58-219">Short expressions can fit on one line:</span></span>

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

<span data-ttu-id="02c58-220">Las expresiones más largas deben utilizar nuevas líneas:</span><span class="sxs-lookup"><span data-stu-id="02c58-220">Longer expressions should use new lines:</span></span>

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="02c58-221">Y al igual que con la guía de registros, es posible que desee dedicar líneas separadas para las llaves y aplicar sangría a un ámbito a la derecha con la expresión.</span><span class="sxs-lookup"><span data-stu-id="02c58-221">And as with the record guidance, you may want to dedicate separate lines for the braces and indent one scope to the right with the expression.</span></span> <span data-ttu-id="02c58-222">En algunos casos especiales, como ajustar un valor con un valor opcional sin paréntesis, es posible que deba mantener una llave en una línea:</span><span class="sxs-lookup"><span data-stu-id="02c58-222">In some special cases, such as wrapping a value with an optional without parentheses, you may need to keep a brace on one line:</span></span>

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

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="02c58-223">Formato de listas y matrices</span><span class="sxs-lookup"><span data-stu-id="02c58-223">Formatting lists and arrays</span></span>

<span data-ttu-id="02c58-224">Escribir `x :: l` con espacios `::` alrededor`::` del operador ( es un operador de infijo, por lo tanto rodeado de espacios).</span><span class="sxs-lookup"><span data-stu-id="02c58-224">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces).</span></span>

<span data-ttu-id="02c58-225">La lista y las matrices declaradas en una sola línea deben tener un espacio después del corchete de apertura y antes del corchete de cierre:</span><span class="sxs-lookup"><span data-stu-id="02c58-225">List and arrays declared on a single line should have a space after the opening bracket and before the closing bracket:</span></span>

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

<span data-ttu-id="02c58-226">Utilice siempre al menos un espacio entre dos operadores distintos de tipo llaves.</span><span class="sxs-lookup"><span data-stu-id="02c58-226">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="02c58-227">Por ejemplo, deje un `[` espacio `{`entre a y a .</span><span class="sxs-lookup"><span data-stu-id="02c58-227">For example, leave a space between a `[` and a `{`.</span></span>

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

<span data-ttu-id="02c58-228">La misma directriz se aplica a listas o matrices de tuplas.</span><span class="sxs-lookup"><span data-stu-id="02c58-228">The same guideline applies for lists or arrays of tuples.</span></span>

<span data-ttu-id="02c58-229">Las listas y matrices que se dividen en varias líneas siguen una regla similar a la de los registros:</span><span class="sxs-lookup"><span data-stu-id="02c58-229">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

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

<span data-ttu-id="02c58-230">Y al igual que con los registros, la declaración de los corchetes de apertura y cierre en su propia línea hará que mover el código y la canalización en funciones sea más fácil.</span><span class="sxs-lookup"><span data-stu-id="02c58-230">And as with records, declaring the opening and closing brackets on their own line will make moving code around and piping into functions easier.</span></span>

<span data-ttu-id="02c58-231">Al generar matrices y listas `->` mediante `do ... yield` programación, prefiera sobre cuándo siempre se genera un valor:</span><span class="sxs-lookup"><span data-stu-id="02c58-231">When generating arrays and lists programmatically, prefer `->` over `do ... yield` when a value is always generated:</span></span>

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x*x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x*x ]
```

<span data-ttu-id="02c58-232">Las versiones anteriores del `yield` lenguaje F- requerían especificar en situaciones en las que los datos se pueden generar condicionalmente o puede haber expresiones consecutivas que se evaluarán.</span><span class="sxs-lookup"><span data-stu-id="02c58-232">Older versions of the F# language required specifying `yield` in situations where data may be generated conditionally, or there may be consecutive expressions to be evaluated.</span></span> <span data-ttu-id="02c58-233">Prefiere omitir `yield` estas palabras clave a menos que deba compilar con una versión de lenguaje de F. anterior:</span><span class="sxs-lookup"><span data-stu-id="02c58-233">Prefer omitting these `yield` keywords unless you must compile with an older F# language version:</span></span>

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

<span data-ttu-id="02c58-234">En algunos `do...yield` casos, puede ayudar en la legibilidad.</span><span class="sxs-lookup"><span data-stu-id="02c58-234">In some cases, `do...yield` may aid in readability.</span></span> <span data-ttu-id="02c58-235">Estos casos, aunque subjetivos, deben tenerse en cuenta.</span><span class="sxs-lookup"><span data-stu-id="02c58-235">These cases, though subjective, should be taken into consideration.</span></span>

## <a name="formatting-if-expressions"></a><span data-ttu-id="02c58-236">Formato si las expresiones</span><span class="sxs-lookup"><span data-stu-id="02c58-236">Formatting if expressions</span></span>

<span data-ttu-id="02c58-237">La sangría de condicionales depende de los tamaños de las expresiones que las componen.</span><span class="sxs-lookup"><span data-stu-id="02c58-237">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="02c58-238">Si `cond` `e1` , `e2` y son cortos, simplemente escríbalos en una línea:</span><span class="sxs-lookup"><span data-stu-id="02c58-238">If `cond`, `e1` and `e2` are short, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="02c58-239">Si `cond`, `e1` `e2` o son más largos, pero no multilínea:</span><span class="sxs-lookup"><span data-stu-id="02c58-239">If either `cond`, `e1` or `e2` are longer, but not multi-line:</span></span>

```fsharp
if cond
then e1
else e2
```

<span data-ttu-id="02c58-240">Si alguna de las expresiones es de varias líneas:</span><span class="sxs-lookup"><span data-stu-id="02c58-240">If any of the expressions are multi-line:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="02c58-241">Múltiples condicionales con `elif` y `else` se indentan `if`en el mismo ámbito que:</span><span class="sxs-lookup"><span data-stu-id="02c58-241">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="02c58-242">Construcciones de coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="02c58-242">Pattern matching constructs</span></span>

<span data-ttu-id="02c58-243">Use `|` a para cada cláusula de una coincidencia sin sangría.</span><span class="sxs-lookup"><span data-stu-id="02c58-243">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="02c58-244">Si la expresión es corta, puede considerar el uso de una sola línea si cada subexpresión también es simple.</span><span class="sxs-lookup"><span data-stu-id="02c58-244">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

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

<span data-ttu-id="02c58-245">Si la expresión de la derecha de la flecha de coincidencia de patrón es `match` / `|`demasiado grande, muévala a la línea siguiente, con sangría a un paso del archivo .</span><span class="sxs-lookup"><span data-stu-id="02c58-245">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="02c58-246">La coincidencia de patrones `function`de funciones anónimas, empezando por , generalmente no debe aplicar sangría demasiado.</span><span class="sxs-lookup"><span data-stu-id="02c58-246">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="02c58-247">Por ejemplo, la sangría de un ámbito de la siguiente manera está bien:</span><span class="sxs-lookup"><span data-stu-id="02c58-247">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="02c58-248">La coincidencia de `let` patrones `let rec` en funciones definidas por `let`o `function` debe sangrar cuatro espacios después de iniciar , incluso si se utiliza la palabra clave:</span><span class="sxs-lookup"><span data-stu-id="02c58-248">Pattern matching in functions defined by `let` or `let rec` should be indented four spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="02c58-249">No se recomienda alinear las flechas.</span><span class="sxs-lookup"><span data-stu-id="02c58-249">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="02c58-250">Formato try/with expressions</span><span class="sxs-lookup"><span data-stu-id="02c58-250">Formatting try/with expressions</span></span>

<span data-ttu-id="02c58-251">La coincidencia de patrones en el tipo de `with`excepción debe sangrar en el mismo nivel que .</span><span class="sxs-lookup"><span data-stu-id="02c58-251">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

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

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="02c58-252">Aplicación de parámetros de función de formato</span><span class="sxs-lookup"><span data-stu-id="02c58-252">Formatting function parameter application</span></span>

<span data-ttu-id="02c58-253">En general, la mayoría de la aplicación de parámetros de función se realiza en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="02c58-253">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="02c58-254">Si desea aplicar parámetros a una función en una nueva línea, indentarlos por un ámbito.</span><span class="sxs-lookup"><span data-stu-id="02c58-254">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

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

<span data-ttu-id="02c58-255">Las mismas directrices se aplican a las expresiones lambda como argumentos de función.</span><span class="sxs-lookup"><span data-stu-id="02c58-255">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="02c58-256">Si el cuerpo de una expresión lambda, el cuerpo puede tener otra línea, con sangría por un ámbito</span><span class="sxs-lookup"><span data-stu-id="02c58-256">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

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

<span data-ttu-id="02c58-257">Sin embargo, si el cuerpo de una expresión lambda es más de una línea, considere la posibilidad de factorizarla en una función independiente en lugar de tener una construcción de varias líneas aplicada como un único argumento a una función.</span><span class="sxs-lookup"><span data-stu-id="02c58-257">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="02c58-258">Formatear operadores de infijos</span><span class="sxs-lookup"><span data-stu-id="02c58-258">Formatting infix operators</span></span>

<span data-ttu-id="02c58-259">Separe los operadores por espacios.</span><span class="sxs-lookup"><span data-stu-id="02c58-259">Separate operators by spaces.</span></span> <span data-ttu-id="02c58-260">Excepciones obvias a `!` esta `.` regla son los operadores y.</span><span class="sxs-lookup"><span data-stu-id="02c58-260">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="02c58-261">Las expresiones de infijo están bien para alinearse en la misma columna:</span><span class="sxs-lookup"><span data-stu-id="02c58-261">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="02c58-262">Formato de operadores de tuberías</span><span class="sxs-lookup"><span data-stu-id="02c58-262">Formatting pipeline operators</span></span>

<span data-ttu-id="02c58-263">Los `|>` operadores de canalización deben ir por debajo de las expresiones en las que operan.</span><span class="sxs-lookup"><span data-stu-id="02c58-263">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

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

### <a name="formatting-modules"></a><span data-ttu-id="02c58-264">Módulos de formato</span><span class="sxs-lookup"><span data-stu-id="02c58-264">Formatting modules</span></span>

<span data-ttu-id="02c58-265">El código de un módulo local debe sangrar en relación con el módulo, pero el código de un módulo de nivel superior no se debe aplicar sangría.</span><span class="sxs-lookup"><span data-stu-id="02c58-265">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="02c58-266">No es necesario aplicar sangría a los elementos de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="02c58-266">Namespace elements do not have to be indented.</span></span>

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a*a + b*b

module A2 =
    let function2 a b = a*a - b*b
```

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="02c58-267">Formato de expresiones e interfaces de objetos</span><span class="sxs-lookup"><span data-stu-id="02c58-267">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="02c58-268">Las expresiones e interfaces de objeto `member` deben alinearse de la misma manera con sangría después de cuatro espacios.</span><span class="sxs-lookup"><span data-stu-id="02c58-268">Object expressions and interfaces should be aligned in the same way with `member` being indented after four spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="02c58-269">Formato de espacios en blanco en expresiones</span><span class="sxs-lookup"><span data-stu-id="02c58-269">Formatting white space in expressions</span></span>

<span data-ttu-id="02c58-270">Evite espacios en blanco extraños en expresiones de F.</span><span class="sxs-lookup"><span data-stu-id="02c58-270">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="02c58-271">Los argumentos con nombre tampoco deben tener espacio en torno a: `=`</span><span class="sxs-lookup"><span data-stu-id="02c58-271">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a><span data-ttu-id="02c58-272">Formato de atributos</span><span class="sxs-lookup"><span data-stu-id="02c58-272">Formatting attributes</span></span>

<span data-ttu-id="02c58-273">[Los atributos](../language-reference/attributes.md) se colocan encima de una construcción:</span><span class="sxs-lookup"><span data-stu-id="02c58-273">[Attributes](../language-reference/attributes.md) are placed above a construct:</span></span>

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

### <a name="formatting-attributes-on-parameters"></a><span data-ttu-id="02c58-274">Formato de atributos en parámetros</span><span class="sxs-lookup"><span data-stu-id="02c58-274">Formatting attributes on parameters</span></span>

<span data-ttu-id="02c58-275">Los atributos también se pueden colocar en parámetros.</span><span class="sxs-lookup"><span data-stu-id="02c58-275">Attributes can also be places on parameters.</span></span> <span data-ttu-id="02c58-276">En este caso, coloque entonces en la misma línea que el parámetro y antes del nombre:</span><span class="sxs-lookup"><span data-stu-id="02c58-276">In this case, place then on the same line as the parameter and before the name:</span></span>

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a><span data-ttu-id="02c58-277">Dar formato a múltiples atributos</span><span class="sxs-lookup"><span data-stu-id="02c58-277">Formatting multiple attributes</span></span>

<span data-ttu-id="02c58-278">Cuando se aplican varios atributos a una construcción que no es un parámetro, deben colocarse de tal forma que haya un atributo por línea:</span><span class="sxs-lookup"><span data-stu-id="02c58-278">When multiple attributes are applied to a construct that is not a parameter, they should be placed such that there is one attribute per line:</span></span>

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

<span data-ttu-id="02c58-279">Cuando se aplican a un parámetro, deben estar `;` en la misma línea y separados por un separador.</span><span class="sxs-lookup"><span data-stu-id="02c58-279">When applied to a parameter, they must be on the same line and separated by a `;` separator.</span></span>

## <a name="formatting-literals"></a><span data-ttu-id="02c58-280">Formato de literales</span><span class="sxs-lookup"><span data-stu-id="02c58-280">Formatting literals</span></span>

<span data-ttu-id="02c58-281">Los [literales](../language-reference/literals.md) de `Literal` F- que utilizan el atributo deben colocar el atributo en su propia línea y utilizar la nomenclatura PascalCase:</span><span class="sxs-lookup"><span data-stu-id="02c58-281">[F# literals](../language-reference/literals.md) using the `Literal` attribute should place the attribute on its own line and use PascalCase naming:</span></span>

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

<span data-ttu-id="02c58-282">Evite colocar el atributo en la misma línea que el valor.</span><span class="sxs-lookup"><span data-stu-id="02c58-282">Avoid placing the attribute on the same line as the value.</span></span>
