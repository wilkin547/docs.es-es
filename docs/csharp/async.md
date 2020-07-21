---
title: 'Programación asincrónica: C#'
description: Obtenga información sobre el modelo de programación asincrónico de nivel de lenguaje de C# que proporciona .NET Core.
author: cartermp
ms.date: 05/20/2020
ms.technology: csharp-async
ms.assetid: b878c34c-a78f-419e-a594-a2b44fa521a4
ms.openlocfilehash: bcea584ded6985a0ef166ab8e24672a19e27b0a3
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2020
ms.locfileid: "86415980"
---
# <a name="asynchronous-programming"></a><span data-ttu-id="a9562-103">Programación asincrónica</span><span class="sxs-lookup"><span data-stu-id="a9562-103">Asynchronous programming</span></span>

<span data-ttu-id="a9562-104">Si tiene cualquier necesidad enlazada a E/S (por ejemplo, solicitar datos de una red, acceder a una base de datos o leer y escribir un sistema de archivos), deberá usar la programación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="a9562-104">If you have any I/O-bound needs (such as requesting data from a network, accessing a database, or reading and writing to a file system), you'll want to utilize asynchronous programming.</span></span> <span data-ttu-id="a9562-105">También podría tener código enlazado a la CPU, como realizar un cálculo costoso, que también es un buen escenario para escribir código asincrónico.</span><span class="sxs-lookup"><span data-stu-id="a9562-105">You could also have CPU-bound code, such as performing an expensive calculation, which is also a good scenario for writing async code.</span></span>

<span data-ttu-id="a9562-106">C# tiene un modelo de programación asincrónico de nivel de lenguaje que permite escribir fácilmente código asincrónico sin tener que hacer malabares con las devoluciones de llamada o ajustarse a una biblioteca que admita la asincronía.</span><span class="sxs-lookup"><span data-stu-id="a9562-106">C# has a language-level asynchronous programming model, which allows for easily writing asynchronous code, without having to juggle callbacks or conform to a library that supports asynchrony.</span></span> <span data-ttu-id="a9562-107">Sigue lo que se conoce como el [modelo asincrónico basado en tareas (TAP)](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="a9562-107">It follows what is known as the [Task-based Asynchronous Pattern (TAP)](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span></span>

## <a name="overview-of-the-asynchronous-model"></a><span data-ttu-id="a9562-108">Información general del modelo asincrónico</span><span class="sxs-lookup"><span data-stu-id="a9562-108">Overview of the asynchronous model</span></span>

<span data-ttu-id="a9562-109">El núcleo de la programación asincrónica son los objetos `Task` y `Task<T>`, que modelan las operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="a9562-109">The core of async programming is the `Task` and `Task<T>` objects, which model asynchronous operations.</span></span> <span data-ttu-id="a9562-110">Son compatibles con las palabras clave `async` y `await`.</span><span class="sxs-lookup"><span data-stu-id="a9562-110">They are supported by the `async` and `await` keywords.</span></span> <span data-ttu-id="a9562-111">El modelo es bastante sencillo en la mayoría de los casos:</span><span class="sxs-lookup"><span data-stu-id="a9562-111">The model is fairly simple in most cases:</span></span>

- <span data-ttu-id="a9562-112">Para el código enlazado a E/S, espera una operación que devuelva `Task` o `Task<T>` dentro de un método `async`.</span><span class="sxs-lookup"><span data-stu-id="a9562-112">For I/O-bound code, you await an operation that returns a `Task` or `Task<T>` inside of an `async` method.</span></span>
- <span data-ttu-id="a9562-113">Para el código enlazado a la CPU, espera una operación que se inicia en un subproceso en segundo plano con el método <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a9562-113">For CPU-bound code, you await an operation that is started on a background thread with the <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="a9562-114">La palabra clave `await` es donde ocurre la magia.</span><span class="sxs-lookup"><span data-stu-id="a9562-114">The `await` keyword is where the magic happens.</span></span> <span data-ttu-id="a9562-115">Genera control para el autor de la llamada del método que ha realizado `await`, y permite en última instancia una interfaz de usuario con capacidad de respuesta o un servicio flexible.</span><span class="sxs-lookup"><span data-stu-id="a9562-115">It yields control to the caller of the method that performed `await`, and it ultimately allows a UI to be responsive or a service to be elastic.</span></span> <span data-ttu-id="a9562-116">Aunque [existen maneras](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) de abordar el código asincrónico diferentes de `async` y `await`, este artículo se centra en las construcciones de nivel de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="a9562-116">While [there are ways](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) to approach async code other than `async` and `await`, this article focuses on the language-level constructs.</span></span>

### <a name="io-bound-example-download-data-from-a-web-service"></a><span data-ttu-id="a9562-117">Ejemplo enlazado a E/S: descarga de datos de un servicio web</span><span class="sxs-lookup"><span data-stu-id="a9562-117">I/O-bound example: Download data from a web service</span></span>

<span data-ttu-id="a9562-118">Puede que necesite descargar algunos datos de un servicio web cuando se presione un botón, pero no quiere bloquear el subproceso de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="a9562-118">You may need to download some data from a web service when a button is pressed, but don't want to block the UI thread.</span></span> <span data-ttu-id="a9562-119">Puede conseguirlo de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="a9562-119">It can be accomplished like this:</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

downloadButton.Clicked += async (o, e) =>
{
    // This line will yield control to the UI as the request
    // from the web service is happening.
    //
    // The UI thread is now free to perform other work.
    var stringData = await _httpClient.GetStringAsync(URL);
    DoSomethingWithData(stringData);
};
```

<span data-ttu-id="a9562-120">El código expresa la intención (descargar datos de forma asincrónica) sin verse obstaculizado en la interacción con objetos `Task`.</span><span class="sxs-lookup"><span data-stu-id="a9562-120">The code expresses the intent (downloading data asynchronously) without getting bogged down in interacting with `Task` objects.</span></span>

### <a name="cpu-bound-example-perform-a-calculation-for-a-game"></a><span data-ttu-id="a9562-121">Ejemplo enlazado a la CPU: realizar un cálculo para un juego</span><span class="sxs-lookup"><span data-stu-id="a9562-121">CPU-bound example: Perform a calculation for a game</span></span>

<span data-ttu-id="a9562-122">Supongamos que está escribiendo un juego para móviles en el que se pueden infligir daños a muchos enemigos en la pantalla pulsando un botón.</span><span class="sxs-lookup"><span data-stu-id="a9562-122">Say you're writing a mobile game where pressing a button can inflict damage on many enemies on the screen.</span></span> <span data-ttu-id="a9562-123">Realizar el cálculo del daño puede resultar costoso y hacerlo en el subproceso de interfaz de usuario haría que pareciera que el juego se pone en pausa mientras se lleva a cabo el cálculo.</span><span class="sxs-lookup"><span data-stu-id="a9562-123">Performing the damage calculation can be expensive, and doing it on the UI thread would make the game appear to pause as the calculation is performed!</span></span>

<span data-ttu-id="a9562-124">La mejor manera de abordar esta situación consiste en iniciar un subproceso en segundo plano que realice la tarea mediante `Task.Run` y esperar su resultado mediante `await`.</span><span class="sxs-lookup"><span data-stu-id="a9562-124">The best way to handle this is to start a background thread, which does the work using `Task.Run`, and await its result using `await`.</span></span> <span data-ttu-id="a9562-125">Esto permite que la interfaz de usuario funcione de manera fluida mientras se lleva a cabo la tarea.</span><span class="sxs-lookup"><span data-stu-id="a9562-125">This allows the UI to feel smooth as the work is being done.</span></span>

```csharp
private DamageResult CalculateDamageDone()
{
    // Code omitted:
    //
    // Does an expensive calculation and returns
    // the result of that calculation.
}

calculateButton.Clicked += async (o, e) =>
{
    // This line will yield control to the UI while CalculateDamageDone()
    // performs its work. The UI thread is free to perform other work.
    var damageResult = await Task.Run(() => CalculateDamageDone());
    DisplayDamage(damageResult);
};
```

<span data-ttu-id="a9562-126">Este código expresa claramente la intención del evento de clic del botón, no requiere la administración manual de un subproceso en segundo plano y lo hace en un modo sin bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a9562-126">This code cleanly expresses the intent of the button's click event, it doesn't require managing a background thread manually, and it does so in a non-blocking way.</span></span>

### <a name="what-happens-under-the-covers"></a><span data-ttu-id="a9562-127">Qué sucede en segundo plano</span><span class="sxs-lookup"><span data-stu-id="a9562-127">What happens under the covers</span></span>

<span data-ttu-id="a9562-128">En las operaciones asincrónicas existen numerosos aspectos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="a9562-128">There are many moving pieces where asynchronous operations are concerned.</span></span> <span data-ttu-id="a9562-129">Si siente curiosidad sobre lo que ocurre en el segundo plano de `Task` y `Task<T>`, eche un vistazo al artículo [Async en profundidad](../standard/async-in-depth.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a9562-129">If you're curious about what's happening underneath the covers of `Task` and `Task<T>`, see the [Async in-depth](../standard/async-in-depth.md) article for more information.</span></span>

<span data-ttu-id="a9562-130">En lo que respecta a C#, el compilador transforma el código en una máquina de estados que realiza el seguimiento de acciones como la retención de la ejecución cuando se alcanza `await` y la reanudación de la ejecución cuando se ha finalizado un trabajo en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="a9562-130">On the C# side of things, the compiler transforms your code into a state machine that keeps track of things like yielding execution when an `await` is reached and resuming execution when a background job has finished.</span></span>

<span data-ttu-id="a9562-131">Para los más interesados en la teoría, se trata de una implementación del [modelo de promesas de asincronía](https://en.wikipedia.org/wiki/Futures_and_promises).</span><span class="sxs-lookup"><span data-stu-id="a9562-131">For the theoretically-inclined, this is an implementation of the [Promise Model of asynchrony](https://en.wikipedia.org/wiki/Futures_and_promises).</span></span>

## <a name="key-pieces-to-understand"></a><span data-ttu-id="a9562-132">Piezas clave que debe comprender</span><span class="sxs-lookup"><span data-stu-id="a9562-132">Key pieces to understand</span></span>

* <span data-ttu-id="a9562-133">El código asincrónico puede usarse para código tanto enlazado a E/S como enlazado a la CPU, pero de forma distinta en cada escenario.</span><span class="sxs-lookup"><span data-stu-id="a9562-133">Async code can be used for both I/O-bound and CPU-bound code, but differently for each scenario.</span></span>
* <span data-ttu-id="a9562-134">El código asincrónico usa `Task<T>` y `Task`, que son construcciones que se usan para modelar el trabajo que se realiza en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="a9562-134">Async code uses `Task<T>` and `Task`, which are constructs used to model work being done in the background.</span></span>
* <span data-ttu-id="a9562-135">La palabra clave `async` convierte un método en un método asincrónico, lo que permite usar la palabra clave `await` en su cuerpo.</span><span class="sxs-lookup"><span data-stu-id="a9562-135">The `async` keyword turns a method into an async method, which allows you to use the `await` keyword in its body.</span></span>
* <span data-ttu-id="a9562-136">Cuando se aplica la palabra clave `await`, se suspende el método de llamada y se cede el control al autor de la llamada hasta que se completa la tarea esperada.</span><span class="sxs-lookup"><span data-stu-id="a9562-136">When the `await` keyword is applied, it suspends the calling method and yields control back to its caller until the awaited task is complete.</span></span>
* <span data-ttu-id="a9562-137">`await` solo puede usarse dentro de un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="a9562-137">`await` can only be used inside an async method.</span></span>

## <a name="recognize-cpu-bound-and-io-bound-work"></a><span data-ttu-id="a9562-138">Reconocer el trabajo enlazado a la CPU y el enlazado a E/S</span><span class="sxs-lookup"><span data-stu-id="a9562-138">Recognize CPU-bound and I/O-bound work</span></span>

<span data-ttu-id="a9562-139">En los dos primeros ejemplos de esta guía se ha explicado cómo se puede usar `async` y `await` para trabajos enlazados a E/S y a la CPU.</span><span class="sxs-lookup"><span data-stu-id="a9562-139">The first two examples of this guide showed how you can use `async` and `await` for I/O-bound and CPU-bound work.</span></span> <span data-ttu-id="a9562-140">Resulta fundamental que pueda identificar si el trabajo que debe realizar está enlazado a E/S o a la CPU, ya que esto puede afectar en gran medida al rendimiento del código y podría dar lugar al uso inadecuado de ciertas construcciones.</span><span class="sxs-lookup"><span data-stu-id="a9562-140">It's key that you can identify when a job you need to do is I/O-bound or CPU-bound, because it can greatly affect the performance of your code and could potentially lead to misusing certain constructs.</span></span>

<span data-ttu-id="a9562-141">A continuación, se indican dos preguntas que debe hacerse antes de escribir el código:</span><span class="sxs-lookup"><span data-stu-id="a9562-141">Here are two questions you should ask before you write any code:</span></span>

1. <span data-ttu-id="a9562-142">¿Estará su código "esperando" algo, como datos de una base de datos?</span><span class="sxs-lookup"><span data-stu-id="a9562-142">Will your code be "waiting" for something, such as data from a database?</span></span>

   <span data-ttu-id="a9562-143">Si la respuesta es "sí", su trabajo está **enlazado a E/S**.</span><span class="sxs-lookup"><span data-stu-id="a9562-143">If your answer is "yes", then your work is **I/O-bound**.</span></span>

1. <span data-ttu-id="a9562-144">¿Realizará el código un cálculo costoso?</span><span class="sxs-lookup"><span data-stu-id="a9562-144">Will your code be performing an expensive computation?</span></span>

   <span data-ttu-id="a9562-145">Si la respuesta es "sí", su trabajo está **enlazado a la CPU**.</span><span class="sxs-lookup"><span data-stu-id="a9562-145">If you answered "yes", then your work is **CPU-bound**.</span></span>

<span data-ttu-id="a9562-146">Si el trabajo que tiene está **enlazado a E/S**, use `async` y `await` *sin* `Task.Run`.</span><span class="sxs-lookup"><span data-stu-id="a9562-146">If the work you have is **I/O-bound**, use `async` and `await` *without* `Task.Run`.</span></span> <span data-ttu-id="a9562-147">*No debe* usar la Biblioteca TPL.</span><span class="sxs-lookup"><span data-stu-id="a9562-147">You *should not* use the Task Parallel Library.</span></span> <span data-ttu-id="a9562-148">Esto se explica en [Async en profundidad](../standard/async-in-depth.md).</span><span class="sxs-lookup"><span data-stu-id="a9562-148">The reason for this is outlined in [Async in Depth](../standard/async-in-depth.md).</span></span>

<span data-ttu-id="a9562-149">Si el trabajo que tiene está **enlazado a la CPU** y le interesa la capacidad de respuesta, use `async` y `await`, pero genere el trabajo en otro subproceso *con* `Task.Run`.</span><span class="sxs-lookup"><span data-stu-id="a9562-149">If the work you have is **CPU-bound** and you care about responsiveness, use `async` and `await`, but spawn off the work on another thread *with* `Task.Run`.</span></span> <span data-ttu-id="a9562-150">Si el trabajo es adecuado para la simultaneidad y el paralelismo, también debe plantearse el uso de la [biblioteca TPL](../standard/parallel-programming/task-parallel-library-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="a9562-150">If the work is appropriate for concurrency and parallelism, also consider using the [Task Parallel Library](../standard/parallel-programming/task-parallel-library-tpl.md).</span></span>

<span data-ttu-id="a9562-151">Además, siempre debe medir la ejecución del código.</span><span class="sxs-lookup"><span data-stu-id="a9562-151">Additionally, you should always measure the execution of your code.</span></span> <span data-ttu-id="a9562-152">Por ejemplo, puede verse en una situación en la que el trabajo enlazado a la CPU no sea suficientemente costoso en comparación con la sobrecarga de cambios de contexto cuando realice multithreading.</span><span class="sxs-lookup"><span data-stu-id="a9562-152">For example, you may find yourself in a situation where your CPU-bound work is not costly enough compared with the overhead of context switches when multithreading.</span></span> <span data-ttu-id="a9562-153">Cada opción tiene su compensación y debe elegir el equilibrio correcto para su situación.</span><span class="sxs-lookup"><span data-stu-id="a9562-153">Every choice has its tradeoff, and you should pick the correct tradeoff for your situation.</span></span>

## <a name="more-examples"></a><span data-ttu-id="a9562-154">Más ejemplos</span><span class="sxs-lookup"><span data-stu-id="a9562-154">More examples</span></span>

<span data-ttu-id="a9562-155">En los ejemplos siguientes se muestran distintas maneras en las que puede escribir código asincrónico en C#.</span><span class="sxs-lookup"><span data-stu-id="a9562-155">The following examples demonstrate various ways you can write async code in C#.</span></span> <span data-ttu-id="a9562-156">Abarcan algunos escenarios diferentes con los que puede encontrarse.</span><span class="sxs-lookup"><span data-stu-id="a9562-156">They cover a few different scenarios you may come across.</span></span>

### <a name="extract-data-from-a-network"></a><span data-ttu-id="a9562-157">Extracción de datos de una red</span><span class="sxs-lookup"><span data-stu-id="a9562-157">Extract data from a network</span></span>

<span data-ttu-id="a9562-158">Este fragmento de código descarga el HTML desde la página principal en <https://dotnetfoundation.org> y cuenta el número de veces que aparece la cadena ".NET" en el código HTML.</span><span class="sxs-lookup"><span data-stu-id="a9562-158">This snippet downloads the HTML from the homepage at <https://dotnetfoundation.org> and counts the number of times the string ".NET" occurs in the HTML.</span></span> <span data-ttu-id="a9562-159">Usa ASP.NET para definir un método de controlador Web API que realiza esta tarea y devuelve el número.</span><span class="sxs-lookup"><span data-stu-id="a9562-159">It uses ASP.NET to define a Web API controller method, which performs this task and returns the number.</span></span>

> [!NOTE]
> <span data-ttu-id="a9562-160">Si tiene previsto realizar un análisis HTML en el código de producción, no use expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="a9562-160">If you plan on doing HTML parsing in production code, don't use regular expressions.</span></span> <span data-ttu-id="a9562-161">Use una biblioteca de análisis en su lugar.</span><span class="sxs-lookup"><span data-stu-id="a9562-161">Use a parsing library instead.</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

[HttpGet, Route("DotNetCount")]
public async Task<int> GetDotNetCount()
{
    // Suspends GetDotNetCount() to allow the caller (the web server)
    // to accept another request, rather than blocking on this one.
    var html = await _httpClient.GetStringAsync("https://dotnetfoundation.org");

    return Regex.Matches(html, @"\.NET").Count;
}
```

<span data-ttu-id="a9562-162">Este es el mismo escenario escrito para una aplicación Windows Universal, que realiza la misma tarea cuando se presiona un botón:</span><span class="sxs-lookup"><span data-stu-id="a9562-162">Here's the same scenario written for a Universal Windows App, which performs the same task when a Button is pressed:</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

private async void OnSeeTheDotNetsButtonClick(object sender, RoutedEventArgs e)
{
    // Capture the task handle here so we can await the background task later.
    var getDotNetFoundationHtmlTask = _httpClient.GetStringAsync("https://dotnetfoundation.org");

    // Any other work on the UI thread can be done here, such as enabling a Progress Bar.
    // This is important to do here, before the "await" call, so that the user
    // sees the progress bar before execution of this method is yielded.
    NetworkProgressBar.IsEnabled = true;
    NetworkProgressBar.Visibility = Visibility.Visible;

    // The await operator suspends OnSeeTheDotNetsButtonClick(), returning control to its caller.
    // This is what allows the app to be responsive and not block the UI thread.
    var html = await getDotNetFoundationHtmlTask;
    int count = Regex.Matches(html, @"\.NET").Count;

    DotNetCountLabel.Text = $"Number of .NETs on dotnetfoundation.org: {count}";

    NetworkProgressBar.IsEnabled = false;
    NetworkProgressBar.Visibility = Visibility.Collapsed;
}
```

### <a name="wait-for-multiple-tasks-to-complete"></a><span data-ttu-id="a9562-163">Esperar a que se completen varias tareas</span><span class="sxs-lookup"><span data-stu-id="a9562-163">Wait for multiple tasks to complete</span></span>

<span data-ttu-id="a9562-164">Es posible que se vea en una situación en la que necesite recuperar varios fragmentos de datos al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="a9562-164">You may find yourself in a situation where you need to retrieve multiple pieces of data concurrently.</span></span> <span data-ttu-id="a9562-165">La API `Task` contiene dos métodos, <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, que permiten escribir código asincrónico que realiza una espera sin bloqueo en varios trabajos en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="a9562-165">The `Task` API contains two methods, <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, that allow you to write asynchronous code that performs a non-blocking wait on multiple background jobs.</span></span>

<span data-ttu-id="a9562-166">En este ejemplo se muestra cómo podría captar datos `User` de un conjunto de elementos `userId`.</span><span class="sxs-lookup"><span data-stu-id="a9562-166">This example shows how you might grab `User` data for a set of `userId`s.</span></span>

```csharp
public async Task<User> GetUserAsync(int userId)
{
    // Code omitted:
    //
    // Given a user Id {userId}, retrieves a User object corresponding
    // to the entry in the database with {userId} as its Id.
}

public static async Task<IEnumerable<User>> GetUsersAsync(IEnumerable<int> userIds)
{
    var getUserTasks = new List<Task<User>>();
    foreach (int userId in userIds)
    {
        getUserTasks.Add(GetUserAsync(userId));
    }

    return await Task.WhenAll(getUserTasks);
}
```

<span data-ttu-id="a9562-167">Aquí tiene otra manera de escribir lo mismo de una forma más sucinta, con LINQ:</span><span class="sxs-lookup"><span data-stu-id="a9562-167">Here's another way to write this more succinctly, using LINQ:</span></span>

```csharp
public async Task<User> GetUserAsync(int userId)
{
    // Code omitted:
    //
    // Given a user Id {userId}, retrieves a User object corresponding
    // to the entry in the database with {userId} as its Id.
}

public static async Task<User[]> GetUsersAsync(IEnumerable<int> userIds)
{
    var getUserTasks = userIds.Select(id => GetUserAsync(id));
    return await Task.WhenAll(getUserTasks);
}
```

<span data-ttu-id="a9562-168">Aunque es menos código, tenga cuidado al combinar LINQ con código asincrónico.</span><span class="sxs-lookup"><span data-stu-id="a9562-168">Although it's less code, use caution when mixing LINQ with asynchronous code.</span></span> <span data-ttu-id="a9562-169">Dado que LINQ usa la ejecución diferida, las llamadas asincrónicas no se realizarán inmediatamente, como lo hacen en un bucle `foreach`, a menos que fuerce la secuencia generada a procesar una iteración con una llamada a `.ToList()` o `.ToArray()`.</span><span class="sxs-lookup"><span data-stu-id="a9562-169">Because LINQ uses deferred (lazy) execution, async calls won't happen immediately as they do in a `foreach` loop unless you force the generated sequence to iterate with a call to `.ToList()` or `.ToArray()`.</span></span>

## <a name="important-info-and-advice"></a><span data-ttu-id="a9562-170">Consejos e información importante</span><span class="sxs-lookup"><span data-stu-id="a9562-170">Important info and advice</span></span>

<span data-ttu-id="a9562-171">Con la programación asincrónica, hay algunos detalles que debe tener en cuenta para evitar un comportamiento inesperado.</span><span class="sxs-lookup"><span data-stu-id="a9562-171">With async programming there are some details to keep in mind which can prevent unexpected behavior.</span></span>

* <span data-ttu-id="a9562-172">Los métodos `async` **deben tener una palabra clave** `await` **en el cuerpo o nunca proporcionarán resultados**.</span><span class="sxs-lookup"><span data-stu-id="a9562-172">`async` **methods need to have an** `await` **keyword in their body or they will never yield!**</span></span>

  <span data-ttu-id="a9562-173">Es importante que tenga esto en cuenta.</span><span class="sxs-lookup"><span data-stu-id="a9562-173">This is important to keep in mind.</span></span> <span data-ttu-id="a9562-174">Si no se usa `await` en el cuerpo de un método `async`, el compilador de C# genera una advertencia, pero el código se compila y se ejecuta como si se tratara de un método normal.</span><span class="sxs-lookup"><span data-stu-id="a9562-174">If `await` is not used in the body of an `async` method, the C# compiler generates a warning, but the code compiles and runs as if it were a normal method.</span></span> <span data-ttu-id="a9562-175">Esto sería muy ineficaz, ya que la máquina de estados generada por el compilador de C# para el método asincrónico no realiza nada.</span><span class="sxs-lookup"><span data-stu-id="a9562-175">This is incredibly inefficient, as the state machine generated by the C# compiler for the async method is not accomplishing anything.</span></span>

* <span data-ttu-id="a9562-176">**Debe agregar "Async" como el sufijo de todos los métodos asincrónicos que escriba.**</span><span class="sxs-lookup"><span data-stu-id="a9562-176">**You should add "Async" as the suffix of every async method name you write.**</span></span>

<span data-ttu-id="a9562-177">Se trata de la convención que se usa en .NET para distinguir más fácilmente los métodos sincrónicos de los asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="a9562-177">This is the convention used in .NET to more easily differentiate synchronous and asynchronous methods.</span></span> <span data-ttu-id="a9562-178">No se aplican necesariamente ciertos métodos a los que el código no llame explícitamente (como controladores de eventos o métodos de controlador web).</span><span class="sxs-lookup"><span data-stu-id="a9562-178">Certain methods that aren't explicitly called by your code (such as event handlers or web controller methods) don't necessarily apply.</span></span> <span data-ttu-id="a9562-179">Puesto que el código no los llama explícitamente, resulta importante explicitar sus nombres.</span><span class="sxs-lookup"><span data-stu-id="a9562-179">Because they are not explicitly called by your code, being explicit about their naming isn't as important.</span></span>

* <span data-ttu-id="a9562-180">`async void` **solo se debe usar para controladores de eventos.**</span><span class="sxs-lookup"><span data-stu-id="a9562-180">`async void` **should only to be used for event handlers.**</span></span>

<span data-ttu-id="a9562-181">`async void` es la única manera de permitir a los controladores de eventos asincrónicos trabajar, ya que los eventos no tienen tipos de valor devuelto (por lo tanto, no pueden hacer uso de `Task` y `Task<T>`).</span><span class="sxs-lookup"><span data-stu-id="a9562-181">`async void` is the only way to allow asynchronous event handlers to work because events do not have return types (thus cannot make use of `Task` and `Task<T>`).</span></span> <span data-ttu-id="a9562-182">Cualquier otro uso de `async void` no sigue el modelo de TAP y puede resultar difícil de usar, como:</span><span class="sxs-lookup"><span data-stu-id="a9562-182">Any other use of `async void` does not follow the TAP model and can be challenging to use, such as:</span></span>

* <span data-ttu-id="a9562-183">Las excepciones producidas en un método `async void` no se pueden detectar fuera de ese método.</span><span class="sxs-lookup"><span data-stu-id="a9562-183">Exceptions thrown in an `async void` method can't be caught outside of that method.</span></span>
* <span data-ttu-id="a9562-184">Los métodos `async void` resultan muy difíciles de probar.</span><span class="sxs-lookup"><span data-stu-id="a9562-184">`async void` methods are difficult to test.</span></span>
* <span data-ttu-id="a9562-185">Los métodos `async void` pueden provocar efectos secundarios negativos si el autor de la llamada no espera que sean asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="a9562-185">`async void` methods can cause bad side effects if the caller isn't expecting them to be async.</span></span>

* <span data-ttu-id="a9562-186">**Tenga cuidado al usar lambdas asincrónicas en las expresiones de LINQ.**</span><span class="sxs-lookup"><span data-stu-id="a9562-186">**Tread carefully when using async lambdas in LINQ expressions**</span></span>

<span data-ttu-id="a9562-187">Las expresiones lambda de LINQ usan la ejecución aplazada, lo que implica que el código podría acabar ejecutándose en un momento en que no se lo espere.</span><span class="sxs-lookup"><span data-stu-id="a9562-187">Lambda expressions in LINQ use deferred execution, meaning code could end up executing at a time when you're not expecting it to.</span></span> <span data-ttu-id="a9562-188">La introducción de las tareas de bloqueo puede dar lugar a un interbloqueo si no se han escrito correctamente.</span><span class="sxs-lookup"><span data-stu-id="a9562-188">The introduction of blocking tasks into this can easily result in a deadlock if not written correctly.</span></span> <span data-ttu-id="a9562-189">Además, el anidamiento de código asincrónico de esta manera también puede hacer que resulte más difícil razonar sobre la ejecución del código.</span><span class="sxs-lookup"><span data-stu-id="a9562-189">Additionally, the nesting of asynchronous code like this can also make it more difficult to reason about the execution of the code.</span></span> <span data-ttu-id="a9562-190">Async y LINQ son eficaces, pero deben usarse conjuntamente con el mayor cuidado y claridad posible.</span><span class="sxs-lookup"><span data-stu-id="a9562-190">Async and LINQ are powerful, but should be used together as carefully and clearly as possible.</span></span>

* <span data-ttu-id="a9562-191">**Escriba código que espere las tareas sin bloqueo.**</span><span class="sxs-lookup"><span data-stu-id="a9562-191">**Write code that awaits Tasks in a non-blocking manner**</span></span>

<span data-ttu-id="a9562-192">Bloquear el subproceso actual como un medio para esperar que se complete `Task` puede dar lugar a interbloqueos y subprocesos de contexto bloqueados, y puede requerir un control de errores más complejo.</span><span class="sxs-lookup"><span data-stu-id="a9562-192">Blocking the current thread as a means to wait for a `Task` to complete can result in deadlocks and blocked context threads, and can require more complex error-handling.</span></span> <span data-ttu-id="a9562-193">En la tabla siguiente se ofrece orientación sobre cómo abordar la espera de las tareas de una manera que no produzca un bloqueo:</span><span class="sxs-lookup"><span data-stu-id="a9562-193">The following table provides guidance on how to deal with waiting for tasks in a non-blocking way:</span></span>

| <span data-ttu-id="a9562-194">Use esto...</span><span class="sxs-lookup"><span data-stu-id="a9562-194">Use this...</span></span>          | <span data-ttu-id="a9562-195">En vez de esto...</span><span class="sxs-lookup"><span data-stu-id="a9562-195">Instead of this...</span></span>           | <span data-ttu-id="a9562-196">Cuando quiera hacer esto...</span><span class="sxs-lookup"><span data-stu-id="a9562-196">When wishing to do this...</span></span>                 |
|----------------------|------------------------------|--------------------------------------------|
| `await`              | <span data-ttu-id="a9562-197">`Task.Wait` o `Task.Result`</span><span class="sxs-lookup"><span data-stu-id="a9562-197">`Task.Wait` or `Task.Result`</span></span> | <span data-ttu-id="a9562-198">Recuperar el resultado de una tarea en segundo plano</span><span class="sxs-lookup"><span data-stu-id="a9562-198">Retrieving the result of a background task</span></span> |
| `await Task.WhenAny` | `Task.WaitAny`               | <span data-ttu-id="a9562-199">Esperar que finalice cualquier tarea</span><span class="sxs-lookup"><span data-stu-id="a9562-199">Waiting for any task to complete</span></span>           |
| `await Task.WhenAll` | `Task.WaitAll`               | <span data-ttu-id="a9562-200">Esperar que finalicen todas las tareas</span><span class="sxs-lookup"><span data-stu-id="a9562-200">Waiting for all tasks to complete</span></span>          |
| `await Task.Delay`   | `Thread.Sleep`               | <span data-ttu-id="a9562-201">Esperar un período de tiempo</span><span class="sxs-lookup"><span data-stu-id="a9562-201">Waiting for a period of time</span></span>               |

* <span data-ttu-id="a9562-202">**Considere la posibilidad de usar** `ValueTask` **cuando sea posible**</span><span class="sxs-lookup"><span data-stu-id="a9562-202">**Consider using** `ValueTask` **where possible**</span></span>

<span data-ttu-id="a9562-203">La devolución de un objeto `Task` desde métodos asincrónicos puede presentar cuellos de botella de rendimiento en determinadas rutas de acceso.</span><span class="sxs-lookup"><span data-stu-id="a9562-203">Returning a `Task` object from async methods can introduce performance bottlenecks in certain paths.</span></span> <span data-ttu-id="a9562-204">`Task` es un tipo de referencia, por lo que su uso implica la asignación de un objeto.</span><span class="sxs-lookup"><span data-stu-id="a9562-204">`Task` is a reference type, so using it means allocating an object.</span></span> <span data-ttu-id="a9562-205">En los casos en los que un método declarado con el modificador `async` devuelva un resultado en caché o se complete sincrónicamente, las asignaciones adicionales pueden suponer un costo considerable de tiempo en secciones críticas para el rendimiento del código.</span><span class="sxs-lookup"><span data-stu-id="a9562-205">In cases where a method declared with the `async` modifier returns a cached result or completes synchronously, the extra allocations can become a significant time cost in performance critical sections of code.</span></span> <span data-ttu-id="a9562-206">Esas asignaciones pueden resultar costosas si se producen en bucles ajustados.</span><span class="sxs-lookup"><span data-stu-id="a9562-206">It can become costly if those allocations occur in tight loops.</span></span> <span data-ttu-id="a9562-207">Para obtener más información, consulte [Tipos de valor devueltos asincrónicos generalizados](whats-new/csharp-7.md#generalized-async-return-types).</span><span class="sxs-lookup"><span data-stu-id="a9562-207">For more information, see [generalized async return types](whats-new/csharp-7.md#generalized-async-return-types).</span></span>

* <span data-ttu-id="a9562-208">**Considere la posibilidad de utilizar** `ConfigureAwait(false)`</span><span class="sxs-lookup"><span data-stu-id="a9562-208">**Consider using** `ConfigureAwait(false)`</span></span>

<span data-ttu-id="a9562-209">Una pregunta habitual es "¿Cuándo debo usar el método <xref:System.Threading.Tasks.Task.ConfigureAwait(System.Boolean)?displayProperty=nameWithType>?".</span><span class="sxs-lookup"><span data-stu-id="a9562-209">A common question is, "when should I use the <xref:System.Threading.Tasks.Task.ConfigureAwait(System.Boolean)?displayProperty=nameWithType> method?".</span></span> <span data-ttu-id="a9562-210">El método permite a una instancia de `Task` configurar su elemento awaiter.</span><span class="sxs-lookup"><span data-stu-id="a9562-210">The method allows for a `Task` instance to configure its awaiter.</span></span> <span data-ttu-id="a9562-211">Este es un aspecto importante que debe tenerse en cuenta, y su configuración incorrecta podría tener implicaciones de rendimiento e incluso interbloqueos.</span><span class="sxs-lookup"><span data-stu-id="a9562-211">This is an important consideration and setting it incorrectly could potentially have performance implications and even deadlocks.</span></span> <span data-ttu-id="a9562-212">Para obtener más información sobre `ConfigureAwait`, consulte las [preguntas más frecuentes sobre ConfigureAwait](https://devblogs.microsoft.com/dotnet/configureawait-faq).</span><span class="sxs-lookup"><span data-stu-id="a9562-212">For more information on `ConfigureAwait`, see the [ConfigureAwait FAQ](https://devblogs.microsoft.com/dotnet/configureawait-faq).</span></span>

* <span data-ttu-id="a9562-213">**Escriba código con menos estados.**</span><span class="sxs-lookup"><span data-stu-id="a9562-213">**Write less stateful code**</span></span>

<span data-ttu-id="a9562-214">No dependa del estado de los objetos globales o la ejecución de ciertos métodos.</span><span class="sxs-lookup"><span data-stu-id="a9562-214">Don't depend on the state of global objects or the execution of certain methods.</span></span> <span data-ttu-id="a9562-215">En su lugar, dependa únicamente de los valores devueltos de los métodos.</span><span class="sxs-lookup"><span data-stu-id="a9562-215">Instead, depend only on the return values of methods.</span></span> <span data-ttu-id="a9562-216">¿Por qué?</span><span class="sxs-lookup"><span data-stu-id="a9562-216">Why?</span></span>

* <span data-ttu-id="a9562-217">Le resultará más fácil razonar sobre el código.</span><span class="sxs-lookup"><span data-stu-id="a9562-217">Code will be easier to reason about.</span></span>
* <span data-ttu-id="a9562-218">Le resultará más fácil probar el código.</span><span class="sxs-lookup"><span data-stu-id="a9562-218">Code will be easier to test.</span></span>
* <span data-ttu-id="a9562-219">Resulta mucho más sencillo mezclar código asincrónico y sincrónico.</span><span class="sxs-lookup"><span data-stu-id="a9562-219">Mixing async and synchronous code is far simpler.</span></span>
* <span data-ttu-id="a9562-220">Normalmente se pueden evitar por completo las condiciones de carrera.</span><span class="sxs-lookup"><span data-stu-id="a9562-220">Race conditions can typically be avoided altogether.</span></span>
* <span data-ttu-id="a9562-221">Depender de los valores devueltos facilita la coordinación de código asincrónico.</span><span class="sxs-lookup"><span data-stu-id="a9562-221">Depending on return values makes coordinating async code simple.</span></span>
* <span data-ttu-id="a9562-222">(Extra) Funciona muy bien con la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="a9562-222">(Bonus) it works really well with dependency injection.</span></span>

<span data-ttu-id="a9562-223">Un objetivo recomendado es lograr una [transparencia referencial](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29) completa o casi completa en el código.</span><span class="sxs-lookup"><span data-stu-id="a9562-223">A recommended goal is to achieve complete or near-complete [Referential Transparency](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29) in your code.</span></span> <span data-ttu-id="a9562-224">Esto se traducirá en un código base extremadamente predecible, que se puede probar y es fácil de mantener.</span><span class="sxs-lookup"><span data-stu-id="a9562-224">Doing so will result in an extremely predictable, testable, and maintainable codebase.</span></span>

## <a name="other-resources"></a><span data-ttu-id="a9562-225">Otros recursos</span><span class="sxs-lookup"><span data-stu-id="a9562-225">Other resources</span></span>

* <span data-ttu-id="a9562-226">En el artículo [Async en profundidad](../standard/async-in-depth.md) se proporciona más información sobre cómo funcionan las tareas.</span><span class="sxs-lookup"><span data-stu-id="a9562-226">[Async in-depth](../standard/async-in-depth.md) provides more information about how Tasks work.</span></span>
* [<span data-ttu-id="a9562-227">Programación asincrónica con async y await (C#)</span><span class="sxs-lookup"><span data-stu-id="a9562-227">Asynchronous programming with async and await (C#)</span></span>](./programming-guide/concepts/async/index.md)
* <span data-ttu-id="a9562-228">Los vídeos [Six Essential Tips for Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async) (Seis consejos esenciales para la programación asincrónica) de Lucian Wischik son un recurso fantástico para este tipo de programación.</span><span class="sxs-lookup"><span data-stu-id="a9562-228">Lucian Wischik's [Six Essential Tips for Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async) are a wonderful resource for async programming</span></span>
