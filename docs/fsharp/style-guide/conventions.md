---
title: Convenciones de código de F#
description: Obtenga información sobre expresiones y directrices generales al escribir código de F#.
ms.date: 05/14/2018
ms.openlocfilehash: 21119b6d69e00f359104bfb6eab7681bdbfb8d78
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "49087393"
---
# <a name="f-coding-conventions"></a><span data-ttu-id="3205a-103">Convenciones de código de F#</span><span class="sxs-lookup"><span data-stu-id="3205a-103">F# coding conventions</span></span>

<span data-ttu-id="3205a-104">Las siguientes convenciones Formula de la experiencia de trabajar con F# grandes bases de datos.</span><span class="sxs-lookup"><span data-stu-id="3205a-104">The following conventions are formulated from experience working with large F# codebases.</span></span> <span data-ttu-id="3205a-105">El [cinco principios del buen código de F#](index.md#five-principles-of-good-f-code) constituyen el fundamento de cada recomendación.</span><span class="sxs-lookup"><span data-stu-id="3205a-105">The [Five principles of good F# code](index.md#five-principles-of-good-f-code) are the foundation of each recommendation.</span></span> <span data-ttu-id="3205a-106">Están relacionadas con la [instrucciones de diseño del componente de F#](component-design-guidelines.md), pero son aplicables a cualquier código de F#, no solo los componentes, como las bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="3205a-106">They are related to the [F# component design guidelines](component-design-guidelines.md), but are applicable for any F# code, not just components such as libraries.</span></span>

## <a name="organizing-code"></a><span data-ttu-id="3205a-107">Organización del código</span><span class="sxs-lookup"><span data-stu-id="3205a-107">Organizing code</span></span>

<span data-ttu-id="3205a-108">Dos métodos principales para organizar el código de características de F#: módulos y espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="3205a-108">F# features two primary ways to organize code: modules and namespaces.</span></span> <span data-ttu-id="3205a-109">Estas son similares, pero tienen las siguientes diferencias:</span><span class="sxs-lookup"><span data-stu-id="3205a-109">These are similar, but do have the following differences:</span></span>

* <span data-ttu-id="3205a-110">Los espacios de nombres se compilan como espacios de nombres. NET.</span><span class="sxs-lookup"><span data-stu-id="3205a-110">Namespaces are compiled as .NET namespaces.</span></span> <span data-ttu-id="3205a-111">Los módulos se compilan como las clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="3205a-111">Modules are compiled as static classes.</span></span>
* <span data-ttu-id="3205a-112">Espacios de nombres siempre son de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="3205a-112">Namespaces are always top level.</span></span> <span data-ttu-id="3205a-113">Pueden ser módulos anidados dentro de otros módulos y de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="3205a-113">Modules can be top-level and nested within other modules.</span></span>
* <span data-ttu-id="3205a-114">Los espacios de nombres pueden abarcar varios archivos.</span><span class="sxs-lookup"><span data-stu-id="3205a-114">Namespaces can span multiple files.</span></span> <span data-ttu-id="3205a-115">No de los módulos.</span><span class="sxs-lookup"><span data-stu-id="3205a-115">Modules cannot.</span></span>
* <span data-ttu-id="3205a-116">Los módulos se pueden decorar con `[<RequireQualifiedAccess>]` y `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="3205a-116">Modules can be decorated with `[<RequireQualifiedAccess>]` and `[<AutoOpen>]`.</span></span>

<span data-ttu-id="3205a-117">Las siguientes directrices le ayudará a utilizar para organizar el código.</span><span class="sxs-lookup"><span data-stu-id="3205a-117">The following guidelines will help you use these to organize your code.</span></span>

### <a name="prefer-namespaces-at-the-top-level"></a><span data-ttu-id="3205a-118">Preferir espacios de nombres en el nivel superior</span><span class="sxs-lookup"><span data-stu-id="3205a-118">Prefer namespaces at the top level</span></span>

<span data-ttu-id="3205a-119">Para cualquier código públicamente, espacios de nombres son preferenciales a los módulos en el nivel superior.</span><span class="sxs-lookup"><span data-stu-id="3205a-119">For any publicly consumable code, namespaces are preferential to modules at the top level.</span></span> <span data-ttu-id="3205a-120">Dado que se compilan como espacios de nombres. NET, son consumibles desde C# con ningún problema.</span><span class="sxs-lookup"><span data-stu-id="3205a-120">Because they are compiled as .NET namespaces, they are consumable from C# with no issue.</span></span>

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

<span data-ttu-id="3205a-121">Uso de un módulo de nivel superior no puede aparecer diferente cuando se llama solo desde F#, pero para los consumidores de C#, los llamadores pueden sorprenderse de tener que calificar `MyClass` con el `MyCode` módulo.</span><span class="sxs-lookup"><span data-stu-id="3205a-121">Using a top-level module may not appear different when called only from F#, but for C# consumers, callers may be surprised by having to qualify `MyClass` with the `MyCode` module.</span></span>

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a><span data-ttu-id="3205a-122">Aplicar con cuidado `[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="3205a-122">Carefully apply `[<AutoOpen>]`</span></span>

<span data-ttu-id="3205a-123">El `[<AutoOpen>]` construcción puede contamina el ámbito de lo que está disponible para los llamadores y la respuesta a algo procedencia es "mágica".</span><span class="sxs-lookup"><span data-stu-id="3205a-123">The `[<AutoOpen>]` construct can pollute the scope of what is available to callers, and the answer to where something comes from is "magic".</span></span> <span data-ttu-id="3205a-124">Por lo general esto no es algo bueno.</span><span class="sxs-lookup"><span data-stu-id="3205a-124">This is generally not a good thing.</span></span> <span data-ttu-id="3205a-125">Una excepción a esta regla es la biblioteca básica de F# propio (aunque este hecho también es algo controvertido).</span><span class="sxs-lookup"><span data-stu-id="3205a-125">An exception to this rule is the F# Core Library itself (though this fact is also a bit controversial).</span></span>

<span data-ttu-id="3205a-126">Sin embargo, es una ventaja si dispone de funcionalidad auxiliar para una API pública que desea organizar por separado desde esa API pública.</span><span class="sxs-lookup"><span data-stu-id="3205a-126">However, it is a convenience if you have helper functionality for a public API that you wish to organize separately from that public API.</span></span>

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

<span data-ttu-id="3205a-127">Esto permite detalles más limpia de implementación independiente desde la API pública de una función sin tener que calificar completamente una aplicación auxiliar de cada vez que lo llama.</span><span class="sxs-lookup"><span data-stu-id="3205a-127">This lets you cleanly separate implementation details from the public API of a function without having to fully qualify a helper each time you call it.</span></span>

<span data-ttu-id="3205a-128">Además, expone los métodos de extensión y los generadores de expresiones en el nivel de espacio de nombres puede perfectamente expresarse con `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="3205a-128">Additionally, exposing extension methods and expression builders at the namespace level can be neatly expressed with `[<AutoOpen>]`.</span></span>

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a><span data-ttu-id="3205a-129">Use `[<RequireQualifiedAccess>]` cada vez que podrían causar conflictos con nombres o cree ayuda a mejorar la legibilidad</span><span class="sxs-lookup"><span data-stu-id="3205a-129">Use `[<RequireQualifiedAccess>]` whenever names could conflict or you feel it helps with readability</span></span>

<span data-ttu-id="3205a-130">Agregar el `[<RequireQualifiedAccess>]` atributo a un módulo indica que no se puede abrir el módulo y que las referencias a los elementos del módulo requieren explícita calificar el acceso.</span><span class="sxs-lookup"><span data-stu-id="3205a-130">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="3205a-131">Por ejemplo, el `Microsoft.FSharp.Collections.List` módulo tiene este atributo.</span><span class="sxs-lookup"><span data-stu-id="3205a-131">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="3205a-132">Esto es útil cuando las funciones y los valores del módulo tienen nombres que es probables que entran en conflicto con los nombres de otros módulos.</span><span class="sxs-lookup"><span data-stu-id="3205a-132">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="3205a-133">Necesidad de tener acceso completo puede aumentar considerablemente el mantenimiento a largo plazo y la capacidad de evolución de una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="3205a-133">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a><span data-ttu-id="3205a-134">Ordenación `open` instrucciones topológicamente</span><span class="sxs-lookup"><span data-stu-id="3205a-134">Sort `open` statements topologically</span></span>

<span data-ttu-id="3205a-135">En F#, se importa el orden de las declaraciones, incluidos con `open` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="3205a-135">In F#, the order of declarations matters, including with `open` statements.</span></span> <span data-ttu-id="3205a-136">Esto es distinto de C#, donde el efecto de `using` y `using static` es independiente de la ordenación de esas instrucciones en un archivo.</span><span class="sxs-lookup"><span data-stu-id="3205a-136">This is unlike C#, where the effect of `using` and `using static` is independent of the ordering of those statements in a file.</span></span>

<span data-ttu-id="3205a-137">En F#, elementos abiertos en un ámbito pueden verse ocultado por otros usuarios ya está presente.</span><span class="sxs-lookup"><span data-stu-id="3205a-137">In F#, elements opened into a scope can shadow others already present.</span></span> <span data-ttu-id="3205a-138">Esto significa que la reordenación `open` instrucciones podrían alterar el significado del código.</span><span class="sxs-lookup"><span data-stu-id="3205a-138">This means that reordering `open` statements could alter the meaning of code.</span></span> <span data-ttu-id="3205a-139">Como resultado, cualquier arbitrario ordenar de todos los `open` instrucciones (por ejemplo, en orden alfanumérico) generalmente no se recomienda, para evitar que generar un comportamiento diferente que podría esperar.</span><span class="sxs-lookup"><span data-stu-id="3205a-139">As a result, any arbitrary sorting of all `open` statements (for example, alphanumerically) is generally not recommended, lest you generate different behavior that you might expect.</span></span>

<span data-ttu-id="3205a-140">En su lugar, se recomienda que se ordenen [topológicamente](https://en.wikipedia.org/wiki/Topological_sorting); es decir, ordenar su `open` instrucciones en el orden en que _capas_ del sistema se definen.</span><span class="sxs-lookup"><span data-stu-id="3205a-140">Instead, we recommend that you sort them [topologically](https://en.wikipedia.org/wiki/Topological_sorting); that is, order your `open` statements in the order in which _layers_ of your system are defined.</span></span> <span data-ttu-id="3205a-141">También se puede considerar haciendo alfanumérica de ordenación en las capas de topológicas diferentes.</span><span class="sxs-lookup"><span data-stu-id="3205a-141">Doing alphanumeric sorting within different topological layers may also be considered.</span></span>

<span data-ttu-id="3205a-142">Por ejemplo, aquí está la ordenación topológica para el archivo F# del compilador servicio público API:</span><span class="sxs-lookup"><span data-stu-id="3205a-142">As an example, here is the topological sorting for the F# compiler service public API file:</span></span>

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

<span data-ttu-id="3205a-143">Tenga en cuenta que un salto de línea separa topológicas capas, cada capa que se ordena en orden alfanumérico posteriormente.</span><span class="sxs-lookup"><span data-stu-id="3205a-143">Note that a line break separates topological layers, with each layer being sorted alphanumerically afterwards.</span></span> <span data-ttu-id="3205a-144">Esto limpiamente organiza el código sin sombrear accidentalmente los valores.</span><span class="sxs-lookup"><span data-stu-id="3205a-144">This cleanly organizes code without accidentally shadowing values.</span></span>

## <a name="use-classes-to-contain-values-that-have-side-effects"></a><span data-ttu-id="3205a-145">Utilizar clases para contener los valores que tienen efectos secundarios</span><span class="sxs-lookup"><span data-stu-id="3205a-145">Use classes to contain values that have side effects</span></span>

<span data-ttu-id="3205a-146">Hay muchas veces cuando la inicialización de un valor puede tener efectos secundarios, como crear una instancia de un contexto de una base de datos u otro recurso remoto.</span><span class="sxs-lookup"><span data-stu-id="3205a-146">There are many times when initializing a value can have side effects, such as instantiating a context to a database or other remote resource.</span></span> <span data-ttu-id="3205a-147">Es tentador inicializar estas cosas en un módulo y su uso en las funciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3205a-147">It is tempting to initialize such things in a module and use it in subsequent functions:</span></span>

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

<span data-ttu-id="3205a-148">Esto suele ser una mala idea por diversas razones:</span><span class="sxs-lookup"><span data-stu-id="3205a-148">This is frequently a bad idea for a few reasons:</span></span>

<span data-ttu-id="3205a-149">En primer lugar, se inserta la configuración de la aplicación en el código base con `dep1` y `dep2`.</span><span class="sxs-lookup"><span data-stu-id="3205a-149">First, application configuration is pushed into the codebase with `dep1` and `dep2`.</span></span> <span data-ttu-id="3205a-150">Esto es difícil de mantener en códigos base más grandes.</span><span class="sxs-lookup"><span data-stu-id="3205a-150">This is difficult to maintain in larger codebases.</span></span>

<span data-ttu-id="3205a-151">Los datos en segundo lugar, de manera estática no deben incluir los valores que no son seguros para subprocesos si el componente a usar varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="3205a-151">Second, statically initialized data should not include values that are not thread safe if your component will itself use multiple threads.</span></span> <span data-ttu-id="3205a-152">Esto es claramente infringida por `dep3`.</span><span class="sxs-lookup"><span data-stu-id="3205a-152">This is clearly violated by `dep3`.</span></span>

<span data-ttu-id="3205a-153">Por último, inicialización del módulo se compila en un constructor estático para la unidad de compilación completo.</span><span class="sxs-lookup"><span data-stu-id="3205a-153">Finally, module initialization compiles into a static constructor for the entire compilation unit.</span></span> <span data-ttu-id="3205a-154">Si se produce un error en la inicialización de un valor enlazado a let en ese módulo, se manifiesta como un `TypeInitializationException` que se almacena en caché para toda la duración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3205a-154">If any error occurs in let-bound value initialization in that module, it manifests as a `TypeInitializationException` that is then cached for the entire lifetime of the application.</span></span> <span data-ttu-id="3205a-155">Esto puede ser difícil de diagnosticar.</span><span class="sxs-lookup"><span data-stu-id="3205a-155">This can be difficult to diagnose.</span></span> <span data-ttu-id="3205a-156">Normalmente es una excepción interna que puede intentar volver a analizar, pero si no existe, a continuación, no es lo que es la causa raíz.</span><span class="sxs-lookup"><span data-stu-id="3205a-156">There is usually an inner exception that you can attempt to reason about, but if there is not, then there is no telling what the root cause is.</span></span>

<span data-ttu-id="3205a-157">En su lugar, use simplemente una clase simple para contener las dependencias:</span><span class="sxs-lookup"><span data-stu-id="3205a-157">Instead, just use a simple class to hold dependencies:</span></span>

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member __.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member __.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

<span data-ttu-id="3205a-158">Esto permite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3205a-158">This enables the following:</span></span>

1. <span data-ttu-id="3205a-159">Inserción de cualquier estado dependiente fuera de la propia API.</span><span class="sxs-lookup"><span data-stu-id="3205a-159">Pushing any dependent state outside of the API itself.</span></span>
2. <span data-ttu-id="3205a-160">Configuración ahora puede realizarse fuera de la API.</span><span class="sxs-lookup"><span data-stu-id="3205a-160">Configuration can now be done outside of the API.</span></span>
3. <span data-ttu-id="3205a-161">Errores de inicialización de los valores dependientes no están probable que manifiesta como un `TypeInitializationException`.</span><span class="sxs-lookup"><span data-stu-id="3205a-161">Errors in initialization for dependent values are not likely to manifest as a `TypeInitializationException`.</span></span>
4. <span data-ttu-id="3205a-162">Ahora es más fácil probar la API.</span><span class="sxs-lookup"><span data-stu-id="3205a-162">The API is now easier to test.</span></span>

## <a name="error-management"></a><span data-ttu-id="3205a-163">Administración de errores</span><span class="sxs-lookup"><span data-stu-id="3205a-163">Error management</span></span>

<span data-ttu-id="3205a-164">Administración de errores en sistemas grandes es una tarea muy compleja y matizada y no hay ningún silver viñetas en asegurar sus sistemas son tolerantes a errores y se comporten bien.</span><span class="sxs-lookup"><span data-stu-id="3205a-164">Error management in large systems is a complex and nuanced endeavor, and there are no silver bullets in ensuring your systems are fault-tolerant and behave well.</span></span> <span data-ttu-id="3205a-165">Las siguientes directrices deben ofrecer instrucciones de navegar por este espacio difícil.</span><span class="sxs-lookup"><span data-stu-id="3205a-165">The following guidelines should offer guidance in navigating this difficult space.</span></span>

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a><span data-ttu-id="3205a-166">Representar los casos de error y el estado no válido en tipos intrínsecos a su dominio</span><span class="sxs-lookup"><span data-stu-id="3205a-166">Represent error cases and illegal state in types intrinsic to your domain</span></span>

<span data-ttu-id="3205a-167">Con [uniones discriminadas](../language-reference/discriminated-unions.md), F# proporciona la capacidad para representar el estado del programa defectuoso en el sistema de tipos.</span><span class="sxs-lookup"><span data-stu-id="3205a-167">With [Discriminated Unions](../language-reference/discriminated-unions.md), F# gives you the ability to represent faulty program state in your type system.</span></span> <span data-ttu-id="3205a-168">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3205a-168">For example:</span></span>

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

<span data-ttu-id="3205a-169">En este caso, hay tres maneras conocidos que puede producir un error al retirar dinero de una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="3205a-169">In this case, there are three known ways that withdrawing money from a bank account can fail.</span></span> <span data-ttu-id="3205a-170">Cada caso de error está representado en el tipo y, por tanto, se puede solucionar en forma segura en todo el programa.</span><span class="sxs-lookup"><span data-stu-id="3205a-170">Each error case is represented in the type, and can thus be dealt with safely throughout the program.</span></span>

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

<span data-ttu-id="3205a-171">En general, si puede modelar las distintas formas que algo puede **producirá un error** en su dominio, a continuación, código de control de errores ya no se tratan como algo que debe tratar con además de flujo del programa normal.</span><span class="sxs-lookup"><span data-stu-id="3205a-171">In general, if you can model the different ways that something can **fail** in your domain, then error handling code is no longer treated as something you must deal with in addition to regular program flow.</span></span> <span data-ttu-id="3205a-172">Es simplemente una parte del flujo normal del programa y no se considera **excepcionales**.</span><span class="sxs-lookup"><span data-stu-id="3205a-172">It is simply a part of normal program flow, and not considered **exceptional**.</span></span> <span data-ttu-id="3205a-173">Hay dos ventajas principales para esto:</span><span class="sxs-lookup"><span data-stu-id="3205a-173">There are two primary benefits to this:</span></span>

1. <span data-ttu-id="3205a-174">Es más fácil de mantener a medida que cambia el dominio con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="3205a-174">It is easier to maintain as your domain changes over time.</span></span>
2. <span data-ttu-id="3205a-175">Casos de error son más fáciles de realizar una prueba unitaria.</span><span class="sxs-lookup"><span data-stu-id="3205a-175">Error cases are easier to unit test.</span></span>

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a><span data-ttu-id="3205a-176">Utilice excepciones cuando no se puede representar errores con tipos</span><span class="sxs-lookup"><span data-stu-id="3205a-176">Use exceptions when errors cannot be represented with types</span></span>

<span data-ttu-id="3205a-177">No todos los errores se pueden representar en un dominio del problema.</span><span class="sxs-lookup"><span data-stu-id="3205a-177">Not all errors can be represented in a problem domain.</span></span> <span data-ttu-id="3205a-178">Estos tipos de errores son *excepcionales* por naturaleza, por lo tanto, la capacidad de generar y capturar excepciones en F#.</span><span class="sxs-lookup"><span data-stu-id="3205a-178">These kinds of faults are *exceptional* in nature, hence the ability to raise and catch exceptions in F#.</span></span>

<span data-ttu-id="3205a-179">En primer lugar, se recomienda que lea el [directrices de diseño de la excepción](../../standard/design-guidelines/exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="3205a-179">First, it is recommended that you read the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md).</span></span> <span data-ttu-id="3205a-180">También son aplicables a F#.</span><span class="sxs-lookup"><span data-stu-id="3205a-180">These are also applicable to F#.</span></span>

<span data-ttu-id="3205a-181">Deben tener en cuenta las construcciones principales disponibles en F# con el fin de generar excepciones en el siguiente orden de preferencia:</span><span class="sxs-lookup"><span data-stu-id="3205a-181">The main constructs available in F# for the purposes of raising exceptions should be considered in the following order of preference:</span></span>

| <span data-ttu-id="3205a-182">Función</span><span class="sxs-lookup"><span data-stu-id="3205a-182">Function</span></span> | <span data-ttu-id="3205a-183">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3205a-183">Syntax</span></span> | <span data-ttu-id="3205a-184">Propósito</span><span class="sxs-lookup"><span data-stu-id="3205a-184">Purpose</span></span> |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | <span data-ttu-id="3205a-185">Genera un `System.ArgumentNullException` con el nombre del argumento especificado.</span><span class="sxs-lookup"><span data-stu-id="3205a-185">Raises a `System.ArgumentNullException` with the specified argument name.</span></span> |
| `invalidArg` | `invalidArg "argumentName" "message"` | <span data-ttu-id="3205a-186">Genera un `System.ArgumentException` con un nombre de argumento especificado y un mensaje.</span><span class="sxs-lookup"><span data-stu-id="3205a-186">Raises a `System.ArgumentException` with a specified argument name and message.</span></span> |
| `invalidOp` | `invalidOp "message"` | <span data-ttu-id="3205a-187">Genera un `System.InvalidOperationException` con el mensaje especificado.</span><span class="sxs-lookup"><span data-stu-id="3205a-187">Raises a `System.InvalidOperationException` with the specified message.</span></span> |
|`raise`| `raise (ExceptionType("message"))` | <span data-ttu-id="3205a-188">Mecanismo de uso general para generar excepciones.</span><span class="sxs-lookup"><span data-stu-id="3205a-188">General-purpose mechanism for throwing exceptions.</span></span> |
| `failwith` | `failwith "message"` | <span data-ttu-id="3205a-189">Genera un `System.Exception` con el mensaje especificado.</span><span class="sxs-lookup"><span data-stu-id="3205a-189">Raises a `System.Exception` with the specified message.</span></span> |
| `failwithf` | `failwithf "format string" argForFormatString` | <span data-ttu-id="3205a-190">Genera un `System.Exception` con un mensaje determinado por la cadena de formato y sus entradas.</span><span class="sxs-lookup"><span data-stu-id="3205a-190">Raises a `System.Exception` with a message determined by the format string and its inputs.</span></span> |

<span data-ttu-id="3205a-191">Use `nullArg`, `invalidArg` y `invalidOp` como mecanismo para producir `ArgumentNullException`, `ArgumentException` y `InvalidOperationException` cuando sea apropiado.</span><span class="sxs-lookup"><span data-stu-id="3205a-191">Use `nullArg`, `invalidArg` and `invalidOp` as the mechanism to throw `ArgumentNullException`, `ArgumentException` and `InvalidOperationException` when appropriate.</span></span>

<span data-ttu-id="3205a-192">El `failwith` y `failwithf` funciones por lo general deben evitarse porque genera la base de `Exception` escriba, no una excepción concreta.</span><span class="sxs-lookup"><span data-stu-id="3205a-192">The `failwith` and `failwithf` functions should generally be avoided because they raise the base `Exception` type, not a specific exception.</span></span> <span data-ttu-id="3205a-193">Tal como se indicó el [directrices de diseño de la excepción](../../standard/design-guidelines/exceptions.md), que desea producir excepciones más específicas cuando sea posible.</span><span class="sxs-lookup"><span data-stu-id="3205a-193">As per the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md), you want to raise more specific exceptions when you can.</span></span>

### <a name="using-exception-handling-syntax"></a><span data-ttu-id="3205a-194">Mediante la sintaxis de control de excepciones</span><span class="sxs-lookup"><span data-stu-id="3205a-194">Using exception-handling syntax</span></span>

<span data-ttu-id="3205a-195">F# admite patrones de la excepción a través de la `try...with` sintaxis:</span><span class="sxs-lookup"><span data-stu-id="3205a-195">F# supports exception patterns via the `try...with` syntax:</span></span>

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

<span data-ttu-id="3205a-196">Reconciliar funcionalidad para realizar en el caso de una excepción con el patrón de coincidencia puede ser un poco complicado si desea mantener limpio el código.</span><span class="sxs-lookup"><span data-stu-id="3205a-196">Reconciling functionality to perform in the face of an exception with pattern matching can be a bit tricky if you wish to keep the code clean.</span></span> <span data-ttu-id="3205a-197">Una manera para controlar esto es usar [modelos activos](../language-reference/active-patterns.md) como un medio para la funcionalidad de grupo que rodea a un caso de error con una excepción propia.</span><span class="sxs-lookup"><span data-stu-id="3205a-197">One such way to handle this is to use [active patterns](../language-reference/active-patterns.md) as a means to group functionality surrounding an error case with an exception itself.</span></span> <span data-ttu-id="3205a-198">Por ejemplo, es posible que consume una API que, cuando produce una excepción, se incluye información valiosa en los metadatos de excepción.</span><span class="sxs-lookup"><span data-stu-id="3205a-198">For example, you may be consuming an API that, when it throws an exception, encloses valuable information in the exception metadata.</span></span> <span data-ttu-id="3205a-199">Un valor útil en el cuerpo de la excepción capturada dentro del modelo activo de la acción de desencapsular y devolver el que el valor puede ser útil en algunas situaciones.</span><span class="sxs-lookup"><span data-stu-id="3205a-199">Unwrapping a useful value in the body of the captured exception inside the Active Pattern and returning that value can be helpful in some situations.</span></span>

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a><span data-ttu-id="3205a-200">No use monádico tratamiento de errores para reemplazar las excepciones</span><span class="sxs-lookup"><span data-stu-id="3205a-200">Do not use monadic error handling to replace exceptions</span></span>

<span data-ttu-id="3205a-201">Las excepciones se consideran un poco taboo en la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="3205a-201">Exceptions are seen as somewhat taboo in functional programming.</span></span> <span data-ttu-id="3205a-202">De hecho, las excepciones infringen la pureza, por lo que es seguro tenerlos en cuenta no muy funcional.</span><span class="sxs-lookup"><span data-stu-id="3205a-202">Indeed, exceptions violate purity, so it's safe to consider them not-quite functional.</span></span> <span data-ttu-id="3205a-203">Sin embargo, esto pasa por alto la realidad de que el código debe ejecutarse y que pueden producirse errores en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3205a-203">However, this ignores the reality of where code must run, and that runtime errors can occur.</span></span> <span data-ttu-id="3205a-204">En general, puede escribir código en la suposición de que la mayoría de las cosas son puros ni total, para minimizar las sorpresas desagradables.</span><span class="sxs-lookup"><span data-stu-id="3205a-204">In general, write code on the assumption that most things are neither pure nor total, to minimize unpleasant surprises.</span></span>

<span data-ttu-id="3205a-205">Es importante tener en cuenta los siguientes puntos fuertes y aspectos básicos de las excepciones con respecto a su relevancia y la adecuación en el tiempo de ejecución de .NET y el ecosistema de idiomas como un todo:</span><span class="sxs-lookup"><span data-stu-id="3205a-205">It is important to consider the following core strengths/aspects of Exceptions with respect to their relevance and appropriateness in the .NET runtime and cross-language ecosystem as a whole:</span></span>

1. <span data-ttu-id="3205a-206">Contienen información de diagnóstico detallada que resulta muy útil al depurar un problema.</span><span class="sxs-lookup"><span data-stu-id="3205a-206">They contain detailed diagnostic information, which is very helpful when debugging an issue.</span></span>
2. <span data-ttu-id="3205a-207">Están bien definidas por el tiempo de ejecución y otros lenguajes. NET.</span><span class="sxs-lookup"><span data-stu-id="3205a-207">They are well-understood by the runtime and other .NET languages.</span></span>
3. <span data-ttu-id="3205a-208">Pueden reducir reutilizable significativa en comparación con el código que se sale del camino a *evitar* excepciones mediante la implementación de algún subconjunto de sus semánticas en forma ad-hoc.</span><span class="sxs-lookup"><span data-stu-id="3205a-208">They can reduce significant boilerplate when compared with code that goes out of its way to *avoid* exceptions by implementing some subset of their semantics on an ad-hoc basis.</span></span>

<span data-ttu-id="3205a-209">Este tercer punto es fundamental.</span><span class="sxs-lookup"><span data-stu-id="3205a-209">This third point is critical.</span></span> <span data-ttu-id="3205a-210">Las operaciones complejas no trivial, no se puede utilizar excepciones puede producir tratar con estructuras similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="3205a-210">For nontrivial complex operations, failing to use exceptions can result in dealing with structures like this:</span></span>

```fsharp
Result<Result<MyType, string>, string list>
```

<span data-ttu-id="3205a-211">Lo que puede provocar fácilmente a código frágil, como "stringly escrito" errores de coincidencia de patrones:</span><span class="sxs-lookup"><span data-stu-id="3205a-211">Which can easily lead to fragile code like pattern matching on "stringly-typed" errors:</span></span>

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

<span data-ttu-id="3205a-212">Además, puede resultar tentador pasar cualquier excepción en la necesidad de una función "simple" que devuelve un tipo de "mejor":</span><span class="sxs-lookup"><span data-stu-id="3205a-212">Additionally, it can be tempting to swallow any exception in the desire for a "simple" function that returns a "nicer" type:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

<span data-ttu-id="3205a-213">Por desgracia, `tryReadAllText` puede producir numerosas excepciones según la infinidad de cosas que pueden ocurrir en un sistema de archivos, y este código ubicación descarta toda la información sobre lo que es posible que en realidad estar funcionando mal en su entorno.</span><span class="sxs-lookup"><span data-stu-id="3205a-213">Unfortunately, `tryReadAllText` can throw numerous exceptions based on the myriad of things that can happen on a file system, and this code discards away any information about what might actually be going wrong in your environment.</span></span> <span data-ttu-id="3205a-214">Si reemplaza este código con un tipo de resultado, va al analizar el mensaje "stringly escrito" error:</span><span class="sxs-lookup"><span data-stu-id="3205a-214">If you replace this code with a result type, then you're back to "stringly-typed" error message parsing:</span></span>

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

<span data-ttu-id="3205a-215">Y colocando el propio objeto de excepción en el `Error` constructor obliga a trabajar correctamente con el tipo de excepción en el sitio de llamada en lugar de en la función.</span><span class="sxs-lookup"><span data-stu-id="3205a-215">And placing the exception object itself in the `Error` constructor just forces you to properly deal with the exception type at the call site rather than in the function.</span></span> <span data-ttu-id="3205a-216">Hacerlo de forma eficaz crea excepciones comprobadas, que son notoriamente unfun tratar como un llamador de una API.</span><span class="sxs-lookup"><span data-stu-id="3205a-216">Doing this effectively creates checked exceptions, which are notoriously unfun to deal with as a caller of an API.</span></span>

<span data-ttu-id="3205a-217">Es una buena alternativa a los ejemplos anteriores detectar *específico* excepciones y devuelva un valor significativo en el contexto de esa excepción.</span><span class="sxs-lookup"><span data-stu-id="3205a-217">A good alternative to the above examples is to catch *specific* exceptions and return a meaningful value in the context of that exception.</span></span> <span data-ttu-id="3205a-218">Si modifica el `tryReadAllText` funcione como sigue, `None` tiene más sentido:</span><span class="sxs-lookup"><span data-stu-id="3205a-218">If you modify the `tryReadAllText` function as follows, `None` has more meaning:</span></span>

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

<span data-ttu-id="3205a-219">En lugar de funcionar como un comodín, esta función ahora controlará correctamente el caso cuando no se encontró y asignar ese significado a una devolución de un archivo.</span><span class="sxs-lookup"><span data-stu-id="3205a-219">Instead of functioning as a catch-all, this function will now properly handle the case when a file was not found and assign that meaning to a return.</span></span> <span data-ttu-id="3205a-220">Este valor devuelto puede asignar a ese caso de error, mientras no descarta cualquier información contextual o al exigir que los llamadores para tratar con un caso de que no puede ser importante en ese momento en el código.</span><span class="sxs-lookup"><span data-stu-id="3205a-220">This return value can map to that error case, while not discarding any contextual information or forcing callers to deal with a case that may not be relevant at that point in the code.</span></span>

<span data-ttu-id="3205a-221">Los tipos, como `Result<'Success, 'Error>` son adecuadas para las operaciones básicas donde no están anidados y tipos de F# opcionales son perfectos para representar cuando algo podría devolver *algo* o *nada*.</span><span class="sxs-lookup"><span data-stu-id="3205a-221">Types such as `Result<'Success, 'Error>` are appropriate for basic operations where they aren't nested, and F# optional types are perfect for representing when something could either return *something* or *nothing*.</span></span> <span data-ttu-id="3205a-222">Sin embargo, no son un reemplazo para las excepciones y no debe usarse en un intento de reemplazar las excepciones.</span><span class="sxs-lookup"><span data-stu-id="3205a-222">They are not a replacement for exceptions, though, and should not be used in an attempt to replace exceptions.</span></span> <span data-ttu-id="3205a-223">En su lugar, se debe aplicar con prudencia a determinados aspectos de la dirección de excepción y la directiva de administración de errores de maneras de destino.</span><span class="sxs-lookup"><span data-stu-id="3205a-223">Rather, they should be applied judiciously to address specific aspects of exception and error management policy in targeted ways.</span></span>

## <a name="partial-application-and-point-free-programming"></a><span data-ttu-id="3205a-224">Aplicación parcial y libre de punto de programación</span><span class="sxs-lookup"><span data-stu-id="3205a-224">Partial application and point-free programming</span></span>

<span data-ttu-id="3205a-225">F# admite la aplicación parcial y, por lo tanto, las diversas formas al programa en un estilo libre de punto.</span><span class="sxs-lookup"><span data-stu-id="3205a-225">F# supports partial application, and thus, various ways to program in a point-free style.</span></span> <span data-ttu-id="3205a-226">Esto puede ser beneficioso para reutilizar el código dentro de un módulo o la implementación de algo, pero generalmente no es algo para exponer públicamente.</span><span class="sxs-lookup"><span data-stu-id="3205a-226">This can be beneficial for code reuse within a module or the implementation of something, but it is generally not something to expose publicly.</span></span> <span data-ttu-id="3205a-227">En general, libre de punto de programación no es una virtud de por sí y puede agregar una barrera importante cognitiva para las personas que no se sumergen en el estilo.</span><span class="sxs-lookup"><span data-stu-id="3205a-227">In general, point-free programming is not a virtue in and of itself, and can add a significant cognitive barrier for people who are not immersed in the style.</span></span>

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a><span data-ttu-id="3205a-228">No use la aplicación parcial y currificación en las API públicas</span><span class="sxs-lookup"><span data-stu-id="3205a-228">Do not use partial application and currying in public APIs</span></span>

<span data-ttu-id="3205a-229">Con pocas excepciones, el uso de la aplicación parcial en las API públicas puede resultar confuso para los consumidores.</span><span class="sxs-lookup"><span data-stu-id="3205a-229">With little exception, the use of partial application in public APIs can be confusing for consumers.</span></span> <span data-ttu-id="3205a-230">Por lo general, `let`-valores enlazados en el código de F# son **valores**, no **los valores de función**.</span><span class="sxs-lookup"><span data-stu-id="3205a-230">Usually, `let`-bound values in F# code are **values**, not **function values**.</span></span> <span data-ttu-id="3205a-231">Combinación de valores y los valores de función puede dar lugar al guardar un pequeño número de líneas de código a cambio de un poco de esfuerzo especial, especialmente si se combina con los operadores como `>>` para componer las funciones.</span><span class="sxs-lookup"><span data-stu-id="3205a-231">Mixing together values and function values can result in saving a small number of lines of code in exchange for quite a bit of cognitive overhead, especially if combined with operators such as `>>` to compose functions.</span></span>

### <a name="consider-the-tooling-implications-for-point-free-programming"></a><span data-ttu-id="3205a-232">Tenga en cuenta las implicaciones de las herramientas para la programación punto libre</span><span class="sxs-lookup"><span data-stu-id="3205a-232">Consider the tooling implications for point-free programming</span></span>

<span data-ttu-id="3205a-233">Funciones currificadas no etiquete sus argumentos.</span><span class="sxs-lookup"><span data-stu-id="3205a-233">Curried functions do not label their arguments.</span></span> <span data-ttu-id="3205a-234">Esto tiene implicaciones de herramientas.</span><span class="sxs-lookup"><span data-stu-id="3205a-234">This has tooling implications.</span></span> <span data-ttu-id="3205a-235">Tenga en cuenta las dos funciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3205a-235">Consider the following two functions:</span></span>

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

<span data-ttu-id="3205a-236">Ambas son funciones válidas, pero `funcWithApplication` es una función currificada.</span><span class="sxs-lookup"><span data-stu-id="3205a-236">Both are valid functions, but `funcWithApplication` is a curried function.</span></span> <span data-ttu-id="3205a-237">Cuando mantenga el mouse sobre sus tipos en un editor, verá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3205a-237">When you hover over their types in an editor, you see this:</span></span>

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

<span data-ttu-id="3205a-238">En el sitio de llamada, información sobre herramientas en herramientas como Visual Studio no le proporcionará información significativa para saber lo que el `string` y `int` realmente representan tipos de entrada.</span><span class="sxs-lookup"><span data-stu-id="3205a-238">At the call site, tooltips in tooling such as Visual Studio will not give you meaningful information as to what the `string` and `int` input types actually represent.</span></span>

<span data-ttu-id="3205a-239">Si encuentra libre de punto de código como `funcWithApplication` es públicamente, se recomienda hacer una expansión η completa para que las herramientas pueden ocupará de nombres descriptivos para los argumentos.</span><span class="sxs-lookup"><span data-stu-id="3205a-239">If you encounter point-free code like `funcWithApplication` that is publicly consumable, it is recommended to do a full η-expansion so that tooling can pick up on meaningful names for arguments.</span></span>

<span data-ttu-id="3205a-240">Además, depuración de código sin punto puede resultar complicado, si no imposible.</span><span class="sxs-lookup"><span data-stu-id="3205a-240">Furthermore, debugging point-free code can be challenging, if not impossible.</span></span> <span data-ttu-id="3205a-241">Herramientas de depuración se basan en valores enlazados a los nombres (por ejemplo, `let` enlaces) para que puede inspeccionar la mitad de los valores intermedios a través de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="3205a-241">Debugging tools rely on values bound to names (for example, `let` bindings) so that you can inspect intermediate values midway through execution.</span></span> <span data-ttu-id="3205a-242">Cuando el código no tiene ningún valor para inspeccionar, no hay nada para depurar.</span><span class="sxs-lookup"><span data-stu-id="3205a-242">When your code has no values to inspect, there is nothing to debug.</span></span> <span data-ttu-id="3205a-243">En el futuro, las herramientas de depuración pueden evolucionar para sintetizar estos valores en función de las rutas de acceso ejecutadas anteriormente, pero no es una buena idea intentan contenerlos sus apuestas en *posibles* funcionalidad de depuración.</span><span class="sxs-lookup"><span data-stu-id="3205a-243">In the future, debugging tools may evolve to synthesize these values based on previously executed paths, but it's not a good idea to hedge your bets on *potential* debugging functionality.</span></span>

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a><span data-ttu-id="3205a-244">Considere la posibilidad de aplicación parcial como una técnica para reducir el texto modelo interno</span><span class="sxs-lookup"><span data-stu-id="3205a-244">Consider partial application as a technique to reduce internal boilerplate</span></span>

<span data-ttu-id="3205a-245">A diferencia de lo anterior, aplicación parcial es una excelente herramienta para reducir el código reutilizable dentro de una aplicación o los aspectos internos de más de una API.</span><span class="sxs-lookup"><span data-stu-id="3205a-245">In contrast to the previous point, partial application is a wonderful tool for reducing boilerplate inside of an application or the deeper internals of an API.</span></span> <span data-ttu-id="3205a-246">Puede ser útil para la implementación de API más complicadas, donde reutilizable a menudo es complicado para tratar de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="3205a-246">It can be helpful for unit testing the implementation of more complicated APIs, where boilerplate is often a pain to deal with.</span></span> <span data-ttu-id="3205a-247">Por ejemplo, el código siguiente muestra cómo se puede realizar qué marcos de simulación más ofrecen sin tomar una dependencia externa en un marco y tener que aprender un relacionados personalizada API.</span><span class="sxs-lookup"><span data-stu-id="3205a-247">For example, the following code shows how you can accomplish what most mocking frameworks give you without taking an external dependency on such a framework and having to learn a related bespoke API.</span></span>

<span data-ttu-id="3205a-248">Por ejemplo, considere la topografía de solución siguientes:</span><span class="sxs-lookup"><span data-stu-id="3205a-248">For example, consider the following solution topography:</span></span>

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

<span data-ttu-id="3205a-249">`ImplementationLogic.fsproj` Por ejemplo, podría exponer el código:</span><span class="sxs-lookup"><span data-stu-id="3205a-249">`ImplementationLogic.fsproj` might expose code such as:</span></span>

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member __.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

<span data-ttu-id="3205a-250">Las pruebas unitarias `Transactions.doTransaction` en `ImplementationLogic.Tests.fspoj` es fácil:</span><span class="sxs-lookup"><span data-stu-id="3205a-250">Unit testing `Transactions.doTransaction` in `ImplementationLogic.Tests.fspoj` is easy:</span></span>

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

<span data-ttu-id="3205a-251">Aplicar parcialmente `doTransaction` con un contexto de simulación objeto le permite llamar a la función en todas las pruebas unitarias sin necesidad de construir un contexto ficticio cada vez:</span><span class="sxs-lookup"><span data-stu-id="3205a-251">Partially applying `doTransaction` with a mocking context object lets you call the function in all of your unit tests without needing to construct a mocked context each time:</span></span>

```fsharp
namespace TransactionTests

open Xunit
open TransactionTypes
open TransactionsTestingUtil
open TransactionsTestingUtil.TransactionsTestable

let testableContext =
    { new ITransactionContext with
        member __.TheFirstMember() = ...
        member __.TheSecondMember() = ... }

let transactionRoutine = getTestableTransactionRoutine testableContext

[<Fact>]
let ``Test withdrawal transaction with 0.0 for balance``() =
    let expected = ...
    let actual = transactionRoutine TransactionType.Withdraw 0.0
    Assert.Equal(expected, actual)
```

<span data-ttu-id="3205a-252">Esta técnica no se debe aplicar universalmente a la base de código completo, pero es una buena forma de reducir el código reutilizable para internals complicadas y los aspectos internos de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="3205a-252">This technique should not be universally applied to your entire codebase, but it is a good way to reduce boilerplate for complicated internals and unit testing those internals.</span></span>

## <a name="access-control"></a><span data-ttu-id="3205a-253">Control de acceso</span><span class="sxs-lookup"><span data-stu-id="3205a-253">Access control</span></span>

<span data-ttu-id="3205a-254">F# tiene varias opciones para [control de acceso](../language-reference/access-control.md), al heredar de lo que está disponible en el tiempo de ejecución. NET.</span><span class="sxs-lookup"><span data-stu-id="3205a-254">F# has multiple options for [Access control](../language-reference/access-control.md), inherited from what is available in the .NET runtime.</span></span> <span data-ttu-id="3205a-255">Estos no son sólo puede usar para los tipos: se pueden usar para las funciones, demasiado.</span><span class="sxs-lookup"><span data-stu-id="3205a-255">These are not just usable for types - you can use them for functions, too.</span></span>

* <span data-ttu-id="3205a-256">Prefiere que no sean de`public` tipos y miembros hasta que se tienen que ser públicamente.</span><span class="sxs-lookup"><span data-stu-id="3205a-256">Prefer non-`public` types and members until you need them to be publicly consumable.</span></span> <span data-ttu-id="3205a-257">Esto minimiza también qué par de los consumidores a.</span><span class="sxs-lookup"><span data-stu-id="3205a-257">This also minimizes what consumers couple to.</span></span>
* <span data-ttu-id="3205a-258">Intente mantener toda la funcionalidad de aplicación auxiliar `private`.</span><span class="sxs-lookup"><span data-stu-id="3205a-258">Strive to keep all helper functionality `private`.</span></span>
* <span data-ttu-id="3205a-259">Considere el uso de `[<AutoOpen>]` en un módulo de funciones de aplicación auxiliar que dejen de estar numerosos privado.</span><span class="sxs-lookup"><span data-stu-id="3205a-259">Consider the use of `[<AutoOpen>]` on a private module of helper functions if they become numerous.</span></span>

## <a name="type-inference-and-generics"></a><span data-ttu-id="3205a-260">Inferencia de tipos y tipos genéricos</span><span class="sxs-lookup"><span data-stu-id="3205a-260">Type inference and generics</span></span>

<span data-ttu-id="3205a-261">Inferencia de tipos puede evitarle escribir mucho código reutilizable.</span><span class="sxs-lookup"><span data-stu-id="3205a-261">Type inference can save you from typing a lot of boilerplate.</span></span> <span data-ttu-id="3205a-262">Y generalización automática en el compilador de F# puede ayudarle a escribir código más genérico casi sin esfuerzo adicional por su parte.</span><span class="sxs-lookup"><span data-stu-id="3205a-262">And automatic generalization in the F# compiler can help you write more generic code with almost no extra effort on your part.</span></span> <span data-ttu-id="3205a-263">Sin embargo, estas características no son buenas universalmente.</span><span class="sxs-lookup"><span data-stu-id="3205a-263">However, these features are not universally good.</span></span>

* <span data-ttu-id="3205a-264">Considere la posibilidad de etiquetado de los nombres de argumento con los tipos explícitos en las API públicas y no confíe en la inferencia de tipos para este.</span><span class="sxs-lookup"><span data-stu-id="3205a-264">Consider labeling argument names with explicit types in public APIs and do not rely on type inference for this.</span></span>

    <span data-ttu-id="3205a-265">La razón de ello es que **debe tener** el control de la forma de la API, no el compilador.</span><span class="sxs-lookup"><span data-stu-id="3205a-265">The reason for this is that **you** should be in control of the shape of your API, not the compiler.</span></span> <span data-ttu-id="3205a-266">Aunque el compilador puede hacer un gran trabajo al inferir tipos para usted, es posible tener la forma de los cambios de la API si los aspectos internos que se basa en han cambiado los tipos.</span><span class="sxs-lookup"><span data-stu-id="3205a-266">Although the compiler can do a fine job at inferring types for you, it is possible to have the shape of your API change if the internals it relies on have changed types.</span></span> <span data-ttu-id="3205a-267">Esto puede ser lo que desea, pero seguramente supondrá una novedad de API que los consumidores de nivel inferiores, a continuación, tendrá que tratar con.</span><span class="sxs-lookup"><span data-stu-id="3205a-267">This may be what you want, but it will almost certainly result in a breaking API change that downstream consumers will then have to deal with.</span></span> <span data-ttu-id="3205a-268">En su lugar, si controla explícitamente la forma de la API pública, puede controlar estos cambios.</span><span class="sxs-lookup"><span data-stu-id="3205a-268">Instead, if you explicitly control the shape of your public API, then you can control these breaking changes.</span></span> <span data-ttu-id="3205a-269">En términos DDD, esto puede considerarse como una capa anticorrupción.</span><span class="sxs-lookup"><span data-stu-id="3205a-269">In DDD terms, this can be thought of as an Anti-corruption layer.</span></span>

* <span data-ttu-id="3205a-270">Dele un nombre significativo para los argumentos genéricos.</span><span class="sxs-lookup"><span data-stu-id="3205a-270">Consider giving a meaningful name to your generic arguments.</span></span>

    <span data-ttu-id="3205a-271">A menos que se está escribiendo código realmente genérico que no es específico a un dominio determinado, un nombre descriptivo puede ayudar a otros programadores entender el dominio que están trabajando en.</span><span class="sxs-lookup"><span data-stu-id="3205a-271">Unless you are writing truly generic code that is not specific to a particular domain, a meaningful name can help other programmers understanding the domain they're working in.</span></span> <span data-ttu-id="3205a-272">Por ejemplo, un parámetro de tipo denominado `'Document` en el contexto de la interacción con un documento de base de datos deja más claro que se pueden aceptar tipos de documento genérico por la función o el miembro que está trabajando.</span><span class="sxs-lookup"><span data-stu-id="3205a-272">For example, a type parameter named `'Document` in the context of interacting with a document database makes it clearer that generic document types can be accepted by the function or member you are working with.</span></span>

* <span data-ttu-id="3205a-273">Considere la posibilidad de asignar nombres a parámetros de tipo genérico con PascalCase.</span><span class="sxs-lookup"><span data-stu-id="3205a-273">Consider naming generic type parameters with PascalCase.</span></span>

    <span data-ttu-id="3205a-274">Esta es la forma general para hacer cosas en. NET, por lo que se recomienda usar PascalCase en lugar de snake_case o camelCase.</span><span class="sxs-lookup"><span data-stu-id="3205a-274">This is the general way to do things in .NET, so it's recommended that you use PascalCase rather than snake_case or camelCase.</span></span>

<span data-ttu-id="3205a-275">Por último, la generalización automática no siempre es una bendición para las personas que están familiarizadas con F# o código base es grande.</span><span class="sxs-lookup"><span data-stu-id="3205a-275">Finally, automatic generalization is not always a boon for people who are new to F# or a large codebase.</span></span> <span data-ttu-id="3205a-276">No hay esfuerzo especial en el uso de componentes que son genéricos.</span><span class="sxs-lookup"><span data-stu-id="3205a-276">There is cognitive overhead in using components that are generic.</span></span> <span data-ttu-id="3205a-277">Además, si automáticamente no se usan funciones generalizadas con diferentes tipos de entrada (let por sí solo si se han diseñado para usarse como tales), entonces no supone ninguna ventaja real a ellos que se va a genérico en ese momento dado.</span><span class="sxs-lookup"><span data-stu-id="3205a-277">Furthermore, if automatically generalized functions are not used with different input types (let alone if they are intended to be used as such), then there is no real benefit to them being generic at that point in time.</span></span> <span data-ttu-id="3205a-278">Siempre tenga en cuenta si el código que se va a escribir realmente se beneficiará de ser genérico.</span><span class="sxs-lookup"><span data-stu-id="3205a-278">Always consider if the code you are writing will actually benefit from being generic.</span></span>

## <a name="performance"></a><span data-ttu-id="3205a-279">Rendimiento</span><span class="sxs-lookup"><span data-stu-id="3205a-279">Performance</span></span>

<span data-ttu-id="3205a-280">Los valores de F# son inmutables de manera predeterminada, lo que permite evitar ciertas clases de errores (especialmente los relacionados con simultaneidad y paralelismo).</span><span class="sxs-lookup"><span data-stu-id="3205a-280">F# values are immutable by default, which allows you to avoid certain classes of bugs (especially those involving concurrency and parallelism).</span></span> <span data-ttu-id="3205a-281">Sin embargo, en algunos casos, con el fin de conseguir eficiencia óptima (o incluso razonable) de tiempo de ejecución o las asignaciones de memoria, un intervalo de trabajo puede mejor implementarse mediante el uso de mutación en lugar del estado.</span><span class="sxs-lookup"><span data-stu-id="3205a-281">However, in certain cases, in order to achieve optimal (or even reasonable) efficiency of execution time or memory allocations, a span of work may best be implemented by using in-place mutation of state.</span></span> <span data-ttu-id="3205a-282">Esto es posible en una base de participación en F# con el `mutable` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="3205a-282">This is possible in an opt-in basis with F# with the `mutable` keyword.</span></span>

<span data-ttu-id="3205a-283">Sin embargo, usar de `mutable` en F# se puede sentir no concuerda con la pureza funcional.</span><span class="sxs-lookup"><span data-stu-id="3205a-283">However, use of `mutable` in F# may feel at odds with functional purity.</span></span> <span data-ttu-id="3205a-284">Esto está bien, si ajusta las expectativas de pureza a [transparencia referencial](https://en.wikipedia.org/wiki/Referential_transparency).</span><span class="sxs-lookup"><span data-stu-id="3205a-284">This is fine, if you adjust expectations from purity to [referential transparency](https://en.wikipedia.org/wiki/Referential_transparency).</span></span> <span data-ttu-id="3205a-285">Transparencia referencial - no pureza - es el objetivo final al escribir las funciones de F#.</span><span class="sxs-lookup"><span data-stu-id="3205a-285">Referential transparency - not purity - is the end goal when writing F# functions.</span></span> <span data-ttu-id="3205a-286">Esto le permite escribir una interfaz funcional a través de una implementación basada en mutación para código crítico de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="3205a-286">This allows you to write a functional interface over a mutation-based implementation for performance critical code.</span></span>

### <a name="wrap-mutable-code-in-immutable-interfaces"></a><span data-ttu-id="3205a-287">Incluya código mutable en interfaces inmutables</span><span class="sxs-lookup"><span data-stu-id="3205a-287">Wrap mutable code in immutable interfaces</span></span>

<span data-ttu-id="3205a-288">Con una transparencia referencial como objetivo, es fundamental para escribir código que no expone el underbelly mutable de las funciones esenciales para el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="3205a-288">With referential transparency as a goal, it is critical to write code that does not expose the mutable underbelly of performance-critical functions.</span></span> <span data-ttu-id="3205a-289">Por ejemplo, el código siguiente implementa el `Array.contains` función en la biblioteca básica de F#:</span><span class="sxs-lookup"><span data-stu-id="3205a-289">For example, the following code implements the `Array.contains` function in the F# core library:</span></span>

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

<span data-ttu-id="3205a-290">Llamar varias veces a esta función no modifica la matriz subyacente, ni es necesario mantener cualquier estado mutable en que lo consume.</span><span class="sxs-lookup"><span data-stu-id="3205a-290">Calling this function multiple times does not change the underlying array, nor does it require you to maintain any mutable state in consuming it.</span></span> <span data-ttu-id="3205a-291">Es forma referencial transparente, aunque casi todas las líneas de código dentro de él usa mutación.</span><span class="sxs-lookup"><span data-stu-id="3205a-291">It is referentially transparent, even though almost every line of code within it uses mutation.</span></span>

### <a name="consider-encapsulating-mutable-data-in-classes"></a><span data-ttu-id="3205a-292">Considere la posibilidad de encapsular datos mutables en clases</span><span class="sxs-lookup"><span data-stu-id="3205a-292">Consider encapsulating mutable data in classes</span></span>

<span data-ttu-id="3205a-293">El ejemplo anterior usa una sola función para encapsular las operaciones con datos mutables.</span><span class="sxs-lookup"><span data-stu-id="3205a-293">The previous example used a single function to encapsulate operations using mutable data.</span></span> <span data-ttu-id="3205a-294">No siempre es suficiente para conjuntos más complejos de datos.</span><span class="sxs-lookup"><span data-stu-id="3205a-294">This is not always sufficient for more complex sets of data.</span></span> <span data-ttu-id="3205a-295">Tenga en cuenta los siguientes conjuntos de funciones:</span><span class="sxs-lookup"><span data-stu-id="3205a-295">Consider the following sets of functions:</span></span>

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

<span data-ttu-id="3205a-296">Este código es eficaz, pero expone la estructura de datos en función de mutación que son responsables de mantener los llamadores.</span><span class="sxs-lookup"><span data-stu-id="3205a-296">This code is performant, but it exposes the mutation-based data structure that callers are responsible for maintaining.</span></span> <span data-ttu-id="3205a-297">Esto puede colocarse dentro de una clase sin miembros subyacente que puede cambiar:</span><span class="sxs-lookup"><span data-stu-id="3205a-297">This can be wrapped inside of a class with no underlying members that can change:</span></span>

```fsharp
open System.Collections.Generic

/// The results of computing the LALR(1) closure of an LR(0) kernel
type Closure1Table() =
    let t = Dictionary<Item0, HashSet<TerminalIndex>>()

    member __.Add(key, value) =
        if not (t.ContainsKey(key)) then
            t.Add(key, value)
        else
            t.[key] <- value

    member __.Count = t.Count

    member __.Contains(key, value) =
        match t.TryGetValue(key) with
        | (true, v) -> v.Equals(value)
        | (false, _) -> false
```

<span data-ttu-id="3205a-298">`Closure1Table` Encapsula la estructura de datos basados en mutación subyacente, por lo que no forzar los llamadores para mantener la estructura de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="3205a-298">`Closure1Table` encapsulates the underlying mutation-based data structure, thereby not forcing callers to maintain the underlying data structure.</span></span> <span data-ttu-id="3205a-299">Las clases son una forma eficaz para encapsular datos y las rutinas que están basados en mutación sin exponer los detalles a los llamadores.</span><span class="sxs-lookup"><span data-stu-id="3205a-299">Classes are a powerful way to encapsulate data and routines that are mutation-based without exposing the details to callers.</span></span>

### <a name="prefer-let-mutable-to-reference-cells"></a><span data-ttu-id="3205a-300">Prefiere `let mutable` a las celdas de referencia</span><span class="sxs-lookup"><span data-stu-id="3205a-300">Prefer `let mutable` to reference cells</span></span>

<span data-ttu-id="3205a-301">Las celdas de referencia son una forma para representar la referencia a un valor en lugar de como el propio valor.</span><span class="sxs-lookup"><span data-stu-id="3205a-301">Reference cells are a way to represent the reference to a value rather than the value itself.</span></span> <span data-ttu-id="3205a-302">Aunque puede usarse para el código crítico para el rendimiento, por lo general no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="3205a-302">Although they can be used for performance-critical code, they are generally not recommended.</span></span> <span data-ttu-id="3205a-303">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3205a-303">Consider the following example:</span></span>

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

<span data-ttu-id="3205a-304">El uso de una celda de referencia "contamina" todo el código subsiguiente con tener que desreferenciar y vuelva a hacer referencia a los datos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="3205a-304">The use of a reference cell now "pollutes" all subsequent code with having to dereference and re-reference the underlying data.</span></span> <span data-ttu-id="3205a-305">En su lugar, considere la posibilidad de `let mutable`:</span><span class="sxs-lookup"><span data-stu-id="3205a-305">Instead, consider `let mutable`:</span></span>

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

<span data-ttu-id="3205a-306">El único punto de mutación en medio de la expresión lambda, aparte de todos los demás código que toca `acc` puede hacerlo de manera que es similar al uso de un mapa normal `let`-valor inmutable del límite.</span><span class="sxs-lookup"><span data-stu-id="3205a-306">Aside from the single point of mutation in the middle of the lambda expression, all other code that touches `acc` can do so in a manner that is no different to the usage of a normal `let`-bound immutable value.</span></span> <span data-ttu-id="3205a-307">Así resultará más fácil cambiar con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="3205a-307">This will make it easier to change over time.</span></span>

## <a name="object-programming"></a><span data-ttu-id="3205a-308">Programación de objetos</span><span class="sxs-lookup"><span data-stu-id="3205a-308">Object programming</span></span>

<span data-ttu-id="3205a-309">F# es totalmente compatible con objetos y conceptos orientados a objetos de (objetos OO).</span><span class="sxs-lookup"><span data-stu-id="3205a-309">F# has full support for objects and object-oriented (OO) concepts.</span></span> <span data-ttu-id="3205a-310">Aunque muchos conceptos OO son eficaz y útil, no todos ellos son idóneos para su uso.</span><span class="sxs-lookup"><span data-stu-id="3205a-310">Although many OO concepts are powerful and useful, not all of them are ideal to use.</span></span> <span data-ttu-id="3205a-311">Las listas siguientes ofrecen instrucciones en las categorías de características orientado a objetos en un nivel alto.</span><span class="sxs-lookup"><span data-stu-id="3205a-311">The following lists offer guidance on categories of OO features at a high level.</span></span>

<span data-ttu-id="3205a-312">**Considere el uso de estas características en muchas situaciones:**</span><span class="sxs-lookup"><span data-stu-id="3205a-312">**Consider using these features in many situations:**</span></span>

* <span data-ttu-id="3205a-313">La notación de puntos (`x.Length`)</span><span class="sxs-lookup"><span data-stu-id="3205a-313">Dot notation (`x.Length`)</span></span>
* <span data-ttu-id="3205a-314">Miembros de instancia</span><span class="sxs-lookup"><span data-stu-id="3205a-314">Instance members</span></span>
* <span data-ttu-id="3205a-315">Constructores implícitos</span><span class="sxs-lookup"><span data-stu-id="3205a-315">Implicit constructors</span></span>
* <span data-ttu-id="3205a-316">Miembros estáticos</span><span class="sxs-lookup"><span data-stu-id="3205a-316">Static members</span></span>
* <span data-ttu-id="3205a-317">Notación de indizador (`arr.[x]`)</span><span class="sxs-lookup"><span data-stu-id="3205a-317">Indexer notation (`arr.[x]`)</span></span>
* <span data-ttu-id="3205a-318">Argumentos opcionales y con nombre</span><span class="sxs-lookup"><span data-stu-id="3205a-318">Named and Optional arguments</span></span>
* <span data-ttu-id="3205a-319">Interfaces y las implementaciones de interfaz</span><span class="sxs-lookup"><span data-stu-id="3205a-319">Interfaces and interface implementations</span></span>

<span data-ttu-id="3205a-320">**No llegan a estas características en primer lugar, pero con prudencia aplicarlos cuando están cómodas resolver un problema:**</span><span class="sxs-lookup"><span data-stu-id="3205a-320">**Don't reach for these features first, but do judiciously apply them when they are convenient to solve a problem:**</span></span>

* <span data-ttu-id="3205a-321">Sobrecarga de métodos</span><span class="sxs-lookup"><span data-stu-id="3205a-321">Method overloading</span></span>
* <span data-ttu-id="3205a-322">Datos mutables encapsulados</span><span class="sxs-lookup"><span data-stu-id="3205a-322">Encapsulated mutable data</span></span>
* <span data-ttu-id="3205a-323">Operadores de tipos</span><span class="sxs-lookup"><span data-stu-id="3205a-323">Operators on types</span></span>
* <span data-ttu-id="3205a-324">Propiedades automáticas</span><span class="sxs-lookup"><span data-stu-id="3205a-324">Auto properties</span></span>
* <span data-ttu-id="3205a-325">Implementar `IDisposable` y `IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="3205a-325">Implementing `IDisposable` and `IEnumerable`</span></span>
* <span data-ttu-id="3205a-326">Extensiones de tipo</span><span class="sxs-lookup"><span data-stu-id="3205a-326">Type extensions</span></span>
* <span data-ttu-id="3205a-327">Eventos</span><span class="sxs-lookup"><span data-stu-id="3205a-327">Events</span></span>
* <span data-ttu-id="3205a-328">Estructuras</span><span class="sxs-lookup"><span data-stu-id="3205a-328">Structs</span></span>
* <span data-ttu-id="3205a-329">Delegados</span><span class="sxs-lookup"><span data-stu-id="3205a-329">Delegates</span></span>
* <span data-ttu-id="3205a-330">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="3205a-330">Enums</span></span>

<span data-ttu-id="3205a-331">**Por lo general debe evitar estas características, a menos que se debe usar:**</span><span class="sxs-lookup"><span data-stu-id="3205a-331">**Generally avoid these features unless you must use them:**</span></span>

* <span data-ttu-id="3205a-332">Las jerarquías de tipo basado en la herencia y herencia de implementación</span><span class="sxs-lookup"><span data-stu-id="3205a-332">Inheritance-based type hierarchies and implementation inheritance</span></span>
* <span data-ttu-id="3205a-333">Los valores NULL y `Unchecked.defaultof<_>`</span><span class="sxs-lookup"><span data-stu-id="3205a-333">Nulls and `Unchecked.defaultof<_>`</span></span>

### <a name="prefer-composition-over-inheritance"></a><span data-ttu-id="3205a-334">Preferir composición herencia</span><span class="sxs-lookup"><span data-stu-id="3205a-334">Prefer composition over inheritance</span></span>

<span data-ttu-id="3205a-335">[Composición con herencia](https://en.wikipedia.org/wiki/Composition_over_inheritance) es una expresión desde hace mucho tiempo que puede cumplir buen código de F#.</span><span class="sxs-lookup"><span data-stu-id="3205a-335">[Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance) is a long-standing idiom that good F# code can adhere to.</span></span> <span data-ttu-id="3205a-336">El principio fundamental es que no debe exponer una clase base y forzar que los llamadores hereden de esa clase base para obtener funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="3205a-336">The fundamental principle is that you should not expose a base class and force callers to inherit from that base class to get functionality.</span></span>

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a><span data-ttu-id="3205a-337">Usar expresiones de objeto para implementar interfaces si no necesita una clase</span><span class="sxs-lookup"><span data-stu-id="3205a-337">Use object expressions to implement interfaces if you don't need a class</span></span>

<span data-ttu-id="3205a-338">[Expresiones de objeto](../language-reference/object-expressions.md) le permiten implementar interfaces sobre la marcha, enlace de la interfaz implementada en un valor sin necesidad de hacerlo dentro de una clase.</span><span class="sxs-lookup"><span data-stu-id="3205a-338">[Object Expressions](../language-reference/object-expressions.md) allow you to implement interfaces on the fly, binding the implemented interface to a value without needing to do so inside of a class.</span></span> <span data-ttu-id="3205a-339">Esto es práctico, especialmente si se _sólo_ debe implementar la interfaz y no es necesario para una clase completa.</span><span class="sxs-lookup"><span data-stu-id="3205a-339">This is convenient, especially if you _only_ need to implement the interface and have no need for a full class.</span></span>

<span data-ttu-id="3205a-340">Por ejemplo, este es el código que se ejecuta en [Ionide](http://ionide.io/) para proporcionar una acción de corrección de código si ha agregado un símbolo que no tiene un `open` instrucción para:</span><span class="sxs-lookup"><span data-stu-id="3205a-340">For example, here is the code that is run in [Ionide](http://ionide.io/) to provide a code fix action if you've added a symbol that you don't have an `open` statement for:</span></span>

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

<span data-ttu-id="3205a-341">Dado que no hay ninguna necesidad de una clase al interactuar con la API de código de Visual Studio, las expresiones de objeto son una herramienta ideal para este.</span><span class="sxs-lookup"><span data-stu-id="3205a-341">Because there is no need for a class when interacting with the Visual Studio Code API, Object Expressions are an ideal tool for this.</span></span> <span data-ttu-id="3205a-342">También son valiosos para las pruebas unitarias, cuando desea extraer una interfaz con las rutinas de prueba el código auxiliar de manera ad hoc.</span><span class="sxs-lookup"><span data-stu-id="3205a-342">They are also valuable for unit testing, when you want to stub out an interface with test routines in an ad hoc manner.</span></span>

## <a name="type-abbreviations"></a><span data-ttu-id="3205a-343">Abreviaturas de tipo</span><span class="sxs-lookup"><span data-stu-id="3205a-343">Type Abbreviations</span></span>

<span data-ttu-id="3205a-344">[Abreviaturas de tipo](../language-reference/type-abbreviations.md) son una manera cómoda de asignar una etiqueta a otro tipo, como una firma de función o un tipo más complejo.</span><span class="sxs-lookup"><span data-stu-id="3205a-344">[Type Abbreviations](../language-reference/type-abbreviations.md) are a convenient way to assign a label to another type, such as a function signature or a more complex type.</span></span> <span data-ttu-id="3205a-345">Por ejemplo, el siguiente alias asigna una etiqueta a qué hace falta para definir un cálculo con [CNTK](https://www.microsoft.com/en-us/cognitive-toolkit/), una biblioteca de aprendizaje profundo:</span><span class="sxs-lookup"><span data-stu-id="3205a-345">For example, the following alias assigns a label to what's needed to define a computation with [CNTK](https://www.microsoft.com/en-us/cognitive-toolkit/), a deep learning library:</span></span>

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

<span data-ttu-id="3205a-346">El `Computation` nombre es una manera cómoda para indicar cualquier función que coincida con la firma es el suavizado de contorno.</span><span class="sxs-lookup"><span data-stu-id="3205a-346">The `Computation` name is a convenient way to denote any function that matches the signature it is aliasing.</span></span> <span data-ttu-id="3205a-347">Mediante las abreviaturas de tipo como esto es conveniente y permite código más concisa.</span><span class="sxs-lookup"><span data-stu-id="3205a-347">Using Type Abbreviations like this is convenient and allows for more succinct code.</span></span>

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a><span data-ttu-id="3205a-348">Evite el uso de las abreviaturas de tipo para representar el dominio</span><span class="sxs-lookup"><span data-stu-id="3205a-348">Avoid using Type Abbreviations to represent your domain</span></span>

<span data-ttu-id="3205a-349">Aunque las abreviaturas de tipo son convenientes para asignar un nombre a las firmas de función, puede resultar confusos cuando abreviar otros tipos.</span><span class="sxs-lookup"><span data-stu-id="3205a-349">Although Type Abbreviations are convenient for giving a name to function signatures, they can be confusing when abbreviating other types.</span></span> <span data-ttu-id="3205a-350">Tenga en cuenta esta abreviatura:</span><span class="sxs-lookup"><span data-stu-id="3205a-350">Consider this abbreviation:</span></span>

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

<span data-ttu-id="3205a-351">Esto puede resultar confuso de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="3205a-351">This can be confusing in multiple ways:</span></span>

* <span data-ttu-id="3205a-352">`BufferSize` no es una abstracción; es simplemente otro nombre para un número entero.</span><span class="sxs-lookup"><span data-stu-id="3205a-352">`BufferSize` is not an abstraction; it is just another name for an integer.</span></span>
* <span data-ttu-id="3205a-353">Si `BufferSize` se expone en una API pública, fácilmente se puedan interpretar erróneamente implica algo más que `int`.</span><span class="sxs-lookup"><span data-stu-id="3205a-353">If `BufferSize` is exposed in a public API, it can easily be misinterpreted to mean more than just `int`.</span></span> <span data-ttu-id="3205a-354">Por lo general, los tipos de dominio tiene varios atributos a ellos y no son tipos primitivos, como `int`.</span><span class="sxs-lookup"><span data-stu-id="3205a-354">Generally, domain types have multiple attributes to them and are not primitive types like `int`.</span></span> <span data-ttu-id="3205a-355">Esta abreviatura infringe esa suposición.</span><span class="sxs-lookup"><span data-stu-id="3205a-355">This abbreviation violates that assumption.</span></span>
* <span data-ttu-id="3205a-356">El uso de mayúsculas y minúsculas de `BufferSize` (PascalCase) implica que este tipo contiene más datos.</span><span class="sxs-lookup"><span data-stu-id="3205a-356">The casing of `BufferSize` (PascalCase) implies that this type holds more data.</span></span>
* <span data-ttu-id="3205a-357">Este alias no ofrece una mayor en comparación con el suministro de un argumento con nombre a una función.</span><span class="sxs-lookup"><span data-stu-id="3205a-357">This alias does not offer increased clarity compared with providing a named argument to a function.</span></span>
* <span data-ttu-id="3205a-358">La abreviatura no se manifiesta en IL compilado; es simplemente un número entero y este alias es una construcción de tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="3205a-358">The abbreviation will not manifest in compiled IL; it is just an integer and this alias is a compile-time construct.</span></span>

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) =
        ...
```

<span data-ttu-id="3205a-359">En resumen, la dificultad con abreviaturas de tipo es que son **no** abstracciones a través de los tipos que son abreviar.</span><span class="sxs-lookup"><span data-stu-id="3205a-359">In summary, the pitfall with Type Abbreviations is that they are **not** abstractions over the types they are abbreviating.</span></span> <span data-ttu-id="3205a-360">En el ejemplo anterior, `BufferSize` es simplemente un `int` en segundo plano, con ningún dato adicional ni ningún beneficio desde el sistema de tipos, además de lo que `int` ya tiene.</span><span class="sxs-lookup"><span data-stu-id="3205a-360">In the previous example, `BufferSize` is just an `int` under the covers, with no additional data, nor any benefits from the type system besides what `int` already has.</span></span>
