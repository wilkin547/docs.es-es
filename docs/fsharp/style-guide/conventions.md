---
title: Convenciones de código de F#
description: Aprenda instrucciones generales y expresiones al escribir F# código.
ms.date: 01/15/2020
ms.openlocfilehash: ca86bcf714d2fb4ee5f173ee54ba12c317f9abe7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737826"
---
# <a name="f-coding-conventions"></a><span data-ttu-id="0677d-103">Convenciones de código de F#</span><span class="sxs-lookup"><span data-stu-id="0677d-103">F# coding conventions</span></span>

<span data-ttu-id="0677d-104">Las siguientes convenciones están formuladas por la experiencia en F# trabajar con códigos base grandes.</span><span class="sxs-lookup"><span data-stu-id="0677d-104">The following conventions are formulated from experience working with large F# codebases.</span></span> <span data-ttu-id="0677d-105">Los [cinco principios de buen F# código](index.md#five-principles-of-good-f-code) son la base de cada recomendación.</span><span class="sxs-lookup"><span data-stu-id="0677d-105">The [Five principles of good F# code](index.md#five-principles-of-good-f-code) are the foundation of each recommendation.</span></span> <span data-ttu-id="0677d-106">Están relacionados con las [ F# directrices de diseño de componentes](component-design-guidelines.md), pero son aplicables a F# cualquier código, no solo a los componentes como las bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="0677d-106">They are related to the [F# component design guidelines](component-design-guidelines.md), but are applicable for any F# code, not just components such as libraries.</span></span>

## <a name="organizing-code"></a><span data-ttu-id="0677d-107">Organizar código</span><span class="sxs-lookup"><span data-stu-id="0677d-107">Organizing code</span></span>

<span data-ttu-id="0677d-108">F#presenta dos maneras principales de organizar el código: los módulos y los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="0677d-108">F# features two primary ways to organize code: modules and namespaces.</span></span> <span data-ttu-id="0677d-109">Son similares, pero tienen las siguientes diferencias:</span><span class="sxs-lookup"><span data-stu-id="0677d-109">These are similar, but do have the following differences:</span></span>

* <span data-ttu-id="0677d-110">Los espacios de nombres se compilan como espacios de nombres .NET.</span><span class="sxs-lookup"><span data-stu-id="0677d-110">Namespaces are compiled as .NET namespaces.</span></span> <span data-ttu-id="0677d-111">Los módulos se compilan como clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="0677d-111">Modules are compiled as static classes.</span></span>
* <span data-ttu-id="0677d-112">Los espacios de nombres siempre son de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="0677d-112">Namespaces are always top level.</span></span> <span data-ttu-id="0677d-113">Los módulos pueden ser de nivel superior y estar anidados dentro de otros módulos.</span><span class="sxs-lookup"><span data-stu-id="0677d-113">Modules can be top-level and nested within other modules.</span></span>
* <span data-ttu-id="0677d-114">Los espacios de nombres pueden abarcar varios archivos.</span><span class="sxs-lookup"><span data-stu-id="0677d-114">Namespaces can span multiple files.</span></span> <span data-ttu-id="0677d-115">Los módulos no pueden.</span><span class="sxs-lookup"><span data-stu-id="0677d-115">Modules cannot.</span></span>
* <span data-ttu-id="0677d-116">Los módulos se pueden decorar con `[<RequireQualifiedAccess>]` y `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="0677d-116">Modules can be decorated with `[<RequireQualifiedAccess>]` and `[<AutoOpen>]`.</span></span>

<span data-ttu-id="0677d-117">Las instrucciones siguientes le ayudarán a usarlos para organizar el código.</span><span class="sxs-lookup"><span data-stu-id="0677d-117">The following guidelines will help you use these to organize your code.</span></span>

### <a name="prefer-namespaces-at-the-top-level"></a><span data-ttu-id="0677d-118">Preferir espacios de nombres en el nivel superior</span><span class="sxs-lookup"><span data-stu-id="0677d-118">Prefer namespaces at the top level</span></span>

<span data-ttu-id="0677d-119">En el caso de cualquier código consumible públicamente, los espacios de nombres son preferentes para los módulos en el nivel superior.</span><span class="sxs-lookup"><span data-stu-id="0677d-119">For any publicly consumable code, namespaces are preferential to modules at the top level.</span></span> <span data-ttu-id="0677d-120">Dado que se compilan como espacios de nombres .NET, se pueden C# consumir desde sin ningún problema.</span><span class="sxs-lookup"><span data-stu-id="0677d-120">Because they are compiled as .NET namespaces, they are consumable from C# with no issue.</span></span>

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

<span data-ttu-id="0677d-121">El uso de un módulo de nivel superior no puede aparecer de forma diferente F#cuando se llama C# solo desde, pero para los consumidores, los autores de la llamada pueden sorprender al tener que calificar `MyClass` con el módulo de `MyCode`.</span><span class="sxs-lookup"><span data-stu-id="0677d-121">Using a top-level module may not appear different when called only from F#, but for C# consumers, callers may be surprised by having to qualify `MyClass` with the `MyCode` module.</span></span>

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a><span data-ttu-id="0677d-122">Aplicar cuidadosamente `[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="0677d-122">Carefully apply `[<AutoOpen>]`</span></span>

<span data-ttu-id="0677d-123">La construcción `[<AutoOpen>]` puede contaminar el ámbito de lo que está disponible para los autores de llamadas y la respuesta a la que procede algo de es "Magic".</span><span class="sxs-lookup"><span data-stu-id="0677d-123">The `[<AutoOpen>]` construct can pollute the scope of what is available to callers, and the answer to where something comes from is "magic".</span></span> <span data-ttu-id="0677d-124">Esto no es una buena cosa.</span><span class="sxs-lookup"><span data-stu-id="0677d-124">This is not a good thing.</span></span> <span data-ttu-id="0677d-125">Una excepción a esta regla es la F# propia biblioteca básica (aunque este hecho también es un poco polémico).</span><span class="sxs-lookup"><span data-stu-id="0677d-125">An exception to this rule is the F# Core Library itself (though this fact is also a bit controversial).</span></span>

<span data-ttu-id="0677d-126">Sin embargo, es una comodidad si tiene una funcionalidad auxiliar para una API pública que desea organizar por separado de esa API pública.</span><span class="sxs-lookup"><span data-stu-id="0677d-126">However, it is a convenience if you have helper functionality for a public API that you wish to organize separately from that public API.</span></span>

```fsharp
module MyAPI =
    [<AutoOpen>]
    module private Helpers =
        let helper1 x y z =
            ...

    let myFunction1 x =
        let y = ...
        let z = ...

        helper1 x y z
```

<span data-ttu-id="0677d-127">Esto le permite separar claramente los detalles de implementación de la API pública de una función sin tener que calificar totalmente una aplicación auxiliar cada vez que la llame.</span><span class="sxs-lookup"><span data-stu-id="0677d-127">This lets you cleanly separate implementation details from the public API of a function without having to fully qualify a helper each time you call it.</span></span>

<span data-ttu-id="0677d-128">Además, exponer métodos de extensión y generadores de expresiones en el nivel de espacio de nombres se puede expresar perfectamente con `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="0677d-128">Additionally, exposing extension methods and expression builders at the namespace level can be neatly expressed with `[<AutoOpen>]`.</span></span>

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a><span data-ttu-id="0677d-129">Usar `[<RequireQualifiedAccess>]` siempre que los nombres puedan entrar en conflicto o se sienta útil para mejorar la legibilidad</span><span class="sxs-lookup"><span data-stu-id="0677d-129">Use `[<RequireQualifiedAccess>]` whenever names could conflict or you feel it helps with readability</span></span>

<span data-ttu-id="0677d-130">Agregar el atributo `[<RequireQualifiedAccess>]` a un módulo indica que el módulo no se puede abrir y que las referencias a los elementos del módulo requieren un acceso calificado explícito.</span><span class="sxs-lookup"><span data-stu-id="0677d-130">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="0677d-131">Por ejemplo, el módulo `Microsoft.FSharp.Collections.List` tiene este atributo.</span><span class="sxs-lookup"><span data-stu-id="0677d-131">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="0677d-132">Esto resulta útil cuando las funciones y los valores del módulo tienen nombres que es probable que entren en conflicto con los nombres de otros módulos.</span><span class="sxs-lookup"><span data-stu-id="0677d-132">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="0677d-133">Requerir acceso cualificado puede aumentar considerablemente el mantenimiento a largo plazo y la evolución de una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="0677d-133">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a><span data-ttu-id="0677d-134">Ordenar `open` instrucciones topológicamente</span><span class="sxs-lookup"><span data-stu-id="0677d-134">Sort `open` statements topologically</span></span>

<span data-ttu-id="0677d-135">En F#, el orden de las declaraciones es importante, incluso con instrucciones `open`.</span><span class="sxs-lookup"><span data-stu-id="0677d-135">In F#, the order of declarations matters, including with `open` statements.</span></span> <span data-ttu-id="0677d-136">Esto no es lo C#mismo, donde el efecto de `using` y `using static` es independiente del orden de esas instrucciones en un archivo.</span><span class="sxs-lookup"><span data-stu-id="0677d-136">This is unlike C#, where the effect of `using` and `using static` is independent of the ordering of those statements in a file.</span></span>

<span data-ttu-id="0677d-137">En F#, los elementos abiertos en un ámbito pueden ocultar otros ya presentes.</span><span class="sxs-lookup"><span data-stu-id="0677d-137">In F#, elements opened into a scope can shadow others already present.</span></span> <span data-ttu-id="0677d-138">Esto significa que la reordenación de `open` instrucciones podría modificar el significado del código.</span><span class="sxs-lookup"><span data-stu-id="0677d-138">This means that reordering `open` statements could alter the meaning of code.</span></span> <span data-ttu-id="0677d-139">Como resultado, no se recomienda ninguna ordenación arbitraria de todas `open` instrucciones (por ejemplo, alfanuméricamente), consulta generar un comportamiento diferente que podría esperar.</span><span class="sxs-lookup"><span data-stu-id="0677d-139">As a result, any arbitrary sorting of all `open` statements (for example, alphanumerically) is not recommended, lest you generate different behavior that you might expect.</span></span>

<span data-ttu-id="0677d-140">En su lugar, se recomienda ordenarlas [topológicamente](https://en.wikipedia.org/wiki/Topological_sorting); es decir, ordene las instrucciones `open` en el orden en el que se definen las _capas_ del sistema.</span><span class="sxs-lookup"><span data-stu-id="0677d-140">Instead, we recommend that you sort them [topologically](https://en.wikipedia.org/wiki/Topological_sorting); that is, order your `open` statements in the order in which _layers_ of your system are defined.</span></span> <span data-ttu-id="0677d-141">También se puede tener en cuenta la ordenación alfanumérica en diferentes capas topológicas.</span><span class="sxs-lookup"><span data-stu-id="0677d-141">Doing alphanumeric sorting within different topological layers may also be considered.</span></span>

<span data-ttu-id="0677d-142">Por ejemplo, esta es la Ordenación topológica del archivo de API F# pública del servicio de compilador:</span><span class="sxs-lookup"><span data-stu-id="0677d-142">As an example, here is the topological sorting for the F# compiler service public API file:</span></span>

```fsharp
namespace Microsoft.FSharp.Compiler.SourceCodeServices

open System
open System.Collections.Generic
open System.Collections.Concurrent
open System.Diagnostics
open System.IO
open System.Reflection
open System.Text

open Microsoft.FSharp.Compiler
open Microsoft.FSharp.Compiler.AbstractIL
open Microsoft.FSharp.Compiler.AbstractIL.Diagnostics
open Microsoft.FSharp.Compiler.AbstractIL.IL
open Microsoft.FSharp.Compiler.AbstractIL.ILBinaryReader
open Microsoft.FSharp.Compiler.AbstractIL.Internal
open Microsoft.FSharp.Compiler.AbstractIL.Internal.Library

open Microsoft.FSharp.Compiler.AccessibilityLogic
open Microsoft.FSharp.Compiler.Ast
open Microsoft.FSharp.Compiler.CompileOps
open Microsoft.FSharp.Compiler.CompileOptions
open Microsoft.FSharp.Compiler.Driver
open Microsoft.FSharp.Compiler.ErrorLogger
open Microsoft.FSharp.Compiler.Infos
open Microsoft.FSharp.Compiler.InfoReader
open Microsoft.FSharp.Compiler.Lexhelp
open Microsoft.FSharp.Compiler.Layout
open Microsoft.FSharp.Compiler.Lib
open Microsoft.FSharp.Compiler.NameResolution
open Microsoft.FSharp.Compiler.PrettyNaming
open Microsoft.FSharp.Compiler.Parser
open Microsoft.FSharp.Compiler.Range
open Microsoft.FSharp.Compiler.Tast
open Microsoft.FSharp.Compiler.Tastops
open Microsoft.FSharp.Compiler.TcGlobals
open Microsoft.FSharp.Compiler.TypeChecker
open Microsoft.FSharp.Compiler.SourceCodeServices.SymbolHelpers

open Internal.Utilities
open Internal.Utilities.Collections
```

<span data-ttu-id="0677d-143">Tenga en cuenta que un salto de línea separa las capas topológicas, y cada capa se ordena de forma alfanumérica después.</span><span class="sxs-lookup"><span data-stu-id="0677d-143">Note that a line break separates topological layers, with each layer being sorted alphanumerically afterwards.</span></span> <span data-ttu-id="0677d-144">Esto organiza correctamente el código sin sombrear los valores accidentalmente.</span><span class="sxs-lookup"><span data-stu-id="0677d-144">This cleanly organizes code without accidentally shadowing values.</span></span>

## <a name="use-classes-to-contain-values-that-have-side-effects"></a><span data-ttu-id="0677d-145">Usar clases para contener valores que tengan efectos secundarios</span><span class="sxs-lookup"><span data-stu-id="0677d-145">Use classes to contain values that have side effects</span></span>

<span data-ttu-id="0677d-146">Hay muchas ocasiones en las que la inicialización de un valor puede tener efectos secundarios, como la creación de instancias de un contexto en una base de datos u otro recurso remoto.</span><span class="sxs-lookup"><span data-stu-id="0677d-146">There are many times when initializing a value can have side effects, such as instantiating a context to a database or other remote resource.</span></span> <span data-ttu-id="0677d-147">Es tentador inicializar estos elementos en un módulo y usarlo en las funciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="0677d-147">It is tempting to initialize such things in a module and use it in subsequent functions:</span></span>

```fsharp
// This is bad!
module MyApi =
    let dep1 = File.ReadAllText "/Users/{your name}/connectionstring.txt"
    let dep2 = Environment.GetEnvironmentVariable "DEP_2"

    let private r = Random()
    let dep3() = r.Next() // Problematic if multiple threads use this

    let function1 arg = doStuffWith dep1 dep2 dep3 arg
    let function2 arg = doSutffWith dep1 dep2 dep3 arg
```

<span data-ttu-id="0677d-148">Esta suele ser una mala idea por varias razones:</span><span class="sxs-lookup"><span data-stu-id="0677d-148">This is frequently a bad idea for a few reasons:</span></span>

<span data-ttu-id="0677d-149">En primer lugar, la configuración de la aplicación se inserta en el código base con `dep1` y `dep2`.</span><span class="sxs-lookup"><span data-stu-id="0677d-149">First, application configuration is pushed into the codebase with `dep1` and `dep2`.</span></span> <span data-ttu-id="0677d-150">Esto es difícil de mantener en códigos base mayores.</span><span class="sxs-lookup"><span data-stu-id="0677d-150">This is difficult to maintain in larger codebases.</span></span>

<span data-ttu-id="0677d-151">En segundo lugar, los datos inicializados de forma estática no deben incluir valores que no sean seguros para subprocesos si el componente utilizará varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="0677d-151">Second, statically initialized data should not include values that are not thread safe if your component will itself use multiple threads.</span></span> <span data-ttu-id="0677d-152">Esto se ha infringido claramente en `dep3`.</span><span class="sxs-lookup"><span data-stu-id="0677d-152">This is clearly violated by `dep3`.</span></span>

<span data-ttu-id="0677d-153">Por último, la inicialización del módulo se compila en un constructor estático para toda la unidad de compilación.</span><span class="sxs-lookup"><span data-stu-id="0677d-153">Finally, module initialization compiles into a static constructor for the entire compilation unit.</span></span> <span data-ttu-id="0677d-154">Si se produce algún error en la inicialización de los valores enlazados en ese módulo, se manifiesta como `TypeInitializationException` que se almacena en caché para toda la duración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0677d-154">If any error occurs in let-bound value initialization in that module, it manifests as a `TypeInitializationException` that is then cached for the entire lifetime of the application.</span></span> <span data-ttu-id="0677d-155">Esto puede ser difícil de diagnosticar.</span><span class="sxs-lookup"><span data-stu-id="0677d-155">This can be difficult to diagnose.</span></span> <span data-ttu-id="0677d-156">Normalmente, hay una excepción interna que se puede tratar de explicar, pero si no lo está, no hay que indicar cuál es la causa raíz.</span><span class="sxs-lookup"><span data-stu-id="0677d-156">There is usually an inner exception that you can attempt to reason about, but if there is not, then there is no telling what the root cause is.</span></span>

<span data-ttu-id="0677d-157">En su lugar, use simplemente una clase simple para almacenar las dependencias:</span><span class="sxs-lookup"><span data-stu-id="0677d-157">Instead, just use a simple class to hold dependencies:</span></span>

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member _.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member _.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

<span data-ttu-id="0677d-158">Esto permite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0677d-158">This enables the following:</span></span>

1. <span data-ttu-id="0677d-159">Inserción de cualquier estado dependiente fuera de la propia API.</span><span class="sxs-lookup"><span data-stu-id="0677d-159">Pushing any dependent state outside of the API itself.</span></span>
2. <span data-ttu-id="0677d-160">La configuración ahora se puede realizar fuera de la API.</span><span class="sxs-lookup"><span data-stu-id="0677d-160">Configuration can now be done outside of the API.</span></span>
3. <span data-ttu-id="0677d-161">No es probable que los errores de inicialización de los valores dependientes sean manifiestos como `TypeInitializationException`.</span><span class="sxs-lookup"><span data-stu-id="0677d-161">Errors in initialization for dependent values are not likely to manifest as a `TypeInitializationException`.</span></span>
4. <span data-ttu-id="0677d-162">La API es ahora más fácil de probar.</span><span class="sxs-lookup"><span data-stu-id="0677d-162">The API is now easier to test.</span></span>

## <a name="error-management"></a><span data-ttu-id="0677d-163">Administración de errores</span><span class="sxs-lookup"><span data-stu-id="0677d-163">Error management</span></span>

<span data-ttu-id="0677d-164">La administración de errores en grandes sistemas es un esfuerzo complejo y con matices, y no hay ninguna viñeta Silver para asegurarse de que los sistemas son tolerantes a errores y se comportan correctamente.</span><span class="sxs-lookup"><span data-stu-id="0677d-164">Error management in large systems is a complex and nuanced endeavor, and there are no silver bullets in ensuring your systems are fault-tolerant and behave well.</span></span> <span data-ttu-id="0677d-165">Las siguientes directrices deben proporcionar orientación para navegar por este espacio difícil.</span><span class="sxs-lookup"><span data-stu-id="0677d-165">The following guidelines should offer guidance in navigating this difficult space.</span></span>

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a><span data-ttu-id="0677d-166">Representar casos de error y estado no válido en tipos intrínsecos de su dominio</span><span class="sxs-lookup"><span data-stu-id="0677d-166">Represent error cases and illegal state in types intrinsic to your domain</span></span>

<span data-ttu-id="0677d-167">Con las [uniones discriminadas](../language-reference/discriminated-unions.md), F# ofrece la posibilidad de representar el estado de un programa defectuoso en el sistema de tipos.</span><span class="sxs-lookup"><span data-stu-id="0677d-167">With [Discriminated Unions](../language-reference/discriminated-unions.md), F# gives you the ability to represent faulty program state in your type system.</span></span> <span data-ttu-id="0677d-168">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0677d-168">For example:</span></span>

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

<span data-ttu-id="0677d-169">En este caso, se puede producir un error en las tres formas conocidas de retirar dinero de una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="0677d-169">In this case, there are three known ways that withdrawing money from a bank account can fail.</span></span> <span data-ttu-id="0677d-170">Cada caso de error se representa en el tipo y, por tanto, se puede tratar con seguridad en todo el programa.</span><span class="sxs-lookup"><span data-stu-id="0677d-170">Each error case is represented in the type, and can thus be dealt with safely throughout the program.</span></span>

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

<span data-ttu-id="0677d-171">En general, si puede modelar las distintas formas en que se puede **producir un error** en el dominio, el código de control de errores ya no se trata como algo que debe abordar además del flujo normal del programa.</span><span class="sxs-lookup"><span data-stu-id="0677d-171">In general, if you can model the different ways that something can **fail** in your domain, then error handling code is no longer treated as something you must deal with in addition to regular program flow.</span></span> <span data-ttu-id="0677d-172">Es simplemente parte del flujo normal del programa y no se considera **excepcional**.</span><span class="sxs-lookup"><span data-stu-id="0677d-172">It is simply a part of normal program flow, and not considered **exceptional**.</span></span> <span data-ttu-id="0677d-173">Esto tiene dos ventajas principales:</span><span class="sxs-lookup"><span data-stu-id="0677d-173">There are two primary benefits to this:</span></span>

1. <span data-ttu-id="0677d-174">Es más fácil de mantener a medida que su dominio cambia con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="0677d-174">It is easier to maintain as your domain changes over time.</span></span>
2. <span data-ttu-id="0677d-175">Los casos de error son más fáciles de probar unitarias.</span><span class="sxs-lookup"><span data-stu-id="0677d-175">Error cases are easier to unit test.</span></span>

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a><span data-ttu-id="0677d-176">Usar excepciones cuando los errores no se pueden representar con tipos</span><span class="sxs-lookup"><span data-stu-id="0677d-176">Use exceptions when errors cannot be represented with types</span></span>

<span data-ttu-id="0677d-177">No todos los errores se pueden representar en un dominio problemático.</span><span class="sxs-lookup"><span data-stu-id="0677d-177">Not all errors can be represented in a problem domain.</span></span> <span data-ttu-id="0677d-178">Estos tipos de errores son *excepcionales* por naturaleza, por lo tanto, la capacidad de generar y detectar F#excepciones en.</span><span class="sxs-lookup"><span data-stu-id="0677d-178">These kinds of faults are *exceptional* in nature, hence the ability to raise and catch exceptions in F#.</span></span>

<span data-ttu-id="0677d-179">En primer lugar, se recomienda leer las [instrucciones de diseño de excepciones](../../standard/design-guidelines/exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="0677d-179">First, it is recommended that you read the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md).</span></span> <span data-ttu-id="0677d-180">También se aplican a F#.</span><span class="sxs-lookup"><span data-stu-id="0677d-180">These are also applicable to F#.</span></span>

<span data-ttu-id="0677d-181">Las construcciones principales disponibles en F# para la generación de excepciones se deben tener en cuenta en el siguiente orden de preferencia:</span><span class="sxs-lookup"><span data-stu-id="0677d-181">The main constructs available in F# for the purposes of raising exceptions should be considered in the following order of preference:</span></span>

| <span data-ttu-id="0677d-182">Función</span><span class="sxs-lookup"><span data-stu-id="0677d-182">Function</span></span> | <span data-ttu-id="0677d-183">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0677d-183">Syntax</span></span> | <span data-ttu-id="0677d-184">Propósito</span><span class="sxs-lookup"><span data-stu-id="0677d-184">Purpose</span></span> |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | <span data-ttu-id="0677d-185">Genera una `System.ArgumentNullException` con el nombre de argumento especificado.</span><span class="sxs-lookup"><span data-stu-id="0677d-185">Raises a `System.ArgumentNullException` with the specified argument name.</span></span> |
| `invalidArg` | `invalidArg "argumentName" "message"` | <span data-ttu-id="0677d-186">Genera una `System.ArgumentException` con un nombre y un mensaje de argumento especificados.</span><span class="sxs-lookup"><span data-stu-id="0677d-186">Raises a `System.ArgumentException` with a specified argument name and message.</span></span> |
| `invalidOp` | `invalidOp "message"` | <span data-ttu-id="0677d-187">Genera una `System.InvalidOperationException` con el mensaje especificado.</span><span class="sxs-lookup"><span data-stu-id="0677d-187">Raises a `System.InvalidOperationException` with the specified message.</span></span> |
|`raise`| `raise (ExceptionType("message"))` | <span data-ttu-id="0677d-188">Mecanismo de uso general para producir excepciones.</span><span class="sxs-lookup"><span data-stu-id="0677d-188">General-purpose mechanism for throwing exceptions.</span></span> |
| `failwith` | `failwith "message"` | <span data-ttu-id="0677d-189">Genera una `System.Exception` con el mensaje especificado.</span><span class="sxs-lookup"><span data-stu-id="0677d-189">Raises a `System.Exception` with the specified message.</span></span> |
| `failwithf` | `failwithf "format string" argForFormatString` | <span data-ttu-id="0677d-190">Genera una `System.Exception` con un mensaje determinado por la cadena de formato y sus entradas.</span><span class="sxs-lookup"><span data-stu-id="0677d-190">Raises a `System.Exception` with a message determined by the format string and its inputs.</span></span> |

<span data-ttu-id="0677d-191">Use `nullArg`, `invalidArg` y `invalidOp` como mecanismo para iniciar `ArgumentNullException`, `ArgumentException` y `InvalidOperationException` cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="0677d-191">Use `nullArg`, `invalidArg` and `invalidOp` as the mechanism to throw `ArgumentNullException`, `ArgumentException` and `InvalidOperationException` when appropriate.</span></span>

<span data-ttu-id="0677d-192">Por lo general, las funciones `failwith` y `failwithf` deben evitarse porque generan el tipo de `Exception` base, no una excepción específica.</span><span class="sxs-lookup"><span data-stu-id="0677d-192">The `failwith` and `failwithf` functions should generally be avoided because they raise the base `Exception` type, not a specific exception.</span></span> <span data-ttu-id="0677d-193">En función de las [instrucciones de diseño de excepciones](../../standard/design-guidelines/exceptions.md), desea producir excepciones más específicas cuando sea posible.</span><span class="sxs-lookup"><span data-stu-id="0677d-193">As per the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md), you want to raise more specific exceptions when you can.</span></span>

### <a name="using-exception-handling-syntax"></a><span data-ttu-id="0677d-194">Usar la sintaxis de control de excepciones</span><span class="sxs-lookup"><span data-stu-id="0677d-194">Using exception-handling syntax</span></span>

<span data-ttu-id="0677d-195">F#admite patrones de excepción a través de la sintaxis de `try...with`:</span><span class="sxs-lookup"><span data-stu-id="0677d-195">F# supports exception patterns via the `try...with` syntax:</span></span>

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

<span data-ttu-id="0677d-196">La reconciliación de la funcionalidad para realizar en el caso de una excepción con la coincidencia de patrones puede ser un poco complicada si desea mantener el código limpio.</span><span class="sxs-lookup"><span data-stu-id="0677d-196">Reconciling functionality to perform in the face of an exception with pattern matching can be a bit tricky if you wish to keep the code clean.</span></span> <span data-ttu-id="0677d-197">Una manera de controlar esto es usar [patrones activos](../language-reference/active-patterns.md) como medio para agrupar la funcionalidad en torno a un caso de error con una excepción.</span><span class="sxs-lookup"><span data-stu-id="0677d-197">One such way to handle this is to use [active patterns](../language-reference/active-patterns.md) as a means to group functionality surrounding an error case with an exception itself.</span></span> <span data-ttu-id="0677d-198">Por ejemplo, puede que esté consumiendo una API que, cuando se produce una excepción, incluye información valiosa en los metadatos de la excepción.</span><span class="sxs-lookup"><span data-stu-id="0677d-198">For example, you may be consuming an API that, when it throws an exception, encloses valuable information in the exception metadata.</span></span> <span data-ttu-id="0677d-199">Desencapsular un valor útil en el cuerpo de la excepción capturada dentro del modelo activo y devolver ese valor puede ser útil en algunas situaciones.</span><span class="sxs-lookup"><span data-stu-id="0677d-199">Unwrapping a useful value in the body of the captured exception inside the Active Pattern and returning that value can be helpful in some situations.</span></span>

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a><span data-ttu-id="0677d-200">No usar el control de errores Monad para reemplazar excepciones</span><span class="sxs-lookup"><span data-stu-id="0677d-200">Do not use monadic error handling to replace exceptions</span></span>

<span data-ttu-id="0677d-201">Las excepciones se ven como algo Taboo en la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="0677d-201">Exceptions are seen as somewhat taboo in functional programming.</span></span> <span data-ttu-id="0677d-202">De hecho, las excepciones infringen la pureza, por lo que es seguro considerarlas que no son bastante funcionales.</span><span class="sxs-lookup"><span data-stu-id="0677d-202">Indeed, exceptions violate purity, so it's safe to consider them not-quite functional.</span></span> <span data-ttu-id="0677d-203">Sin embargo, esto omite la realidad de dónde se debe ejecutar el código y que se pueden producir errores en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0677d-203">However, this ignores the reality of where code must run, and that runtime errors can occur.</span></span> <span data-ttu-id="0677d-204">En general, escriba código en el supuesto de que la mayoría de las cosas no son puras ni totales, con el fin de minimizar las sorpresas desagradables.</span><span class="sxs-lookup"><span data-stu-id="0677d-204">In general, write code on the assumption that most things are neither pure nor total, to minimize unpleasant surprises.</span></span>

<span data-ttu-id="0677d-205">Es importante tener en cuenta los siguientes aspectos principales y aspectos de las excepciones con respecto a su relevancia y adecuadaidad en el entorno de tiempo de ejecución .NET y el ecosistema multilingüe:</span><span class="sxs-lookup"><span data-stu-id="0677d-205">It is important to consider the following core strengths/aspects of Exceptions with respect to their relevance and appropriateness in the .NET runtime and cross-language ecosystem as a whole:</span></span>

1. <span data-ttu-id="0677d-206">Contienen información de diagnóstico detallada, que es muy útil al depurar un problema.</span><span class="sxs-lookup"><span data-stu-id="0677d-206">They contain detailed diagnostic information, which is very helpful when debugging an issue.</span></span>
2. <span data-ttu-id="0677d-207">Son perfectamente entendidos por el tiempo de ejecución y otros lenguajes de .NET.</span><span class="sxs-lookup"><span data-stu-id="0677d-207">They are well-understood by the runtime and other .NET languages.</span></span>
3. <span data-ttu-id="0677d-208">Pueden reducir el REUTILIZADOR significativo cuando se comparan con el código que sale de su forma de *evitar* excepciones mediante la implementación de un subconjunto de su semántica de manera ad hoc.</span><span class="sxs-lookup"><span data-stu-id="0677d-208">They can reduce significant boilerplate when compared with code that goes out of its way to *avoid* exceptions by implementing some subset of their semantics on an ad-hoc basis.</span></span>

<span data-ttu-id="0677d-209">Este tercer punto es crítico.</span><span class="sxs-lookup"><span data-stu-id="0677d-209">This third point is critical.</span></span> <span data-ttu-id="0677d-210">En el caso de las operaciones complejas no triviales, el uso de excepciones puede tener como resultado la gestión de estructuras como esta:</span><span class="sxs-lookup"><span data-stu-id="0677d-210">For nontrivial complex operations, failing to use exceptions can result in dealing with structures like this:</span></span>

```fsharp
Result<Result<MyType, string>, string list>
```

<span data-ttu-id="0677d-211">Que puede conducir fácilmente a un código frágil, como la coincidencia de patrones en errores "con tipo de cadena":</span><span class="sxs-lookup"><span data-stu-id="0677d-211">Which can easily lead to fragile code like pattern matching on "stringly-typed" errors:</span></span>

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

<span data-ttu-id="0677d-212">Además, puede ser tentador admitir cualquier excepción en el deseo de una función "simple" que devuelva un tipo "agradable":</span><span class="sxs-lookup"><span data-stu-id="0677d-212">Additionally, it can be tempting to swallow any exception in the desire for a "simple" function that returns a "nicer" type:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

<span data-ttu-id="0677d-213">Desafortunadamente, `tryReadAllText` puede producir numerosas excepciones en función de la infinidad de cosas que pueden producirse en un sistema de archivos, y este código descarta cualquier información sobre lo que podría estar realmente mal en su entorno.</span><span class="sxs-lookup"><span data-stu-id="0677d-213">Unfortunately, `tryReadAllText` can throw numerous exceptions based on the myriad of things that can happen on a file system, and this code discards away any information about what might actually be going wrong in your environment.</span></span> <span data-ttu-id="0677d-214">Si reemplaza este código por un tipo de resultado, volverá al análisis de mensajes de error "con tipo de cadena":</span><span class="sxs-lookup"><span data-stu-id="0677d-214">If you replace this code with a result type, then you're back to "stringly-typed" error message parsing:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Ok
    with e -> Error e.Message

let r = tryReadAllText "path-to-file"
match r with
| Ok text -> ...
| Error e ->
    if e.Contains "uh oh, here we go again..." then ...
    else ...
```

<span data-ttu-id="0677d-215">Y colocar el objeto de excepción en el constructor `Error` simplemente obliga a tratar correctamente el tipo de excepción en el sitio de llamada en lugar de en la función.</span><span class="sxs-lookup"><span data-stu-id="0677d-215">And placing the exception object itself in the `Error` constructor just forces you to properly deal with the exception type at the call site rather than in the function.</span></span> <span data-ttu-id="0677d-216">De este modo, se crean excepciones comprobadas, que son muy unfuns de tratar como llamador de una API.</span><span class="sxs-lookup"><span data-stu-id="0677d-216">Doing this effectively creates checked exceptions, which are notoriously unfun to deal with as a caller of an API.</span></span>

<span data-ttu-id="0677d-217">Una buena alternativa a los ejemplos anteriores es detectar excepciones *específicas* y devolver un valor significativo en el contexto de esa excepción.</span><span class="sxs-lookup"><span data-stu-id="0677d-217">A good alternative to the above examples is to catch *specific* exceptions and return a meaningful value in the context of that exception.</span></span> <span data-ttu-id="0677d-218">Si modifica la función de `tryReadAllText` como se indica a continuación, `None` tiene un significado más:</span><span class="sxs-lookup"><span data-stu-id="0677d-218">If you modify the `tryReadAllText` function as follows, `None` has more meaning:</span></span>

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

<span data-ttu-id="0677d-219">En lugar de funcionar como una instrucción catch-all, esta función controlará correctamente el caso cuando no se encuentre un archivo y lo asigne a una devolución.</span><span class="sxs-lookup"><span data-stu-id="0677d-219">Instead of functioning as a catch-all, this function will now properly handle the case when a file was not found and assign that meaning to a return.</span></span> <span data-ttu-id="0677d-220">Este valor devuelto se puede asignar a ese caso de error, sin descartar ninguna información contextual ni obligar a los autores de llamadas a tratar con un caso que puede no ser relevante en ese punto del código.</span><span class="sxs-lookup"><span data-stu-id="0677d-220">This return value can map to that error case, while not discarding any contextual information or forcing callers to deal with a case that may not be relevant at that point in the code.</span></span>

<span data-ttu-id="0677d-221">Los tipos como `Result<'Success, 'Error>` son adecuados para las operaciones básicas en las que no están anidados y F# los tipos opcionales son perfectos para representar cuando algo puede devolver *algo* o *nada*.</span><span class="sxs-lookup"><span data-stu-id="0677d-221">Types such as `Result<'Success, 'Error>` are appropriate for basic operations where they aren't nested, and F# optional types are perfect for representing when something could either return *something* or *nothing*.</span></span> <span data-ttu-id="0677d-222">Sin embargo, no sustituyen a las excepciones y no se deben usar en un intento de reemplazar excepciones.</span><span class="sxs-lookup"><span data-stu-id="0677d-222">They are not a replacement for exceptions, though, and should not be used in an attempt to replace exceptions.</span></span> <span data-ttu-id="0677d-223">En su lugar, deben aplicarse prudentemente para abordar aspectos específicos de la Directiva de administración de errores y excepciones de manera dirigida.</span><span class="sxs-lookup"><span data-stu-id="0677d-223">Rather, they should be applied judiciously to address specific aspects of exception and error management policy in targeted ways.</span></span>

## <a name="partial-application-and-point-free-programming"></a><span data-ttu-id="0677d-224">Aplicación parcial y programación sin punto</span><span class="sxs-lookup"><span data-stu-id="0677d-224">Partial application and point-free programming</span></span>

<span data-ttu-id="0677d-225">F#admite la aplicación parcial y, por tanto, varias maneras de programar en un estilo sin punto.</span><span class="sxs-lookup"><span data-stu-id="0677d-225">F# supports partial application, and thus, various ways to program in a point-free style.</span></span> <span data-ttu-id="0677d-226">Esto puede ser beneficioso para la reutilización de código dentro de un módulo o la implementación de algo, pero no es algo que exponer públicamente.</span><span class="sxs-lookup"><span data-stu-id="0677d-226">This can be beneficial for code reuse within a module or the implementation of something, but it is not something to expose publicly.</span></span> <span data-ttu-id="0677d-227">En general, la programación sin puntos no es un marco de sí mismo y puede Agregar una barrera cognitiva significativa para personas que no están sumergidas en el estilo.</span><span class="sxs-lookup"><span data-stu-id="0677d-227">In general, point-free programming is not a virtue in and of itself, and can add a significant cognitive barrier for people who are not immersed in the style.</span></span>

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a><span data-ttu-id="0677d-228">No use la aplicación parcial y currificación en las API públicas</span><span class="sxs-lookup"><span data-stu-id="0677d-228">Do not use partial application and currying in public APIs</span></span>

<span data-ttu-id="0677d-229">Con poca excepción, el uso de una aplicación parcial en las API públicas puede resultar confuso para los consumidores.</span><span class="sxs-lookup"><span data-stu-id="0677d-229">With little exception, the use of partial application in public APIs can be confusing for consumers.</span></span> <span data-ttu-id="0677d-230">Normalmente, los valores enlazados a F# `let`en el código son **valores**, no **valores de función**.</span><span class="sxs-lookup"><span data-stu-id="0677d-230">Usually, `let`-bound values in F# code are **values**, not **function values**.</span></span> <span data-ttu-id="0677d-231">La combinación de valores y valores de función puede dar lugar a que se guarde un número pequeño de líneas de código en Exchange para un poco de sobrecarga cognitiva, especialmente si se combina con operadores como `>>` para componer funciones.</span><span class="sxs-lookup"><span data-stu-id="0677d-231">Mixing together values and function values can result in saving a small number of lines of code in exchange for quite a bit of cognitive overhead, especially if combined with operators such as `>>` to compose functions.</span></span>

### <a name="consider-the-tooling-implications-for-point-free-programming"></a><span data-ttu-id="0677d-232">Tenga en cuenta las implicaciones de las herramientas para la programación sin puntos</span><span class="sxs-lookup"><span data-stu-id="0677d-232">Consider the tooling implications for point-free programming</span></span>

<span data-ttu-id="0677d-233">Las funciones currificadas no etiquetan sus argumentos.</span><span class="sxs-lookup"><span data-stu-id="0677d-233">Curried functions do not label their arguments.</span></span> <span data-ttu-id="0677d-234">Esto tiene implicaciones para las herramientas.</span><span class="sxs-lookup"><span data-stu-id="0677d-234">This has tooling implications.</span></span> <span data-ttu-id="0677d-235">Tenga en cuenta las dos funciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="0677d-235">Consider the following two functions:</span></span>

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

<span data-ttu-id="0677d-236">Ambos son funciones válidas, pero `funcWithApplication` es una función currificada.</span><span class="sxs-lookup"><span data-stu-id="0677d-236">Both are valid functions, but `funcWithApplication` is a curried function.</span></span> <span data-ttu-id="0677d-237">Al mantener el mouse sobre sus tipos en un editor, verá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0677d-237">When you hover over their types in an editor, you see this:</span></span>

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

<span data-ttu-id="0677d-238">En el sitio de la llamada, la información sobre herramientas, como Visual Studio, no proporcionará información significativa sobre lo que representan realmente los tipos de entrada `string` y `int`.</span><span class="sxs-lookup"><span data-stu-id="0677d-238">At the call site, tooltips in tooling such as Visual Studio will not give you meaningful information as to what the `string` and `int` input types actually represent.</span></span>

<span data-ttu-id="0677d-239">Si se encuentra con código sin punto, como `funcWithApplication` que se puede consumir públicamente, se recomienda realizar una expansión η completa para que las herramientas puedan recoger nombres descriptivos para los argumentos.</span><span class="sxs-lookup"><span data-stu-id="0677d-239">If you encounter point-free code like `funcWithApplication` that is publicly consumable, it is recommended to do a full η-expansion so that tooling can pick up on meaningful names for arguments.</span></span>

<span data-ttu-id="0677d-240">Además, el código sin punto de depuración puede ser desafiante, si no imposible.</span><span class="sxs-lookup"><span data-stu-id="0677d-240">Furthermore, debugging point-free code can be challenging, if not impossible.</span></span> <span data-ttu-id="0677d-241">Las herramientas de depuración se basan en valores enlazados a nombres (por ejemplo, enlaces de `let`) para que pueda inspeccionar valores intermedios a mitad de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="0677d-241">Debugging tools rely on values bound to names (for example, `let` bindings) so that you can inspect intermediate values midway through execution.</span></span> <span data-ttu-id="0677d-242">Cuando el código no tiene valores para inspeccionar, no hay nada que depurar.</span><span class="sxs-lookup"><span data-stu-id="0677d-242">When your code has no values to inspect, there is nothing to debug.</span></span> <span data-ttu-id="0677d-243">En el futuro, es posible que las herramientas de depuración evolucionen para sintetizar estos valores en función de las rutas de acceso ejecutadas anteriormente, pero no es una buena idea repartir sus *posibilidades* de depuración.</span><span class="sxs-lookup"><span data-stu-id="0677d-243">In the future, debugging tools may evolve to synthesize these values based on previously executed paths, but it's not a good idea to hedge your bets on *potential* debugging functionality.</span></span>

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a><span data-ttu-id="0677d-244">Considere la aplicación parcial como una técnica para reducir el uso del texto interno.</span><span class="sxs-lookup"><span data-stu-id="0677d-244">Consider partial application as a technique to reduce internal boilerplate</span></span>

<span data-ttu-id="0677d-245">A diferencia del punto anterior, la aplicación parcial es una herramienta maravillosa para reducir el contenido Reutilizable dentro de una aplicación o los aspectos internos más profundos de una API.</span><span class="sxs-lookup"><span data-stu-id="0677d-245">In contrast to the previous point, partial application is a wonderful tool for reducing boilerplate inside of an application or the deeper internals of an API.</span></span> <span data-ttu-id="0677d-246">Puede ser útil para las pruebas unitarias de la implementación de API más complicadas, donde reutilizable suele ser un problema.</span><span class="sxs-lookup"><span data-stu-id="0677d-246">It can be helpful for unit testing the implementation of more complicated APIs, where boilerplate is often a pain to deal with.</span></span> <span data-ttu-id="0677d-247">Por ejemplo, en el código siguiente se muestra cómo puede realizar lo que la mayoría de los marcos ficticios le proporciona sin tomar una dependencia externa de este marco de trabajo y tener que aprender una API relacionada relacionada.</span><span class="sxs-lookup"><span data-stu-id="0677d-247">For example, the following code shows how you can accomplish what most mocking frameworks give you without taking an external dependency on such a framework and having to learn a related bespoke API.</span></span>

<span data-ttu-id="0677d-248">Por ejemplo, considere la siguiente topografía de la solución:</span><span class="sxs-lookup"><span data-stu-id="0677d-248">For example, consider the following solution topography:</span></span>

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

<span data-ttu-id="0677d-249">`ImplementationLogic.fsproj` podría exponer código como:</span><span class="sxs-lookup"><span data-stu-id="0677d-249">`ImplementationLogic.fsproj` might expose code such as:</span></span>

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member _.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

<span data-ttu-id="0677d-250">La `Transactions.doTransaction` de pruebas unitarias en `ImplementationLogic.Tests.fsproj` es fácil:</span><span class="sxs-lookup"><span data-stu-id="0677d-250">Unit testing `Transactions.doTransaction` in `ImplementationLogic.Tests.fsproj` is easy:</span></span>

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

<span data-ttu-id="0677d-251">Aplicar `doTransaction` parcialmente con un objeto de contexto ficticio le permite llamar a la función en todas las pruebas unitarias sin necesidad de crear un contexto ficticio cada vez:</span><span class="sxs-lookup"><span data-stu-id="0677d-251">Partially applying `doTransaction` with a mocking context object lets you call the function in all of your unit tests without needing to construct a mocked context each time:</span></span>

```fsharp
namespace TransactionTests

open Xunit
open TransactionTypes
open TransactionsTestingUtil
open TransactionsTestingUtil.TransactionsTestable

let testableContext =
    { new ITransactionContext with
        member _.TheFirstMember() = ...
        member _.TheSecondMember() = ... }

let transactionRoutine = getTestableTransactionRoutine testableContext

[<Fact>]
let ``Test withdrawal transaction with 0.0 for balance``() =
    let expected = ...
    let actual = transactionRoutine TransactionType.Withdraw 0.0
    Assert.Equal(expected, actual)
```

<span data-ttu-id="0677d-252">Esta técnica no se debe aplicar universalmente a toda la base de código, pero es una buena forma de reducir los elementos reutilizables para las pruebas unitarias e internas complicadas.</span><span class="sxs-lookup"><span data-stu-id="0677d-252">This technique should not be universally applied to your entire codebase, but it is a good way to reduce boilerplate for complicated internals and unit testing those internals.</span></span>

## <a name="access-control"></a><span data-ttu-id="0677d-253">Control de acceso</span><span class="sxs-lookup"><span data-stu-id="0677d-253">Access control</span></span>

<span data-ttu-id="0677d-254">F#tiene varias opciones para el [control de acceso](../language-reference/access-control.md), que se heredan de lo que está disponible en el tiempo de ejecución de .net.</span><span class="sxs-lookup"><span data-stu-id="0677d-254">F# has multiple options for [Access control](../language-reference/access-control.md), inherited from what is available in the .NET runtime.</span></span> <span data-ttu-id="0677d-255">No solo se pueden usar para los tipos. también puede utilizarlos para funciones.</span><span class="sxs-lookup"><span data-stu-id="0677d-255">These are not just usable for types - you can use them for functions, too.</span></span>

* <span data-ttu-id="0677d-256">Prefiera tipos y miembros que no sean de`public` hasta que los necesite para ser consumibles públicamente.</span><span class="sxs-lookup"><span data-stu-id="0677d-256">Prefer non-`public` types and members until you need them to be publicly consumable.</span></span> <span data-ttu-id="0677d-257">Esto también minimiza lo que los consumidores acoplan a.</span><span class="sxs-lookup"><span data-stu-id="0677d-257">This also minimizes what consumers couple to.</span></span>
* <span data-ttu-id="0677d-258">Esforzarse por mantener `private`toda la funcionalidad auxiliar.</span><span class="sxs-lookup"><span data-stu-id="0677d-258">Strive to keep all helper functionality `private`.</span></span>
* <span data-ttu-id="0677d-259">Considere el uso de `[<AutoOpen>]` en un módulo privado de funciones auxiliares si son numerosas.</span><span class="sxs-lookup"><span data-stu-id="0677d-259">Consider the use of `[<AutoOpen>]` on a private module of helper functions if they become numerous.</span></span>

## <a name="type-inference-and-generics"></a><span data-ttu-id="0677d-260">Inferencia de tipos y genéricos</span><span class="sxs-lookup"><span data-stu-id="0677d-260">Type inference and generics</span></span>

<span data-ttu-id="0677d-261">La inferencia de tipos puede ahorrarle escribir una gran cantidad de texto reutilizable.</span><span class="sxs-lookup"><span data-stu-id="0677d-261">Type inference can save you from typing a lot of boilerplate.</span></span> <span data-ttu-id="0677d-262">Además, la generalización automática F# en el compilador puede ayudarle a escribir código más genérico sin ningún esfuerzo adicional por su parte.</span><span class="sxs-lookup"><span data-stu-id="0677d-262">And automatic generalization in the F# compiler can help you write more generic code with almost no extra effort on your part.</span></span> <span data-ttu-id="0677d-263">Sin embargo, estas características no son universalmente buenas.</span><span class="sxs-lookup"><span data-stu-id="0677d-263">However, these features are not universally good.</span></span>

* <span data-ttu-id="0677d-264">Considere la posibilidad de etiquetar nombres de argumento con tipos explícitos en las API públicas y no confíe en la inferencia de tipos para este.</span><span class="sxs-lookup"><span data-stu-id="0677d-264">Consider labeling argument names with explicit types in public APIs and do not rely on type inference for this.</span></span>

    <span data-ttu-id="0677d-265">El **motivo es que debería tener** el control de la forma de la API, no del compilador.</span><span class="sxs-lookup"><span data-stu-id="0677d-265">The reason for this is that **you** should be in control of the shape of your API, not the compiler.</span></span> <span data-ttu-id="0677d-266">Aunque el compilador puede realizar un trabajo adecuado en la inferencia de tipos automáticamente, es posible que la forma de la API cambie si el interno en el que se basa ha cambiado de tipo.</span><span class="sxs-lookup"><span data-stu-id="0677d-266">Although the compiler can do a fine job at inferring types for you, it is possible to have the shape of your API change if the internals it relies on have changed types.</span></span> <span data-ttu-id="0677d-267">Esto puede ser lo que desea, pero es muy probable que se produzca un cambio de API importante que los consumidores de nivel inferior tendrán que tratar.</span><span class="sxs-lookup"><span data-stu-id="0677d-267">This may be what you want, but it will almost certainly result in a breaking API change that downstream consumers will then have to deal with.</span></span> <span data-ttu-id="0677d-268">En su lugar, si controla explícitamente la forma de la API pública, puede controlar estos cambios importantes.</span><span class="sxs-lookup"><span data-stu-id="0677d-268">Instead, if you explicitly control the shape of your public API, then you can control these breaking changes.</span></span> <span data-ttu-id="0677d-269">En términos de DDD, esto puede considerarse como una capa contra daños.</span><span class="sxs-lookup"><span data-stu-id="0677d-269">In DDD terms, this can be thought of as an Anti-corruption layer.</span></span>

* <span data-ttu-id="0677d-270">Considere la posibilidad de asignar un nombre descriptivo a los argumentos genéricos.</span><span class="sxs-lookup"><span data-stu-id="0677d-270">Consider giving a meaningful name to your generic arguments.</span></span>

    <span data-ttu-id="0677d-271">A menos que esté escribiendo código realmente genérico que no sea específico de un dominio determinado, un nombre descriptivo puede ayudar a otros programadores a entender el dominio en el que están trabajando.</span><span class="sxs-lookup"><span data-stu-id="0677d-271">Unless you are writing truly generic code that is not specific to a particular domain, a meaningful name can help other programmers understanding the domain they're working in.</span></span> <span data-ttu-id="0677d-272">Por ejemplo, un parámetro de tipo denominado `'Document` en el contexto de interactuar con una base de datos de documento hace que sea más claro que la función o el miembro con el que está trabajando puede aceptar los tipos de documento genéricos.</span><span class="sxs-lookup"><span data-stu-id="0677d-272">For example, a type parameter named `'Document` in the context of interacting with a document database makes it clearer that generic document types can be accepted by the function or member you are working with.</span></span>

* <span data-ttu-id="0677d-273">Considere la posibilidad de asignar nombres a los parámetros de tipo genérico con PascalCase.</span><span class="sxs-lookup"><span data-stu-id="0677d-273">Consider naming generic type parameters with PascalCase.</span></span>

    <span data-ttu-id="0677d-274">Esta es la manera general de hacer cosas en .NET, por lo que se recomienda que use PascalCase en lugar de snake_case o camelCase.</span><span class="sxs-lookup"><span data-stu-id="0677d-274">This is the general way to do things in .NET, so it's recommended that you use PascalCase rather than snake_case or camelCase.</span></span>

<span data-ttu-id="0677d-275">Por último, la generalización automática no siempre es una gran ventaja para las personas F# que son nuevas en o en un código base grande.</span><span class="sxs-lookup"><span data-stu-id="0677d-275">Finally, automatic generalization is not always a boon for people who are new to F# or a large codebase.</span></span> <span data-ttu-id="0677d-276">El uso de componentes que son genéricos es una sobrecarga cognitiva.</span><span class="sxs-lookup"><span data-stu-id="0677d-276">There is cognitive overhead in using components that are generic.</span></span> <span data-ttu-id="0677d-277">Además, si las funciones generalizadas automáticamente no se usan con distintos tipos de entrada (por sí solo si están pensadas para usarse como tal), no hay ninguna ventaja real de que sean genéricas en ese momento.</span><span class="sxs-lookup"><span data-stu-id="0677d-277">Furthermore, if automatically generalized functions are not used with different input types (let alone if they are intended to be used as such), then there is no real benefit to them being generic at that point in time.</span></span> <span data-ttu-id="0677d-278">Considere siempre si el código que está escribiendo se beneficiará de ser genérico.</span><span class="sxs-lookup"><span data-stu-id="0677d-278">Always consider if the code you are writing will actually benefit from being generic.</span></span>

## <a name="performance"></a><span data-ttu-id="0677d-279">Rendimiento</span><span class="sxs-lookup"><span data-stu-id="0677d-279">Performance</span></span>

### <a name="prefer-structs-for-small-data-types"></a><span data-ttu-id="0677d-280">Preferir Structs para tipos de datos pequeños</span><span class="sxs-lookup"><span data-stu-id="0677d-280">Prefer structs for small data types</span></span>

<span data-ttu-id="0677d-281">El uso de Structs (también denominados tipos de valor) puede dar lugar a un mayor rendimiento en el código, ya que normalmente evita la asignación de objetos.</span><span class="sxs-lookup"><span data-stu-id="0677d-281">Using structs (also called Value Types) can often result in higher performance for some code because it typically avoids allocating objects.</span></span> <span data-ttu-id="0677d-282">Sin embargo, los Structs no siempre son un botón "ir más rápido": Si el tamaño de los datos de una estructura supera los 16 bytes, la copia de los datos a menudo puede producir más tiempo de CPU que el uso de un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="0677d-282">However, structs are not always a "go faster" button: if the size of the data in a struct exceeds 16 bytes, copying the data can often result in more CPU time spend than using a reference type.</span></span>

<span data-ttu-id="0677d-283">Para determinar si debe usar un struct, tenga en cuenta las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="0677d-283">To determine if you should use a struct, consider the following conditions:</span></span>

- <span data-ttu-id="0677d-284">Si el tamaño de los datos es de 16 bytes o menos.</span><span class="sxs-lookup"><span data-stu-id="0677d-284">If the size of your data is 16 bytes or smaller.</span></span>
- <span data-ttu-id="0677d-285">Si es probable que tenga muchos de estos tipos de datos residentes en memoria en un programa en ejecución.</span><span class="sxs-lookup"><span data-stu-id="0677d-285">If you're likely to have many of these data types resident in memory in a running program.</span></span>

<span data-ttu-id="0677d-286">Si se aplica la primera condición, generalmente debería usar un struct.</span><span class="sxs-lookup"><span data-stu-id="0677d-286">If the first condition applies, you should generally use a struct.</span></span> <span data-ttu-id="0677d-287">Si ambos se aplican, casi siempre debe usar un struct.</span><span class="sxs-lookup"><span data-stu-id="0677d-287">If both apply, you should almost always use a struct.</span></span> <span data-ttu-id="0677d-288">Puede haber algunos casos en los que se apliquen las condiciones anteriores, pero el uso de una estructura no es mejor o peor que el uso de un tipo de referencia, pero es probable que no sean habituales.</span><span class="sxs-lookup"><span data-stu-id="0677d-288">There may be some cases where the previous conditions apply, but using a struct is no better or worse than using a reference type, but they are likely to be rare.</span></span> <span data-ttu-id="0677d-289">Es importante medir siempre cuando se realizan cambios como este, sin embargo, y no funcionan en supuestos o Intuition.</span><span class="sxs-lookup"><span data-stu-id="0677d-289">It's important to always measure when making changes like this, though, and not operate on assumption or intuition.</span></span>

#### <a name="prefer-struct-tuples-when-grouping-small-value-types"></a><span data-ttu-id="0677d-290">Preferir tuplas de struct al agrupar tipos de valores pequeños</span><span class="sxs-lookup"><span data-stu-id="0677d-290">Prefer struct tuples when grouping small value types</span></span>

<span data-ttu-id="0677d-291">Tenga en cuenta las dos funciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="0677d-291">Consider the following two functions:</span></span>

```fsharp
let rec runWithTuple t offset times =
    let offsetValues x y z offset =
        (x + offset, y + offset, z + offset)

    if times <= 0 then
        t
    else
        let (x, y, z) = t
        let r = offsetValues x y z offset
        runWithTuple r offset (times - 1)

let rec runWithStructTuple t offset times =
    let offsetValues x y z offset =
        struct(x + offset, y + offset, z + offset)

    if times <= 0 then
        t
    else
        let struct(x, y, z) = t
        let r = offsetValues x y z offset
        runWithStructTuple r offset (times - 1)
```

<span data-ttu-id="0677d-292">Al realizar una prueba comparativa de estas funciones con una herramienta estadística de pruebas comparativas como [BenchmarkDotNet](https://benchmarkdotnet.org/), observará que la función `runWithStructTuple` que usa las tuplas de estructura ejecuta un 40% más rápido y no asigna memoria.</span><span class="sxs-lookup"><span data-stu-id="0677d-292">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that the `runWithStructTuple` function that uses struct tuples runs 40% faster and allocates no memory.</span></span>

<span data-ttu-id="0677d-293">Sin embargo, estos resultados no siempre serán el caso en su propio código.</span><span class="sxs-lookup"><span data-stu-id="0677d-293">However, these results won't always be the case in your own code.</span></span> <span data-ttu-id="0677d-294">Si marca una función como `inline`, el código que usa tuplas de referencia puede obtener algunas optimizaciones adicionales, o el código que asignaría se podría simplemente optimizar.</span><span class="sxs-lookup"><span data-stu-id="0677d-294">If you mark a function as `inline`, code that uses reference tuples may get some additional optimizations, or code that would allocate could simply be optimized away.</span></span> <span data-ttu-id="0677d-295">Siempre debe medir los resultados siempre que el rendimiento esté relacionado y nunca funcione en función de supuestos o Intuition.</span><span class="sxs-lookup"><span data-stu-id="0677d-295">You should always measure results whenever performance is concerned, and never operate based on assumption or intuition.</span></span>

#### <a name="prefer-struct-records-when-the-data-type-is-small"></a><span data-ttu-id="0677d-296">Preferir registros struct cuando el tipo de datos sea pequeño</span><span class="sxs-lookup"><span data-stu-id="0677d-296">Prefer struct records when the data type is small</span></span>

<span data-ttu-id="0677d-297">La regla de Thumb descrita anteriormente también contiene [ F# tipos de registro](../language-reference/records.md).</span><span class="sxs-lookup"><span data-stu-id="0677d-297">The rule of thumb described earlier also holds for [F# record types](../language-reference/records.md).</span></span> <span data-ttu-id="0677d-298">Tenga en cuenta los siguientes tipos de datos y funciones que los procesan:</span><span class="sxs-lookup"><span data-stu-id="0677d-298">Consider the following data types and functions that process them:</span></span>

```fsharp
type Point = { X: float; Y: float; Z: float }

[<Struct>]
type SPoint = { X: float; Y: float; Z: float }

let rec processPoint (p: Point) offset times =
    let inline offsetValues (p: Point) offset =
        { p with X = p.X + offset; Y = p.Y + offset; Z = p.Z + offset }

    if times <= 0 then
        p
    else
        let r = offsetValues p offset
        processPoint r offset (times - 1)

let rec processStructPoint (p: SPoint) offset times =
    let inline offsetValues (p: SPoint) offset =
        { p with X = p.X + offset; Y = p.Y + offset; Z = p.Z + offset }

    if times <= 0 then
        p
    else
        let r = offsetValues p offset
        processStructPoint r offset (times - 1)
```

<span data-ttu-id="0677d-299">Esto es similar al código de tupla anterior, pero esta vez el ejemplo usa registros y una función interna insertada.</span><span class="sxs-lookup"><span data-stu-id="0677d-299">This is similar to the previous tuple code, but this time the example uses records and an inlined inner function.</span></span>

<span data-ttu-id="0677d-300">Al realizar una prueba comparativa de estas funciones con una herramienta estadística de pruebas comparativas como [BenchmarkDotNet](https://benchmarkdotnet.org/), observará que `processStructPoint` se ejecuta casi un 60% más rápido y asigna nada en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="0677d-300">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that `processStructPoint` runs nearly 60% faster and allocates nothing on the managed heap.</span></span>

#### <a name="prefer-struct-discriminated-unions-when-the-data-type-is-small"></a><span data-ttu-id="0677d-301">Prefieren uniones discriminadas de struct cuando el tipo de datos es pequeño</span><span class="sxs-lookup"><span data-stu-id="0677d-301">Prefer struct discriminated unions when the data type is small</span></span>

<span data-ttu-id="0677d-302">Las observaciones anteriores sobre el rendimiento con tuplas y registros de [ F# struct también contienen uniones discriminadas](../language-reference/discriminated-unions.md).</span><span class="sxs-lookup"><span data-stu-id="0677d-302">The previous observations about performance with struct tuples and records also holds for [F# Discriminated Unions](../language-reference/discriminated-unions.md).</span></span> <span data-ttu-id="0677d-303">Observe el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0677d-303">Consider the following code:</span></span>

```fsharp
    type Name = Name of string
    
    [<Struct>]
    type SName = SName of string

    let reverseName (Name s) =
        s.ToCharArray()
        |> Array.rev
        |> string
        |> Name

    let structReverseName (SName s) =
        s.ToCharArray()
        |> Array.rev
        |> string
        |> SName
```

<span data-ttu-id="0677d-304">Es habitual definir uniones discriminadas de un solo caso como esta para el modelado de dominios.</span><span class="sxs-lookup"><span data-stu-id="0677d-304">It's common to define single-case Discriminated Unions like this for domain modeling.</span></span> <span data-ttu-id="0677d-305">Cuando realice una prueba comparativa de estas funciones con una herramienta estadística de pruebas comparativas como [BenchmarkDotNet](https://benchmarkdotnet.org/), verá que `structReverseName` se ejecuta aproximadamente un 25% más rápido que `reverseName` para cadenas pequeñas.</span><span class="sxs-lookup"><span data-stu-id="0677d-305">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that `structReverseName` runs about 25% faster than `reverseName` for small strings.</span></span> <span data-ttu-id="0677d-306">En el caso de las cadenas grandes, ambos realizan aproximadamente el mismo.</span><span class="sxs-lookup"><span data-stu-id="0677d-306">For large strings, both perform about the same.</span></span> <span data-ttu-id="0677d-307">Por lo tanto, en este caso, siempre es preferible usar un struct.</span><span class="sxs-lookup"><span data-stu-id="0677d-307">So, in this case, it's always preferable to use a struct.</span></span> <span data-ttu-id="0677d-308">Como se mencionó anteriormente, mida siempre y no opere en suposiciones o Intuition.</span><span class="sxs-lookup"><span data-stu-id="0677d-308">As previously mentioned, always measure and do not operate on assumptions or intuition.</span></span>

<span data-ttu-id="0677d-309">Aunque en el ejemplo anterior se mostró que una Unión discriminada de struct produjeron un mejor rendimiento, es habitual tener uniones discriminadas más grandes al modelar un dominio.</span><span class="sxs-lookup"><span data-stu-id="0677d-309">Although the previous example showed that a struct Discriminated Union yielded better performance, it is common to have larger Discriminated Unions when modeling a domain.</span></span> <span data-ttu-id="0677d-310">Los tipos de datos de mayor tamaño, como, pueden no funcionar también si son Structs en función de las operaciones que contengan, ya que pueden estar implicados más copias.</span><span class="sxs-lookup"><span data-stu-id="0677d-310">Larger data types like that may not perform as well if they are structs depending on the operations on them, since more copying could be involved.</span></span>

### <a name="functional-programming-and-mutation"></a><span data-ttu-id="0677d-311">Programación funcional y mutación</span><span class="sxs-lookup"><span data-stu-id="0677d-311">Functional programming and mutation</span></span>

<span data-ttu-id="0677d-312">F#los valores son inmutables de forma predeterminada, lo que permite evitar ciertas clases de errores (especialmente aquellos que implican simultaneidad y paralelismo).</span><span class="sxs-lookup"><span data-stu-id="0677d-312">F# values are immutable by default, which allows you to avoid certain classes of bugs (especially those involving concurrency and parallelism).</span></span> <span data-ttu-id="0677d-313">Sin embargo, en algunos casos, para lograr una eficiencia óptima (o incluso razonable) de tiempo de ejecución o asignaciones de memoria, es posible que se pueda implementar un intervalo de trabajo mediante la mutación en contexto del estado.</span><span class="sxs-lookup"><span data-stu-id="0677d-313">However, in certain cases, in order to achieve optimal (or even reasonable) efficiency of execution time or memory allocations, a span of work may best be implemented by using in-place mutation of state.</span></span> <span data-ttu-id="0677d-314">Esto es posible en función F# de la opción con la palabra clave `mutable`.</span><span class="sxs-lookup"><span data-stu-id="0677d-314">This is possible in an opt-in basis with F# with the `mutable` keyword.</span></span>

<span data-ttu-id="0677d-315">El uso de `mutable` F# en puede sentir en probabilidades de una pureza funcional.</span><span class="sxs-lookup"><span data-stu-id="0677d-315">Use of `mutable` in F# may feel at odds with functional purity.</span></span> <span data-ttu-id="0677d-316">Esto es comprensible, pero la pureza funcional en todo el mundo puede ser probable con objetivos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0677d-316">This is understandable, but functional purity everywhere can be at odds with performance goals.</span></span> <span data-ttu-id="0677d-317">Un compromiso es encapsular la mutación de modo que los llamadores no tengan que preocuparse de lo que sucede cuando llaman a una función.</span><span class="sxs-lookup"><span data-stu-id="0677d-317">A compromise is to encapsulate mutation such that callers need not care about what happens when they call a function.</span></span> <span data-ttu-id="0677d-318">Esto le permite escribir una interfaz funcional sobre una implementación basada en mutación para el código crítico para el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0677d-318">This allows you to write a functional interface over a mutation-based implementation for performance-critical code.</span></span>

#### <a name="wrap-mutable-code-in-immutable-interfaces"></a><span data-ttu-id="0677d-319">Ajuste del código mutable en interfaces inmutables</span><span class="sxs-lookup"><span data-stu-id="0677d-319">Wrap mutable code in immutable interfaces</span></span>

<span data-ttu-id="0677d-320">Con la transparencia referencial como objetivo, es fundamental escribir código que no exponga la subclave mutable de las funciones críticas para el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0677d-320">With referential transparency as a goal, it is critical to write code that does not expose the mutable underbelly of performance-critical functions.</span></span> <span data-ttu-id="0677d-321">Por ejemplo, el código siguiente implementa la función `Array.contains` en la F# biblioteca principal:</span><span class="sxs-lookup"><span data-stu-id="0677d-321">For example, the following code implements the `Array.contains` function in the F# core library:</span></span>

```fsharp
[<CompiledName("Contains")>]
let inline contains value (array:'T[]) =
    checkNonNull "array" array
    let mutable state = false
    let mutable i = 0
    while not state && i < array.Length do
        state <- value = array.[i]
        i <- i + 1
    state
```

<span data-ttu-id="0677d-322">Si se llama a esta función varias veces, no se cambia la matriz subyacente, ni se requiere que se mantenga ningún estado mutable en su consumo.</span><span class="sxs-lookup"><span data-stu-id="0677d-322">Calling this function multiple times does not change the underlying array, nor does it require you to maintain any mutable state in consuming it.</span></span> <span data-ttu-id="0677d-323">Es referencialmente transparente, aunque casi todas las líneas de código dentro de él utilicen mutación.</span><span class="sxs-lookup"><span data-stu-id="0677d-323">It is referentially transparent, even though almost every line of code within it uses mutation.</span></span>

#### <a name="consider-encapsulating-mutable-data-in-classes"></a><span data-ttu-id="0677d-324">Considere la posibilidad de encapsular datos mutables en clases</span><span class="sxs-lookup"><span data-stu-id="0677d-324">Consider encapsulating mutable data in classes</span></span>

<span data-ttu-id="0677d-325">En el ejemplo anterior se usaba una sola función para encapsular operaciones mediante datos mutables.</span><span class="sxs-lookup"><span data-stu-id="0677d-325">The previous example used a single function to encapsulate operations using mutable data.</span></span> <span data-ttu-id="0677d-326">Esto no siempre es suficiente para conjuntos de datos más complejos.</span><span class="sxs-lookup"><span data-stu-id="0677d-326">This is not always sufficient for more complex sets of data.</span></span> <span data-ttu-id="0677d-327">Tenga en cuenta los siguientes conjuntos de funciones:</span><span class="sxs-lookup"><span data-stu-id="0677d-327">Consider the following sets of functions:</span></span>

```fsharp
open System.Collections.Generic

let addToClosureTable (key, value) (t: Dictionary<_,_>) =
    if not (t.ContainsKey(key)) then
        t.Add(key, value)
    else
        t.[key] <- value

let closureTableCount (t: Dictionary<_,_>) = t.Count

let closureTableContains (key, value) (t: Dictionary<_, HashSet<_>>) =
    match t.TryGetValue(key) with
    | (true, v) -> v.Equals(value)
    | (false, _) -> false
```

<span data-ttu-id="0677d-328">Este código tiene un rendimiento, pero expone la estructura de datos basada en mutación que los llamadores son responsables de mantener.</span><span class="sxs-lookup"><span data-stu-id="0677d-328">This code is performant, but it exposes the mutation-based data structure that callers are responsible for maintaining.</span></span> <span data-ttu-id="0677d-329">Esto puede ajustarse dentro de una clase sin miembros subyacentes que puedan cambiar:</span><span class="sxs-lookup"><span data-stu-id="0677d-329">This can be wrapped inside of a class with no underlying members that can change:</span></span>

```fsharp
open System.Collections.Generic

/// The results of computing the LALR(1) closure of an LR(0) kernel
type Closure1Table() =
    let t = Dictionary<Item0, HashSet<TerminalIndex>>()

    member _.Add(key, value) =
        if not (t.ContainsKey(key)) then
            t.Add(key, value)
        else
            t.[key] <- value

    member _.Count = t.Count

    member _.Contains(key, value) =
        match t.TryGetValue(key) with
        | (true, v) -> v.Equals(value)
        | (false, _) -> false
```

<span data-ttu-id="0677d-330">`Closure1Table` encapsula la estructura de datos basada en mutación subyacente, por lo que no obliga a los autores de llamadas a mantener la estructura de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="0677d-330">`Closure1Table` encapsulates the underlying mutation-based data structure, thereby not forcing callers to maintain the underlying data structure.</span></span> <span data-ttu-id="0677d-331">Las clases son una manera eficaz de encapsular datos y rutinas que se basan en la mutación sin exponer los detalles a los llamadores.</span><span class="sxs-lookup"><span data-stu-id="0677d-331">Classes are a powerful way to encapsulate data and routines that are mutation-based without exposing the details to callers.</span></span>

#### <a name="prefer-let-mutable-to-reference-cells"></a><span data-ttu-id="0677d-332">Preferir `let mutable` para hacer referencia a celdas</span><span class="sxs-lookup"><span data-stu-id="0677d-332">Prefer `let mutable` to reference cells</span></span>

<span data-ttu-id="0677d-333">Las celdas de referencia son una manera de representar la referencia a un valor en lugar del propio valor.</span><span class="sxs-lookup"><span data-stu-id="0677d-333">Reference cells are a way to represent the reference to a value rather than the value itself.</span></span> <span data-ttu-id="0677d-334">Aunque se pueden usar para el código crítico para el rendimiento, no se recomiendan.</span><span class="sxs-lookup"><span data-stu-id="0677d-334">Although they can be used for performance-critical code, they are not recommended.</span></span> <span data-ttu-id="0677d-335">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0677d-335">Consider the following example:</span></span>

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

<span data-ttu-id="0677d-336">El uso de una celda de referencia ahora "contamina" todo el código subsiguiente con tener que desreferenciar y volver a hacer referencia a los datos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="0677d-336">The use of a reference cell now "pollutes" all subsequent code with having to dereference and re-reference the underlying data.</span></span> <span data-ttu-id="0677d-337">En su lugar, considere la posibilidad de `let mutable`:</span><span class="sxs-lookup"><span data-stu-id="0677d-337">Instead, consider `let mutable`:</span></span>

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

<span data-ttu-id="0677d-338">Aparte del punto único de mutación en el medio de la expresión lambda, todo el resto del código que toca `acc` puede hacerlo de una manera que no sea diferente al uso de un valor normal enlazado a `let`.</span><span class="sxs-lookup"><span data-stu-id="0677d-338">Aside from the single point of mutation in the middle of the lambda expression, all other code that touches `acc` can do so in a manner that is no different to the usage of a normal `let`-bound immutable value.</span></span> <span data-ttu-id="0677d-339">Esto hará que sea más fácil cambiar con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="0677d-339">This will make it easier to change over time.</span></span>

## <a name="object-programming"></a><span data-ttu-id="0677d-340">Programación de objetos</span><span class="sxs-lookup"><span data-stu-id="0677d-340">Object programming</span></span>

<span data-ttu-id="0677d-341">F#tiene compatibilidad total con objetos y conceptos orientados a objetos (OO).</span><span class="sxs-lookup"><span data-stu-id="0677d-341">F# has full support for objects and object-oriented (OO) concepts.</span></span> <span data-ttu-id="0677d-342">Aunque muchos conceptos de OO son eficaces y útiles, no todos ellos son ideales para su uso.</span><span class="sxs-lookup"><span data-stu-id="0677d-342">Although many OO concepts are powerful and useful, not all of them are ideal to use.</span></span> <span data-ttu-id="0677d-343">En las listas siguientes se ofrecen instrucciones sobre las categorías de características de OO en un nivel alto.</span><span class="sxs-lookup"><span data-stu-id="0677d-343">The following lists offer guidance on categories of OO features at a high level.</span></span>

<span data-ttu-id="0677d-344">**Considere la posibilidad de usar estas características en muchas situaciones:**</span><span class="sxs-lookup"><span data-stu-id="0677d-344">**Consider using these features in many situations:**</span></span>

* <span data-ttu-id="0677d-345">Notación de puntos (`x.Length`)</span><span class="sxs-lookup"><span data-stu-id="0677d-345">Dot notation (`x.Length`)</span></span>
* <span data-ttu-id="0677d-346">Miembros de instancia</span><span class="sxs-lookup"><span data-stu-id="0677d-346">Instance members</span></span>
* <span data-ttu-id="0677d-347">Constructores implícitos</span><span class="sxs-lookup"><span data-stu-id="0677d-347">Implicit constructors</span></span>
* <span data-ttu-id="0677d-348">Miembros estáticos</span><span class="sxs-lookup"><span data-stu-id="0677d-348">Static members</span></span>
* <span data-ttu-id="0677d-349">Notación de indexador (`arr.[x]`)</span><span class="sxs-lookup"><span data-stu-id="0677d-349">Indexer notation (`arr.[x]`)</span></span>
* <span data-ttu-id="0677d-350">Argumentos opcionales y con nombre</span><span class="sxs-lookup"><span data-stu-id="0677d-350">Named and Optional arguments</span></span>
* <span data-ttu-id="0677d-351">Interfaces e implementaciones de interfaz</span><span class="sxs-lookup"><span data-stu-id="0677d-351">Interfaces and interface implementations</span></span>

<span data-ttu-id="0677d-352">**No se debe llegar a estas características en primer lugar, pero se aplican de forma prudente cuando sea conveniente solucionar un problema:**</span><span class="sxs-lookup"><span data-stu-id="0677d-352">**Don't reach for these features first, but do judiciously apply them when they are convenient to solve a problem:**</span></span>

* <span data-ttu-id="0677d-353">Sobrecarga de métodos</span><span class="sxs-lookup"><span data-stu-id="0677d-353">Method overloading</span></span>
* <span data-ttu-id="0677d-354">Datos mutables encapsulados</span><span class="sxs-lookup"><span data-stu-id="0677d-354">Encapsulated mutable data</span></span>
* <span data-ttu-id="0677d-355">Operadores en tipos</span><span class="sxs-lookup"><span data-stu-id="0677d-355">Operators on types</span></span>
* <span data-ttu-id="0677d-356">Propiedades automáticas</span><span class="sxs-lookup"><span data-stu-id="0677d-356">Auto properties</span></span>
* <span data-ttu-id="0677d-357">Implementar `IDisposable` y `IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="0677d-357">Implementing `IDisposable` and `IEnumerable`</span></span>
* <span data-ttu-id="0677d-358">Extensiones de tipo</span><span class="sxs-lookup"><span data-stu-id="0677d-358">Type extensions</span></span>
* <span data-ttu-id="0677d-359">Eventos</span><span class="sxs-lookup"><span data-stu-id="0677d-359">Events</span></span>
* <span data-ttu-id="0677d-360">Estructuras</span><span class="sxs-lookup"><span data-stu-id="0677d-360">Structs</span></span>
* <span data-ttu-id="0677d-361">Delegados</span><span class="sxs-lookup"><span data-stu-id="0677d-361">Delegates</span></span>
* <span data-ttu-id="0677d-362">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="0677d-362">Enums</span></span>

<span data-ttu-id="0677d-363">**Normalmente, evite estas características a menos que deba utilizarlas:**</span><span class="sxs-lookup"><span data-stu-id="0677d-363">**Generally avoid these features unless you must use them:**</span></span>

* <span data-ttu-id="0677d-364">Jerarquías de tipos basados en herencia y herencia de implementación</span><span class="sxs-lookup"><span data-stu-id="0677d-364">Inheritance-based type hierarchies and implementation inheritance</span></span>
* <span data-ttu-id="0677d-365">Valores NULL y `Unchecked.defaultof<_>`</span><span class="sxs-lookup"><span data-stu-id="0677d-365">Nulls and `Unchecked.defaultof<_>`</span></span>

### <a name="prefer-composition-over-inheritance"></a><span data-ttu-id="0677d-366">Preferir composición sobre herencia</span><span class="sxs-lookup"><span data-stu-id="0677d-366">Prefer composition over inheritance</span></span>

<span data-ttu-id="0677d-367">La [composición sobre la herencia](https://en.wikipedia.org/wiki/Composition_over_inheritance) es una expresión de larga duración F# que puede cumplir un buen código.</span><span class="sxs-lookup"><span data-stu-id="0677d-367">[Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance) is a long-standing idiom that good F# code can adhere to.</span></span> <span data-ttu-id="0677d-368">El principio fundamental es que no se debe exponer una clase base y forzar que los llamadores hereden de esa clase base para obtener la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="0677d-368">The fundamental principle is that you should not expose a base class and force callers to inherit from that base class to get functionality.</span></span>

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a><span data-ttu-id="0677d-369">Usar expresiones de objeto para implementar interfaces si no se necesita una clase</span><span class="sxs-lookup"><span data-stu-id="0677d-369">Use object expressions to implement interfaces if you don't need a class</span></span>

<span data-ttu-id="0677d-370">Las [expresiones de objeto](../language-reference/object-expressions.md) permiten implementar interfaces sobre la marcha, enlazando la interfaz implementada a un valor sin necesidad de hacerlo dentro de una clase.</span><span class="sxs-lookup"><span data-stu-id="0677d-370">[Object Expressions](../language-reference/object-expressions.md) allow you to implement interfaces on the fly, binding the implemented interface to a value without needing to do so inside of a class.</span></span> <span data-ttu-id="0677d-371">Esto resulta cómodo, especialmente si _solo_ necesita implementar la interfaz y no necesita una clase completa.</span><span class="sxs-lookup"><span data-stu-id="0677d-371">This is convenient, especially if you _only_ need to implement the interface and have no need for a full class.</span></span>

<span data-ttu-id="0677d-372">Por ejemplo, este es el código que se ejecuta en [Ionide](http://ionide.io/) para proporcionar una acción de corrección de código si ha agregado un símbolo que no tiene una instrucción `open` para:</span><span class="sxs-lookup"><span data-stu-id="0677d-372">For example, here is the code that is run in [Ionide](http://ionide.io/) to provide a code fix action if you've added a symbol that you don't have an `open` statement for:</span></span>

```fsharp
    let private createProvider () =
        { new CodeActionProvider with
            member this.provideCodeActions(doc, range, context, ct) =
                let diagnostics = context.diagnostics
                let diagnostic = diagnostics |> Seq.tryFind (fun d -> d.message.Contains "Unused open statement")
                let res =
                    match diagnostic with
                    | None -> [||]
                    | Some d ->
                        let line = doc.lineAt d.range.start.line
                        let cmd = createEmpty<Command>
                        cmd.title <- "Remove unused open"
                        cmd.command <- "fsharp.unusedOpenFix"
                        cmd.arguments <- Some ([| doc |> unbox; line.range |> unbox; |] |> ResizeArray)
                        [|cmd |]
                res
                |> ResizeArray
                |> U2.Case1
        }
```

<span data-ttu-id="0677d-373">Dado que no hay necesidad de una clase al interactuar con la API de Visual Studio Code, las expresiones de objeto son una herramienta ideal para esto.</span><span class="sxs-lookup"><span data-stu-id="0677d-373">Because there is no need for a class when interacting with the Visual Studio Code API, Object Expressions are an ideal tool for this.</span></span> <span data-ttu-id="0677d-374">También son útiles para las pruebas unitarias, cuando se desea realizar un código auxiliar de una interfaz con rutinas de prueba de forma ad hoc.</span><span class="sxs-lookup"><span data-stu-id="0677d-374">They are also valuable for unit testing, when you want to stub out an interface with test routines in an ad hoc manner.</span></span>

## <a name="consider-type-abbreviations-to-shorten-signatures"></a><span data-ttu-id="0677d-375">Considere las abreviaturas de tipo para acortar las firmas</span><span class="sxs-lookup"><span data-stu-id="0677d-375">Consider Type Abbreviations to shorten signatures</span></span>

<span data-ttu-id="0677d-376">Las [abreviaturas de tipo](../language-reference/type-abbreviations.md) son una manera cómoda de asignar una etiqueta a otro tipo, como una firma de función o un tipo más complejo.</span><span class="sxs-lookup"><span data-stu-id="0677d-376">[Type Abbreviations](../language-reference/type-abbreviations.md) are a convenient way to assign a label to another type, such as a function signature or a more complex type.</span></span> <span data-ttu-id="0677d-377">Por ejemplo, el alias siguiente asigna una etiqueta a lo que se necesita para definir un cálculo con [CNTK](https://docs.microsoft.com/cognitive-toolkit/), una biblioteca de aprendizaje profundo:</span><span class="sxs-lookup"><span data-stu-id="0677d-377">For example, the following alias assigns a label to what's needed to define a computation with [CNTK](https://docs.microsoft.com/cognitive-toolkit/), a deep learning library:</span></span>

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

<span data-ttu-id="0677d-378">El nombre del `Computation` es una manera cómoda de indicar cualquier función que coincida con la firma a la que se asignan alias.</span><span class="sxs-lookup"><span data-stu-id="0677d-378">The `Computation` name is a convenient way to denote any function that matches the signature it is aliasing.</span></span> <span data-ttu-id="0677d-379">El uso de abreviaturas de tipo como esta es cómodo y permite el código más conciso.</span><span class="sxs-lookup"><span data-stu-id="0677d-379">Using Type Abbreviations like this is convenient and allows for more succinct code.</span></span>

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a><span data-ttu-id="0677d-380">Evite el uso de abreviaturas de tipo para representar su dominio</span><span class="sxs-lookup"><span data-stu-id="0677d-380">Avoid using Type Abbreviations to represent your domain</span></span>

<span data-ttu-id="0677d-381">Aunque las abreviaturas de tipo son convenientes para asignar un nombre a las firmas de función, pueden resultar confusos al abreviar otros tipos.</span><span class="sxs-lookup"><span data-stu-id="0677d-381">Although Type Abbreviations are convenient for giving a name to function signatures, they can be confusing when abbreviating other types.</span></span> <span data-ttu-id="0677d-382">Tenga en cuenta esta abreviatura:</span><span class="sxs-lookup"><span data-stu-id="0677d-382">Consider this abbreviation:</span></span>

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

<span data-ttu-id="0677d-383">Esto puede resultar confuso de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="0677d-383">This can be confusing in multiple ways:</span></span>

* <span data-ttu-id="0677d-384">`BufferSize` no es una abstracción; es simplemente otro nombre para un entero.</span><span class="sxs-lookup"><span data-stu-id="0677d-384">`BufferSize` is not an abstraction; it is just another name for an integer.</span></span>
* <span data-ttu-id="0677d-385">Si `BufferSize` se expone en una API pública, se puede malinterpretar fácilmente que significa más que simplemente `int`.</span><span class="sxs-lookup"><span data-stu-id="0677d-385">If `BufferSize` is exposed in a public API, it can easily be misinterpreted to mean more than just `int`.</span></span> <span data-ttu-id="0677d-386">Por lo general, los tipos de dominio tienen varios atributos y no son tipos primitivos como `int`.</span><span class="sxs-lookup"><span data-stu-id="0677d-386">Generally, domain types have multiple attributes to them and are not primitive types like `int`.</span></span> <span data-ttu-id="0677d-387">Esta abreviatura infringe esa hipótesis.</span><span class="sxs-lookup"><span data-stu-id="0677d-387">This abbreviation violates that assumption.</span></span>
* <span data-ttu-id="0677d-388">El uso de mayúsculas y minúsculas en `BufferSize` (PascalCase) implica que este tipo contiene más datos.</span><span class="sxs-lookup"><span data-stu-id="0677d-388">The casing of `BufferSize` (PascalCase) implies that this type holds more data.</span></span>
* <span data-ttu-id="0677d-389">Este alias no ofrece mayor claridad en comparación con proporcionar un argumento con nombre a una función.</span><span class="sxs-lookup"><span data-stu-id="0677d-389">This alias does not offer increased clarity compared with providing a named argument to a function.</span></span>
* <span data-ttu-id="0677d-390">La abreviatura no emitirá un manifiesto en IL compilado; es simplemente un entero y este alias es una construcción en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="0677d-390">The abbreviation will not manifest in compiled IL; it is just an integer and this alias is a compile-time construct.</span></span>

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

<span data-ttu-id="0677d-391">En Resumen, el inconveniente de las abreviaturas de tipo es que **no** son abstracciones sobre los tipos que se van a abreviar.</span><span class="sxs-lookup"><span data-stu-id="0677d-391">In summary, the pitfall with Type Abbreviations is that they are **not** abstractions over the types they are abbreviating.</span></span> <span data-ttu-id="0677d-392">En el ejemplo anterior, `BufferSize` es simplemente un `int` en segundo plano, sin datos adicionales, ni tampoco ventajas del sistema de tipos, además de lo que ya tiene el `int`.</span><span class="sxs-lookup"><span data-stu-id="0677d-392">In the previous example, `BufferSize` is just an `int` under the covers, with no additional data, nor any benefits from the type system besides what `int` already has.</span></span>

<span data-ttu-id="0677d-393">Un enfoque alternativo al uso de las abreviaturas de tipo para representar un dominio es utilizar uniones discriminadas de un solo caso.</span><span class="sxs-lookup"><span data-stu-id="0677d-393">An alternative approach to using type abbreviations to represent a domain is to use single-case discriminated unions.</span></span> <span data-ttu-id="0677d-394">El ejemplo anterior se puede modelar como sigue:</span><span class="sxs-lookup"><span data-stu-id="0677d-394">The previous sample can be modeled as follows:</span></span>

```fsharp
type BufferSize = BufferSize of int
```

<span data-ttu-id="0677d-395">Si escribe código que funciona en términos de `BufferSize` y su valor subyacente, debe construir uno en lugar de pasarlo en cualquier entero arbitrario:</span><span class="sxs-lookup"><span data-stu-id="0677d-395">If you write code that operates in terms of `BufferSize` and its underlying value, you need to construct one rather than pass in any arbitrary integer:</span></span>

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

<span data-ttu-id="0677d-396">Esto reduce la probabilidad de pasar erróneamente un entero arbitrario a la función `send`, porque el llamador debe construir un tipo `BufferSize` para ajustar un valor antes de llamar a la función.</span><span class="sxs-lookup"><span data-stu-id="0677d-396">This reduces the likelihood of mistakenly passing an arbitrary integer into the `send` function, because the caller must construct a `BufferSize` type to wrap a value before calling the function.</span></span>
