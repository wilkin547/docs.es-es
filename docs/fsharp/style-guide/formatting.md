---
title: 'Instrucciones de formato del código de F #'
description: 'Obtenga información sobre las directrices para dar formato al código de F #.'
ms.date: 05/14/2018
ms.openlocfilehash: 0d7d2d1771710db55bf990f3a06079b2aec48fd7
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858010"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="c98df-103">Instrucciones de formato del código de F #</span><span class="sxs-lookup"><span data-stu-id="c98df-103">F# code formatting guidelines</span></span>

<span data-ttu-id="c98df-104">En este artículo ofrece instrucciones acerca de cómo dar formato al código para que el código de F # es:</span><span class="sxs-lookup"><span data-stu-id="c98df-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="c98df-105">Por lo general se ven como más legible</span><span class="sxs-lookup"><span data-stu-id="c98df-105">Generally viewed as more legible</span></span>
* <span data-ttu-id="c98df-106">Está de acuerdo con las convenciones que se aplica al dar formato a otros editores y herramientas en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c98df-106">Is in accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="c98df-107">Similar a otro código en línea</span><span class="sxs-lookup"><span data-stu-id="c98df-107">Similar to other code online</span></span>

<span data-ttu-id="c98df-108">Estas instrucciones se basan en [una guía completa sobre convenciones de formato de F #](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) por [Anh-Dung Phan](https://github.com/dungpa).</span><span class="sxs-lookup"><span data-stu-id="c98df-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="c98df-109">Reglas generales para la sangría</span><span class="sxs-lookup"><span data-stu-id="c98df-109">General rules for indentation</span></span>

<span data-ttu-id="c98df-110">F # utiliza el espacio en blanco significativo de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c98df-110">F# uses significant white space by default.</span></span> <span data-ttu-id="c98df-111">Las instrucciones siguientes están diseñadas para proporcionar una orientación acerca de cómo jugar con algunos desafíos que esto puede imponer.</span><span class="sxs-lookup"><span data-stu-id="c98df-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="c98df-112">Uso de espacios</span><span class="sxs-lookup"><span data-stu-id="c98df-112">Using spaces</span></span>

<span data-ttu-id="c98df-113">Cuando se requiere la sangría, debe usar espacios, tabulaciones no.</span><span class="sxs-lookup"><span data-stu-id="c98df-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="c98df-114">Se requiere al menos un espacio.</span><span class="sxs-lookup"><span data-stu-id="c98df-114">At least one space is required.</span></span> <span data-ttu-id="c98df-115">Su organización puede crear los estándares de codificación para especificar el número de espacios que se usará para la sangría; dos, tres o cuatro espacios de sangría en cada nivel donde se produce la sangría es habitual.</span><span class="sxs-lookup"><span data-stu-id="c98df-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="c98df-116">**Se recomienda 4 espacios por sangría.**</span><span class="sxs-lookup"><span data-stu-id="c98df-116">**We recommend 4 spaces per indentation.**</span></span>

<span data-ttu-id="c98df-117">Es decir, la sangría de programas es algo subjetivo.</span><span class="sxs-lookup"><span data-stu-id="c98df-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="c98df-118">Las variaciones son correctos, pero la primera regla que debería seguir es *coherencia de sangría*.</span><span class="sxs-lookup"><span data-stu-id="c98df-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="c98df-119">Elegir un estilo de sangría generalmente aceptado y utilícela sistemáticamente en el código base.</span><span class="sxs-lookup"><span data-stu-id="c98df-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-blank-lines"></a><span data-ttu-id="c98df-120">Aplicar formato a líneas en blanco</span><span class="sxs-lookup"><span data-stu-id="c98df-120">Formatting blank lines</span></span>

* <span data-ttu-id="c98df-121">Independiente nivel superior (función) y la clase de definiciones con dos líneas en blanco.</span><span class="sxs-lookup"><span data-stu-id="c98df-121">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="c98df-122">Las definiciones de método dentro de una clase se separan mediante una sola línea en blanco.</span><span class="sxs-lookup"><span data-stu-id="c98df-122">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="c98df-123">Líneas en blanco adicionales pueden usarse (con moderación) para separar los grupos de funciones relacionadas.</span><span class="sxs-lookup"><span data-stu-id="c98df-123">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="c98df-124">Pueden omitirse las líneas en blanco entre una serie de líneas de código relacionadas (por ejemplo, un conjunto de implementaciones ficticias).</span><span class="sxs-lookup"><span data-stu-id="c98df-124">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="c98df-125">Use líneas en blanco en las funciones, con moderación, para indicar secciones lógicas.</span><span class="sxs-lookup"><span data-stu-id="c98df-125">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="c98df-126">Aplicar formato a los comentarios</span><span class="sxs-lookup"><span data-stu-id="c98df-126">Formatting comments</span></span>

<span data-ttu-id="c98df-127">Generalmente prefieren varios comentarios de barra diagonal doble a través de comentarios del bloque de estilo de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="c98df-127">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="c98df-128">Comentarios en línea deben poner en mayúsculas la primera letra.</span><span class="sxs-lookup"><span data-stu-id="c98df-128">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="c98df-129">Convenciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="c98df-129">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="c98df-130">Usar camelCase para funciones y los valores de límite de clase, expresión enlazados y patrón enlazadas</span><span class="sxs-lookup"><span data-stu-id="c98df-130">Use camelCase for class-bound, expression-bound and pattern-bound values and functions</span></span>

<span data-ttu-id="c98df-131">Es común y aceptados de F # estilo usar camelCase para nombres de todos los enlazados como variables locales o en coincidencias de patrones y las definiciones de función.</span><span class="sxs-lookup"><span data-stu-id="c98df-131">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="c98df-132">Localmente las funciones enlazadas en clases también deben usar camelCase.</span><span class="sxs-lookup"><span data-stu-id="c98df-132">Locally-bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="c98df-133">Usar camelCase para funciones públicas de módulo enlazados</span><span class="sxs-lookup"><span data-stu-id="c98df-133">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="c98df-134">Cuando una función de módulo enlazados es parte de una API pública, debe usar camelCase:</span><span class="sxs-lookup"><span data-stu-id="c98df-134">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="c98df-135">Usar camelCase para las funciones y los valores de módulo enlazados internos y privados</span><span class="sxs-lookup"><span data-stu-id="c98df-135">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="c98df-136">Usar camelCase para los valores de módulo enlazados privados, incluidas las siguientes:</span><span class="sxs-lookup"><span data-stu-id="c98df-136">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="c98df-137">Funciones ad hoc en secuencias de comandos</span><span class="sxs-lookup"><span data-stu-id="c98df-137">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="c98df-138">Valores que conforman la implementación interna de un tipo o módulo</span><span class="sxs-lookup"><span data-stu-id="c98df-138">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="c98df-139">Usar camelCase para los parámetros</span><span class="sxs-lookup"><span data-stu-id="c98df-139">Use camelCase for parameters</span></span>

<span data-ttu-id="c98df-140">Todos los parámetros deben usar camelCase según las convenciones de nomenclatura. NET.</span><span class="sxs-lookup"><span data-stu-id="c98df-140">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="c98df-141">Usar PascalCase para los módulos</span><span class="sxs-lookup"><span data-stu-id="c98df-141">Use PascalCase for modules</span></span>

<span data-ttu-id="c98df-142">Todos los módulos (nivel superior, internos, privados, anidados) deben usar PascalCase.</span><span class="sxs-lookup"><span data-stu-id="c98df-142">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="c98df-143">Uso PascalCase para las declaraciones de tipos, miembros y etiquetas</span><span class="sxs-lookup"><span data-stu-id="c98df-143">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="c98df-144">Las clases, interfaces, estructuras, enumeraciones, delegados, registros y uniones discriminadas deben denominarse con PascalCase.</span><span class="sxs-lookup"><span data-stu-id="c98df-144">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="c98df-145">Los miembros de tipos y las etiquetas para los registros y uniones discriminadas también deben usar PascalCase.</span><span class="sxs-lookup"><span data-stu-id="c98df-145">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="c98df-146">Usar PascalCase para construcciones intrínsecas para .NET</span><span class="sxs-lookup"><span data-stu-id="c98df-146">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="c98df-147">Espacios de nombres, las excepciones, eventos y proyecto /`.dll` nombres también deben usar PascalCase.</span><span class="sxs-lookup"><span data-stu-id="c98df-147">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="c98df-148">No sólo hace esto que el consumo de otros lenguajes .NET resultar más natural a los consumidores, también es coherente con las convenciones de nomenclatura de .NET que es probable que encuentre.</span><span class="sxs-lookup"><span data-stu-id="c98df-148">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="c98df-149">Evite los caracteres de subrayado en nombres</span><span class="sxs-lookup"><span data-stu-id="c98df-149">Avoid underscores in names</span></span>

<span data-ttu-id="c98df-150">Históricamente, algunas bibliotecas de F # han usado los caracteres de subrayado en nombres.</span><span class="sxs-lookup"><span data-stu-id="c98df-150">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="c98df-151">Sin embargo, esto es ya no amplia aceptación, en parte porque entra en conflicto con las convenciones de nomenclatura. NET.</span><span class="sxs-lookup"><span data-stu-id="c98df-151">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="c98df-152">Es decir, algunos programadores de F # utilizan caracteres de subrayado mucho, en parte por motivos históricos y respeto y la tolerancia es importante.</span><span class="sxs-lookup"><span data-stu-id="c98df-152">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="c98df-153">Sin embargo, tenga en cuenta que el estilo a menudo no me gustó por otros usuarios que tienen la opción de elegir si desea usarlo.</span><span class="sxs-lookup"><span data-stu-id="c98df-153">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="c98df-154">Algunas excepciones incluye interoperar con componentes nativos, en caracteres de subrayado son muy comunes.</span><span class="sxs-lookup"><span data-stu-id="c98df-154">Some exceptions includes interoperating with native components, where underscores are very common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="c98df-155">Utilizar operadores estándar de F #</span><span class="sxs-lookup"><span data-stu-id="c98df-155">Use standard F# operators</span></span>

<span data-ttu-id="c98df-156">Los operadores siguientes se definen en la biblioteca estándar de F # y deben usarse en lugar de definir equivalentes.</span><span class="sxs-lookup"><span data-stu-id="c98df-156">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="c98df-157">Uso de estos operadores se recomienda que tiende a hacer el código más legible e idiomático.</span><span class="sxs-lookup"><span data-stu-id="c98df-157">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="c98df-158">Estar acostumbrados a idiomas distintos a los desarrolladores con experiencia en OCaml o en otro lenguaje de programación funcional.</span><span class="sxs-lookup"><span data-stu-id="c98df-158">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="c98df-159">En la lista siguiente se resume los operadores de F # recomendados.</span><span class="sxs-lookup"><span data-stu-id="c98df-159">The following list summarizes the recommended F# operators.</span></span>

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="c98df-160">Use la sintaxis de prefijo para los genéricos (`Foo<T>`) con preferencia a la sintaxis de postfijo (`T Foo`)</span><span class="sxs-lookup"><span data-stu-id="c98df-160">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="c98df-161">F # hereda tanto el estilo de aprendizaje automático de postfijo de asignación de nombres de tipos genéricos (por ejemplo, `int list`), así como el prefijo de estilo .NET (por ejemplo, `list<int>`).</span><span class="sxs-lookup"><span data-stu-id="c98df-161">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="c98df-162">Se prefiere el estilo. NET, excepto los cuatro tipos específicos:</span><span class="sxs-lookup"><span data-stu-id="c98df-162">Prefer the .NET style, except for four specific types:</span></span>

1. <span data-ttu-id="c98df-163">Para F # las listas, utilice la forma de postfijo: `int list` lugar `list<int>`.</span><span class="sxs-lookup"><span data-stu-id="c98df-163">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="c98df-164">Para opciones de F #, utilice la forma de postfijo: `int option` lugar `option<int>`.</span><span class="sxs-lookup"><span data-stu-id="c98df-164">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="c98df-165">Para las matrices de F #, utilice el nombre sintáctico `int[]` lugar `int array` o `array<int>`.</span><span class="sxs-lookup"><span data-stu-id="c98df-165">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
4. <span data-ttu-id="c98df-166">Para las celdas de referencia, utilice `int ref` lugar `ref<int>` o `Ref<int>`.</span><span class="sxs-lookup"><span data-stu-id="c98df-166">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="c98df-167">Para los demás tipos, use el formato de prefijo.</span><span class="sxs-lookup"><span data-stu-id="c98df-167">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="c98df-168">Aplicar formato a las tuplas</span><span class="sxs-lookup"><span data-stu-id="c98df-168">Formatting tuples</span></span>

<span data-ttu-id="c98df-169">Creación de instancias de una tupla debe incluirse entre paréntesis, y las comas dentro de delimitadores deben ir seguidas por un espacio, por ejemplo: `(1, 2)`, `(x, y, z)`.</span><span class="sxs-lookup"><span data-stu-id="c98df-169">A tuple instantiation should be parenthesized, and the delimiting commas within should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="c98df-170">Normalmente se acepta para omitir los paréntesis en la coincidencia de patrones de tuplas:</span><span class="sxs-lookup"><span data-stu-id="c98df-170">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="c98df-171">Formato discriminadas declaraciones de unión</span><span class="sxs-lookup"><span data-stu-id="c98df-171">Formatting discriminated union declarations</span></span>

<span data-ttu-id="c98df-172">Aplicar sangría a `|` en la definición de tipo por 4 espacios:</span><span class="sxs-lookup"><span data-stu-id="c98df-172">Indent `|` in type definition by 4 spaces:</span></span>

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

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="c98df-173">Formato de uniones discriminadas</span><span class="sxs-lookup"><span data-stu-id="c98df-173">Formatting discriminated unions</span></span>

<span data-ttu-id="c98df-174">Uniones discriminadas con instancias que se dividen en varias líneas debe proporcionar datos contenidos en un nuevo ámbito con sangría:</span><span class="sxs-lookup"><span data-stu-id="c98df-174">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="c98df-175">También puede ser el paréntesis de cierre en una nueva línea:</span><span class="sxs-lookup"><span data-stu-id="c98df-175">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="c98df-176">Aplicar formato a las declaraciones de registro</span><span class="sxs-lookup"><span data-stu-id="c98df-176">Formatting record declarations</span></span>

<span data-ttu-id="c98df-177">Aplicar sangría a `{` en el tipo de definición por 4 espacios e iniciar la lista de campos en la misma línea:</span><span class="sxs-lookup"><span data-stu-id="c98df-177">Indent `{` in type definition by 4 spaces and start the field list on the same line:</span></span>

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

<span data-ttu-id="c98df-178">Al colocar el símbolo (token) de apertura en la misma línea y el token de cierre en una nueva línea también está bien, pero tenga en cuenta que debe usar el [sintaxis detallada](../language-reference/verbose-syntax.md) para definir los miembros (el `with` palabra clave):</span><span class="sxs-lookup"><span data-stu-id="c98df-178">Placing the opening token on the same line and the closing token on a new line is also fine, but be aware that you need to use the [verbose syntax](../language-reference/verbose-syntax.md) to define members (the `with` keyword):</span></span>

```fsharp
//  OK, but verbose syntax required
type PostalAddress = { 
    Address: string
    City: string
    Zip: string
} with
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City
```

## <a name="formatting-records"></a><span data-ttu-id="c98df-179">Formato de registros</span><span class="sxs-lookup"><span data-stu-id="c98df-179">Formatting records</span></span>

<span data-ttu-id="c98df-180">Registros cortos pueden escribirse en una sola línea:</span><span class="sxs-lookup"><span data-stu-id="c98df-180">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="c98df-181">Los registros que son más largas deben usar nuevas líneas para etiquetas:</span><span class="sxs-lookup"><span data-stu-id="c98df-181">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="c98df-182">Al colocar el símbolo (token) de apertura en la misma línea y el token de cierre en una nueva línea también está bien:</span><span class="sxs-lookup"><span data-stu-id="c98df-182">Placing the opening token on the same line and the closing token on a new line is also fine:</span></span>

```fsharp
let rainbow = {
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
```

<span data-ttu-id="c98df-183">Se aplican las mismas reglas para los elementos de lista y matriz.</span><span class="sxs-lookup"><span data-stu-id="c98df-183">The same rules apply for list and array elements.</span></span>

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="c98df-184">Aplicar formato a las listas y matrices</span><span class="sxs-lookup"><span data-stu-id="c98df-184">Formatting lists and arrays</span></span>

<span data-ttu-id="c98df-185">Escribir `x :: l` con espacios alrededor de la `::` operador (`::` es un operador infijo, por lo tanto, rodeado por espacios) y `[1; 2; 3]` (`;` es un delimitador, por lo tanto, seguido por un espacio).</span><span class="sxs-lookup"><span data-stu-id="c98df-185">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces) and `[1; 2; 3]` (`;` is a delimiter, hence followed by a space).</span></span>

<span data-ttu-id="c98df-186">Use siempre al menos un espacio entre dos operadores llave similar a distinct.</span><span class="sxs-lookup"><span data-stu-id="c98df-186">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="c98df-187">Por ejemplo, deje un espacio entre un `[` y un `{`.</span><span class="sxs-lookup"><span data-stu-id="c98df-187">For example, leave a space between a `[` and a `{`.</span></span>

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

<span data-ttu-id="c98df-188">Listas y matrices que se dividen en varias líneas siguen una regla similar como hacen los registros:</span><span class="sxs-lookup"><span data-stu-id="c98df-188">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

```fsharp
let pascalsTriangle = [|
    [|1|]
    [|1; 1|]
    [|1; 2; 1|]
    [|1; 3; 3; 1|]
    [|1; 4; 6; 4; 1|]
    [|1; 5; 10; 10; 5; 1|]
    [|1; 6; 15; 20; 15; 6; 1|]
    [|1; 7; 21; 35; 35; 21; 7; 1|]
    [|1; 8; 28; 56; 70; 56; 28; 8; 1|]
|]
```

## <a name="formatting-if-expressions"></a><span data-ttu-id="c98df-189">Formato if expresiones</span><span class="sxs-lookup"><span data-stu-id="c98df-189">Formatting if expressions</span></span>

<span data-ttu-id="c98df-190">Sangría de condicionales depende de los tamaños de las expresiones que los componen.</span><span class="sxs-lookup"><span data-stu-id="c98df-190">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="c98df-191">Si `cond`, `e1` y `e2` son a corto, basta con escribirlos en una sola línea:</span><span class="sxs-lookup"><span data-stu-id="c98df-191">If `cond`, `e1` and `e2` are short, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="c98df-192">Si bien `cond`, `e1` o `e2` son más larga, pero no de varias líneas:</span><span class="sxs-lookup"><span data-stu-id="c98df-192">If either `cond`, `e1` or `e2` are longer, but not multi-line:</span></span>

```fsharp
if cond
then e1
else e2
```

<span data-ttu-id="c98df-193">Si alguna de las expresiones de varias líneas:</span><span class="sxs-lookup"><span data-stu-id="c98df-193">If any of the expressions are multi-line:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="c98df-194">Varias instrucciones condicionales con `elif` y `else` se les aplica sangría en el mismo ámbito que la `if`:</span><span class="sxs-lookup"><span data-stu-id="c98df-194">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="c98df-195">Construcciones de coincidencia de patrón</span><span class="sxs-lookup"><span data-stu-id="c98df-195">Pattern matching constructs</span></span>

<span data-ttu-id="c98df-196">Use un `|` para cada cláusula de una coincidencia con ninguna sangría.</span><span class="sxs-lookup"><span data-stu-id="c98df-196">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="c98df-197">Si la expresión es corta, puede usar una sola línea, si cada subexpresión también es sencillo.</span><span class="sxs-lookup"><span data-stu-id="c98df-197">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> _
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> _
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

<span data-ttu-id="c98df-198">Si la expresión a la derecha de la flecha de coincidencia es demasiado grande, se moverá a la siguiente línea, un paso con sangría desde el `match` / `|`.</span><span class="sxs-lookup"><span data-stu-id="c98df-198">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="c98df-199">Coincidencia de las funciones anónimas, empezando por `function`, por lo general debe no aplicar sangría demasiado lejos.</span><span class="sxs-lookup"><span data-stu-id="c98df-199">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="c98df-200">Por ejemplo, está bien aplicar sangría a un ámbito como sigue:</span><span class="sxs-lookup"><span data-stu-id="c98df-200">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="c98df-201">Coincidencia de patrones en las funciones definidas por `let` o `let rec` debe ser con sangría 4 espacios después de iniciar de `let`, incluso si `function` se utiliza la palabra clave:</span><span class="sxs-lookup"><span data-stu-id="c98df-201">Pattern matching in functions defined by `let` or `let rec` should be indented 4 spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="c98df-202">No se recomienda alinear las flechas.</span><span class="sxs-lookup"><span data-stu-id="c98df-202">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="c98df-203">Formato try / with expresiones</span><span class="sxs-lookup"><span data-stu-id="c98df-203">Formatting try/with expressions</span></span>

<span data-ttu-id="c98df-204">Coincidencia de patrones en el tipo de excepción deben aplicarse sangría en el mismo nivel que `with`.</span><span class="sxs-lookup"><span data-stu-id="c98df-204">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

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

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="c98df-205">Aplicar formato a la aplicación de parámetro de función</span><span class="sxs-lookup"><span data-stu-id="c98df-205">Formatting function parameter application</span></span>

<span data-ttu-id="c98df-206">En general, la mayoría de los aplicaciones de parámetro de función se realiza en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="c98df-206">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="c98df-207">Si desea aplicar los parámetros a una función en una nueva línea, sangría por un ámbito.</span><span class="sxs-lookup"><span data-stu-id="c98df-207">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

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

<span data-ttu-id="c98df-208">Se aplican las mismas instrucciones para las expresiones lambda como argumentos de función.</span><span class="sxs-lookup"><span data-stu-id="c98df-208">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="c98df-209">Si el cuerpo de una expresión lambda, el cuerpo puede tener la siguiente línea, aplica sangría a un ámbito</span><span class="sxs-lookup"><span data-stu-id="c98df-209">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

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

<span data-ttu-id="c98df-210">Sin embargo, si el cuerpo de una expresión lambda tiene más de una línea, considere la posibilidad de factorización a probarlo en una función independiente en lugar de tener una construcción de varias líneas, aplicarse como un único argumento a una función.</span><span class="sxs-lookup"><span data-stu-id="c98df-210">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="c98df-211">Aplicar formato a los operadores de infijo</span><span class="sxs-lookup"><span data-stu-id="c98df-211">Formatting infix operators</span></span>

<span data-ttu-id="c98df-212">Operadores separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="c98df-212">Separate operators by spaces.</span></span> <span data-ttu-id="c98df-213">Obvias excepciones a esta regla son los `!` y `.` operadores.</span><span class="sxs-lookup"><span data-stu-id="c98df-213">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="c98df-214">Las expresiones de infijo son Aceptar a línea en la misma columna:</span><span class="sxs-lookup"><span data-stu-id="c98df-214">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="c98df-215">Aplicar formato a los operadores de canalización</span><span class="sxs-lookup"><span data-stu-id="c98df-215">Formatting pipeline operators</span></span>

<span data-ttu-id="c98df-216">Canalización `|>` operadores deben ir debajo de las expresiones que operan en.</span><span class="sxs-lookup"><span data-stu-id="c98df-216">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

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

### <a name="formatting-modules"></a><span data-ttu-id="c98df-217">Aplicar formato a los módulos</span><span class="sxs-lookup"><span data-stu-id="c98df-217">Formatting modules</span></span>

<span data-ttu-id="c98df-218">Código de un módulo local se debe aplicar sangría en relación con el módulo, pero no debe aplicarse sangría a código en un módulo de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="c98df-218">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="c98df-219">Elementos Namespace no es necesario que tenga la sangría.</span><span class="sxs-lookup"><span data-stu-id="c98df-219">Namespace elements do not have to be indented.</span></span>

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

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="c98df-220">Aplicar formato a expresiones de objeto e interfaces</span><span class="sxs-lookup"><span data-stu-id="c98df-220">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="c98df-221">Expresiones de objeto y las interfaces deben alinearse de la misma manera con `member` que se aplica sangría después de 4 espacios.</span><span class="sxs-lookup"><span data-stu-id="c98df-221">Object expressions and interfaces should be aligned in the same way with `member` being indented after 4 spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s : String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="c98df-222">Espacio en blanco en las expresiones de formato</span><span class="sxs-lookup"><span data-stu-id="c98df-222">Formatting white space in expressions</span></span>

<span data-ttu-id="c98df-223">Evite los espacios en blanco en las expresiones de F #.</span><span class="sxs-lookup"><span data-stu-id="c98df-223">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="c98df-224">Argumentos con nombre también no deben tener espacio que rodea el `=`:</span><span class="sxs-lookup"><span data-stu-id="c98df-224">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```
