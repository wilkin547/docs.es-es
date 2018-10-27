---
title: Programación de AsyncF#
description: Obtenga información sobre cómo F# programación asincrónica se logra a través de un modelo de programación de nivel de lenguaje que sea fácil de usar y el lenguaje natural.
ms.date: 06/20/2016
ms.openlocfilehash: de07f1252df56e3dfec5ea7a34a283b1c9508523
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50034432"
---
# <a name="async-programming-in-f"></a><span data-ttu-id="6d95c-103">Programación de AsyncF#</span><span class="sxs-lookup"><span data-stu-id="6d95c-103">Async Programming in F#</span></span> #

> [!NOTE]
> <span data-ttu-id="6d95c-104">Se han descubierto algunas imprecisiones en este artículo.</span><span class="sxs-lookup"><span data-stu-id="6d95c-104">Some inaccuracies have been discovered in this article.</span></span>  <span data-ttu-id="6d95c-105">Se está sobrescribiendo.</span><span class="sxs-lookup"><span data-stu-id="6d95c-105">It is being rewritten.</span></span>  <span data-ttu-id="6d95c-106">Consulte [problema #666](https://github.com/dotnet/docs/issues/666) para obtener información acerca de los cambios.</span><span class="sxs-lookup"><span data-stu-id="6d95c-106">See [Issue #666](https://github.com/dotnet/docs/issues/666) to learn about the changes.</span></span>

<span data-ttu-id="6d95c-107">Programación de Async F# puede realizarse a través de un modelo de programación de nivel de lenguaje diseñado para ser fácil de usar y el lenguaje natural.</span><span class="sxs-lookup"><span data-stu-id="6d95c-107">Async programming in F# can be accomplished through a language-level programming model designed to be easy to use and natural to the language.</span></span>

<span data-ttu-id="6d95c-108">El núcleo de la programación de async F# es `Async<'T>`, una representación de trabajo que puede activarse para ejecutar en segundo plano, donde `'T` se devuelve el tipo a través de especial `return` palabra clave o `unit` si el flujo de trabajo asincrónico no tiene ningún resultado para devolver.</span><span class="sxs-lookup"><span data-stu-id="6d95c-108">The core of async programming in F# is `Async<'T>`, a representation of work that can be triggered to run in the background, where `'T` is either the type returned via the special `return` keyword or `unit` if the async workflow has no result to return.</span></span>

<span data-ttu-id="6d95c-109">El concepto clave para comprender es que el tipo de una expresión de async es `Async<'T>`, que es simplemente un _especificación_ de trabajo se realice en un contexto asincrónico.</span><span class="sxs-lookup"><span data-stu-id="6d95c-109">The key concept to understand is that an async expression’s type is `Async<'T>`, which is merely a _specification_ of work to be done in an asynchronous context.</span></span> <span data-ttu-id="6d95c-110">No se ejecuta hasta que lo inicie explícitamente con una de las funciones de iniciales (como `Async.RunSynchronously`).</span><span class="sxs-lookup"><span data-stu-id="6d95c-110">It is not executed until you explicitly start it with one of the starting functions (such as `Async.RunSynchronously`).</span></span> <span data-ttu-id="6d95c-111">Aunque se trata de una forma diferente de reflexionar sobre cómo realizar el trabajo termina siendo bastante sencillo en la práctica.</span><span class="sxs-lookup"><span data-stu-id="6d95c-111">Although this is a different way of thinking about doing work, it ends up being quite simple in practice.</span></span>

<span data-ttu-id="6d95c-112">Por ejemplo, supongamos que desea descargar el código HTML de dotnetfoundation.org sin bloquear el subproceso principal.</span><span class="sxs-lookup"><span data-stu-id="6d95c-112">For example, say you wanted to download the HTML from dotnetfoundation.org without blocking the main thread.</span></span> <span data-ttu-id="6d95c-113">Puede realizarlo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6d95c-113">You can accomplish it like this:</span></span>

```fsharp
open System
open System.Net

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()

        // Execution of fetchHtmlAsync won't continue until the result
        // of AsyncDownloadString is bound.
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let html = "https://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously
printfn "%s" html
```

<span data-ttu-id="6d95c-114">Y listo.</span><span class="sxs-lookup"><span data-stu-id="6d95c-114">And that’s it!</span></span> <span data-ttu-id="6d95c-115">Aparte del uso de `async`, `let!`, y `return`, esto es normal F# código.</span><span class="sxs-lookup"><span data-stu-id="6d95c-115">Aside from the use of `async`, `let!`, and `return`, this is just normal F# code.</span></span>

<span data-ttu-id="6d95c-116">Hay algunas construcciones sintácticas que merece la pena tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="6d95c-116">There are a few syntactical constructs which are worth noting:</span></span>

*   <span data-ttu-id="6d95c-117">`let!` enlaza el resultado de una expresión de async (que se ejecuta en otro contexto).</span><span class="sxs-lookup"><span data-stu-id="6d95c-117">`let!` binds the result of an async expression (which runs on another context).</span></span>
*   <span data-ttu-id="6d95c-118">`use!` funciona igual que `let!`, pero elimina sus recursos enlazados cuando sale del ámbito.</span><span class="sxs-lookup"><span data-stu-id="6d95c-118">`use!` works just like `let!`, but disposes its bound resources when it goes out of scope.</span></span>
*   <span data-ttu-id="6d95c-119">`do!` se espera un flujo de trabajo asincrónico que no devuelve nada.</span><span class="sxs-lookup"><span data-stu-id="6d95c-119">`do!` will await an async workflow which doesn’t return anything.</span></span>
*   <span data-ttu-id="6d95c-120">`return` simplemente devuelve un resultado de una expresión de async.</span><span class="sxs-lookup"><span data-stu-id="6d95c-120">`return` simply returns a result from an async expression.</span></span>
*   <span data-ttu-id="6d95c-121">`return!` ejecuta otro flujo de trabajo asincrónico y devuelve su valor devuelto como resultado.</span><span class="sxs-lookup"><span data-stu-id="6d95c-121">`return!` executes another async workflow and returns its return value as a result.</span></span>

<span data-ttu-id="6d95c-122">Además, normal `let`, `use`, y `do` palabras clave pueden utilizarse junto con las versiones asincrónicas tal como haría en una función normal.</span><span class="sxs-lookup"><span data-stu-id="6d95c-122">Additionally, normal `let`, `use`, and `do` keywords can be used alongside the async versions just as they would in a normal function.</span></span>

## <a name="how-to-start-async-code-in-f"></a><span data-ttu-id="6d95c-123">Cómo iniciar el código asincrónico enF#</span><span class="sxs-lookup"><span data-stu-id="6d95c-123">How to start Async Code in F#</span></span> #

<span data-ttu-id="6d95c-124">Como se mencionó anteriormente, el código asincrónico es una especificación de trabajo se realice en otro contexto que se debe iniciar explícitamente.</span><span class="sxs-lookup"><span data-stu-id="6d95c-124">As mentioned earlier, async code is a specification of work to be done in another context which needs to be explicitly started.</span></span> <span data-ttu-id="6d95c-125">Existen dos formas principales para lograr esto:</span><span class="sxs-lookup"><span data-stu-id="6d95c-125">Here are two primary ways to accomplish this:</span></span>

1.  <span data-ttu-id="6d95c-126">`Async.RunSynchronously` iniciará un flujo de trabajo asincrónico en otro subproceso y espera su resultado.</span><span class="sxs-lookup"><span data-stu-id="6d95c-126">`Async.RunSynchronously` will start an async workflow on another thread and await its result.</span></span>

```fsharp
open System
open System.Net

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

 // Execution will pause until fetchHtmlAsync finishes
 let html = "https://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously

 // you actually have the result from fetchHtmlAsync now!
 printfn "%s" html
 ```

2.  <span data-ttu-id="6d95c-127">`Async.Start` iniciar un flujo de trabajo de async en otro subproceso y, le **no** espera su resultado.</span><span class="sxs-lookup"><span data-stu-id="6d95c-127">`Async.Start` will start an async workflow on another thread, and will **not** await its result.</span></span>

```fsharp
open System
open System.Net
  
let uploadDataAsync url data = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        webClient.UploadStringAsync(uri, data)
    }

let workflow = uploadDataAsync "https://url-to-upload-to.com" "hello, world!"

// Execution will continue after calling this!
Async.Start(workflow)

printfn "%s" "uploadDataAsync is running in the background..."
 ```

<span data-ttu-id="6d95c-128">Hay otras maneras de iniciar un flujo de trabajo asincrónicos disponible para escenarios más específicos.</span><span class="sxs-lookup"><span data-stu-id="6d95c-128">There are other ways to start an async workflow available for more specific scenarios.</span></span> <span data-ttu-id="6d95c-129">Se detallan [en la referencia de Async](https://msdn.microsoft.com/library/ee370232.aspx).</span><span class="sxs-lookup"><span data-stu-id="6d95c-129">They are detailed [in the Async reference](https://msdn.microsoft.com/library/ee370232.aspx).</span></span>

### <a name="a-note-on-threads"></a><span data-ttu-id="6d95c-130">Una nota en subprocesos</span><span class="sxs-lookup"><span data-stu-id="6d95c-130">A Note on Threads</span></span>

<span data-ttu-id="6d95c-131">La frase "en otro subproceso" esté mencionada anteriormente, pero es importante saber que **esto no significa que los flujos de trabajo asincrónicos son una fachada para multithreading**.</span><span class="sxs-lookup"><span data-stu-id="6d95c-131">The phrase "on another thread" is mentioned above, but it is important to know that **this does not mean that async workflows are a facade for multithreading**.</span></span> <span data-ttu-id="6d95c-132">El flujo de trabajo realmente "salta" entre subprocesos, de préstamo de una pequeña cantidad de tiempo para realizar trabajo útil.</span><span class="sxs-lookup"><span data-stu-id="6d95c-132">The workflow actually "jumps" between threads, borrowing them for a small amount of time to do useful work.</span></span> <span data-ttu-id="6d95c-133">Cuando un flujo de trabajo asincrónico está eficazmente "esperando" (por ejemplo, esperando una llamada de red devolver algo), se libera cualquier subproceso que se toma prestado en el momento hasta vaya realice trabajo útil en alguna otra cosa.</span><span class="sxs-lookup"><span data-stu-id="6d95c-133">When an async workflow is effectively "waiting" (for example, waiting for a network call to return something), any thread it was borrowing at the time is freed up to go do useful work on something else.</span></span> <span data-ttu-id="6d95c-134">Esto permite flujos de trabajo asincrónicos para que usen el sistema que se ejecutan en forma más eficaz posible y hace que sea especialmente seguros para escenarios de E/S de gran volumen.</span><span class="sxs-lookup"><span data-stu-id="6d95c-134">This allows async workflows to utilize the system they run on as effectively as possible, and makes them especially strong for high-volume I/O scenarios.</span></span>

## <a name="how-to-add-parallelism-to-async-code"></a><span data-ttu-id="6d95c-135">Cómo agregar paralelismo a código asincrónico</span><span class="sxs-lookup"><span data-stu-id="6d95c-135">How to Add Parallelism to Async Code</span></span>

<span data-ttu-id="6d95c-136">En ocasiones, es posible que necesita para realizar varias tareas asincrónicas en paralelo, recopilar sus resultados e interpretarlos de alguna manera.</span><span class="sxs-lookup"><span data-stu-id="6d95c-136">Sometimes you may need to perform multiple asynchronous jobs in parallel, collect their results, and interpret them in some way.</span></span> <span data-ttu-id="6d95c-137">`Async.Parallel` permite realizar esto sin necesidad de usar la biblioteca TPL, lo que implicaría la necesidad de convertir `Task<'T>` y `Async<'T>` tipos.</span><span class="sxs-lookup"><span data-stu-id="6d95c-137">`Async.Parallel` allows you to do this without needing to use the Task Parallel Library, which would involve needing to coerce `Task<'T>` and `Async<'T>` types.</span></span>

<span data-ttu-id="6d95c-138">En el ejemplo siguiente, se usará `Async.Parallel` para descargar el código HTML de cuatro sitios más populares en paralelo, espere a que esas tareas se completen y, a continuación, imprima el código HTML que se descargó.</span><span class="sxs-lookup"><span data-stu-id="6d95c-138">The following example will use `Async.Parallel` to download the HTML from four popular sites in parallel, wait for those tasks to complete, and then print the HTML which was downloaded.</span></span>

```fsharp
open System
open System.Net

let urlList = 
    [ "https://www.microsoft.com"
      "https://www.google.com"
      "https://www.amazon.com"
      "https://www.facebook.com" ]

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let getHtmlList urls =
    urls
    |> Seq.map fetchHtmlAsync   // Build an Async<'T> for each site
    |> Async.Parallel           // Returns an Async<'T []>
    |> Async.RunSynchronously   // Wait for the result of the parallel work

let htmlList = getHtmlList urlList

// We now have the downloaded HTML for each site!
for html in htmlList do
    printfn "%s" html
```

## <a name="important-info-and-advice"></a><span data-ttu-id="6d95c-139">Consejos e información importante</span><span class="sxs-lookup"><span data-stu-id="6d95c-139">Important Info and Advice</span></span>

*   <span data-ttu-id="6d95c-140">Anexa "Async" al final de cualquier función que se va a consumir</span><span class="sxs-lookup"><span data-stu-id="6d95c-140">Append "Async" to the end of any functions you’ll consume</span></span>

 <span data-ttu-id="6d95c-141">Aunque se trata de una convención de nomenclatura, lo facilitar las cosas como la detectabilidad de las API.</span><span class="sxs-lookup"><span data-stu-id="6d95c-141">Although this is just a naming convention, it does make things like API discoverability easier.</span></span> <span data-ttu-id="6d95c-142">Especialmente si hay versiones sincrónicas y asincrónicas de la misma rutina, es una buena idea para indicar explícitamente que es asincrónico por medio del nombre.</span><span class="sxs-lookup"><span data-stu-id="6d95c-142">Particularly if there are synchronous and asynchronous versions of the same routine, it’s a good idea to explicitly state which is asynchronous via the name.</span></span>

*   <span data-ttu-id="6d95c-143">Escuchar al compilador.</span><span class="sxs-lookup"><span data-stu-id="6d95c-143">Listen to the compiler!</span></span>

 <span data-ttu-id="6d95c-144">F#del compilador es muy estricto, lo que casi imposible hacer algo problemáticos, como ejecutar "async" código de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="6d95c-144">F#’s compiler is very strict, making it nearly impossible to do something troubling like run "async" code synchronously.</span></span> <span data-ttu-id="6d95c-145">Si llega a través de una advertencia, que es un inicio de sesión que el código no ejecutará cómo cree que lo hará.</span><span class="sxs-lookup"><span data-stu-id="6d95c-145">If you come across a warning, that’s a sign that the code won’t execute how you think it will.</span></span> <span data-ttu-id="6d95c-146">Si puede hacer que el compilador feliz, más probable es que se ejecutará el código según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="6d95c-146">If you can make the compiler happy, your code will most likely execute as expected.</span></span>

## <a name="for-the-cvb-programmer-looking-into-f"></a><span data-ttu-id="6d95c-147">Para el C#programador/VB estudiandoF#</span><span class="sxs-lookup"><span data-stu-id="6d95c-147">For the C#/VB Programmer Looking Into F#</span></span> #

<span data-ttu-id="6d95c-148">En esta sección se da por supuesto que está familiarizado con el modelo asincrónico en C#/VB.</span><span class="sxs-lookup"><span data-stu-id="6d95c-148">This section assumes you’re familiar with the async model in C#/VB.</span></span> <span data-ttu-id="6d95c-149">Si no, [de programación asincrónica en C# ](../../../csharp/async.md) es un punto de partida.</span><span class="sxs-lookup"><span data-stu-id="6d95c-149">If you are not, [Async Programming in C#](../../../csharp/async.md) is a starting point.</span></span>

<span data-ttu-id="6d95c-150">Hay una diferencia fundamental entre el C#/VB async modelo y el F# modelo asincrónico.</span><span class="sxs-lookup"><span data-stu-id="6d95c-150">There is a fundamental difference between the C#/VB async model and the F# async model.</span></span>

<span data-ttu-id="6d95c-151">Cuando se llama a una función que devuelve un `Task` o `Task<'T>`, ese trabajo ya ha comenzado la ejecución.</span><span class="sxs-lookup"><span data-stu-id="6d95c-151">When you call a function which returns a `Task` or `Task<'T>`, that job has already begun execution.</span></span> <span data-ttu-id="6d95c-152">El identificador devuelto representa un trabajo asincrónico está ya en ejecución.</span><span class="sxs-lookup"><span data-stu-id="6d95c-152">The handle returned represents an already-running asynchronous job.</span></span> <span data-ttu-id="6d95c-153">En cambio, cuando se llama a una función asincrónica F#, `Async<'a>` devuelto representa un trabajo que será **genera** en algún momento.</span><span class="sxs-lookup"><span data-stu-id="6d95c-153">In contrast, when you call an async function in F#, the `Async<'a>` returned represents a job which will be **generated** at some point.</span></span> <span data-ttu-id="6d95c-154">Descripción de este modelo es eficaz, porque permite trabajos asincrónicos en F# se pueden encadenar, realiza de forma condicional y se puede iniciar con un nivel de detalle más preciso de control.</span><span class="sxs-lookup"><span data-stu-id="6d95c-154">Understanding this model is powerful, because it allows for asynchronous jobs in F# to be chained together easier, performed conditionally, and be started with a finer grain of control.</span></span>

<span data-ttu-id="6d95c-155">Hay algunos otros las similitudes y diferencias cabe destacar.</span><span class="sxs-lookup"><span data-stu-id="6d95c-155">There are a few other similarities and differences worth noting.</span></span>

### <a name="similarities"></a><span data-ttu-id="6d95c-156">Similitudes</span><span class="sxs-lookup"><span data-stu-id="6d95c-156">Similarities</span></span>

*   <span data-ttu-id="6d95c-157">`let!`, `use!`, y `do!` son análogos a `await` al llamar a un trabajo asincrónico desde una `async{ }` bloque.</span><span class="sxs-lookup"><span data-stu-id="6d95c-157">`let!`, `use!`, and `do!` are analogous to `await` when calling an async job from within an `async{ }` block.</span></span>

 <span data-ttu-id="6d95c-158">Las tres palabras clave solo se pueden usar dentro de un `async { }` bloque, similar a cómo `await` solo puede invocarse dentro de un `async` método.</span><span class="sxs-lookup"><span data-stu-id="6d95c-158">The three keywords can only be used within an `async { }` block, similar to how `await` can only be invoked inside an `async` method.</span></span> <span data-ttu-id="6d95c-159">En resumen, `let!` es para cuando desee capturar y utilizar un resultado, `use!` es el mismo pero algo cuyos recursos deben obtener limpiados tras su uso, y `do!` es para cuando desee esperar un flujo de trabajo asincrónico sin ningún valor devuelto al finalizar antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="6d95c-159">In short, `let!` is for when you want to capture and use a result, `use!` is the same but for something whose resources should get cleaned after it’s used, and `do!` is for when you want to wait for an async workflow with no return value to finish before moving on.</span></span>

*   <span data-ttu-id="6d95c-160">F#admite el paralelismo de datos de forma similar.</span><span class="sxs-lookup"><span data-stu-id="6d95c-160">F# supports data-parallelism in a similar way.</span></span>

 <span data-ttu-id="6d95c-161">Aunque funciona de forma muy distinta, `Async.Parallel` corresponde a `Task.WhenAll` en el caso de que los resultados de un conjunto de trabajos asincrónicos cuando se completan.</span><span class="sxs-lookup"><span data-stu-id="6d95c-161">Although it operates very differently, `Async.Parallel` corresponds to `Task.WhenAll` for the scenario of wanting the results of a set of async jobs when they all complete.</span></span>

### <a name="differences"></a><span data-ttu-id="6d95c-162">Diferencias</span><span class="sxs-lookup"><span data-stu-id="6d95c-162">Differences</span></span>

*   <span data-ttu-id="6d95c-163">Anidar `let!` no se permite, a diferencia de anidados `await`</span><span class="sxs-lookup"><span data-stu-id="6d95c-163">Nested `let!` is not allowed, unlike nested `await`</span></span>

 <span data-ttu-id="6d95c-164">A diferencia de `await`, que se pueden anidar indefinidamente, `let!` no se puede y debe tener su resultado enlazados antes de usarlo dentro de otra `let!`, `do!`, o `use!`.</span><span class="sxs-lookup"><span data-stu-id="6d95c-164">Unlike `await`, which can be nested indefinitely, `let!` cannot and must have its result bound before using it inside of another `let!`, `do!`, or `use!`.</span></span>

*   <span data-ttu-id="6d95c-165">Compatibilidad con la cancelación es más sencillo en F# que en C#/VB.</span><span class="sxs-lookup"><span data-stu-id="6d95c-165">Cancellation support is simpler in F# than in C#/VB.</span></span>

 <span data-ttu-id="6d95c-166">Admitir la cancelación de una tarea a mitad de camino su ejecución en C#/VB requiere comprobación el `IsCancellationRequested` propiedad o llamar a `ThrowIfCancellationRequested()` en un `CancellationToken` objeto que se pasa al método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="6d95c-166">Supporting cancellation of a task midway through its execution in C#/VB requires checking the `IsCancellationRequested` property or calling `ThrowIfCancellationRequested()` on a `CancellationToken` object that’s passed into the async method.</span></span>

<span data-ttu-id="6d95c-167">En cambio, F# flujos de trabajo asincrónicos son cancelables de manera más natural.</span><span class="sxs-lookup"><span data-stu-id="6d95c-167">In contrast, F# async workflows are more naturally cancellable.</span></span> <span data-ttu-id="6d95c-168">La cancelación es un proceso sencillo de tres pasos.</span><span class="sxs-lookup"><span data-stu-id="6d95c-168">Cancellation is a simple three-step process.</span></span>

1.  <span data-ttu-id="6d95c-169">Cree un nuevo objeto `CancellationTokenSource`.</span><span class="sxs-lookup"><span data-stu-id="6d95c-169">Create a new `CancellationTokenSource`.</span></span>
2.  <span data-ttu-id="6d95c-170">Pasarlo a una función inicial.</span><span class="sxs-lookup"><span data-stu-id="6d95c-170">Pass it into a starting function.</span></span>
3.  <span data-ttu-id="6d95c-171">Llamar a `Cancel` en el token.</span><span class="sxs-lookup"><span data-stu-id="6d95c-171">Call `Cancel` on the token.</span></span>

<span data-ttu-id="6d95c-172">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6d95c-172">Example:</span></span>

```fsharp
open System
open System.Net
open System.Threading

let uploadDataAsync url data = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        webClient.UploadStringAsync(uri, data)
    }

let workflow = uploadDataAsync "https://url-to-upload-to.com" "hello, world!"

let token = new CancellationTokenSource()
Async.Start (workflow, token.Token)

// Immediately cancel uploadDataAsync after it's been started.
token.Cancel()
```

<span data-ttu-id="6d95c-173">Y listo.</span><span class="sxs-lookup"><span data-stu-id="6d95c-173">And that’s it!</span></span>

## <a name="further-resources"></a><span data-ttu-id="6d95c-174">Recursos adicionales:</span><span class="sxs-lookup"><span data-stu-id="6d95c-174">Further resources:</span></span>

*   [<span data-ttu-id="6d95c-175">Flujos de trabajo asincrónicos en MSDN</span><span class="sxs-lookup"><span data-stu-id="6d95c-175">Async Workflows on MSDN</span></span>](https://msdn.microsoft.com/library/dd233250.aspx)
*   [<span data-ttu-id="6d95c-176">Secuencias asincrónicas paraF#</span><span class="sxs-lookup"><span data-stu-id="6d95c-176">Asynchronous Sequences for F#</span></span>](https://fsprojects.github.io/FSharp.Control.AsyncSeq/library/AsyncSeq.html)
*   [<span data-ttu-id="6d95c-177">F#Utilidades de datos HTTP</span><span class="sxs-lookup"><span data-stu-id="6d95c-177">F# Data HTTP Utilities</span></span>](https://fsharp.github.io/FSharp.Data/library/Http.html)
