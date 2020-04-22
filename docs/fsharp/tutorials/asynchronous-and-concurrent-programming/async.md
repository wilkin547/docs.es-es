---
title: Programación asíncrona
description: Descubra cómo F- proporciona soporte limpio para la asincronía basada en un modelo de programación de nivel de lenguaje derivado de los conceptos básicos de programación funcional.
ms.date: 12/17/2018
ms.openlocfilehash: 0a7d400c9778e30d6b25798239f12b7b2b0e3d82
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021524"
---
# <a name="async-programming-in-f"></a><span data-ttu-id="66b7b-103">Programación asíncrona en F\#</span><span class="sxs-lookup"><span data-stu-id="66b7b-103">Async programming in F\#</span></span>

<span data-ttu-id="66b7b-104">La programación asincrónica es un mecanismo que es esencial para las aplicaciones modernas por diversas razones.</span><span class="sxs-lookup"><span data-stu-id="66b7b-104">Asynchronous programming is a mechanism that is essential to modern applications for diverse reasons.</span></span> <span data-ttu-id="66b7b-105">Hay dos casos de uso principales que la mayoría de los desarrolladores encontrarán:</span><span class="sxs-lookup"><span data-stu-id="66b7b-105">There are two primary use cases that most developers will encounter:</span></span>

- <span data-ttu-id="66b7b-106">Presentar un proceso de servidor que puede dar servicio a un número significativo de solicitudes entrantes simultáneas, al tiempo que se minimizan los recursos del sistema ocupados mientras el procesamiento de solicitudes espera entradas de sistemas o servicios externos a ese proceso</span><span class="sxs-lookup"><span data-stu-id="66b7b-106">Presenting a server process that can service a significant number of concurrent incoming requests, while minimizing the system resources occupied while request processing awaits inputs from systems or services external to that process</span></span>
- <span data-ttu-id="66b7b-107">Mantener una interfaz de usuario responsiva o un subproceso principal mientras se progresa simultáneamente en el trabajo en segundo plano</span><span class="sxs-lookup"><span data-stu-id="66b7b-107">Maintaining a responsive UI or main thread while concurrently progressing background work</span></span>

<span data-ttu-id="66b7b-108">Aunque el trabajo en segundo plano a menudo implica la utilización de varios subprocesos, es importante tener en cuenta los conceptos de asincronía y multiproceso por separado.</span><span class="sxs-lookup"><span data-stu-id="66b7b-108">Although background work often does involve the utilization of multiple threads, it's important to consider the concepts of asynchrony and multi-threading separately.</span></span> <span data-ttu-id="66b7b-109">De hecho, son preocupaciones separadas, y una no implica la otra.</span><span class="sxs-lookup"><span data-stu-id="66b7b-109">In fact, they are separate concerns, and one does not imply the other.</span></span> <span data-ttu-id="66b7b-110">En este artículo se describen los conceptos separados con más detalle.</span><span class="sxs-lookup"><span data-stu-id="66b7b-110">This article describes the separate concepts in more detail.</span></span>

## <a name="asynchrony-defined"></a><span data-ttu-id="66b7b-111">Asincronía definida</span><span class="sxs-lookup"><span data-stu-id="66b7b-111">Asynchrony defined</span></span>

<span data-ttu-id="66b7b-112">El punto anterior - que la asincronía es independiente de la utilización de varios subprocesos - vale la pena explicar un poco más.</span><span class="sxs-lookup"><span data-stu-id="66b7b-112">The previous point - that asynchrony is independent of the utilization of multiple threads - is worth explaining a bit further.</span></span> <span data-ttu-id="66b7b-113">Hay tres conceptos que a veces están relacionados, pero estrictamente independientes entre sí:</span><span class="sxs-lookup"><span data-stu-id="66b7b-113">There are three concepts that are sometimes related, but strictly independent of one another:</span></span>

- <span data-ttu-id="66b7b-114">Simultaneidad; cuando se ejecutan varios cálculos en períodos de tiempo superpuestos.</span><span class="sxs-lookup"><span data-stu-id="66b7b-114">Concurrency; when multiple computations execute in overlapping time periods.</span></span>
- <span data-ttu-id="66b7b-115">Paralelismo; cuando varios cálculos o varias partes de un solo cálculo se ejecutan exactamente al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="66b7b-115">Parallelism; when multiple computations or several parts of a single computation run at exactly the same time.</span></span>
- <span data-ttu-id="66b7b-116">Asincronía; cuando uno o más cálculos se pueden ejecutar por separado del flujo principal del programa.</span><span class="sxs-lookup"><span data-stu-id="66b7b-116">Asynchrony; when one or more computations can execute separately from the main program flow.</span></span>

<span data-ttu-id="66b7b-117">Los tres son conceptos ortogonales, pero se pueden confundenr fácilmente, especialmente cuando se utilizan juntos.</span><span class="sxs-lookup"><span data-stu-id="66b7b-117">All three are orthogonal concepts, but can be easily conflated, especially when they are used together.</span></span> <span data-ttu-id="66b7b-118">Por ejemplo, es posible que deba ejecutar varios cálculos asincrónicos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="66b7b-118">For example, you may need to execute multiple asynchronous computations in parallel.</span></span> <span data-ttu-id="66b7b-119">Esta relación no significa que el paralelismo o la asincronía impliquen unos a otros.</span><span class="sxs-lookup"><span data-stu-id="66b7b-119">This relationship does not mean that parallelism or asynchrony imply one another.</span></span>

<span data-ttu-id="66b7b-120">Si considera la etimología de la palabra "asincrónico", hay dos piezas involucradas:</span><span class="sxs-lookup"><span data-stu-id="66b7b-120">If you consider the etymology of the word "asynchronous", there are two pieces involved:</span></span>

- <span data-ttu-id="66b7b-121">"a", que significa "no".</span><span class="sxs-lookup"><span data-stu-id="66b7b-121">"a", meaning "not".</span></span>
- <span data-ttu-id="66b7b-122">"sincrónico", que significa "al mismo tiempo".</span><span class="sxs-lookup"><span data-stu-id="66b7b-122">"synchronous", meaning "at the same time".</span></span>

<span data-ttu-id="66b7b-123">Cuando se juntan estos dos términos, verá que "asincrónico" significa "no al mismo tiempo".</span><span class="sxs-lookup"><span data-stu-id="66b7b-123">When you put these two terms together, you'll see that "asynchronous" means "not at the same time".</span></span> <span data-ttu-id="66b7b-124">Eso es todo.</span><span class="sxs-lookup"><span data-stu-id="66b7b-124">That's it!</span></span> <span data-ttu-id="66b7b-125">No hay ninguna implicación de simultaneidad o paralelismo en esta definición.</span><span class="sxs-lookup"><span data-stu-id="66b7b-125">There is no implication of concurrency or parallelism in this definition.</span></span> <span data-ttu-id="66b7b-126">Esto también es cierto en la práctica.</span><span class="sxs-lookup"><span data-stu-id="66b7b-126">This is also true in practice.</span></span>

<span data-ttu-id="66b7b-127">En términos prácticos, los cálculos asincrónicos en F- están programados para ejecutarse independientemente del flujo principal del programa.</span><span class="sxs-lookup"><span data-stu-id="66b7b-127">In practical terms, asynchronous computations in F# are scheduled to execute independently of the main program flow.</span></span> <span data-ttu-id="66b7b-128">Esta ejecución independiente no implica simultaneidad o paralelismo, ni implica que siempre se produce un cálculo en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="66b7b-128">This independent execution doesn't imply concurrency or parallelism, nor does it imply that a computation always happens in the background.</span></span> <span data-ttu-id="66b7b-129">De hecho, los cálculos asincrónicos pueden incluso ejecutarse sincrónicamente, dependiendo de la naturaleza del cálculo y el entorno en el que se ejecuta el cálculo.</span><span class="sxs-lookup"><span data-stu-id="66b7b-129">In fact, asynchronous computations can even execute synchronously, depending on the nature of the computation and the environment the computation is executing in.</span></span>

<span data-ttu-id="66b7b-130">La principal toma que debe tener es que los cálculos asincrónicos son independientes del flujo del programa principal.</span><span class="sxs-lookup"><span data-stu-id="66b7b-130">The main takeaway you should have is that asynchronous computations are independent of the main program flow.</span></span> <span data-ttu-id="66b7b-131">Aunque hay pocas garantías sobre cuándo o cómo se ejecuta un cálculo asincrónico, hay algunos enfoques para orquestarlos y programarlos.</span><span class="sxs-lookup"><span data-stu-id="66b7b-131">Although there are few guarantees about when or how an asynchronous computation executes, there are some approaches to orchestrating and scheduling them.</span></span> <span data-ttu-id="66b7b-132">En el resto de este artículo se exploran los conceptos básicos de la asincronía de F y cómo usar los tipos, funciones y expresiones integradas en F .</span><span class="sxs-lookup"><span data-stu-id="66b7b-132">The rest of this article explores core concepts for F# asynchrony and how to use the types, functions, and expressions built into F#.</span></span>

## <a name="core-concepts"></a><span data-ttu-id="66b7b-133">Conceptos principales</span><span class="sxs-lookup"><span data-stu-id="66b7b-133">Core concepts</span></span>

<span data-ttu-id="66b7b-134">En F, la programación asincrónica se centra en tres conceptos básicos:</span><span class="sxs-lookup"><span data-stu-id="66b7b-134">In F#, asynchronous programming is centered around three core concepts:</span></span>

- <span data-ttu-id="66b7b-135">El `Async<'T>` tipo, que representa un cálculo asincrónico componible.</span><span class="sxs-lookup"><span data-stu-id="66b7b-135">The `Async<'T>` type, which represents a composable asynchronous computation.</span></span>
- <span data-ttu-id="66b7b-136">Las `Async` funciones del módulo, que permiten programar el trabajo asincrónico, componer cálculos asincrónicos y transformar resultados asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="66b7b-136">The `Async` module functions, which let you schedule asynchronous work, compose asynchronous computations, and transform asynchronous results.</span></span>
- <span data-ttu-id="66b7b-137">La `async { }` [expresión de cálculo](../../language-reference/computation-expressions.md), que proporciona una sintaxis conveniente para crear y controlar cálculos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="66b7b-137">The `async { }` [computation expression](../../language-reference/computation-expressions.md), which provides a convenient syntax for building and controlling asynchronous computations.</span></span>

<span data-ttu-id="66b7b-138">Puede ver estos tres conceptos en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="66b7b-138">You can see these three concepts in the following example:</span></span>

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    printTotalFileBytes "path-to-file.txt"
    |> Async.RunSynchronously

    Console.Read() |> ignore
    0
```

<span data-ttu-id="66b7b-139">En el ejemplo, la `printTotalFileBytes` `string -> Async<unit>`función es de tipo .</span><span class="sxs-lookup"><span data-stu-id="66b7b-139">In the example, the `printTotalFileBytes` function is of type `string -> Async<unit>`.</span></span> <span data-ttu-id="66b7b-140">Llamar a la función no ejecuta realmente el cálculo asincrónico.</span><span class="sxs-lookup"><span data-stu-id="66b7b-140">Calling the function does not actually execute the asynchronous computation.</span></span> <span data-ttu-id="66b7b-141">En su lugar, devuelve un `Async<unit>` que actúa como una *especificación* del trabajo que se ejecuta de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="66b7b-141">Instead, it returns an `Async<unit>` that acts as a *specification* of the work that is to execute asynchronously.</span></span> <span data-ttu-id="66b7b-142">Llama `Async.AwaitTask` a su cuerpo, que convierte <xref:System.IO.File.ReadAllBytesAsync%2A> el resultado de un tipo adecuado.</span><span class="sxs-lookup"><span data-stu-id="66b7b-142">It calls `Async.AwaitTask` in its body, which converts the result of <xref:System.IO.File.ReadAllBytesAsync%2A> to an appropriate type.</span></span>

<span data-ttu-id="66b7b-143">Otra línea importante es `Async.RunSynchronously`la llamada a .</span><span class="sxs-lookup"><span data-stu-id="66b7b-143">Another important line is the call to `Async.RunSynchronously`.</span></span> <span data-ttu-id="66b7b-144">Esta es una de las funciones de inicio del módulo async a las que tendrá que llamar si desea ejecutar realmente un cálculo asincrónico de F.</span><span class="sxs-lookup"><span data-stu-id="66b7b-144">This is one of the Async module starting functions that you'll need to call if you want to actually execute an F# asynchronous computation.</span></span>

<span data-ttu-id="66b7b-145">Esta es una diferencia fundamental con el `async` estilo de programación de C/Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="66b7b-145">This is a fundamental difference with the C#/Visual Basic style of `async` programming.</span></span> <span data-ttu-id="66b7b-146">En F, los cálculos asincrónicos se pueden considerar como **tareas frías**.</span><span class="sxs-lookup"><span data-stu-id="66b7b-146">In F#, asynchronous computations can be thought of as **Cold tasks**.</span></span> <span data-ttu-id="66b7b-147">Deben iniciarse explícitamente para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="66b7b-147">They must be explicitly started to actually execute.</span></span> <span data-ttu-id="66b7b-148">Esto tiene algunas ventajas, ya que le permite combinar y secuenciar el trabajo asincrónico mucho más fácilmente que en C o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="66b7b-148">This has some advantages, as it allows you to combine and sequence asynchronous work much more easily than in C# or Visual Basic.</span></span>

## <a name="combine-asynchronous-computations"></a><span data-ttu-id="66b7b-149">Combinar cálculos asincrónicos</span><span class="sxs-lookup"><span data-stu-id="66b7b-149">Combine asynchronous computations</span></span>

<span data-ttu-id="66b7b-150">Este es un ejemplo que se basa en el anterior mediante la combinación de cálculos:</span><span class="sxs-lookup"><span data-stu-id="66b7b-150">Here is an example that builds upon the previous one by combining computations:</span></span>

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Parallel
    |> Async.Ignore
    |> Async.RunSynchronously

    0
```

<span data-ttu-id="66b7b-151">Como puede ver, `main` la función tiene bastantes llamadas más realizadas.</span><span class="sxs-lookup"><span data-stu-id="66b7b-151">As you can see, the `main` function has quite a few more calls made.</span></span> <span data-ttu-id="66b7b-152">Conceptualmente, hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="66b7b-152">Conceptually, it does the following:</span></span>

1. <span data-ttu-id="66b7b-153">Transforme los argumentos `Async<unit>` de línea `Array.map`de comandos en cálculos con .</span><span class="sxs-lookup"><span data-stu-id="66b7b-153">Transform the command-line arguments into `Async<unit>` computations with `Array.map`.</span></span>
2. <span data-ttu-id="66b7b-154">Cree `Async<'T[]>` un que programe `printTotalFileBytes` y ejecute los cálculos en paralelo cuando se ejecute.</span><span class="sxs-lookup"><span data-stu-id="66b7b-154">Create an `Async<'T[]>` that schedules and runs the `printTotalFileBytes` computations in parallel when it runs.</span></span>
3. <span data-ttu-id="66b7b-155">Cree `Async<unit>` un que ejecute el cálculo paralelo e ignore su resultado.</span><span class="sxs-lookup"><span data-stu-id="66b7b-155">Create an `Async<unit>` that will run the parallel computation and ignore its result.</span></span>
4. <span data-ttu-id="66b7b-156">Ejecute explícitamente el `Async.RunSynchronously` último cálculo con y bloquee hasta que se complete.</span><span class="sxs-lookup"><span data-stu-id="66b7b-156">Explicitly run the last computation with `Async.RunSynchronously` and block until it completes.</span></span>

<span data-ttu-id="66b7b-157">Cuando se ejecuta `printTotalFileBytes` este programa, se ejecuta en paralelo para cada argumento de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="66b7b-157">When this program runs, `printTotalFileBytes` runs in parallel for each command-line argument.</span></span> <span data-ttu-id="66b7b-158">Dado que los cálculos asincrónicos se ejecutan independientemente del flujo del programa, no hay ningún orden en el que impriman su información y terminen de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="66b7b-158">Because asynchronous computations execute independently of program flow, there is no order in which they print their information and finish executing.</span></span> <span data-ttu-id="66b7b-159">Los cálculos se programarán en paralelo, pero su orden de ejecución no está garantizado.</span><span class="sxs-lookup"><span data-stu-id="66b7b-159">The computations will be scheduled in parallel, but their order of execution is not guaranteed.</span></span>

## <a name="sequence-asynchronous-computations"></a><span data-ttu-id="66b7b-160">Secuenciar cálculos asincrónicos</span><span class="sxs-lookup"><span data-stu-id="66b7b-160">Sequence asynchronous computations</span></span>

<span data-ttu-id="66b7b-161">Dado `Async<'T>` que es una especificación de trabajo en lugar de una tarea que ya se está ejecutando, puede realizar transformaciones más complejas fácilmente.</span><span class="sxs-lookup"><span data-stu-id="66b7b-161">Because `Async<'T>` is a specification of work rather than an already-running task, you can perform more intricate transformations easily.</span></span> <span data-ttu-id="66b7b-162">Este es un ejemplo que secuencia un conjunto de cálculos asincrónicos para que se ejecuten uno tras otro.</span><span class="sxs-lookup"><span data-stu-id="66b7b-162">Here is an example that sequences a set of Async computations so they execute one after another.</span></span>

```fsharp
let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Sequential
    |> Async.Ignore
    |> Async.RunSynchronously
    |> ignore
```

<span data-ttu-id="66b7b-163">Esto se `printTotalFileBytes` programará para ejecutar en `argv` el orden de los elementos de en lugar de programarlos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="66b7b-163">This will schedule `printTotalFileBytes` to execute in the order of the elements of `argv` rather than scheduling them in parallel.</span></span> <span data-ttu-id="66b7b-164">Dado que el siguiente elemento no se programará hasta que el último cálculo haya terminado de ejecutarse, los cálculos se secuencian de forma que no haya superposición en su ejecución.</span><span class="sxs-lookup"><span data-stu-id="66b7b-164">Because the next item will not be scheduled until after the last computation has finished executing, the computations are sequenced such that there is no overlap in their execution.</span></span>

## <a name="important-async-module-functions"></a><span data-ttu-id="66b7b-165">Funciones importantes del módulo asincrónico</span><span class="sxs-lookup"><span data-stu-id="66b7b-165">Important Async module functions</span></span>

<span data-ttu-id="66b7b-166">Cuando se escribe código asincrónico en F, normalmente interactuará con un marco de trabajo que controla la programación de cálculos automáticamente.</span><span class="sxs-lookup"><span data-stu-id="66b7b-166">When you write async code in F#, you'll usually interact with a framework that handles scheduling of computations for you.</span></span> <span data-ttu-id="66b7b-167">Sin embargo, este no siempre es el caso, por lo que es bueno aprender las diversas funciones de inicio para programar el trabajo asincrónico.</span><span class="sxs-lookup"><span data-stu-id="66b7b-167">However, this is not always the case, so it is good to learn the various starting functions to schedule asynchronous work.</span></span>

<span data-ttu-id="66b7b-168">Debido a que los cálculos asincrónicos de F son una _especificación_ de trabajo en lugar de una representación del trabajo que ya se está ejecutando, deben iniciarse explícitamente con una función de inicio.</span><span class="sxs-lookup"><span data-stu-id="66b7b-168">Because F# asynchronous computations are a _specification_ of work rather than a representation of work that is already executing, they must be explicitly started with a starting function.</span></span> <span data-ttu-id="66b7b-169">Hay muchas [funciones de inicio async](https://msdn.microsoft.com/library/ee370232.aspx) que son útiles en diferentes contextos.</span><span class="sxs-lookup"><span data-stu-id="66b7b-169">There are many [Async starting functions](https://msdn.microsoft.com/library/ee370232.aspx) that are helpful in different contexts.</span></span> <span data-ttu-id="66b7b-170">En la siguiente sección se describen algunas de las funciones de inicio más comunes.</span><span class="sxs-lookup"><span data-stu-id="66b7b-170">The following section describes some of the more common starting functions.</span></span>

### <a name="asyncstartchild"></a><span data-ttu-id="66b7b-171">Async.StartChild</span><span class="sxs-lookup"><span data-stu-id="66b7b-171">Async.StartChild</span></span>

<span data-ttu-id="66b7b-172">Inicia un cálculo secundario dentro de un cálculo asincrónico.</span><span class="sxs-lookup"><span data-stu-id="66b7b-172">Starts a child computation within an asynchronous computation.</span></span> <span data-ttu-id="66b7b-173">Esto permite que varios cálculos asincrónicos se ejecuten simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="66b7b-173">This allows multiple asynchronous computations to be executed concurrently.</span></span> <span data-ttu-id="66b7b-174">El cálculo secundario comparte un token de cancelación con el cálculo primario.</span><span class="sxs-lookup"><span data-stu-id="66b7b-174">The child computation shares a cancellation token with the parent computation.</span></span> <span data-ttu-id="66b7b-175">Si se cancela el cálculo primario, también se cancela el cálculo secundario.</span><span class="sxs-lookup"><span data-stu-id="66b7b-175">If the parent computation is canceled, the child computation is also canceled.</span></span>

<span data-ttu-id="66b7b-176">Signature:</span><span class="sxs-lookup"><span data-stu-id="66b7b-176">Signature:</span></span>

```fsharp
computation: Async<'T> * timeout: ?int -> Async<Async<'T>>
```

<span data-ttu-id="66b7b-177">Cuándo usarlo:</span><span class="sxs-lookup"><span data-stu-id="66b7b-177">When to use:</span></span>

- <span data-ttu-id="66b7b-178">Si desea ejecutar varios cálculos asincrónicos simultáneamente en lugar de uno a la vez, pero no tenerlos programados en paralelo.</span><span class="sxs-lookup"><span data-stu-id="66b7b-178">When you want to execute multiple asynchronous computations concurrently rather than one at a time, but not have them scheduled in parallel.</span></span>
- <span data-ttu-id="66b7b-179">Cuando desea vincular la duración de un cálculo secundario a la de un cálculo primario.</span><span class="sxs-lookup"><span data-stu-id="66b7b-179">When you wish to tie the lifetime of a child computation to that of a parent computation.</span></span>

<span data-ttu-id="66b7b-180">Qué tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="66b7b-180">What to watch out for:</span></span>

- <span data-ttu-id="66b7b-181">Iniciar varios cálculos con `Async.StartChild` no es lo mismo que programarlos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="66b7b-181">Starting multiple computations with `Async.StartChild` isn't the same as scheduling them in parallel.</span></span> <span data-ttu-id="66b7b-182">Si desea programar cálculos en `Async.Parallel`paralelo, utilice .</span><span class="sxs-lookup"><span data-stu-id="66b7b-182">If you wish to schedule computations in parallel, use `Async.Parallel`.</span></span>
- <span data-ttu-id="66b7b-183">La cancelación de un cálculo primario desencadenará la cancelación de todos los cálculos secundarios que inició.</span><span class="sxs-lookup"><span data-stu-id="66b7b-183">Canceling a parent computation will trigger cancellation of all child computations it started.</span></span>

### <a name="asyncstartimmediate"></a><span data-ttu-id="66b7b-184">Async.StartImmediate</span><span class="sxs-lookup"><span data-stu-id="66b7b-184">Async.StartImmediate</span></span>

<span data-ttu-id="66b7b-185">Ejecuta un cálculo asincrónico y comienza inmediatamente en el subproceso actual del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="66b7b-185">Runs an asynchronous computation, starting immediately on the current operating system thread.</span></span> <span data-ttu-id="66b7b-186">Esto es útil si necesita actualizar algo en el subproceso que realiza la llamada durante el cálculo.</span><span class="sxs-lookup"><span data-stu-id="66b7b-186">This is helpful if you need to update something on the calling thread during the computation.</span></span> <span data-ttu-id="66b7b-187">Por ejemplo, si un cálculo asincrónico debe actualizar una `Async.StartImmediate` interfaz de usuario (por ejemplo, actualizar una barra de progreso), debe usarse.</span><span class="sxs-lookup"><span data-stu-id="66b7b-187">For example, if an asynchronous computation must update a UI (such as updating a progress bar), then `Async.StartImmediate` should be used.</span></span>

<span data-ttu-id="66b7b-188">Signature:</span><span class="sxs-lookup"><span data-stu-id="66b7b-188">Signature:</span></span>

```fsharp
computation: Async<unit> * cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="66b7b-189">Cuándo usarlo:</span><span class="sxs-lookup"><span data-stu-id="66b7b-189">When to use:</span></span>

- <span data-ttu-id="66b7b-190">Cuando necesite actualizar algo en el subproceso que realiza la llamada en medio de un cálculo asincrónico.</span><span class="sxs-lookup"><span data-stu-id="66b7b-190">When you need to update something on the calling thread in the middle of an asynchronous computation.</span></span>

<span data-ttu-id="66b7b-191">Qué tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="66b7b-191">What to watch out for:</span></span>

- <span data-ttu-id="66b7b-192">El código del cálculo asincrónico se ejecutará en cualquier subproceso en el que se programe.</span><span class="sxs-lookup"><span data-stu-id="66b7b-192">Code in the asynchronous computation will run on whatever thread one happens to be scheduled on.</span></span> <span data-ttu-id="66b7b-193">Esto puede ser problemático si ese subproceso es de alguna manera sensible, como un subproceso de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="66b7b-193">This can be problematic if that thread is in some way sensitive, such as a UI thread.</span></span> <span data-ttu-id="66b7b-194">En tales `Async.StartImmediate` casos, es probable que no sea apropiado de usar.</span><span class="sxs-lookup"><span data-stu-id="66b7b-194">In such cases, `Async.StartImmediate` is likely inappropriate to use.</span></span>

### <a name="asyncstartastask"></a><span data-ttu-id="66b7b-195">Async.StartAsTask</span><span class="sxs-lookup"><span data-stu-id="66b7b-195">Async.StartAsTask</span></span>

<span data-ttu-id="66b7b-196">Ejecuta un cálculo en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="66b7b-196">Executes a computation in the thread pool.</span></span> <span data-ttu-id="66b7b-197">Devuelve <xref:System.Threading.Tasks.Task%601> un que se completará en el estado correspondiente una vez que finalice el cálculo (produce el resultado, produce una excepción o se cancela).</span><span class="sxs-lookup"><span data-stu-id="66b7b-197">Returns a <xref:System.Threading.Tasks.Task%601> that will be completed on the corresponding state once the computation terminates (produces the result, throws exception, or gets canceled).</span></span> <span data-ttu-id="66b7b-198">Si no se proporciona ningún token de cancelación, se usa el token de cancelación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="66b7b-198">If no cancellation token is provided, then the default cancellation token is used.</span></span>

<span data-ttu-id="66b7b-199">Signature:</span><span class="sxs-lookup"><span data-stu-id="66b7b-199">Signature:</span></span>

```fsharp
computation: Async<'T> * taskCreationOptions: ?TaskCreationOptions * cancellationToken: ?CancellationToken -> Task<'T>
```

<span data-ttu-id="66b7b-200">Cuándo usarlo:</span><span class="sxs-lookup"><span data-stu-id="66b7b-200">When to use:</span></span>

- <span data-ttu-id="66b7b-201">Cuando necesite llamar a una API de <xref:System.Threading.Tasks.Task%601> .NET que espera que represente el resultado de un cálculo asincrónico.</span><span class="sxs-lookup"><span data-stu-id="66b7b-201">When you need to call into a .NET API that expects a <xref:System.Threading.Tasks.Task%601> to represent the result of an asynchronous computation.</span></span>

<span data-ttu-id="66b7b-202">Qué tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="66b7b-202">What to watch out for:</span></span>

- <span data-ttu-id="66b7b-203">Esta llamada asignará `Task` un objeto adicional, que puede aumentar la sobrecarga si se utiliza con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="66b7b-203">This call will allocate an additional `Task` object, which can increase overhead if it is used often.</span></span>

### <a name="asyncparallel"></a><span data-ttu-id="66b7b-204">Async.Parallel</span><span class="sxs-lookup"><span data-stu-id="66b7b-204">Async.Parallel</span></span>

<span data-ttu-id="66b7b-205">Programa una secuencia de cálculos asincrónicos que se ejecutarán en paralelo.</span><span class="sxs-lookup"><span data-stu-id="66b7b-205">Schedules a sequence of asynchronous computations to be executed in parallel.</span></span> <span data-ttu-id="66b7b-206">El grado de paralelismo se puede ajustar/limitar `maxDegreesOfParallelism` opcionalmente especificando el parámetro.</span><span class="sxs-lookup"><span data-stu-id="66b7b-206">The degree of parallelism can be optionally tuned/throttled by specifying the `maxDegreesOfParallelism` parameter.</span></span>

<span data-ttu-id="66b7b-207">Signature:</span><span class="sxs-lookup"><span data-stu-id="66b7b-207">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> * ?maxDegreesOfParallelism: int -> Async<'T[]>
```

<span data-ttu-id="66b7b-208">Cuándo usarlo</span><span class="sxs-lookup"><span data-stu-id="66b7b-208">When to use it:</span></span>

- <span data-ttu-id="66b7b-209">Si necesita ejecutar un conjunto de cálculos al mismo tiempo y no depende de su orden de ejecución.</span><span class="sxs-lookup"><span data-stu-id="66b7b-209">If you need to run a set of computations at the same time and have no reliance on their order of execution.</span></span>
- <span data-ttu-id="66b7b-210">Si no necesita resultados de cálculos programados en paralelo hasta que se hayan completado todos.</span><span class="sxs-lookup"><span data-stu-id="66b7b-210">If you don't require results from computations scheduled in parallel until they have all completed.</span></span>

<span data-ttu-id="66b7b-211">Qué tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="66b7b-211">What to watch out for:</span></span>

- <span data-ttu-id="66b7b-212">Solo puede acceder a la matriz resultante de valores una vez que todos los cálculos han finalizado.</span><span class="sxs-lookup"><span data-stu-id="66b7b-212">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="66b7b-213">Los cálculos se ejecutarán siempre que terminen programados.</span><span class="sxs-lookup"><span data-stu-id="66b7b-213">Computations will be run whenever they end up getting scheduled.</span></span> <span data-ttu-id="66b7b-214">Este comportamiento significa que no puede confiar en su orden de ejecución.</span><span class="sxs-lookup"><span data-stu-id="66b7b-214">This behavior means you cannot rely on their order of their execution.</span></span>

### <a name="asyncsequential"></a><span data-ttu-id="66b7b-215">Async.Sequential</span><span class="sxs-lookup"><span data-stu-id="66b7b-215">Async.Sequential</span></span>

<span data-ttu-id="66b7b-216">Programa una secuencia de cálculos asincrónicos que se ejecutarán en el orden en que se pasan.</span><span class="sxs-lookup"><span data-stu-id="66b7b-216">Schedules a sequence of asynchronous computations to be executed in the order that they are passed.</span></span> <span data-ttu-id="66b7b-217">Se ejecutará el primer cálculo, luego el siguiente, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="66b7b-217">The first computation will be executed, then the next, and so on.</span></span> <span data-ttu-id="66b7b-218">No se ejecutarán cálculos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="66b7b-218">No computations will be executed in parallel.</span></span>

<span data-ttu-id="66b7b-219">Signature:</span><span class="sxs-lookup"><span data-stu-id="66b7b-219">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

<span data-ttu-id="66b7b-220">Cuándo usarlo</span><span class="sxs-lookup"><span data-stu-id="66b7b-220">When to use it:</span></span>

- <span data-ttu-id="66b7b-221">Si necesita ejecutar varios cálculos en orden.</span><span class="sxs-lookup"><span data-stu-id="66b7b-221">If you need to execute multiple computations in order.</span></span>

<span data-ttu-id="66b7b-222">Qué tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="66b7b-222">What to watch out for:</span></span>

- <span data-ttu-id="66b7b-223">Solo puede acceder a la matriz resultante de valores una vez que todos los cálculos han finalizado.</span><span class="sxs-lookup"><span data-stu-id="66b7b-223">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="66b7b-224">Los cálculos se ejecutarán en el orden en que se pasan a esta función, lo que puede significar que transcurrirá más tiempo antes de que se devuelvan los resultados.</span><span class="sxs-lookup"><span data-stu-id="66b7b-224">Computations will be run in the order that they are passed to this function, which can mean that more time will elapse before the results are returned.</span></span>

### <a name="asyncawaittask"></a><span data-ttu-id="66b7b-225">Async.AwaitTask</span><span class="sxs-lookup"><span data-stu-id="66b7b-225">Async.AwaitTask</span></span>

<span data-ttu-id="66b7b-226">Devuelve un cálculo asincrónico <xref:System.Threading.Tasks.Task%601> que espera a que se complete el dado y devuelve su resultado como un`Async<'T>`</span><span class="sxs-lookup"><span data-stu-id="66b7b-226">Returns an asynchronous computation that waits for the given <xref:System.Threading.Tasks.Task%601> to complete and returns its result as an `Async<'T>`</span></span>

<span data-ttu-id="66b7b-227">Signature:</span><span class="sxs-lookup"><span data-stu-id="66b7b-227">Signature:</span></span>

```fsharp
task: Task<'T> -> Async<'T>
```

<span data-ttu-id="66b7b-228">Cuándo usarlo:</span><span class="sxs-lookup"><span data-stu-id="66b7b-228">When to use:</span></span>

- <span data-ttu-id="66b7b-229">Cuando se consume una API de <xref:System.Threading.Tasks.Task%601> .NET que devuelve un cálculo asincrónico dentro de F .</span><span class="sxs-lookup"><span data-stu-id="66b7b-229">When you are consuming a .NET API that returns a <xref:System.Threading.Tasks.Task%601> within an F# asynchronous computation.</span></span>

<span data-ttu-id="66b7b-230">Qué tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="66b7b-230">What to watch out for:</span></span>

- <span data-ttu-id="66b7b-231">Las excepciones se <xref:System.AggregateException> ajustan siguiendo la convención de la biblioteca de tareas paralelas y este comportamiento es diferente de cómo se asincrónico de F - generalmente expone excepciones.</span><span class="sxs-lookup"><span data-stu-id="66b7b-231">Exceptions are wrapped in <xref:System.AggregateException> following the convention of the Task Parallel Library, and this behavior is different from how F# async generally surfaces exceptions.</span></span>

### <a name="asynccatch"></a><span data-ttu-id="66b7b-232">Async.Catch</span><span class="sxs-lookup"><span data-stu-id="66b7b-232">Async.Catch</span></span>

<span data-ttu-id="66b7b-233">Crea un cálculo asincrónico `Async<'T>`que ejecuta `Async<Choice<'T, exn>>`un determinado , devolviendo un archivo .</span><span class="sxs-lookup"><span data-stu-id="66b7b-233">Creates an asynchronous computation that executes a given `Async<'T>`, returning an `Async<Choice<'T, exn>>`.</span></span> <span data-ttu-id="66b7b-234">Si el `Async<'T>` especificado se completa `Choice1Of2` correctamente, se devuelve a con el valor resultante.</span><span class="sxs-lookup"><span data-stu-id="66b7b-234">If the given `Async<'T>` completes successfully, then a `Choice1Of2` is returned with the resultant value.</span></span> <span data-ttu-id="66b7b-235">Si se produce una excepción antes `Choice2of2` de que se complete, se devuelve a a con la excepción provocada.</span><span class="sxs-lookup"><span data-stu-id="66b7b-235">If an exception is thrown before it completes, then a `Choice2of2` is returned with the raised exception.</span></span> <span data-ttu-id="66b7b-236">Si se utiliza en un cálculo asincrónico que se compone de muchos cálculos y uno de esos cálculos produce una excepción, el cálculo que abarca se detendrá por completo.</span><span class="sxs-lookup"><span data-stu-id="66b7b-236">If it is used on an asynchronous computation that is itself composed of many computations, and one of those computations throws an exception, the encompassing computation will be stopped entirely.</span></span>

<span data-ttu-id="66b7b-237">Signature:</span><span class="sxs-lookup"><span data-stu-id="66b7b-237">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

<span data-ttu-id="66b7b-238">Cuándo usarlo:</span><span class="sxs-lookup"><span data-stu-id="66b7b-238">When to use:</span></span>

- <span data-ttu-id="66b7b-239">Al realizar un trabajo asincrónico que puede producir un error con una excepción y desea controlar esa excepción en el llamador.</span><span class="sxs-lookup"><span data-stu-id="66b7b-239">When you are performing asynchronous work that may fail with an exception and you want to handle that exception in the caller.</span></span>

<span data-ttu-id="66b7b-240">Qué tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="66b7b-240">What to watch out for:</span></span>

- <span data-ttu-id="66b7b-241">Cuando se utilizan cálculos asincrónicos combinados o secuenciados, el cálculo que abarca se detendrá por completo si uno de sus cálculos "internos" produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="66b7b-241">When using combined or sequenced asynchronous computations, the encompassing computation will fully stop if one of its "internal" computations throws an exception.</span></span>

### <a name="asyncignore"></a><span data-ttu-id="66b7b-242">Async.Ignore</span><span class="sxs-lookup"><span data-stu-id="66b7b-242">Async.Ignore</span></span>

<span data-ttu-id="66b7b-243">Crea un cálculo asincrónico que ejecuta el cálculo especificado y omite su resultado.</span><span class="sxs-lookup"><span data-stu-id="66b7b-243">Creates an asynchronous computation that runs the given computation and ignores its result.</span></span>

<span data-ttu-id="66b7b-244">Signature:</span><span class="sxs-lookup"><span data-stu-id="66b7b-244">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<unit>
```

<span data-ttu-id="66b7b-245">Cuándo usarlo:</span><span class="sxs-lookup"><span data-stu-id="66b7b-245">When to use:</span></span>

- <span data-ttu-id="66b7b-246">Cuando tiene un cálculo asincrónico cuyo resultado no es necesario.</span><span class="sxs-lookup"><span data-stu-id="66b7b-246">When you have an asynchronous computation whose result is not needed.</span></span> <span data-ttu-id="66b7b-247">Esto es análogo `ignore` al código para el código no asincrónico.</span><span class="sxs-lookup"><span data-stu-id="66b7b-247">This is analogous to the `ignore` code for non-asynchronous code.</span></span>

<span data-ttu-id="66b7b-248">Qué tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="66b7b-248">What to watch out for:</span></span>

- <span data-ttu-id="66b7b-249">Si debe `Async.Ignore` utilizar porque desea `Async.Start` utilizar u otra `Async<unit>`función que requiera, considere si descartar el resultado está bien.</span><span class="sxs-lookup"><span data-stu-id="66b7b-249">If you must use `Async.Ignore` because you wish to use `Async.Start` or another function that requires `Async<unit>`, consider if discarding the result is okay.</span></span> <span data-ttu-id="66b7b-250">Evite descartar los resultados solo para ajustarse a una firma de tipo.</span><span class="sxs-lookup"><span data-stu-id="66b7b-250">Avoid discarding results just to fit a type signature.</span></span>

### <a name="asyncrunsynchronously"></a><span data-ttu-id="66b7b-251">Async.RunSynchronously</span><span class="sxs-lookup"><span data-stu-id="66b7b-251">Async.RunSynchronously</span></span>

<span data-ttu-id="66b7b-252">Ejecuta un cálculo asincrónico y espera su resultado en el subproceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="66b7b-252">Runs an asynchronous computation and awaits its result on the calling thread.</span></span> <span data-ttu-id="66b7b-253">Esta llamada está bloqueando.</span><span class="sxs-lookup"><span data-stu-id="66b7b-253">This call is blocking.</span></span>

<span data-ttu-id="66b7b-254">Signature:</span><span class="sxs-lookup"><span data-stu-id="66b7b-254">Signature:</span></span>

```fsharp
computation: Async<'T> * timeout: ?int * cancellationToken: ?CancellationToken -> 'T
```

<span data-ttu-id="66b7b-255">Cuándo usarlo</span><span class="sxs-lookup"><span data-stu-id="66b7b-255">When to use it:</span></span>

- <span data-ttu-id="66b7b-256">Si lo necesita, úselo solo una vez en una aplicación - en el punto de entrada para un ejecutable.</span><span class="sxs-lookup"><span data-stu-id="66b7b-256">If you need it, use it only once in an application - at the entry point for an executable.</span></span>
- <span data-ttu-id="66b7b-257">Cuando no le importa el rendimiento y desea ejecutar un conjunto de otras operaciones asincrónicas a la vez.</span><span class="sxs-lookup"><span data-stu-id="66b7b-257">When you don't care about performance and want to execute a set of other asynchronous operations at once.</span></span>

<span data-ttu-id="66b7b-258">Qué tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="66b7b-258">What to watch out for:</span></span>

- <span data-ttu-id="66b7b-259">Al `Async.RunSynchronously` llamar, se bloquea el subproceso que realiza la llamada hasta que se completa la ejecución.</span><span class="sxs-lookup"><span data-stu-id="66b7b-259">Calling `Async.RunSynchronously` blocks the calling thread until the execution completes.</span></span>

### <a name="asyncstart"></a><span data-ttu-id="66b7b-260">Async.Start</span><span class="sxs-lookup"><span data-stu-id="66b7b-260">Async.Start</span></span>

<span data-ttu-id="66b7b-261">Inicia un cálculo asincrónico `unit`en el grupo de subprocesos que devuelve .</span><span class="sxs-lookup"><span data-stu-id="66b7b-261">Starts an asynchronous computation in the thread pool that returns `unit`.</span></span> <span data-ttu-id="66b7b-262">No espera su resultado.</span><span class="sxs-lookup"><span data-stu-id="66b7b-262">Doesn't wait for its result.</span></span> <span data-ttu-id="66b7b-263">Los cálculos `Async.Start` anidados iniciados con se inician independientemente del cálculo primario que los llamó.</span><span class="sxs-lookup"><span data-stu-id="66b7b-263">Nested computations started with `Async.Start` are started independently of the parent computation that called them.</span></span> <span data-ttu-id="66b7b-264">Su vida útil no está vinculada a ningún cálculo principal.</span><span class="sxs-lookup"><span data-stu-id="66b7b-264">Their lifetime is not tied to any parent computation.</span></span> <span data-ttu-id="66b7b-265">Si se cancela el cálculo primario, no se cancela ningún cálculo secundario.</span><span class="sxs-lookup"><span data-stu-id="66b7b-265">If the parent computation is canceled, no child computations are canceled.</span></span>

<span data-ttu-id="66b7b-266">Signature:</span><span class="sxs-lookup"><span data-stu-id="66b7b-266">Signature:</span></span>

```fsharp
computation: Async<unit> * cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="66b7b-267">Utilícelo solo cuando:</span><span class="sxs-lookup"><span data-stu-id="66b7b-267">Use only when:</span></span>

- <span data-ttu-id="66b7b-268">Tiene un cálculo asincrónico que no produce un resultado y/o requiere el procesamiento de uno.</span><span class="sxs-lookup"><span data-stu-id="66b7b-268">You have an asynchronous computation that doesn't yield a result and/or require processing of one.</span></span>
- <span data-ttu-id="66b7b-269">No es necesario saber cuándo se completa un cálculo asincrónico.</span><span class="sxs-lookup"><span data-stu-id="66b7b-269">You don't need to know when an asynchronous computation completes.</span></span>
- <span data-ttu-id="66b7b-270">No le importa en qué subproceso se ejecute un cálculo asincrónico.</span><span class="sxs-lookup"><span data-stu-id="66b7b-270">You don't care which thread an asynchronous computation runs on.</span></span>
- <span data-ttu-id="66b7b-271">No es necesario tener en cuenta o notificar excepciones resultantes de la tarea.</span><span class="sxs-lookup"><span data-stu-id="66b7b-271">You don't have any need to be aware of or report exceptions resulting from the task.</span></span>

<span data-ttu-id="66b7b-272">Qué tener en cuenta:</span><span class="sxs-lookup"><span data-stu-id="66b7b-272">What to watch out for:</span></span>

- <span data-ttu-id="66b7b-273">Las excepciones provocadas por `Async.Start` los cálculos iniciados con no se propagan al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="66b7b-273">Exceptions raised by computations started with `Async.Start` aren't propagated to the caller.</span></span> <span data-ttu-id="66b7b-274">La pila de llamadas será completamente desenrollada.</span><span class="sxs-lookup"><span data-stu-id="66b7b-274">The call stack will be completely unwound.</span></span>
- <span data-ttu-id="66b7b-275">Cualquier trabajo (como `printfn`la `Async.Start` llamada) iniciado con no hará que el efecto ocurra en el subproceso principal de la ejecución de un programa.</span><span class="sxs-lookup"><span data-stu-id="66b7b-275">Any work (such as calling `printfn`) started with `Async.Start` won't cause the effect to happen on the main thread of a program's execution.</span></span>

## <a name="interoperate-with-net"></a><span data-ttu-id="66b7b-276">Interoperar con .NET</span><span class="sxs-lookup"><span data-stu-id="66b7b-276">Interoperate with .NET</span></span>

<span data-ttu-id="66b7b-277">Es posible que esté trabajando con una biblioteca de .NET o un código base de código que use programación asincrónica [async/await](../../../standard/async.md)-style.</span><span class="sxs-lookup"><span data-stu-id="66b7b-277">You may be working with a .NET library or C# codebase that uses [async/await](../../../standard/async.md)-style asynchronous programming.</span></span> <span data-ttu-id="66b7b-278">Debido a que la mayoría de las <xref:System.Threading.Tasks.Task%601> <xref:System.Threading.Tasks.Task> bibliotecas de .NET usan `Async<'T>`los tipos y como sus abstracciones principales en lugar de , debe cruzar un límite entre estos dos enfoques de asincronía.</span><span class="sxs-lookup"><span data-stu-id="66b7b-278">Because C# and the majority of .NET libraries use the <xref:System.Threading.Tasks.Task%601> and <xref:System.Threading.Tasks.Task> types as their core abstractions rather than `Async<'T>`, you must cross a boundary between these two approaches to asynchrony.</span></span>

### <a name="how-to-work-with-net-async-and-taskt"></a><span data-ttu-id="66b7b-279">Cómo trabajar con .NET async y`Task<T>`</span><span class="sxs-lookup"><span data-stu-id="66b7b-279">How to work with .NET async and `Task<T>`</span></span>

<span data-ttu-id="66b7b-280">Trabajar con bibliotecas asincrónicas de <xref:System.Threading.Tasks.Task%601> .NET y bases de código que usan (es decir, cálculos asincrónicos que tienen valores devueltos) es sencillo y tiene compatibilidad integrada con F .</span><span class="sxs-lookup"><span data-stu-id="66b7b-280">Working with .NET async libraries and codebases that use <xref:System.Threading.Tasks.Task%601> (that is, async computations that have return values) is straightforward and has built-in support with F#.</span></span>

<span data-ttu-id="66b7b-281">Puede utilizar `Async.AwaitTask` la función para esperar un cálculo asincrónico de .NET:</span><span class="sxs-lookup"><span data-stu-id="66b7b-281">You can use the `Async.AwaitTask` function to await a .NET asynchronous computation:</span></span>

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

<span data-ttu-id="66b7b-282">Puede utilizar `Async.StartAsTask` la función para pasar un cálculo asincrónico a un llamador de .NET:</span><span class="sxs-lookup"><span data-stu-id="66b7b-282">You can use the `Async.StartAsTask` function to pass an asynchronous computation to a .NET caller:</span></span>

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a><span data-ttu-id="66b7b-283">Cómo trabajar con .NET async y`Task`</span><span class="sxs-lookup"><span data-stu-id="66b7b-283">How to work with .NET async and `Task`</span></span>

<span data-ttu-id="66b7b-284">Para trabajar con las <xref:System.Threading.Tasks.Task> API que usan (es decir, cálculos asincrónicos de .NET que `Async<'T>` no <xref:System.Threading.Tasks.Task>devuelven un valor), es posible que deba agregar una función adicional que convierta un valor en :</span><span class="sxs-lookup"><span data-stu-id="66b7b-284">To work with APIs that use <xref:System.Threading.Tasks.Task> (that is, .NET async computations that do not return a value), you may need to add an additional function that will convert an `Async<'T>` to a <xref:System.Threading.Tasks.Task>:</span></span>

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

<span data-ttu-id="66b7b-285">Ya hay `Async.AwaitTask` un que <xref:System.Threading.Tasks.Task> acepta un como entrada.</span><span class="sxs-lookup"><span data-stu-id="66b7b-285">There is already an `Async.AwaitTask` that accepts a <xref:System.Threading.Tasks.Task> as input.</span></span> <span data-ttu-id="66b7b-286">Con esta y `startTaskFromAsyncUnit` la función definida <xref:System.Threading.Tasks.Task> anteriormente, puede iniciar y esperar tipos desde un cálculo asincrónico de F .</span><span class="sxs-lookup"><span data-stu-id="66b7b-286">With this and the previously defined `startTaskFromAsyncUnit` function, you can start and await <xref:System.Threading.Tasks.Task> types from an F# async computation.</span></span>

## <a name="relationship-to-multi-threading"></a><span data-ttu-id="66b7b-287">Relación con el multi-threading</span><span class="sxs-lookup"><span data-stu-id="66b7b-287">Relationship to multi-threading</span></span>

<span data-ttu-id="66b7b-288">Aunque el enhebrado se menciona a lo largo de este artículo, hay dos cosas importantes que debe recordar:</span><span class="sxs-lookup"><span data-stu-id="66b7b-288">Although threading is mentioned throughout this article, there are two important things to remember:</span></span>

1. <span data-ttu-id="66b7b-289">No hay afinidad entre un cálculo asincrónico y un subproceso, a menos que se inicie explícitamente en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="66b7b-289">There is no affinity between an asynchronous computation and a thread, unless explicitly started on the current thread.</span></span>
1. <span data-ttu-id="66b7b-290">La programación asincrónica en F no es una abstracción para multiproceso.</span><span class="sxs-lookup"><span data-stu-id="66b7b-290">Asynchronous programming in F# is not an abstraction for multi-threading.</span></span>

<span data-ttu-id="66b7b-291">Por ejemplo, un cálculo puede ejecutarse realmente en el subproceso de su llamador, dependiendo de la naturaleza del trabajo.</span><span class="sxs-lookup"><span data-stu-id="66b7b-291">For example, a computation may actually run on its caller's thread, depending on the nature of the work.</span></span> <span data-ttu-id="66b7b-292">Un cálculo también podría "saltar" entre subprocesos, tomándolos prestados durante una pequeña cantidad de tiempo para realizar un trabajo útil entre períodos de "espera" (por ejemplo, cuando una llamada de red está en tránsito).</span><span class="sxs-lookup"><span data-stu-id="66b7b-292">A computation could also "jump" between threads, borrowing them for a small amount of time to do useful work in between periods of "waiting" (such as when a network call is in transit).</span></span>

<span data-ttu-id="66b7b-293">Aunque F- proporciona algunas capacidades para iniciar un cálculo asincrónico en el subproceso actual (o explícitamente no en el subproceso actual), la asincronía generalmente no está asociada a una estrategia de subprocesos determinada.</span><span class="sxs-lookup"><span data-stu-id="66b7b-293">Although F# provides some abilities to start an asynchronous computation on the current thread (or explicitly not on the current thread), asynchrony generally is not associated with a particular threading strategy.</span></span>

## <a name="see-also"></a><span data-ttu-id="66b7b-294">Vea también</span><span class="sxs-lookup"><span data-stu-id="66b7b-294">See also</span></span>

- [<span data-ttu-id="66b7b-295">El modelo de programación asincrónica de F</span><span class="sxs-lookup"><span data-stu-id="66b7b-295">The F# Asynchronous Programming Model</span></span>](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [<span data-ttu-id="66b7b-296">Guía asincrona de F'com</span><span class="sxs-lookup"><span data-stu-id="66b7b-296">Jet.com's F# Async Guide</span></span>](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [<span data-ttu-id="66b7b-297">Para la diversión y la guía de programación asincrónica de beneficios</span><span class="sxs-lookup"><span data-stu-id="66b7b-297">F# for fun and profit's Asynchronous Programming guide</span></span>](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [<span data-ttu-id="66b7b-298">Asincrónico en C- y F-: gotchas asincrónicos en C #</span><span class="sxs-lookup"><span data-stu-id="66b7b-298">Async in C# and F#: Asynchronous gotchas in C#</span></span>](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
