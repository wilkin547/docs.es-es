---
title: Convenciones de código de F#
description: Aprenda las pautas generales y los modismos al escribir código de F.
ms.date: 01/15/2020
ms.openlocfilehash: 7266211e501bdb52564220781e2347d1aceaf296
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401152"
---
# <a name="f-coding-conventions"></a><span data-ttu-id="b7ea9-103">Convenciones de código de F#</span><span class="sxs-lookup"><span data-stu-id="b7ea9-103">F# coding conventions</span></span>

<span data-ttu-id="b7ea9-104">Las siguientes convenciones se formulan a partir de la experiencia de trabajo con grandes bases de código de F.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-104">The following conventions are formulated from experience working with large F# codebases.</span></span> <span data-ttu-id="b7ea9-105">Los [cinco principios del buen código de F](index.md#five-principles-of-good-f-code) son la base de cada recomendación.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-105">The [Five principles of good F# code](index.md#five-principles-of-good-f-code) are the foundation of each recommendation.</span></span> <span data-ttu-id="b7ea9-106">Están relacionados con las directrices de diseño de [componentes](component-design-guidelines.md)de F , pero son aplicables a cualquier código de F, no solo a componentes como bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-106">They are related to the [F# component design guidelines](component-design-guidelines.md), but are applicable for any F# code, not just components such as libraries.</span></span>

## <a name="organizing-code"></a><span data-ttu-id="b7ea9-107">Organización del código</span><span class="sxs-lookup"><span data-stu-id="b7ea9-107">Organizing code</span></span>

<span data-ttu-id="b7ea9-108">F- cuenta con dos formas principales de organizar el código: módulos y espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-108">F# features two primary ways to organize code: modules and namespaces.</span></span> <span data-ttu-id="b7ea9-109">Estos son similares, pero tienen las siguientes diferencias:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-109">These are similar, but do have the following differences:</span></span>

* <span data-ttu-id="b7ea9-110">Los espacios de nombres se compilan como espacios de nombres .NET.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-110">Namespaces are compiled as .NET namespaces.</span></span> <span data-ttu-id="b7ea9-111">Los módulos se compilan como clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-111">Modules are compiled as static classes.</span></span>
* <span data-ttu-id="b7ea9-112">Los espacios de nombres siempre son de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-112">Namespaces are always top level.</span></span> <span data-ttu-id="b7ea9-113">Los módulos pueden ser de nivel superior y anidados dentro de otros módulos.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-113">Modules can be top-level and nested within other modules.</span></span>
* <span data-ttu-id="b7ea9-114">Los espacios de nombres pueden abarcar varios archivos.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-114">Namespaces can span multiple files.</span></span> <span data-ttu-id="b7ea9-115">Los módulos no pueden.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-115">Modules cannot.</span></span>
* <span data-ttu-id="b7ea9-116">Los módulos `[<RequireQualifiedAccess>]` se `[<AutoOpen>]`pueden decorar con y .</span><span class="sxs-lookup"><span data-stu-id="b7ea9-116">Modules can be decorated with `[<RequireQualifiedAccess>]` and `[<AutoOpen>]`.</span></span>

<span data-ttu-id="b7ea9-117">Las siguientes directrices le ayudarán a usarlas para organizar el código.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-117">The following guidelines will help you use these to organize your code.</span></span>

### <a name="prefer-namespaces-at-the-top-level"></a><span data-ttu-id="b7ea9-118">Prefiere espacios de nombres en el nivel superior</span><span class="sxs-lookup"><span data-stu-id="b7ea9-118">Prefer namespaces at the top level</span></span>

<span data-ttu-id="b7ea9-119">Para cualquier código consumible públicamente, los espacios de nombres son preferenciales a los módulos en el nivel superior.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-119">For any publicly consumable code, namespaces are preferential to modules at the top level.</span></span> <span data-ttu-id="b7ea9-120">Debido a que se compilan como espacios de nombres de .NET, son consumibles de C- sin ningún problema.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-120">Because they are compiled as .NET namespaces, they are consumable from C# with no issue.</span></span>

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

<span data-ttu-id="b7ea9-121">El uso de un módulo de nivel superior puede no parecer diferente cuando se llama solo desde `MyClass` F, pero para los consumidores de C, los llamadores pueden sorprenderse al tener que calificar con el `MyCode` módulo.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-121">Using a top-level module may not appear different when called only from F#, but for C# consumers, callers may be surprised by having to qualify `MyClass` with the `MyCode` module.</span></span>

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a><span data-ttu-id="b7ea9-122">Aplicar con cuidado`[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="b7ea9-122">Carefully apply `[<AutoOpen>]`</span></span>

<span data-ttu-id="b7ea9-123">La `[<AutoOpen>]` construcción puede contaminar el alcance de lo que está disponible para las personas que llaman, y la respuesta a donde algo viene es "magia".</span><span class="sxs-lookup"><span data-stu-id="b7ea9-123">The `[<AutoOpen>]` construct can pollute the scope of what is available to callers, and the answer to where something comes from is "magic".</span></span> <span data-ttu-id="b7ea9-124">Esto no es algo bueno.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-124">This is not a good thing.</span></span> <span data-ttu-id="b7ea9-125">Una excepción a esta regla es la propia biblioteca principal de F - (aunque este hecho también es un poco controvertido).</span><span class="sxs-lookup"><span data-stu-id="b7ea9-125">An exception to this rule is the F# Core Library itself (though this fact is also a bit controversial).</span></span>

<span data-ttu-id="b7ea9-126">Sin embargo, es una comodidad si tiene funcionalidad de aplicación auxiliar para una API pública que desea organizar por separado de esa API pública.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-126">However, it is a convenience if you have helper functionality for a public API that you wish to organize separately from that public API.</span></span>

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

<span data-ttu-id="b7ea9-127">Esto le permite separar limpiamente los detalles de implementación de la API pública de una función sin tener que calificar completamente a una aplicación auxiliar cada vez que la llame.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-127">This lets you cleanly separate implementation details from the public API of a function without having to fully qualify a helper each time you call it.</span></span>

<span data-ttu-id="b7ea9-128">Además, la exposición de métodos de extensión y `[<AutoOpen>]`generadores de expresiones en el nivel de espacio de nombres se puede expresar perfectamente con .</span><span class="sxs-lookup"><span data-stu-id="b7ea9-128">Additionally, exposing extension methods and expression builders at the namespace level can be neatly expressed with `[<AutoOpen>]`.</span></span>

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a><span data-ttu-id="b7ea9-129">Usar `[<RequireQualifiedAccess>]` siempre que los nombres puedan entrar en conflicto o sienta que ayuda con la legibilidad</span><span class="sxs-lookup"><span data-stu-id="b7ea9-129">Use `[<RequireQualifiedAccess>]` whenever names could conflict or you feel it helps with readability</span></span>

<span data-ttu-id="b7ea9-130">Agregar `[<RequireQualifiedAccess>]` el atributo a un módulo indica que el módulo no se puede abrir y que las referencias a los elementos del módulo requieren acceso calificado explícito.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-130">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="b7ea9-131">Por ejemplo, `Microsoft.FSharp.Collections.List` el módulo tiene este atributo.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-131">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="b7ea9-132">Esto es útil cuando las funciones y los valores del módulo tienen nombres que probablemente entren en conflicto con los nombres de otros módulos.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-132">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="b7ea9-133">Requerir acceso calificado puede aumentar en gran medida la capacidad de mantenimiento y la capacidad de conexión a largo plazo de una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-133">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a><span data-ttu-id="b7ea9-134">Ordenar `open` las declaraciones topológicamente</span><span class="sxs-lookup"><span data-stu-id="b7ea9-134">Sort `open` statements topologically</span></span>

<span data-ttu-id="b7ea9-135">El orden de las declaraciones es `open` importante, incluso con las declaraciones.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-135">In F#, the order of declarations matters, including with `open` statements.</span></span> <span data-ttu-id="b7ea9-136">Esto es diferente de C- `using` `using static` , donde el efecto de y es independiente del orden de esas instrucciones en un archivo.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-136">This is unlike C#, where the effect of `using` and `using static` is independent of the ordering of those statements in a file.</span></span>

<span data-ttu-id="b7ea9-137">Los elementos abiertos en un ámbito pueden sombrear a otros ya presentes en F.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-137">In F#, elements opened into a scope can shadow others already present.</span></span> <span data-ttu-id="b7ea9-138">Esto significa que `open` reordenar instrucciones podría alterar el significado del código.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-138">This means that reordering `open` statements could alter the meaning of code.</span></span> <span data-ttu-id="b7ea9-139">Como resultado, no se recomienda `open` cualquier ordenación arbitraria de todas las instrucciones (por ejemplo, alfanuméricamente), no sea que genere un comportamiento diferente que pueda esperar.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-139">As a result, any arbitrary sorting of all `open` statements (for example, alphanumerically) is not recommended, lest you generate different behavior that you might expect.</span></span>

<span data-ttu-id="b7ea9-140">En su lugar, se recomienda ordenarlos [topológicamente;](https://en.wikipedia.org/wiki/Topological_sorting) es decir, `open` ordene sus estados de cuenta en el orden en que se definen _las capas_ del sistema.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-140">Instead, we recommend that you sort them [topologically](https://en.wikipedia.org/wiki/Topological_sorting); that is, order your `open` statements in the order in which _layers_ of your system are defined.</span></span> <span data-ttu-id="b7ea9-141">También se puede considerar la ordenación alfanumérica dentro de diferentes capas topológicas.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-141">Doing alphanumeric sorting within different topological layers may also be considered.</span></span>

<span data-ttu-id="b7ea9-142">Por ejemplo, aquí está la ordenación topológica para el archivo de API pública del servicio del compilador de F:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-142">As an example, here is the topological sorting for the F# compiler service public API file:</span></span>

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

<span data-ttu-id="b7ea9-143">Tenga en cuenta que un salto de línea separa las capas topológicas, con cada capa que se ordena alfanuméricamente después.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-143">Note that a line break separates topological layers, with each layer being sorted alphanumerically afterwards.</span></span> <span data-ttu-id="b7ea9-144">Esto organiza limpiamente el código sin sombreado accidentalmente los valores.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-144">This cleanly organizes code without accidentally shadowing values.</span></span>

## <a name="use-classes-to-contain-values-that-have-side-effects"></a><span data-ttu-id="b7ea9-145">Utilice clases para contener valores que tengan efectos secundarios</span><span class="sxs-lookup"><span data-stu-id="b7ea9-145">Use classes to contain values that have side effects</span></span>

<span data-ttu-id="b7ea9-146">Hay muchas veces cuando la inicialización de un valor puede tener efectos secundarios, como crear instancias de un contexto en una base de datos u otro recurso remoto.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-146">There are many times when initializing a value can have side effects, such as instantiating a context to a database or other remote resource.</span></span> <span data-ttu-id="b7ea9-147">Es tentador inicializar tales cosas en un módulo y utilizarlo en funciones posteriores:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-147">It is tempting to initialize such things in a module and use it in subsequent functions:</span></span>

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

<span data-ttu-id="b7ea9-148">Esto es con frecuencia una mala idea por algunas razones:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-148">This is frequently a bad idea for a few reasons:</span></span>

<span data-ttu-id="b7ea9-149">En primer lugar, la configuración `dep1` de `dep2`la aplicación se inserta en el código base con y .</span><span class="sxs-lookup"><span data-stu-id="b7ea9-149">First, application configuration is pushed into the codebase with `dep1` and `dep2`.</span></span> <span data-ttu-id="b7ea9-150">Esto es difícil de mantener en bases de código más grandes.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-150">This is difficult to maintain in larger codebases.</span></span>

<span data-ttu-id="b7ea9-151">En segundo lugar, los datos inicializados estáticamente no deben incluir valores que no sean seguros para subprocesos si el componente utilizará varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-151">Second, statically initialized data should not include values that are not thread safe if your component will itself use multiple threads.</span></span> <span data-ttu-id="b7ea9-152">Esto es claramente `dep3`violado por .</span><span class="sxs-lookup"><span data-stu-id="b7ea9-152">This is clearly violated by `dep3`.</span></span>

<span data-ttu-id="b7ea9-153">Por último, la inicialización del módulo se compila en un constructor estático para toda la unidad de compilación.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-153">Finally, module initialization compiles into a static constructor for the entire compilation unit.</span></span> <span data-ttu-id="b7ea9-154">Si se produce algún error en la inicialización del `TypeInitializationException` valor enlazado a let en ese módulo, se manifiesta como un que, a continuación, se almacena en caché durante toda la duración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-154">If any error occurs in let-bound value initialization in that module, it manifests as a `TypeInitializationException` that is then cached for the entire lifetime of the application.</span></span> <span data-ttu-id="b7ea9-155">Esto puede ser difícil de diagnosticar.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-155">This can be difficult to diagnose.</span></span> <span data-ttu-id="b7ea9-156">Por lo general, hay una excepción interna sobre la que puede intentar razonar, pero si no lo hay, entonces no se sabe cuál es la causa raíz.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-156">There is usually an inner exception that you can attempt to reason about, but if there is not, then there is no telling what the root cause is.</span></span>

<span data-ttu-id="b7ea9-157">En su lugar, solo tiene que utilizar una clase simple para contener dependencias:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-157">Instead, just use a simple class to hold dependencies:</span></span>

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member _.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member _.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

<span data-ttu-id="b7ea9-158">Esto permite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-158">This enables the following:</span></span>

1. <span data-ttu-id="b7ea9-159">Empujar cualquier estado dependiente fuera de la propia API.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-159">Pushing any dependent state outside of the API itself.</span></span>
2. <span data-ttu-id="b7ea9-160">La configuración ahora se puede realizar fuera de la API.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-160">Configuration can now be done outside of the API.</span></span>
3. <span data-ttu-id="b7ea9-161">No es probable que los errores en `TypeInitializationException`la inicialización de valores dependientes se manifiesten como un archivo .</span><span class="sxs-lookup"><span data-stu-id="b7ea9-161">Errors in initialization for dependent values are not likely to manifest as a `TypeInitializationException`.</span></span>
4. <span data-ttu-id="b7ea9-162">La API ahora es más fácil de probar.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-162">The API is now easier to test.</span></span>

## <a name="error-management"></a><span data-ttu-id="b7ea9-163">Gestión de errores</span><span class="sxs-lookup"><span data-stu-id="b7ea9-163">Error management</span></span>

<span data-ttu-id="b7ea9-164">La gestión de errores en sistemas grandes es un esfuerzo complejo y matizado, y no hay balas de plata para garantizar que sus sistemas sean tolerantes a fallas y se comporten bien.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-164">Error management in large systems is a complex and nuanced endeavor, and there are no silver bullets in ensuring your systems are fault-tolerant and behave well.</span></span> <span data-ttu-id="b7ea9-165">Las siguientes pautas deben ofrecer orientación para navegar por este difícil espacio.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-165">The following guidelines should offer guidance in navigating this difficult space.</span></span>

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a><span data-ttu-id="b7ea9-166">Representar casos de error y estado ilegal en tipos intrínsecos a tu dominio</span><span class="sxs-lookup"><span data-stu-id="b7ea9-166">Represent error cases and illegal state in types intrinsic to your domain</span></span>

<span data-ttu-id="b7ea9-167">Con [las Uniones Discriminadas](../language-reference/discriminated-unions.md), F- le da la capacidad de representar el estado defectuoso del programa en su sistema de tipos.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-167">With [Discriminated Unions](../language-reference/discriminated-unions.md), F# gives you the ability to represent faulty program state in your type system.</span></span> <span data-ttu-id="b7ea9-168">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-168">For example:</span></span>

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

<span data-ttu-id="b7ea9-169">En este caso, hay tres maneras conocidas de que la retirada de dinero de una cuenta bancaria puede fallar.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-169">In this case, there are three known ways that withdrawing money from a bank account can fail.</span></span> <span data-ttu-id="b7ea9-170">Cada caso de error se representa en el tipo, y por lo tanto se puede tratar de forma segura en todo el programa.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-170">Each error case is represented in the type, and can thus be dealt with safely throughout the program.</span></span>

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

<span data-ttu-id="b7ea9-171">En general, si puede modelar las diferentes formas en que algo puede **fallar** en su dominio, el código de control de errores ya no se trata como algo que debe tratar además del flujo de programa normal.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-171">In general, if you can model the different ways that something can **fail** in your domain, then error handling code is no longer treated as something you must deal with in addition to regular program flow.</span></span> <span data-ttu-id="b7ea9-172">Es simplemente una parte del flujo normal del programa, y no se considera **excepcional.**</span><span class="sxs-lookup"><span data-stu-id="b7ea9-172">It is simply a part of normal program flow, and not considered **exceptional**.</span></span> <span data-ttu-id="b7ea9-173">Hay dos beneficios principales para esto:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-173">There are two primary benefits to this:</span></span>

1. <span data-ttu-id="b7ea9-174">Es más fácil de mantener a medida que el dominio cambia con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-174">It is easier to maintain as your domain changes over time.</span></span>
2. <span data-ttu-id="b7ea9-175">Los casos de error son más fáciles de probar unitariamente.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-175">Error cases are easier to unit test.</span></span>

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a><span data-ttu-id="b7ea9-176">Use excepciones cuando los errores no se puedan representar con tipos</span><span class="sxs-lookup"><span data-stu-id="b7ea9-176">Use exceptions when errors cannot be represented with types</span></span>

<span data-ttu-id="b7ea9-177">No todos los errores se pueden representar en un dominio problemático.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-177">Not all errors can be represented in a problem domain.</span></span> <span data-ttu-id="b7ea9-178">Este tipo de fallas son de naturaleza *excepcional,* de ahí la capacidad de generar y detectar excepciones en F .</span><span class="sxs-lookup"><span data-stu-id="b7ea9-178">These kinds of faults are *exceptional* in nature, hence the ability to raise and catch exceptions in F#.</span></span>

<span data-ttu-id="b7ea9-179">En primer lugar, se recomienda que lea las Directrices de [diseño de excepciones](../../standard/design-guidelines/exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="b7ea9-179">First, it is recommended that you read the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md).</span></span> <span data-ttu-id="b7ea9-180">Estos también son aplicables a F.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-180">These are also applicable to F#.</span></span>

<span data-ttu-id="b7ea9-181">Las principales construcciones disponibles en F- a los efectos de la generación de excepciones deben tenerse en cuenta en el siguiente orden de preferencia:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-181">The main constructs available in F# for the purposes of raising exceptions should be considered in the following order of preference:</span></span>

| <span data-ttu-id="b7ea9-182">Función</span><span class="sxs-lookup"><span data-stu-id="b7ea9-182">Function</span></span> | <span data-ttu-id="b7ea9-183">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7ea9-183">Syntax</span></span> | <span data-ttu-id="b7ea9-184">Propósito</span><span class="sxs-lookup"><span data-stu-id="b7ea9-184">Purpose</span></span> |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | <span data-ttu-id="b7ea9-185">Genera a `System.ArgumentNullException` con el nombre de argumento especificado.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-185">Raises a `System.ArgumentNullException` with the specified argument name.</span></span> |
| `invalidArg` | `invalidArg "argumentName" "message"` | <span data-ttu-id="b7ea9-186">Genera un `System.ArgumentException` con un nombre de argumento y un mensaje especificados.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-186">Raises a `System.ArgumentException` with a specified argument name and message.</span></span> |
| `invalidOp` | `invalidOp "message"` | <span data-ttu-id="b7ea9-187">Genera a `System.InvalidOperationException` con el mensaje especificado.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-187">Raises a `System.InvalidOperationException` with the specified message.</span></span> |
|`raise`| `raise (ExceptionType("message"))` | <span data-ttu-id="b7ea9-188">Mecanismo de uso general para producir excepciones.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-188">General-purpose mechanism for throwing exceptions.</span></span> |
| `failwith` | `failwith "message"` | <span data-ttu-id="b7ea9-189">Genera a `System.Exception` con el mensaje especificado.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-189">Raises a `System.Exception` with the specified message.</span></span> |
| `failwithf` | `failwithf "format string" argForFormatString` | <span data-ttu-id="b7ea9-190">Genera un `System.Exception` mensaje determinado por la cadena de formato y sus entradas.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-190">Raises a `System.Exception` with a message determined by the format string and its inputs.</span></span> |

<span data-ttu-id="b7ea9-191">Utilice `nullArg` `invalidArg` , `invalidOp` y como `ArgumentNullException`mecanismo `ArgumentException` `InvalidOperationException` para lanzar , y cuando corresponda.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-191">Use `nullArg`, `invalidArg` and `invalidOp` as the mechanism to throw `ArgumentNullException`, `ArgumentException` and `InvalidOperationException` when appropriate.</span></span>

<span data-ttu-id="b7ea9-192">Las `failwith` `failwithf` funciones y generalmente deben evitarse `Exception` porque generan el tipo base, no una excepción específica.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-192">The `failwith` and `failwithf` functions should generally be avoided because they raise the base `Exception` type, not a specific exception.</span></span> <span data-ttu-id="b7ea9-193">Según las directrices de diseño de [excepciones,](../../standard/design-guidelines/exceptions.md)desea generar excepciones más específicas cuando pueda.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-193">As per the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md), you want to raise more specific exceptions when you can.</span></span>

### <a name="using-exception-handling-syntax"></a><span data-ttu-id="b7ea9-194">Uso de la sintaxis de control de excepciones</span><span class="sxs-lookup"><span data-stu-id="b7ea9-194">Using exception-handling syntax</span></span>

<span data-ttu-id="b7ea9-195">F- soporta patrones de `try...with` excepción a través de la sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-195">F# supports exception patterns via the `try...with` syntax:</span></span>

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

<span data-ttu-id="b7ea9-196">La conciliación de la funcionalidad para realizar frente a una excepción con la coincidencia de patrones puede ser un poco complicada si desea mantener el código limpio.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-196">Reconciling functionality to perform in the face of an exception with pattern matching can be a bit tricky if you wish to keep the code clean.</span></span> <span data-ttu-id="b7ea9-197">Una de estas maneras de controlar esto es usar [patrones activos](../language-reference/active-patterns.md) como un medio para agrupar la funcionalidad que rodea un caso de error con una excepción en sí.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-197">One such way to handle this is to use [active patterns](../language-reference/active-patterns.md) as a means to group functionality surrounding an error case with an exception itself.</span></span> <span data-ttu-id="b7ea9-198">Por ejemplo, puede estar consumiendo una API que, cuando produce una excepción, encierra información valiosa en los metadatos de la excepción.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-198">For example, you may be consuming an API that, when it throws an exception, encloses valuable information in the exception metadata.</span></span> <span data-ttu-id="b7ea9-199">Desencapsular un valor útil en el cuerpo de la excepción capturada dentro del patrón activo y devolver ese valor puede ser útil en algunas situaciones.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-199">Unwrapping a useful value in the body of the captured exception inside the Active Pattern and returning that value can be helpful in some situations.</span></span>

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a><span data-ttu-id="b7ea9-200">No utilice el control de errores monádicos para reemplazar las excepciones</span><span class="sxs-lookup"><span data-stu-id="b7ea9-200">Do not use monadic error handling to replace exceptions</span></span>

<span data-ttu-id="b7ea9-201">Las excepciones se ven como algo tabú en la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-201">Exceptions are seen as somewhat taboo in functional programming.</span></span> <span data-ttu-id="b7ea9-202">De hecho, las excepciones violan la pureza, por lo que es seguro considerarlas no del todo funcionales.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-202">Indeed, exceptions violate purity, so it's safe to consider them not-quite functional.</span></span> <span data-ttu-id="b7ea9-203">Sin embargo, esto omite la realidad de dónde se debe ejecutar el código y que pueden producirse errores en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-203">However, this ignores the reality of where code must run, and that runtime errors can occur.</span></span> <span data-ttu-id="b7ea9-204">En general, escriba código en la suposición de que la mayoría de las cosas no son puras ni totales, para minimizar sorpresas desagradables.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-204">In general, write code on the assumption that most things are neither pure nor total, to minimize unpleasant surprises.</span></span>

<span data-ttu-id="b7ea9-205">Es importante tener en cuenta las siguientes fortalezas/aspectos principales de las excepciones con respecto a su relevancia y adecuación en el entorno de ejecución de .NET y en el ecosistema entre idiomas en su conjunto:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-205">It is important to consider the following core strengths/aspects of Exceptions with respect to their relevance and appropriateness in the .NET runtime and cross-language ecosystem as a whole:</span></span>

1. <span data-ttu-id="b7ea9-206">Contienen información de diagnóstico detallada, que es muy útil al depurar un problema.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-206">They contain detailed diagnostic information, which is very helpful when debugging an issue.</span></span>
2. <span data-ttu-id="b7ea9-207">El tiempo de ejecución y otros lenguajes .NET los entienden bien.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-207">They are well-understood by the runtime and other .NET languages.</span></span>
3. <span data-ttu-id="b7ea9-208">Pueden reducir la potencia significativa en comparación con el código que hace todo lo posible para *evitar* excepciones mediante la implementación de algún subconjunto de su semántica sobre una base ad hoc.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-208">They can reduce significant boilerplate when compared with code that goes out of its way to *avoid* exceptions by implementing some subset of their semantics on an ad-hoc basis.</span></span>

<span data-ttu-id="b7ea9-209">Este tercer punto es crítico.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-209">This third point is critical.</span></span> <span data-ttu-id="b7ea9-210">Para operaciones complejas no triviales, no usar excepciones puede resultar en el tratamiento de estructuras como esta:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-210">For nontrivial complex operations, failing to use exceptions can result in dealing with structures like this:</span></span>

```fsharp
Result<Result<MyType, string>, string list>
```

<span data-ttu-id="b7ea9-211">Lo que puede conducir fácilmente a código frágil como la coincidencia de patrones en errores "con tipo de cadena":</span><span class="sxs-lookup"><span data-stu-id="b7ea9-211">Which can easily lead to fragile code like pattern matching on "stringly-typed" errors:</span></span>

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

<span data-ttu-id="b7ea9-212">Además, puede ser tentador tragar cualquier excepción en el deseo de una función "simple" que devuelve un tipo "más agradable":</span><span class="sxs-lookup"><span data-stu-id="b7ea9-212">Additionally, it can be tempting to swallow any exception in the desire for a "simple" function that returns a "nicer" type:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

<span data-ttu-id="b7ea9-213">Desafortunadamente, `tryReadAllText` puede producir numerosas excepciones basadas en la infinidad de cosas que pueden suceder en un sistema de archivos, y este código descarta cualquier información sobre lo que realmente podría estar yendo mal en su entorno.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-213">Unfortunately, `tryReadAllText` can throw numerous exceptions based on the myriad of things that can happen on a file system, and this code discards away any information about what might actually be going wrong in your environment.</span></span> <span data-ttu-id="b7ea9-214">Si reemplaza este código con un tipo de resultado, volverá al análisis de mensajes de error "con tipo de cadena":</span><span class="sxs-lookup"><span data-stu-id="b7ea9-214">If you replace this code with a result type, then you're back to "stringly-typed" error message parsing:</span></span>

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

<span data-ttu-id="b7ea9-215">Y colocar el propio `Error` objeto de excepción en el constructor sólo obliga a tratar correctamente con el tipo de excepción en el sitio de llamada en lugar de en la función.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-215">And placing the exception object itself in the `Error` constructor just forces you to properly deal with the exception type at the call site rather than in the function.</span></span> <span data-ttu-id="b7ea9-216">Al hacerlo, se crean excepciones comprobadas, que no pueden ser divertidas de tratar como llamador de una API.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-216">Doing this effectively creates checked exceptions, which are notoriously unfun to deal with as a caller of an API.</span></span>

<span data-ttu-id="b7ea9-217">Una buena alternativa a los ejemplos anteriores es detectar excepciones *específicas* y devolver un valor significativo en el contexto de esa excepción.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-217">A good alternative to the above examples is to catch *specific* exceptions and return a meaningful value in the context of that exception.</span></span> <span data-ttu-id="b7ea9-218">Si modifica `tryReadAllText` la función `None` de la siguiente manera, tiene más significado:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-218">If you modify the `tryReadAllText` function as follows, `None` has more meaning:</span></span>

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

<span data-ttu-id="b7ea9-219">En lugar de funcionar como un catch-all, esta función ahora controlará correctamente el caso cuando no se encontró un archivo y asignará ese significado a una devolución.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-219">Instead of functioning as a catch-all, this function will now properly handle the case when a file was not found and assign that meaning to a return.</span></span> <span data-ttu-id="b7ea9-220">Este valor devuelto puede asignarse a ese caso de error, sin descartar ninguna información contextual ni forzar a los llamadores a tratar un caso que puede no ser relevante en ese momento del código.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-220">This return value can map to that error case, while not discarding any contextual information or forcing callers to deal with a case that may not be relevant at that point in the code.</span></span>

<span data-ttu-id="b7ea9-221">Tipos como `Result<'Success, 'Error>` son adecuados para operaciones básicas en las que no están anidados y los tipos opcionales de F - son perfectos para representar cuando algo podría devolver *algo* o *nada.*</span><span class="sxs-lookup"><span data-stu-id="b7ea9-221">Types such as `Result<'Success, 'Error>` are appropriate for basic operations where they aren't nested, and F# optional types are perfect for representing when something could either return *something* or *nothing*.</span></span> <span data-ttu-id="b7ea9-222">Sin embargo, no sustituyen las excepciones y no deben usarse en un intento de reemplazar excepciones.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-222">They are not a replacement for exceptions, though, and should not be used in an attempt to replace exceptions.</span></span> <span data-ttu-id="b7ea9-223">Más bien, deberían aplicarse con prudencia para abordar aspectos específicos de la política de administración de excepciones y errores de maneras específicas.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-223">Rather, they should be applied judiciously to address specific aspects of exception and error management policy in targeted ways.</span></span>

## <a name="partial-application-and-point-free-programming"></a><span data-ttu-id="b7ea9-224">Aplicación parcial y programación sin puntos</span><span class="sxs-lookup"><span data-stu-id="b7ea9-224">Partial application and point-free programming</span></span>

<span data-ttu-id="b7ea9-225">F- es compatible con la aplicación parcial, y por lo tanto, varias maneras de programar en un estilo sin puntos.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-225">F# supports partial application, and thus, various ways to program in a point-free style.</span></span> <span data-ttu-id="b7ea9-226">Esto puede ser beneficioso para la reutilización de código dentro de un módulo o la implementación de algo, pero no es algo para exponer públicamente.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-226">This can be beneficial for code reuse within a module or the implementation of something, but it is not something to expose publicly.</span></span> <span data-ttu-id="b7ea9-227">En general, la programación sin puntos no es una virtud en sí misma, y puede añadir una barrera cognitiva significativa para las personas que no están inmersas en el estilo.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-227">In general, point-free programming is not a virtue in and of itself, and can add a significant cognitive barrier for people who are not immersed in the style.</span></span>

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a><span data-ttu-id="b7ea9-228">No utilice la aplicación parcial y el curry en las API públicas</span><span class="sxs-lookup"><span data-stu-id="b7ea9-228">Do not use partial application and currying in public APIs</span></span>

<span data-ttu-id="b7ea9-229">Con poca excepción, el uso de la aplicación parcial en las API públicas puede ser confuso para los consumidores.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-229">With little exception, the use of partial application in public APIs can be confusing for consumers.</span></span> <span data-ttu-id="b7ea9-230">Por `let`lo general, los valores -bound en el código de F son **valores,** no valores de **función.**</span><span class="sxs-lookup"><span data-stu-id="b7ea9-230">Usually, `let`-bound values in F# code are **values**, not **function values**.</span></span> <span data-ttu-id="b7ea9-231">Mezclar valores y valores de función puede resultar en guardar un pequeño número de líneas de código `>>` a cambio de un poco de sobrecarga cognitiva, especialmente si se combina con operadores como para componer funciones.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-231">Mixing together values and function values can result in saving a small number of lines of code in exchange for quite a bit of cognitive overhead, especially if combined with operators such as `>>` to compose functions.</span></span>

### <a name="consider-the-tooling-implications-for-point-free-programming"></a><span data-ttu-id="b7ea9-232">Considere las implicaciones de las herramientas para la programación sin puntos</span><span class="sxs-lookup"><span data-stu-id="b7ea9-232">Consider the tooling implications for point-free programming</span></span>

<span data-ttu-id="b7ea9-233">Las funciones curradas no etiquetan sus argumentos.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-233">Curried functions do not label their arguments.</span></span> <span data-ttu-id="b7ea9-234">Esto tiene implicaciones de herramientas.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-234">This has tooling implications.</span></span> <span data-ttu-id="b7ea9-235">Considere las dos funciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-235">Consider the following two functions:</span></span>

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

<span data-ttu-id="b7ea9-236">Ambas son funciones `funcWithApplication` válidas, pero es una función curried.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-236">Both are valid functions, but `funcWithApplication` is a curried function.</span></span> <span data-ttu-id="b7ea9-237">Cuando pasa el cursor sobre sus tipos en un editor, verá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-237">When you hover over their types in an editor, you see this:</span></span>

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

<span data-ttu-id="b7ea9-238">En el sitio de llamada, la información sobre herramientas de herramientas como `string` `int` Visual Studio no le proporcionará información significativa sobre lo que realmente representan los tipos de entrada y.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-238">At the call site, tooltips in tooling such as Visual Studio will not give you meaningful information as to what the `string` and `int` input types actually represent.</span></span>

<span data-ttu-id="b7ea9-239">Si encuentra código sin `funcWithApplication` puntos como ese es consumible públicamente, se recomienda hacer una expansión completa para que las herramientas puedan obtener nombres significativos para los argumentos.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-239">If you encounter point-free code like `funcWithApplication` that is publicly consumable, it is recommended to do a full η-expansion so that tooling can pick up on meaningful names for arguments.</span></span>

<span data-ttu-id="b7ea9-240">Además, depurar código sin puntos puede ser difícil, si no imposible.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-240">Furthermore, debugging point-free code can be challenging, if not impossible.</span></span> <span data-ttu-id="b7ea9-241">Las herramientas de depuración se basan `let` en valores enlazados a nombres (por ejemplo, enlaces) para que pueda inspeccionar los valores intermedios a mitad de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-241">Debugging tools rely on values bound to names (for example, `let` bindings) so that you can inspect intermediate values midway through execution.</span></span> <span data-ttu-id="b7ea9-242">Cuando el código no tiene valores que inspeccionar, no hay nada que depurar.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-242">When your code has no values to inspect, there is nothing to debug.</span></span> <span data-ttu-id="b7ea9-243">En el futuro, las herramientas de depuración pueden evolucionar para sintetizar estos valores en función de las rutas ejecutadas anteriormente, pero no es una buena idea cubrir sus apuestas sobre la funcionalidad de depuración *potencial.*</span><span class="sxs-lookup"><span data-stu-id="b7ea9-243">In the future, debugging tools may evolve to synthesize these values based on previously executed paths, but it's not a good idea to hedge your bets on *potential* debugging functionality.</span></span>

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a><span data-ttu-id="b7ea9-244">Considere la aplicación parcial como una técnica para reducir la placa de caldera interna</span><span class="sxs-lookup"><span data-stu-id="b7ea9-244">Consider partial application as a technique to reduce internal boilerplate</span></span>

<span data-ttu-id="b7ea9-245">A diferencia del punto anterior, la aplicación parcial es una herramienta maravillosa para reducir la placa reutilizable dentro de una aplicación o los internos más profundos de una API.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-245">In contrast to the previous point, partial application is a wonderful tool for reducing boilerplate inside of an application or the deeper internals of an API.</span></span> <span data-ttu-id="b7ea9-246">Puede ser útil para la prueba unitaria de la implementación de API más complicadas, donde la placa reutilizable es a menudo un dolor para tratar.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-246">It can be helpful for unit testing the implementation of more complicated APIs, where boilerplate is often a pain to deal with.</span></span> <span data-ttu-id="b7ea9-247">Por ejemplo, el código siguiente muestra cómo puede lograr lo que la mayoría de los marcos de simulación le proporcionan sin tomar una dependencia externa en dicho marco de trabajo y tener que aprender una API a medida relacionada.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-247">For example, the following code shows how you can accomplish what most mocking frameworks give you without taking an external dependency on such a framework and having to learn a related bespoke API.</span></span>

<span data-ttu-id="b7ea9-248">Por ejemplo, considere la siguiente topografía de solución:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-248">For example, consider the following solution topography:</span></span>

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

<span data-ttu-id="b7ea9-249">`ImplementationLogic.fsproj`podría exponer código como:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-249">`ImplementationLogic.fsproj` might expose code such as:</span></span>

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member _.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

<span data-ttu-id="b7ea9-250">Las `Transactions.doTransaction` pruebas `ImplementationLogic.Tests.fsproj` unitarias son fáciles:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-250">Unit testing `Transactions.doTransaction` in `ImplementationLogic.Tests.fsproj` is easy:</span></span>

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

<span data-ttu-id="b7ea9-251">Aplicar parcialmente `doTransaction` con un objeto de contexto de simulación le permite llamar a la función en todas las pruebas unitarias sin necesidad de construir un contexto simulado cada vez:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-251">Partially applying `doTransaction` with a mocking context object lets you call the function in all of your unit tests without needing to construct a mocked context each time:</span></span>

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

<span data-ttu-id="b7ea9-252">Esta técnica no se debe aplicar universalmente a toda la base de código, pero es una buena manera de reducir la placa de caldera para los internos complicados y las pruebas unitarias de esos internos.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-252">This technique should not be universally applied to your entire codebase, but it is a good way to reduce boilerplate for complicated internals and unit testing those internals.</span></span>

## <a name="access-control"></a><span data-ttu-id="b7ea9-253">Control de acceso</span><span class="sxs-lookup"><span data-stu-id="b7ea9-253">Access control</span></span>

<span data-ttu-id="b7ea9-254">F- tiene varias opciones para [el control](../language-reference/access-control.md)de acceso , heredadas de lo que está disponible en el tiempo de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-254">F# has multiple options for [Access control](../language-reference/access-control.md), inherited from what is available in the .NET runtime.</span></span> <span data-ttu-id="b7ea9-255">Estos no son sólo utilizables para los tipos - se puede utilizar para las funciones, también.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-255">These are not just usable for types - you can use them for functions, too.</span></span>

* <span data-ttu-id="b7ea9-256">Prefiere los`public` no tipos y miembros hasta que necesite que sean consumibles públicamente.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-256">Prefer non-`public` types and members until you need them to be publicly consumable.</span></span> <span data-ttu-id="b7ea9-257">Esto también minimiza lo que los consumidores se aparejan.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-257">This also minimizes what consumers couple to.</span></span>
* <span data-ttu-id="b7ea9-258">Esfuércese por `private`mantener todas las funciones de la aplicación auxiliar.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-258">Strive to keep all helper functionality `private`.</span></span>
* <span data-ttu-id="b7ea9-259">Considere el `[<AutoOpen>]` uso de en un módulo privado de funciones auxiliares si se convierten en numerosas.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-259">Consider the use of `[<AutoOpen>]` on a private module of helper functions if they become numerous.</span></span>

## <a name="type-inference-and-generics"></a><span data-ttu-id="b7ea9-260">Inferencia de tipos y genéricos</span><span class="sxs-lookup"><span data-stu-id="b7ea9-260">Type inference and generics</span></span>

<span data-ttu-id="b7ea9-261">La inferencia de tipo puede ahorrarle escribir una gran cantidad de reutilizable.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-261">Type inference can save you from typing a lot of boilerplate.</span></span> <span data-ttu-id="b7ea9-262">Además, la generalización automática en el compilador de F - puede ayudarle a escribir código más genérico sin casi ningún esfuerzo adicional por su parte.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-262">And automatic generalization in the F# compiler can help you write more generic code with almost no extra effort on your part.</span></span> <span data-ttu-id="b7ea9-263">Sin embargo, estas características no son universalmente buenas.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-263">However, these features are not universally good.</span></span>

* <span data-ttu-id="b7ea9-264">Considere la posibilidad de etiquetar nombres de argumentos con tipos explícitos en LAS API públicas y no se base en la inferencia de tipos para ello.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-264">Consider labeling argument names with explicit types in public APIs and do not rely on type inference for this.</span></span>

    <span data-ttu-id="b7ea9-265">La razón de esto es que **debe** tener el control de la forma de la API, no del compilador.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-265">The reason for this is that **you** should be in control of the shape of your API, not the compiler.</span></span> <span data-ttu-id="b7ea9-266">Aunque el compilador puede hacer un trabajo excelente en la inferir tipos por usted, es posible tener la forma del cambio de API si los internos en los que se basa han cambiado los tipos.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-266">Although the compiler can do a fine job at inferring types for you, it is possible to have the shape of your API change if the internals it relies on have changed types.</span></span> <span data-ttu-id="b7ea9-267">Esto puede ser lo que desea, pero casi con seguridad resultará en un cambio de API de última hora que los consumidores intermedios tendrán que lidiar con.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-267">This may be what you want, but it will almost certainly result in a breaking API change that downstream consumers will then have to deal with.</span></span> <span data-ttu-id="b7ea9-268">En su lugar, si controla explícitamente la forma de la API pública, puede controlar estos cambios importantes.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-268">Instead, if you explicitly control the shape of your public API, then you can control these breaking changes.</span></span> <span data-ttu-id="b7ea9-269">En términos de DDD, esto se puede considerar como una capa anticorrupción.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-269">In DDD terms, this can be thought of as an Anti-corruption layer.</span></span>

* <span data-ttu-id="b7ea9-270">Considere la posibilidad de dar un nombre significativo a los argumentos genéricos.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-270">Consider giving a meaningful name to your generic arguments.</span></span>

    <span data-ttu-id="b7ea9-271">A menos que escriba código verdaderamente genérico que no sea específico de un dominio determinado, un nombre significativo puede ayudar a otros programadores a comprender el dominio en el que están trabajando.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-271">Unless you are writing truly generic code that is not specific to a particular domain, a meaningful name can help other programmers understanding the domain they're working in.</span></span> <span data-ttu-id="b7ea9-272">Por ejemplo, un `'Document` parámetro de tipo denominado en el contexto de la interacción con una base de datos de documentos hace que sea más claro que la función o el miembro con el que está trabajando puedan aceptar tipos de documentos genéricos.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-272">For example, a type parameter named `'Document` in the context of interacting with a document database makes it clearer that generic document types can be accepted by the function or member you are working with.</span></span>

* <span data-ttu-id="b7ea9-273">Considere la posibilidad de nombrar parámetros de tipo genérico con PascalCase.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-273">Consider naming generic type parameters with PascalCase.</span></span>

    <span data-ttu-id="b7ea9-274">Esta es la forma general de hacer las cosas en .NET, por lo que se recomienda usar PascalCase en lugar de snake_case o camelCase.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-274">This is the general way to do things in .NET, so it's recommended that you use PascalCase rather than snake_case or camelCase.</span></span>

<span data-ttu-id="b7ea9-275">Por último, la generalización automática no siempre es una bendición para las personas que son nuevas en F o un código base grande.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-275">Finally, automatic generalization is not always a boon for people who are new to F# or a large codebase.</span></span> <span data-ttu-id="b7ea9-276">Hay sobrecarga cognitiva en el uso de componentes que son genéricos.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-276">There is cognitive overhead in using components that are generic.</span></span> <span data-ttu-id="b7ea9-277">Además, si las funciones generalizadas automáticamente no se utilizan con diferentes tipos de entrada (por no hablar si están destinadas a ser utilizadas como tales), entonces no hay ningún beneficio real para que sean genéricas en ese momento.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-277">Furthermore, if automatically generalized functions are not used with different input types (let alone if they are intended to be used as such), then there is no real benefit to them being generic at that point in time.</span></span> <span data-ttu-id="b7ea9-278">Considere siempre si el código que está escribiendo realmente se beneficiará de ser genérico.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-278">Always consider if the code you are writing will actually benefit from being generic.</span></span>

## <a name="performance"></a><span data-ttu-id="b7ea9-279">Rendimiento</span><span class="sxs-lookup"><span data-stu-id="b7ea9-279">Performance</span></span>

### <a name="prefer-structs-for-small-data-types"></a><span data-ttu-id="b7ea9-280">Prefiere estructuras para tipos de datos pequeños</span><span class="sxs-lookup"><span data-stu-id="b7ea9-280">Prefer structs for small data types</span></span>

<span data-ttu-id="b7ea9-281">El uso de estructuras (también denominadatipos de valor) a menudo puede dar lugar a un mayor rendimiento para algunos códigos, ya que normalmente evita la asignación de objetos.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-281">Using structs (also called Value Types) can often result in higher performance for some code because it typically avoids allocating objects.</span></span> <span data-ttu-id="b7ea9-282">Sin embargo, las estructuras no siempre son un botón de "ir más rápido": si el tamaño de los datos en una estructura supera los 16 bytes, copiar los datos a menudo puede dar lugar a más tiempo de CPU que a usar un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-282">However, structs are not always a "go faster" button: if the size of the data in a struct exceeds 16 bytes, copying the data can often result in more CPU time spend than using a reference type.</span></span>

<span data-ttu-id="b7ea9-283">Para determinar si debe utilizar una estructura, tenga en cuenta las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-283">To determine if you should use a struct, consider the following conditions:</span></span>

- <span data-ttu-id="b7ea9-284">Si el tamaño de los datos es de 16 bytes o menos.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-284">If the size of your data is 16 bytes or smaller.</span></span>
- <span data-ttu-id="b7ea9-285">Si es probable que tenga muchos de estos tipos de datos residentes en la memoria en un programa en ejecución.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-285">If you're likely to have many of these data types resident in memory in a running program.</span></span>

<span data-ttu-id="b7ea9-286">Si se aplica la primera condición, generalmente debe usar una estructura.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-286">If the first condition applies, you should generally use a struct.</span></span> <span data-ttu-id="b7ea9-287">Si ambos se aplican, casi siempre debe utilizar un struct.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-287">If both apply, you should almost always use a struct.</span></span> <span data-ttu-id="b7ea9-288">Puede haber algunos casos en los que se aplican las condiciones anteriores, pero el uso de una estructura no es mejor o peor que usar un tipo de referencia, pero es probable que sean raros.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-288">There may be some cases where the previous conditions apply, but using a struct is no better or worse than using a reference type, but they are likely to be rare.</span></span> <span data-ttu-id="b7ea9-289">Sin embargo, es importante medir siempre al realizar cambios como este, y no operar con suposición o intuición.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-289">It's important to always measure when making changes like this, though, and not operate on assumption or intuition.</span></span>

#### <a name="prefer-struct-tuples-when-grouping-small-value-types"></a><span data-ttu-id="b7ea9-290">Prefiere tuplas de estructura al agrupar tipos de valores pequeños</span><span class="sxs-lookup"><span data-stu-id="b7ea9-290">Prefer struct tuples when grouping small value types</span></span>

<span data-ttu-id="b7ea9-291">Considere las dos funciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-291">Consider the following two functions:</span></span>

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

<span data-ttu-id="b7ea9-292">Al comparar estas funciones con una herramienta de benchmarking estadística `runWithStructTuple` como [BenchmarkDotNet,](https://benchmarkdotnet.org/)encontrará que la función que utiliza tuplas struct se ejecuta un 40% más rápido y no asigna memoria.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-292">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that the `runWithStructTuple` function that uses struct tuples runs 40% faster and allocates no memory.</span></span>

<span data-ttu-id="b7ea9-293">Sin embargo, estos resultados no siempre serán el caso en su propio código.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-293">However, these results won't always be the case in your own code.</span></span> <span data-ttu-id="b7ea9-294">Si marca una `inline`función como , el código que usa tuplas de referencia puede obtener algunas optimizaciones adicionales, o el código que asignaría simplemente podría optimizarse.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-294">If you mark a function as `inline`, code that uses reference tuples may get some additional optimizations, or code that would allocate could simply be optimized away.</span></span> <span data-ttu-id="b7ea9-295">Siempre debe medir los resultados cuando se trata de rendimiento, y nunca operar en base a suposición o intuición.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-295">You should always measure results whenever performance is concerned, and never operate based on assumption or intuition.</span></span>

#### <a name="prefer-struct-records-when-the-data-type-is-small"></a><span data-ttu-id="b7ea9-296">Prefiere registros de estructura cuando el tipo de datos es pequeño</span><span class="sxs-lookup"><span data-stu-id="b7ea9-296">Prefer struct records when the data type is small</span></span>

<span data-ttu-id="b7ea9-297">La regla general descrita anteriormente también se mantiene para los tipos de [registro de F](../language-reference/records.md).</span><span class="sxs-lookup"><span data-stu-id="b7ea9-297">The rule of thumb described earlier also holds for [F# record types](../language-reference/records.md).</span></span> <span data-ttu-id="b7ea9-298">Tenga en cuenta los siguientes tipos de datos y funciones que los procesan:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-298">Consider the following data types and functions that process them:</span></span>

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

<span data-ttu-id="b7ea9-299">Esto es similar al código de tupla anterior, pero esta vez el ejemplo utiliza registros y una función interna insertada.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-299">This is similar to the previous tuple code, but this time the example uses records and an inlined inner function.</span></span>

<span data-ttu-id="b7ea9-300">Al comparar estas funciones con una herramienta de benchmarking estadística `processStructPoint` como [BenchmarkDotNet,](https://benchmarkdotnet.org/)encontrará que se ejecuta casi un 60% más rápido y no asigna nada en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-300">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that `processStructPoint` runs nearly 60% faster and allocates nothing on the managed heap.</span></span>

#### <a name="prefer-struct-discriminated-unions-when-the-data-type-is-small"></a><span data-ttu-id="b7ea9-301">Prefiere las uniones discriminadas de estructura cuando el tipo de datos es pequeño</span><span class="sxs-lookup"><span data-stu-id="b7ea9-301">Prefer struct discriminated unions when the data type is small</span></span>

<span data-ttu-id="b7ea9-302">Las observaciones anteriores sobre el rendimiento con tuplas y registros de estructura también se mantienen para [las Uniones Discriminadas](../language-reference/discriminated-unions.md)de F.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-302">The previous observations about performance with struct tuples and records also holds for [F# Discriminated Unions](../language-reference/discriminated-unions.md).</span></span> <span data-ttu-id="b7ea9-303">Observe el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-303">Consider the following code:</span></span>

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

<span data-ttu-id="b7ea9-304">Es común definir uniones discriminadas de un solo caso como esta para el modelado de dominios.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-304">It's common to define single-case Discriminated Unions like this for domain modeling.</span></span> <span data-ttu-id="b7ea9-305">Al comparar estas funciones con una herramienta de benchmarking estadística `structReverseName` como [BenchmarkDotNet,](https://benchmarkdotnet.org/)encontrará que se ejecuta aproximadamente un 25% más rápido que `reverseName` para cadenas pequeñas.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-305">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that `structReverseName` runs about 25% faster than `reverseName` for small strings.</span></span> <span data-ttu-id="b7ea9-306">Para cadenas grandes, ambas funcionan aproximadamente igual.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-306">For large strings, both perform about the same.</span></span> <span data-ttu-id="b7ea9-307">Por lo tanto, en este caso, siempre es preferible usar una estructura.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-307">So, in this case, it's always preferable to use a struct.</span></span> <span data-ttu-id="b7ea9-308">Como se mencionó anteriormente, medir siempre y no operar en supuestos o intuición.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-308">As previously mentioned, always measure and do not operate on assumptions or intuition.</span></span>

<span data-ttu-id="b7ea9-309">Aunque en el ejemplo anterior se mostró que una unión discriminada de estructura tenía un mejor rendimiento, es común tener uniones discriminadas más grandes al modelar un dominio.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-309">Although the previous example showed that a struct Discriminated Union yielded better performance, it is common to have larger Discriminated Unions when modeling a domain.</span></span> <span data-ttu-id="b7ea9-310">Los tipos de datos más grandes como ese pueden no funcionar tan bien si son estructuras en función de las operaciones en ellos, ya que podría haber más copia.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-310">Larger data types like that may not perform as well if they are structs depending on the operations on them, since more copying could be involved.</span></span>

### <a name="functional-programming-and-mutation"></a><span data-ttu-id="b7ea9-311">Programación funcional y mutación</span><span class="sxs-lookup"><span data-stu-id="b7ea9-311">Functional programming and mutation</span></span>

<span data-ttu-id="b7ea9-312">Los valores de F - son inmutables de forma predeterminada, lo que le permite evitar ciertas clases de errores (especialmente aquellos que implican simultaneidad y paralelismo).</span><span class="sxs-lookup"><span data-stu-id="b7ea9-312">F# values are immutable by default, which allows you to avoid certain classes of bugs (especially those involving concurrency and parallelism).</span></span> <span data-ttu-id="b7ea9-313">Sin embargo, en ciertos casos, con el fin de lograr una eficiencia óptima (o incluso razonable) del tiempo de ejecución o de las asignaciones de memoria, se puede implementar mejor un intervalo de trabajo mediante el uso de la mutación in situ del estado.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-313">However, in certain cases, in order to achieve optimal (or even reasonable) efficiency of execution time or memory allocations, a span of work may best be implemented by using in-place mutation of state.</span></span> <span data-ttu-id="b7ea9-314">Esto es posible de forma opcional con `mutable` F con la palabra clave.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-314">This is possible in an opt-in basis with F# with the `mutable` keyword.</span></span>

<span data-ttu-id="b7ea9-315">El `mutable` uso de f- puede estar en desacuerdo con la pureza funcional.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-315">Use of `mutable` in F# may feel at odds with functional purity.</span></span> <span data-ttu-id="b7ea9-316">Esto es comprensible, pero la pureza funcional en todas partes puede estar en desacuerdo con los objetivos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-316">This is understandable, but functional purity everywhere can be at odds with performance goals.</span></span> <span data-ttu-id="b7ea9-317">Un compromiso es encapsular la mutación de tal manera que los llamadores no tengan que preocuparse por lo que sucede cuando llaman a una función.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-317">A compromise is to encapsulate mutation such that callers need not care about what happens when they call a function.</span></span> <span data-ttu-id="b7ea9-318">Esto le permite escribir una interfaz funcional sobre una implementación basada en mutaciones para el código crítico para el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-318">This allows you to write a functional interface over a mutation-based implementation for performance-critical code.</span></span>

#### <a name="wrap-mutable-code-in-immutable-interfaces"></a><span data-ttu-id="b7ea9-319">Envolver código mutable en interfaces inmutables</span><span class="sxs-lookup"><span data-stu-id="b7ea9-319">Wrap mutable code in immutable interfaces</span></span>

<span data-ttu-id="b7ea9-320">Con la transparencia referencial como objetivo, es fundamental escribir código que no exponga el vientre mutable de las funciones críticas para el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-320">With referential transparency as a goal, it is critical to write code that does not expose the mutable underbelly of performance-critical functions.</span></span> <span data-ttu-id="b7ea9-321">Por ejemplo, el código `Array.contains` siguiente implementa la función en la biblioteca principal de F.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-321">For example, the following code implements the `Array.contains` function in the F# core library:</span></span>

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

<span data-ttu-id="b7ea9-322">Llamar a esta función varias veces no cambia la matriz subyacente, ni requiere que mantenga ningún estado mutable al consumirla.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-322">Calling this function multiple times does not change the underlying array, nor does it require you to maintain any mutable state in consuming it.</span></span> <span data-ttu-id="b7ea9-323">Es referencialmente transparente, a pesar de que casi todas las líneas de código que contiene utilizan mutaciones.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-323">It is referentially transparent, even though almost every line of code within it uses mutation.</span></span>

#### <a name="consider-encapsulating-mutable-data-in-classes"></a><span data-ttu-id="b7ea9-324">Considere la posibilidad de encapsular datos mutables en clases</span><span class="sxs-lookup"><span data-stu-id="b7ea9-324">Consider encapsulating mutable data in classes</span></span>

<span data-ttu-id="b7ea9-325">En el ejemplo anterior se utilizaba una sola función para encapsular operaciones mediante datos mutables.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-325">The previous example used a single function to encapsulate operations using mutable data.</span></span> <span data-ttu-id="b7ea9-326">Esto no siempre es suficiente para conjuntos de datos más complejos.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-326">This is not always sufficient for more complex sets of data.</span></span> <span data-ttu-id="b7ea9-327">Considere los siguientes conjuntos de funciones:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-327">Consider the following sets of functions:</span></span>

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

<span data-ttu-id="b7ea9-328">Este código es performant, pero expone la estructura de datos basada en mutaciones que los llamadores son responsables de mantener.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-328">This code is performant, but it exposes the mutation-based data structure that callers are responsible for maintaining.</span></span> <span data-ttu-id="b7ea9-329">Esto se puede ajustar dentro de una clase sin miembros subyacentes que puedan cambiar:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-329">This can be wrapped inside of a class with no underlying members that can change:</span></span>

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

<span data-ttu-id="b7ea9-330">`Closure1Table`encapsula la estructura de datos subyacente basada en mutaciones, por lo que no obliga a los llamadores a mantener la estructura de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-330">`Closure1Table` encapsulates the underlying mutation-based data structure, thereby not forcing callers to maintain the underlying data structure.</span></span> <span data-ttu-id="b7ea9-331">Las clases son una forma eficaz de encapsular datos y rutinas basadas en mutaciones sin exponer los detalles a las personas que llaman.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-331">Classes are a powerful way to encapsulate data and routines that are mutation-based without exposing the details to callers.</span></span>

#### <a name="prefer-let-mutable-to-reference-cells"></a><span data-ttu-id="b7ea9-332">Prefiere `let mutable` hacer referencia a las celdas</span><span class="sxs-lookup"><span data-stu-id="b7ea9-332">Prefer `let mutable` to reference cells</span></span>

<span data-ttu-id="b7ea9-333">Las celdas de referencia son una forma de representar la referencia a un valor en lugar del propio valor.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-333">Reference cells are a way to represent the reference to a value rather than the value itself.</span></span> <span data-ttu-id="b7ea9-334">Aunque se pueden usar para código crítico para el rendimiento, no se recomiendan.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-334">Although they can be used for performance-critical code, they are not recommended.</span></span> <span data-ttu-id="b7ea9-335">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-335">Consider the following example:</span></span>

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

<span data-ttu-id="b7ea9-336">El uso de una celda de referencia ahora "contamina" todo el código subsiguiente con tener que desreferenciar y volver a hacer referencia a los datos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-336">The use of a reference cell now "pollutes" all subsequent code with having to dereference and re-reference the underlying data.</span></span> <span data-ttu-id="b7ea9-337">En su `let mutable`lugar, considere:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-337">Instead, consider `let mutable`:</span></span>

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

<span data-ttu-id="b7ea9-338">Aparte del único punto de mutación en el centro de `acc` la expresión lambda, todo el demás código `let`que toca puede hacerlo de una manera que no es diferente al uso de un valor inmutable enlazado normal.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-338">Aside from the single point of mutation in the middle of the lambda expression, all other code that touches `acc` can do so in a manner that is no different to the usage of a normal `let`-bound immutable value.</span></span> <span data-ttu-id="b7ea9-339">Esto hará que sea más fácil cambiar con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-339">This will make it easier to change over time.</span></span>

## <a name="object-programming"></a><span data-ttu-id="b7ea9-340">Programación de objetos</span><span class="sxs-lookup"><span data-stu-id="b7ea9-340">Object programming</span></span>

<span data-ttu-id="b7ea9-341">F- tiene soporte completo para objetos y conceptos orientados a objetos (OO).</span><span class="sxs-lookup"><span data-stu-id="b7ea9-341">F# has full support for objects and object-oriented (OO) concepts.</span></span> <span data-ttu-id="b7ea9-342">Aunque muchos conceptos de OO son potentes y útiles, no todos ellos son ideales para usar.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-342">Although many OO concepts are powerful and useful, not all of them are ideal to use.</span></span> <span data-ttu-id="b7ea9-343">Las siguientes listas ofrecen orientación sobre categorías de características de OO a un nivel alto.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-343">The following lists offer guidance on categories of OO features at a high level.</span></span>

<span data-ttu-id="b7ea9-344">**Considere el uso de estas características en muchas situaciones:**</span><span class="sxs-lookup"><span data-stu-id="b7ea9-344">**Consider using these features in many situations:**</span></span>

* <span data-ttu-id="b7ea9-345">Notación`x.Length`de puntos ( )</span><span class="sxs-lookup"><span data-stu-id="b7ea9-345">Dot notation (`x.Length`)</span></span>
* <span data-ttu-id="b7ea9-346">Miembros de la instancia</span><span class="sxs-lookup"><span data-stu-id="b7ea9-346">Instance members</span></span>
* <span data-ttu-id="b7ea9-347">Constructores implícitos</span><span class="sxs-lookup"><span data-stu-id="b7ea9-347">Implicit constructors</span></span>
* <span data-ttu-id="b7ea9-348">Miembros estáticos</span><span class="sxs-lookup"><span data-stu-id="b7ea9-348">Static members</span></span>
* <span data-ttu-id="b7ea9-349">Notación del`arr.[x]`indexador ( )</span><span class="sxs-lookup"><span data-stu-id="b7ea9-349">Indexer notation (`arr.[x]`)</span></span>
* <span data-ttu-id="b7ea9-350">Argumentos con nombre y opcionales</span><span class="sxs-lookup"><span data-stu-id="b7ea9-350">Named and Optional arguments</span></span>
* <span data-ttu-id="b7ea9-351">Interfaces e implementaciones de interfaces</span><span class="sxs-lookup"><span data-stu-id="b7ea9-351">Interfaces and interface implementations</span></span>

<span data-ttu-id="b7ea9-352">**No busques estas funciones primero, pero aplicalas juiciosamente cuando sean convenientes para resolver un problema:**</span><span class="sxs-lookup"><span data-stu-id="b7ea9-352">**Don't reach for these features first, but do judiciously apply them when they are convenient to solve a problem:**</span></span>

* <span data-ttu-id="b7ea9-353">Sobrecarga de métodos</span><span class="sxs-lookup"><span data-stu-id="b7ea9-353">Method overloading</span></span>
* <span data-ttu-id="b7ea9-354">Datos mutables encapsulados</span><span class="sxs-lookup"><span data-stu-id="b7ea9-354">Encapsulated mutable data</span></span>
* <span data-ttu-id="b7ea9-355">Operadores en tipos</span><span class="sxs-lookup"><span data-stu-id="b7ea9-355">Operators on types</span></span>
* <span data-ttu-id="b7ea9-356">Propiedades automáticas</span><span class="sxs-lookup"><span data-stu-id="b7ea9-356">Auto properties</span></span>
* <span data-ttu-id="b7ea9-357">Implementación `IDisposable` y`IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="b7ea9-357">Implementing `IDisposable` and `IEnumerable`</span></span>
* <span data-ttu-id="b7ea9-358">Extensiones de tipo</span><span class="sxs-lookup"><span data-stu-id="b7ea9-358">Type extensions</span></span>
* <span data-ttu-id="b7ea9-359">Eventos</span><span class="sxs-lookup"><span data-stu-id="b7ea9-359">Events</span></span>
* <span data-ttu-id="b7ea9-360">Estructuras</span><span class="sxs-lookup"><span data-stu-id="b7ea9-360">Structs</span></span>
* <span data-ttu-id="b7ea9-361">Delegados</span><span class="sxs-lookup"><span data-stu-id="b7ea9-361">Delegates</span></span>
* <span data-ttu-id="b7ea9-362">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="b7ea9-362">Enums</span></span>

<span data-ttu-id="b7ea9-363">**Por lo general, evite estas características a menos que deba utilizarlas:**</span><span class="sxs-lookup"><span data-stu-id="b7ea9-363">**Generally avoid these features unless you must use them:**</span></span>

* <span data-ttu-id="b7ea9-364">Jerarquías de tipos basadas en herencia y herencia de implementación</span><span class="sxs-lookup"><span data-stu-id="b7ea9-364">Inheritance-based type hierarchies and implementation inheritance</span></span>
* <span data-ttu-id="b7ea9-365">Nulls y`Unchecked.defaultof<_>`</span><span class="sxs-lookup"><span data-stu-id="b7ea9-365">Nulls and `Unchecked.defaultof<_>`</span></span>

### <a name="prefer-composition-over-inheritance"></a><span data-ttu-id="b7ea9-366">Prefiere la composición sobre la herencia</span><span class="sxs-lookup"><span data-stu-id="b7ea9-366">Prefer composition over inheritance</span></span>

<span data-ttu-id="b7ea9-367">[La composición sobre](https://en.wikipedia.org/wiki/Composition_over_inheritance) la herencia es un modismo de larga data al que puede adherirse un buen código de F.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-367">[Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance) is a long-standing idiom that good F# code can adhere to.</span></span> <span data-ttu-id="b7ea9-368">El principio fundamental es que no debe exponer una clase base y forzar a los llamadores a heredar de esa clase base para obtener funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-368">The fundamental principle is that you should not expose a base class and force callers to inherit from that base class to get functionality.</span></span>

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a><span data-ttu-id="b7ea9-369">Utilice expresiones de objeto para implementar interfaces si no necesita una clase</span><span class="sxs-lookup"><span data-stu-id="b7ea9-369">Use object expressions to implement interfaces if you don't need a class</span></span>

<span data-ttu-id="b7ea9-370">[Las expresiones](../language-reference/object-expressions.md) de objeto le permiten implementar interfaces sobre la marcha, enlazando la interfaz implementada a un valor sin necesidad de hacerlo dentro de una clase.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-370">[Object Expressions](../language-reference/object-expressions.md) allow you to implement interfaces on the fly, binding the implemented interface to a value without needing to do so inside of a class.</span></span> <span data-ttu-id="b7ea9-371">Esto es conveniente, especialmente si _solo_ necesita implementar la interfaz y no tiene necesidad de una clase completa.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-371">This is convenient, especially if you _only_ need to implement the interface and have no need for a full class.</span></span>

<span data-ttu-id="b7ea9-372">Por ejemplo, aquí está el código que se ejecuta en [Ionide](http://ionide.io/) para proporcionar una acción de `open` corrección de código si ha agregado un símbolo para el que no tiene una instrucción:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-372">For example, here is the code that is run in [Ionide](http://ionide.io/) to provide a code fix action if you've added a symbol that you don't have an `open` statement for:</span></span>

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

<span data-ttu-id="b7ea9-373">Dado que no hay necesidad de una clase al interactuar con la API de visual studio Code, las expresiones de objeto son una herramienta ideal para esto.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-373">Because there is no need for a class when interacting with the Visual Studio Code API, Object Expressions are an ideal tool for this.</span></span> <span data-ttu-id="b7ea9-374">También son valiosos para las pruebas unitarias, cuando se desea extraer una interfaz con rutinas de prueba de una manera ad hoc.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-374">They are also valuable for unit testing, when you want to stub out an interface with test routines in an ad hoc manner.</span></span>

## <a name="consider-type-abbreviations-to-shorten-signatures"></a><span data-ttu-id="b7ea9-375">Considere las abreviaturas de tipo para acortar las firmas</span><span class="sxs-lookup"><span data-stu-id="b7ea9-375">Consider Type Abbreviations to shorten signatures</span></span>

<span data-ttu-id="b7ea9-376">[Las abreviaturas](../language-reference/type-abbreviations.md) de tipo son una forma cómoda de asignar una etiqueta a otro tipo, como una firma de función o un tipo más complejo.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-376">[Type Abbreviations](../language-reference/type-abbreviations.md) are a convenient way to assign a label to another type, such as a function signature or a more complex type.</span></span> <span data-ttu-id="b7ea9-377">Por ejemplo, el siguiente alias asigna una etiqueta a lo que se necesita para definir un cálculo con [CNTK,](https://docs.microsoft.com/cognitive-toolkit/)una biblioteca de aprendizaje profundo:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-377">For example, the following alias assigns a label to what's needed to define a computation with [CNTK](https://docs.microsoft.com/cognitive-toolkit/), a deep learning library:</span></span>

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

<span data-ttu-id="b7ea9-378">El `Computation` nombre es una forma cómoda de denotar cualquier función que coincida con la firma que está aliasando.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-378">The `Computation` name is a convenient way to denote any function that matches the signature it is aliasing.</span></span> <span data-ttu-id="b7ea9-379">El uso de abreviaturas de tipo como esta es conveniente y permite un código más sucinto.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-379">Using Type Abbreviations like this is convenient and allows for more succinct code.</span></span>

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a><span data-ttu-id="b7ea9-380">Evita usar abreviaturas de tipo para representar tu dominio</span><span class="sxs-lookup"><span data-stu-id="b7ea9-380">Avoid using Type Abbreviations to represent your domain</span></span>

<span data-ttu-id="b7ea9-381">Aunque las abreviaturas de tipo son convenientes para dar un nombre a las firmas de función, pueden ser confusas al abreviar otros tipos.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-381">Although Type Abbreviations are convenient for giving a name to function signatures, they can be confusing when abbreviating other types.</span></span> <span data-ttu-id="b7ea9-382">Considere esta abreviatura:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-382">Consider this abbreviation:</span></span>

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

<span data-ttu-id="b7ea9-383">Esto puede ser confuso de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-383">This can be confusing in multiple ways:</span></span>

* <span data-ttu-id="b7ea9-384">`BufferSize`no es una abstracción; es sólo otro nombre para un entero.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-384">`BufferSize` is not an abstraction; it is just another name for an integer.</span></span>
* <span data-ttu-id="b7ea9-385">Si `BufferSize` se expone en una API pública, se puede malinterpretar fácilmente para significar algo más que `int`.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-385">If `BufferSize` is exposed in a public API, it can easily be misinterpreted to mean more than just `int`.</span></span> <span data-ttu-id="b7ea9-386">Por lo general, los tipos de dominio tienen `int`varios atributos y no son tipos primitivos como .</span><span class="sxs-lookup"><span data-stu-id="b7ea9-386">Generally, domain types have multiple attributes to them and are not primitive types like `int`.</span></span> <span data-ttu-id="b7ea9-387">Esta abreviatura viola esa suposición.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-387">This abbreviation violates that assumption.</span></span>
* <span data-ttu-id="b7ea9-388">La mayúsculas y minúsculas de `BufferSize` (PascalCase) implica que este tipo contiene más datos.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-388">The casing of `BufferSize` (PascalCase) implies that this type holds more data.</span></span>
* <span data-ttu-id="b7ea9-389">Este alias no ofrece mayor claridad en comparación con proporcionar un argumento con nombre a una función.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-389">This alias does not offer increased clarity compared with providing a named argument to a function.</span></span>
* <span data-ttu-id="b7ea9-390">La abreviatura no se manifestará en IL compilado; es sólo un entero y este alias es una construcción en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-390">The abbreviation will not manifest in compiled IL; it is just an integer and this alias is a compile-time construct.</span></span>

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

<span data-ttu-id="b7ea9-391">En resumen, el escollo con abreviaturas de tipo es que **no** son abstracciones sobre los tipos que están abreviados.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-391">In summary, the pitfall with Type Abbreviations is that they are **not** abstractions over the types they are abbreviating.</span></span> <span data-ttu-id="b7ea9-392">En el ejemplo `BufferSize` anterior, `int` es sólo un bajo las cubiertas, sin datos `int` adicionales, ni ningún beneficio del sistema de tipos además de lo que ya tiene.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-392">In the previous example, `BufferSize` is just an `int` under the covers, with no additional data, nor any benefits from the type system besides what `int` already has.</span></span>

<span data-ttu-id="b7ea9-393">Un enfoque alternativo al uso de abreviaturas de tipo para representar un dominio es usar uniones discriminadas de un solo caso.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-393">An alternative approach to using type abbreviations to represent a domain is to use single-case discriminated unions.</span></span> <span data-ttu-id="b7ea9-394">El ejemplo anterior se puede modelar de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-394">The previous sample can be modeled as follows:</span></span>

```fsharp
type BufferSize = BufferSize of int
```

<span data-ttu-id="b7ea9-395">Si escribe código que funciona `BufferSize` en términos de y su valor subyacente, debe construir uno en lugar de pasar cualquier entero arbitrario:</span><span class="sxs-lookup"><span data-stu-id="b7ea9-395">If you write code that operates in terms of `BufferSize` and its underlying value, you need to construct one rather than pass in any arbitrary integer:</span></span>

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

<span data-ttu-id="b7ea9-396">Esto reduce la probabilidad de pasar por `send` error un entero arbitrario `BufferSize` en la función, porque el llamador debe construir un tipo para ajustar un valor antes de llamar a la función.</span><span class="sxs-lookup"><span data-stu-id="b7ea9-396">This reduces the likelihood of mistakenly passing an arbitrary integer into the `send` function, because the caller must construct a `BufferSize` type to wrap a value before calling the function.</span></span>
