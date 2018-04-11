---
title: 'Programación asincrónica en F #'
description: 'Obtenga información acerca de cómo programación asincrónica de F # se lleva a cabo a través de un modelo de programación de nivel de lenguaje que sea fácil de usar y el lenguaje natural.'
keywords: .NET, .NET Core
author: cartermp
ms.author: phcart
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f9196bfc-b8a8-4d33-8b53-0dcbd58a69d8
ms.openlocfilehash: c3fde46e804b7acac78d3ce5454a3c6f806e24e7
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
---
# <a name="async-programming-in-f"></a><span data-ttu-id="91e4f-104">Programación asincrónica en F #</span><span class="sxs-lookup"><span data-stu-id="91e4f-104">Async Programming in F#</span></span> #

> [!NOTE]
> <span data-ttu-id="91e4f-105">Se han descubierto algunos imprecisiones en este artículo.</span><span class="sxs-lookup"><span data-stu-id="91e4f-105">Some inaccuracies have been discovered in this article.</span></span>  <span data-ttu-id="91e4f-106">Se está sobrescribiendo.</span><span class="sxs-lookup"><span data-stu-id="91e4f-106">It is being rewritten.</span></span>  <span data-ttu-id="91e4f-107">Vea [problema #666](https://github.com/dotnet/docs/issues/666) para obtener información acerca de los cambios.</span><span class="sxs-lookup"><span data-stu-id="91e4f-107">See [Issue #666](https://github.com/dotnet/docs/issues/666) to learn about the changes.</span></span>

<span data-ttu-id="91e4f-108">Programación en F # asincrónico puede realizarse a través de un modelo de programación de nivel de lenguaje está diseñado para ser fácil de usar y el lenguaje natural.</span><span class="sxs-lookup"><span data-stu-id="91e4f-108">Async programming in F# can be accomplished through a language-level programming model designed to be easy to use and natural to the language.</span></span>

<span data-ttu-id="91e4f-109">El núcleo de la programación asincrónica en F # es `Async<'T>`, una representación de trabajo que se puede programar para ejecutarse en segundo plano, donde `'T` se devuelve el tipo a través de especial `return` palabra clave o `unit` si el flujo de trabajo asincrónico no tiene ningún resultados para devolver.</span><span class="sxs-lookup"><span data-stu-id="91e4f-109">The core of async programming in F# is `Async<'T>`, a representation of work that can be triggered to run in the background, where `'T` is either the type returned via the special `return` keyword or `unit` if the async workflow has no result to return.</span></span>

<span data-ttu-id="91e4f-110">El concepto clave para comprender es que es el tipo de una expresión de async `Async<'T>`, que es simplemente un _especificación_ de trabajo se realice en un contexto asincrónico.</span><span class="sxs-lookup"><span data-stu-id="91e4f-110">The key concept to understand is that an async expression’s type is `Async<'T>`, which is merely a _specification_ of work to be done in an asynchronous context.</span></span> <span data-ttu-id="91e4f-111">No se ejecuta hasta que lo inicie explícitamente con una de las funciones de iniciales (como `Async.RunSynchronously`).</span><span class="sxs-lookup"><span data-stu-id="91e4f-111">It is not executed until you explicitly start it with one of the starting functions (such as `Async.RunSynchronously`).</span></span> <span data-ttu-id="91e4f-112">Aunque se trata de una forma diferente de pensar en realizar el trabajo, lo que acabe siendo bastante simple en la práctica.</span><span class="sxs-lookup"><span data-stu-id="91e4f-112">Although this is a different way of thinking about doing work, it ends up being quite simple in practice.</span></span>

<span data-ttu-id="91e4f-113">Por ejemplo, supongamos que desea descargar el código HTML de dotnetfoundation.org sin bloquear el subproceso principal.</span><span class="sxs-lookup"><span data-stu-id="91e4f-113">For example, say you wanted to download the HTML from dotnetfoundation.org without blocking the main thread.</span></span> <span data-ttu-id="91e4f-114">Puedes conseguir similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="91e4f-114">You can accomplish it like this:</span></span>

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

<span data-ttu-id="91e4f-115">Y listo.</span><span class="sxs-lookup"><span data-stu-id="91e4f-115">And that’s it!</span></span> <span data-ttu-id="91e4f-116">Aparte del uso de `async`, `let!`, y `return`, se trata de código de F # solo normales.</span><span class="sxs-lookup"><span data-stu-id="91e4f-116">Aside from the use of `async`, `let!`, and `return`, this is just normal F# code.</span></span>

<span data-ttu-id="91e4f-117">Hay algunas construcciones sintácticas que se debe tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="91e4f-117">There are a few syntactical constructs which are worth noting:</span></span>

*   <span data-ttu-id="91e4f-118">`let!` enlaza el resultado de una expresión de async (que se ejecuta en otro contexto).</span><span class="sxs-lookup"><span data-stu-id="91e4f-118">`let!` binds the result of an async expression (which runs on another context).</span></span>
*   <span data-ttu-id="91e4f-119">`use!` funciona igual que `let!`, pero elimina sus recursos enlazados cuando sale del ámbito.</span><span class="sxs-lookup"><span data-stu-id="91e4f-119">`use!` works just like `let!`, but disposes its bound resources when it goes out of scope.</span></span>
*   <span data-ttu-id="91e4f-120">`do!` esperar a un flujo de trabajo asincrónico que no devuelve nada.</span><span class="sxs-lookup"><span data-stu-id="91e4f-120">`do!` will await an async workflow which doesn’t return anything.</span></span>
*   <span data-ttu-id="91e4f-121">`return` simplemente devuelve un resultado de una expresión asincrónica.</span><span class="sxs-lookup"><span data-stu-id="91e4f-121">`return` simply returns a result from an async expression.</span></span>
*   <span data-ttu-id="91e4f-122">`return!` ejecuta otro flujo de trabajo asincrónico y devuelve su valor devuelto como resultado.</span><span class="sxs-lookup"><span data-stu-id="91e4f-122">`return!` executes another async workflow and returns its return value as a result.</span></span>

<span data-ttu-id="91e4f-123">Además, normal `let`, `use`, y `do` palabras clave puede utilizarse junto con las versiones asincrónicas igual que lo harían en una función normal.</span><span class="sxs-lookup"><span data-stu-id="91e4f-123">Additionally, normal `let`, `use`, and `do` keywords can be used alongside the async versions just as they would in a normal function.</span></span>

## <a name="how-to-start-async-code-in-f"></a><span data-ttu-id="91e4f-124">Cómo iniciar código asincrónico en F #</span><span class="sxs-lookup"><span data-stu-id="91e4f-124">How to start Async Code in F#</span></span> #

<span data-ttu-id="91e4f-125">Como se mencionó anteriormente, código asincrónico es una especificación de trabajo que se va a realizarse en otro contexto que tiene que iniciarse de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="91e4f-125">As mentioned earlier, async code is a specification of work to be done in another context which needs to be explicitly started.</span></span> <span data-ttu-id="91e4f-126">Estas son dos métodos principales para lograr esto:</span><span class="sxs-lookup"><span data-stu-id="91e4f-126">Here are two primary ways to accomplish this:</span></span>

1.  <span data-ttu-id="91e4f-127">`Async.RunSynchronously` iniciará un flujo de trabajo asincrónico en otro subproceso y espera su resultado.</span><span class="sxs-lookup"><span data-stu-id="91e4f-127">`Async.RunSynchronously` will start an async workflow on another thread and await its result.</span></span>

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

2.  <span data-ttu-id="91e4f-128">`Async.Start` se inicia un flujo de trabajo asincrónico en otro subproceso y le **no** espera su resultado.</span><span class="sxs-lookup"><span data-stu-id="91e4f-128">`Async.Start` will start an async workflow on another thread, and will **not** await its result.</span></span>

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

<span data-ttu-id="91e4f-129">Hay otras maneras de iniciar un flujo de trabajo asincrónico disponible para escenarios más específicos.</span><span class="sxs-lookup"><span data-stu-id="91e4f-129">There are other ways to start an async workflow available for more specific scenarios.</span></span> <span data-ttu-id="91e4f-130">Que se explican con detalle [en la referencia de Async](https://msdn.microsoft.com/library/ee370232.aspx).</span><span class="sxs-lookup"><span data-stu-id="91e4f-130">They are detailed [in the Async reference](https://msdn.microsoft.com/library/ee370232.aspx).</span></span>

### <a name="a-note-on-threads"></a><span data-ttu-id="91e4f-131">Una nota en subprocesos</span><span class="sxs-lookup"><span data-stu-id="91e4f-131">A Note on Threads</span></span>

<span data-ttu-id="91e4f-132">La frase "en otro subproceso" esté mencionada anteriormente, pero es importante saber que **esto no significa que los flujos de trabajo asincrónicos son una fachada para multithreading**.</span><span class="sxs-lookup"><span data-stu-id="91e4f-132">The phrase "on another thread" is mentioned above, but it is important to know that **this does not mean that async workflows are a facade for multithreading**.</span></span> <span data-ttu-id="91e4f-133">El flujo de trabajo realmente "salta" entre los subprocesos, préstamo una pequeña cantidad de tiempo en realizar trabajo útil.</span><span class="sxs-lookup"><span data-stu-id="91e4f-133">The workflow actually "jumps" between threads, borrowing them for a small amount of time to do useful work.</span></span> <span data-ttu-id="91e4f-134">Cuando un flujo de trabajo asincrónico eficazmente "espera" (por ejemplo, esperando una llamada de red devolver algo), se libera cualquier subproceso que se toma prestado en el momento hasta vaya realice trabajo útil en otra cosa.</span><span class="sxs-lookup"><span data-stu-id="91e4f-134">When an async workflow is effectively "waiting" (for example, waiting for a network call to return something), any thread it was borrowing at the time is freed up to go do useful work on something else.</span></span> <span data-ttu-id="91e4f-135">Esto permite que los flujos de trabajo asincrónico que utilizar el sistema que se ejecutan de forma más eficaz posible y hace que sean especialmente buenas para escenarios de E/S de gran volumen.</span><span class="sxs-lookup"><span data-stu-id="91e4f-135">This allows async workflows to utilize the system they run on as effectively as possible, and makes them especially strong for high-volume I/O scenarios.</span></span>

## <a name="how-to-add-parallelism-to-async-code"></a><span data-ttu-id="91e4f-136">Cómo agregar paralelismo al código asincrónico</span><span class="sxs-lookup"><span data-stu-id="91e4f-136">How to Add Parallelism to Async Code</span></span>

<span data-ttu-id="91e4f-137">A veces puede necesita para realizar varias tareas asincrónicas en paralelo, recopilar sus resultados e interpretarlos de alguna manera.</span><span class="sxs-lookup"><span data-stu-id="91e4f-137">Sometimes you may need to perform multiple asynchronous jobs in parallel, collect their results, and interpret them in some way.</span></span> <span data-ttu-id="91e4f-138">`Async.Parallel` le permite hacerlo sin necesidad de usar la biblioteca TPL, lo que implicaría la necesidad de coerce `Task<'T>` y `Async<'T>` tipos.</span><span class="sxs-lookup"><span data-stu-id="91e4f-138">`Async.Parallel` allows you to do this without needing to use the Task Parallel Library, which would involve needing to coerce `Task<'T>` and `Async<'T>` types.</span></span>

<span data-ttu-id="91e4f-139">En el ejemplo siguiente, se utilizará `Async.Parallel` para descargar el código HTML de los sitios más frecuentados cuatro en paralelo, espere a que esas tareas se completen y, a continuación, imprima el código HTML que se descargó.</span><span class="sxs-lookup"><span data-stu-id="91e4f-139">The following example will use `Async.Parallel` to download the HTML from four popular sites in parallel, wait for those tasks to complete, and then print the HTML which was downloaded.</span></span>

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

## <a name="important-info-and-advice"></a><span data-ttu-id="91e4f-140">Consejos e información importante</span><span class="sxs-lookup"><span data-stu-id="91e4f-140">Important Info and Advice</span></span>

*   <span data-ttu-id="91e4f-141">Anexa "Async" al final de las funciones que podrá consumir</span><span class="sxs-lookup"><span data-stu-id="91e4f-141">Append "Async" to the end of any functions you’ll consume</span></span>

 <span data-ttu-id="91e4f-142">Aunque se trata de una convención de nomenclatura, lo facilitar las cosas como la detectabilidad de API.</span><span class="sxs-lookup"><span data-stu-id="91e4f-142">Although this is just a naming convention, it does make things like API discoverability easier.</span></span> <span data-ttu-id="91e4f-143">Especialmente si hay versiones sincrónicas y asincrónicas de la misma rutina, resulta una buena idea para indicar explícitamente que es asincrónica mediante el nombre.</span><span class="sxs-lookup"><span data-stu-id="91e4f-143">Particularly if there are synchronous and asynchronous versions of the same routine, it’s a good idea to explicitly state which is asynchronous via the name.</span></span>

*   <span data-ttu-id="91e4f-144">Realizar escuchas para el compilador.</span><span class="sxs-lookup"><span data-stu-id="91e4f-144">Listen to the compiler!</span></span>

 <span data-ttu-id="91e4f-145">Compilador de F # es muy estricta, lo que sea casi imposible hacer algo troubling como ejecutar código de "async" de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="91e4f-145">F#’s compiler is very strict, making it nearly impossible to do something troubling like run "async" code synchronously.</span></span> <span data-ttu-id="91e4f-146">Si llega a través de una advertencia, que es un inicio de sesión que el código no ejecute crea que hará lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="91e4f-146">If you come across a warning, that’s a sign that the code won’t execute how you think it will.</span></span> <span data-ttu-id="91e4f-147">Si puede hacer que el compilador satisfecho, más probable es que se ejecutará el código según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="91e4f-147">If you can make the compiler happy, your code will most likely execute as expected.</span></span>

## <a name="for-the-cvb-programmer-looking-into-f"></a><span data-ttu-id="91e4f-148">Para C# /VB programador estudiando F #</span><span class="sxs-lookup"><span data-stu-id="91e4f-148">For the C#/VB Programmer Looking Into F#</span></span> #

<span data-ttu-id="91e4f-149">En esta sección se supone que está familiarizado con el modelo asincrónico en C# / VB.</span><span class="sxs-lookup"><span data-stu-id="91e4f-149">This section assumes you’re familiar with the async model in C#/VB.</span></span> <span data-ttu-id="91e4f-150">Si no, [de programación asincrónica en C#](../../../csharp/async.md) es un punto de partida.</span><span class="sxs-lookup"><span data-stu-id="91e4f-150">If you are not, [Async Programming in C#](../../../csharp/async.md) is a starting point.</span></span>

<span data-ttu-id="91e4f-151">Hay una diferencia fundamental entre el modelo de C# /VB asincrónico y el modelo asincrónico de F #.</span><span class="sxs-lookup"><span data-stu-id="91e4f-151">There is a fundamental difference between the C#/VB async model and the F# async model.</span></span>

<span data-ttu-id="91e4f-152">Cuando se llama a una función que devuelve un `Task` o `Task<'T>`, que el trabajo ya ha comenzado la ejecución.</span><span class="sxs-lookup"><span data-stu-id="91e4f-152">When you call a function which returns a `Task` or `Task<'T>`, that job has already begun execution.</span></span> <span data-ttu-id="91e4f-153">El identificador devuelto representa una tarea asincrónica ya se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="91e4f-153">The handle returned represents an already-running asynchronous job.</span></span> <span data-ttu-id="91e4f-154">En cambio, cuando se llama a una función asincrónica en F #, la `Async<'a>` devuelto representa un trabajo que será **generado** en algún momento.</span><span class="sxs-lookup"><span data-stu-id="91e4f-154">In contrast, when you call an async function in F#, the `Async<'a>` returned represents a job which will be **generated** at some point.</span></span> <span data-ttu-id="91e4f-155">Descripción de este modelo es eficaz, porque permite trabajos asincrónicos en F # para que se pueden encadenar juntos, realiza de forma condicional y puede iniciar con una granularidad más fina del control.</span><span class="sxs-lookup"><span data-stu-id="91e4f-155">Understanding this model is powerful, because it allows for asynchronous jobs in F# to be chained together easier, performed conditionally, and be started with a finer grain of control.</span></span>

<span data-ttu-id="91e4f-156">Hay algunas otras similitudes y diferencias que hay que tener en cuenta.</span><span class="sxs-lookup"><span data-stu-id="91e4f-156">There are a few other similarities and differences worth noting.</span></span>

### <a name="similarities"></a><span data-ttu-id="91e4f-157">Similitudes</span><span class="sxs-lookup"><span data-stu-id="91e4f-157">Similarities</span></span>

*   <span data-ttu-id="91e4f-158">`let!`, `use!`, y `do!` son análogos a `await` al llamar a un trabajo asincrónico desde una `async{ }` bloque.</span><span class="sxs-lookup"><span data-stu-id="91e4f-158">`let!`, `use!`, and `do!` are analogous to `await` when calling an async job from within an `async{ }` block.</span></span>

 <span data-ttu-id="91e4f-159">Las tres palabras clave solo pueden utilizarse dentro de un `async { }` bloque, similar a cómo `await` sólo se puede invocar dentro de un `async` método.</span><span class="sxs-lookup"><span data-stu-id="91e4f-159">The three keywords can only be used within an `async { }` block, similar to how `await` can only be invoked inside an `async` method.</span></span> <span data-ttu-id="91e4f-160">En resumen, `let!` es adecuada cuando desea capturar y utilizar un resultado, `use!` es el mismo, pero lo que se deben obtener limpiar cuyos recursos después de que se utiliza, y `do!` es adecuada cuando desea esperar a un flujo de trabajo asincrónico sin ningún valor devuelto para finalizar antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="91e4f-160">In short, `let!` is for when you want to capture and use a result, `use!` is the same but for something whose resources should get cleaned after it’s used, and `do!` is for when you want to wait for an async workflow with no return value to finish before moving on.</span></span>

*   <span data-ttu-id="91e4f-161">F # admite el paralelismo de datos de una manera similar.</span><span class="sxs-lookup"><span data-stu-id="91e4f-161">F# supports data-parallelism in a similar way.</span></span>

 <span data-ttu-id="91e4f-162">Aunque funciona de forma muy diferente, `Async.Parallel` corresponde a `Task.WhenAll` en el caso de que los resultados de un conjunto de trabajos asincrónicos cuando se completen.</span><span class="sxs-lookup"><span data-stu-id="91e4f-162">Although it operates very differently, `Async.Parallel` corresponds to `Task.WhenAll` for the scenario of wanting the results of a set of async jobs when they all complete.</span></span>

### <a name="differences"></a><span data-ttu-id="91e4f-163">Diferencias</span><span class="sxs-lookup"><span data-stu-id="91e4f-163">Differences</span></span>

*   <span data-ttu-id="91e4f-164">Anidar `let!` no permitido, a diferencia de anidados `await`</span><span class="sxs-lookup"><span data-stu-id="91e4f-164">Nested `let!` is not allowed, unlike nested `await`</span></span>

 <span data-ttu-id="91e4f-165">A diferencia de `await`, que se pueden anidar indefinidamente, `let!` no se puede y debe tener su resultado enlazado antes de usarlo dentro de otro `let!`, `do!`, o `use!`.</span><span class="sxs-lookup"><span data-stu-id="91e4f-165">Unlike `await`, which can be nested indefinitely, `let!` cannot and must have its result bound before using it inside of another `let!`, `do!`, or `use!`.</span></span>

*   <span data-ttu-id="91e4f-166">Compatibilidad con la cancelación es más sencillo en F # que en C# / VB.</span><span class="sxs-lookup"><span data-stu-id="91e4f-166">Cancellation support is simpler in F# than in C#/VB.</span></span>

 <span data-ttu-id="91e4f-167">Admitir la cancelación de una mitad de la tarea a través de su ejecución en C# /VB requiere la comprobación de la `IsCancellationRequested` propiedad o llamar a `ThrowIfCancellationRequested()` en un `CancellationToken` objeto que se haya pasado al método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="91e4f-167">Supporting cancellation of a task midway through its execution in C#/VB requires checking the `IsCancellationRequested` property or calling `ThrowIfCancellationRequested()` on a `CancellationToken` object that’s passed into the async method.</span></span>

<span data-ttu-id="91e4f-168">En cambio, F # asincrónico los flujos de trabajo son más natural cancelables.</span><span class="sxs-lookup"><span data-stu-id="91e4f-168">In contrast, F# async workflows are more naturally cancellable.</span></span> <span data-ttu-id="91e4f-169">Cancelación es un proceso sencillo de tres pasos.</span><span class="sxs-lookup"><span data-stu-id="91e4f-169">Cancellation is a simple three-step process.</span></span>

1.  <span data-ttu-id="91e4f-170">Cree un nuevo objeto `CancellationTokenSource`.</span><span class="sxs-lookup"><span data-stu-id="91e4f-170">Create a new `CancellationTokenSource`.</span></span>
2.  <span data-ttu-id="91e4f-171">Pasar dicho valor en una función inicial.</span><span class="sxs-lookup"><span data-stu-id="91e4f-171">Pass it into a starting function.</span></span>
3.  <span data-ttu-id="91e4f-172">Llamar a `Cancel` en el token.</span><span class="sxs-lookup"><span data-stu-id="91e4f-172">Call `Cancel` on the token.</span></span>

<span data-ttu-id="91e4f-173">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="91e4f-173">Example:</span></span>

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

let token = new CancellationTokenSource()
Async.Start (workflow, token)

// Immediately cancel uploadDataAsync after it's been started.
token.Cancel()
```

<span data-ttu-id="91e4f-174">Y listo.</span><span class="sxs-lookup"><span data-stu-id="91e4f-174">And that’s it!</span></span>

## <a name="further-resources"></a><span data-ttu-id="91e4f-175">Recursos adicionales:</span><span class="sxs-lookup"><span data-stu-id="91e4f-175">Further resources:</span></span>

*   [<span data-ttu-id="91e4f-176">Flujos de trabajo asincrónicos en MSDN</span><span class="sxs-lookup"><span data-stu-id="91e4f-176">Async Workflows on MSDN</span></span>](https://msdn.microsoft.com/library/dd233250.aspx)
*   [<span data-ttu-id="91e4f-177">Secuencias asincrónicas para F #</span><span class="sxs-lookup"><span data-stu-id="91e4f-177">Asynchronous Sequences for F#</span></span>](https://fsprojects.github.io/FSharp.Control.AsyncSeq/library/AsyncSeq.html)
*   [<span data-ttu-id="91e4f-178">Utilidades de F # datos HTTP</span><span class="sxs-lookup"><span data-stu-id="91e4f-178">F# Data HTTP Utilities</span></span>](https://fsharp.github.io/FSharp.Data/library/Http.html)
