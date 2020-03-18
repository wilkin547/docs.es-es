---
title: 'Programación asincrónica: C#'
description: Obtenga información sobre el modelo de programación asincrónico de nivel de lenguaje de C# que proporciona .NET Core.
author: cartermp
ms.date: 06/20/2016
ms.technology: csharp-async
ms.assetid: b878c34c-a78f-419e-a594-a2b44fa521a4
ms.openlocfilehash: 38d7c856e9a536db9ef26349175ad440a49f5fe2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713948"
---
# <a name="asynchronous-programming"></a><span data-ttu-id="d6779-103">Programación asincrónica</span><span class="sxs-lookup"><span data-stu-id="d6779-103">Asynchronous programming</span></span>

<span data-ttu-id="d6779-104">Si tiene cualquier necesidad enlazada a E/S (por ejemplo, solicitar datos de una red o acceder a una base de datos), deberá usar la programación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="d6779-104">If you have any I/O-bound needs (such as requesting data from a network or accessing a database), you'll want to utilize asynchronous programming.</span></span>  <span data-ttu-id="d6779-105">También podría tener código enlazado a la CPU, como realizar un cálculo costoso, que también es un buen escenario para escribir código asincrónico.</span><span class="sxs-lookup"><span data-stu-id="d6779-105">You could also have CPU-bound code, such as performing an expensive calculation, which is also a good scenario for writing async code.</span></span>

<span data-ttu-id="d6779-106">C# tiene un modelo de programación asincrónico de nivel de lenguaje que permite escribir fácilmente código asincrónico sin tener que hacer malabares con las devoluciones de llamada o ajustarse a una biblioteca que admita la asincronía.</span><span class="sxs-lookup"><span data-stu-id="d6779-106">C# has a language-level asynchronous programming model which allows for easily writing asynchronous code without having to juggle callbacks or conform to a library which supports asynchrony.</span></span> <span data-ttu-id="d6779-107">Sigue lo que se conoce como el [modelo asincrónico basado en tareas (TAP)](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="d6779-107">It follows what is known as the [Task-based Asynchronous Pattern (TAP)](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span></span>

## <a name="basic-overview-of-the-asynchronous-model"></a><span data-ttu-id="d6779-108">Información general básica del modelo asincrónico</span><span class="sxs-lookup"><span data-stu-id="d6779-108">Basic Overview of the Asynchronous Model</span></span>

<span data-ttu-id="d6779-109">El núcleo de la programación asincrónica son los objetos `Task` y `Task<T>`, que modelan las operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="d6779-109">The core of async programming is the `Task` and `Task<T>` objects, which model asynchronous operations.</span></span>  <span data-ttu-id="d6779-110">Son compatibles con las palabras clave `async` y `await`.</span><span class="sxs-lookup"><span data-stu-id="d6779-110">They are supported by the `async` and `await` keywords.</span></span>  <span data-ttu-id="d6779-111">El modelo es bastante sencillo en la mayoría de los casos:</span><span class="sxs-lookup"><span data-stu-id="d6779-111">The model is fairly simple in most cases:</span></span>

<span data-ttu-id="d6779-112">Para el código enlazado a E/S, se aplica la palabra clave `await` a una operación que devuelve un objeto `Task` o `Task<T>` dentro de un método `async`.</span><span class="sxs-lookup"><span data-stu-id="d6779-112">For I/O-bound code, you `await` an operation which returns a `Task` or `Task<T>` inside of an `async` method.</span></span>

<span data-ttu-id="d6779-113">Para el código enlazado a la CPU, se aplica la palabra clave `await` a una operación que se inicia en un subproceso en segundo plano con el método `Task.Run`.</span><span class="sxs-lookup"><span data-stu-id="d6779-113">For CPU-bound code, you `await` an operation which is started on a background thread with the `Task.Run` method.</span></span>

<span data-ttu-id="d6779-114">La palabra clave `await` es donde ocurre la magia.</span><span class="sxs-lookup"><span data-stu-id="d6779-114">The `await` keyword is where the magic happens.</span></span> <span data-ttu-id="d6779-115">Genera control para el autor de la llamada del método que ha realizado `await`, y permite en última instancia una interfaz de usuario con capacidad de respuesta o un servicio flexible.</span><span class="sxs-lookup"><span data-stu-id="d6779-115">It yields control to the caller of the method that performed `await`, and it ultimately allows a UI to be responsive or a service to be elastic.</span></span>

<span data-ttu-id="d6779-116">Hay otras formas de abordar el código asincrónico aparte de `async` y `await`, que se describen en el artículo de TAP indicado anteriormente, pero en este documento nos centraremos en las construcciones de nivel de lenguaje de aquí en adelante.</span><span class="sxs-lookup"><span data-stu-id="d6779-116">There are other ways to approach async code than `async` and `await` outlined in the TAP article linked above, but this document will focus on the language-level constructs from this point forward.</span></span>

### <a name="io-bound-example-downloading-data-from-a-web-service"></a><span data-ttu-id="d6779-117">Ejemplo enlazado a E/S: descarga de datos de un servicio web</span><span class="sxs-lookup"><span data-stu-id="d6779-117">I/O-Bound Example: Downloading data from a web service</span></span>

<span data-ttu-id="d6779-118">Puede que necesite descargar algunos datos de un servicio web cuando se presione un botón, pero no quiera bloquear el subproceso de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="d6779-118">You may need to download some data from a web service when a button is pressed, but don’t want to block the UI thread.</span></span> <span data-ttu-id="d6779-119">Puede conseguirlo fácilmente de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="d6779-119">It can be accomplished simply like this:</span></span>

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

<span data-ttu-id="d6779-120">Y listo.</span><span class="sxs-lookup"><span data-stu-id="d6779-120">And that’s it!</span></span> <span data-ttu-id="d6779-121">El código expresa la intención (descargar algunos datos de forma asincrónica) sin verse obstaculizado en la interacción con objetos Task.</span><span class="sxs-lookup"><span data-stu-id="d6779-121">The code expresses the intent (downloading some data asynchronously) without getting bogged down in interacting with Task objects.</span></span>

### <a name="cpu-bound-example-performing-a-calculation-for-a-game"></a><span data-ttu-id="d6779-122">Ejemplo enlazado a la CPU: realizar un cálculo para un juego</span><span class="sxs-lookup"><span data-stu-id="d6779-122">CPU-bound Example: Performing a Calculation for a Game</span></span>

<span data-ttu-id="d6779-123">Supongamos que está escribiendo un juego para móviles en el que se pueden infligir daños a muchos enemigos en la pantalla pulsando un botón.</span><span class="sxs-lookup"><span data-stu-id="d6779-123">Say you're writing a mobile game where pressing a button can inflict damage on many enemies on the screen.</span></span>  <span data-ttu-id="d6779-124">Realizar el cálculo del daño puede resultar costoso y hacerlo en el subproceso de interfaz de usuario haría que pareciera que el juego se pone en pausa mientras se lleva a cabo el cálculo.</span><span class="sxs-lookup"><span data-stu-id="d6779-124">Performing the damage calculation can be expensive, and doing it on the UI thread would make the game appear to pause as the calculation is performed!</span></span>

<span data-ttu-id="d6779-125">La mejor manera de abordar esta situación consiste en iniciar un subproceso en segundo plano que realice la tarea mediante `Task.Run` y aplique la palabra clave `await` para esperar su resultado.</span><span class="sxs-lookup"><span data-stu-id="d6779-125">The best way to handle this is to start a background thread which does the work using `Task.Run`, and `await` its result.</span></span>  <span data-ttu-id="d6779-126">Esto permitirá que la interfaz de usuario funcione de manera fluida mientras se lleva a cabo la tarea.</span><span class="sxs-lookup"><span data-stu-id="d6779-126">This will allow the UI to feel smooth as the work is being done.</span></span>

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
    // performs its work.  The UI thread is free to perform other work.
    var damageResult = await Task.Run(() => CalculateDamageDone());
    DisplayDamage(damageResult);
};
```

<span data-ttu-id="d6779-127">Y listo.</span><span class="sxs-lookup"><span data-stu-id="d6779-127">And that's it!</span></span>  <span data-ttu-id="d6779-128">Este código expresa claramente la intención del evento de clic del botón, no requiere la administración manual de un subproceso en segundo plano y lo hace en un modo sin bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d6779-128">This code cleanly expresses the intent of the button's click event, it doesn't require managing a background thread manually, and it does so in a non-blocking way.</span></span>

### <a name="what-happens-under-the-covers"></a><span data-ttu-id="d6779-129">Qué sucede en segundo plano</span><span class="sxs-lookup"><span data-stu-id="d6779-129">What happens under the covers</span></span>

<span data-ttu-id="d6779-130">En las operaciones asincrónicas existen numerosos aspectos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="d6779-130">There's a lot of moving pieces where asynchronous operations are concerned.</span></span>  <span data-ttu-id="d6779-131">Si siente curiosidad sobre lo que ocurre en el segundo plano de `Task` y `Task<T>`, eche un vistazo al artículo [Async en profundidad](../standard/async-in-depth.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d6779-131">If you're curious about what's happening underneath the covers of `Task` and `Task<T>`, checkout the [Async in-depth](../standard/async-in-depth.md) article for more information.</span></span>

<span data-ttu-id="d6779-132">En lo que respecta a C#, el compilador transforma el código en una máquina de estados que realiza el seguimiento de acciones como la retención de la ejecución cuando se alcanza `await` y la reanudación de la ejecución cuando se ha finalizado un trabajo en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="d6779-132">On the C# side of things, the compiler transforms your code into a state machine which keeps track of things like yielding execution when an `await` is reached and resuming execution when a background job has finished.</span></span>

<span data-ttu-id="d6779-133">Para los más interesados en la teoría, se trata de una implementación del [modelo de promesas de asincronía](https://en.wikipedia.org/wiki/Futures_and_promises).</span><span class="sxs-lookup"><span data-stu-id="d6779-133">For the theoretically-inclined, this is an implementation of the [Promise Model of asynchrony](https://en.wikipedia.org/wiki/Futures_and_promises).</span></span>

## <a name="key-pieces-to-understand"></a><span data-ttu-id="d6779-134">Piezas clave que debe comprender</span><span class="sxs-lookup"><span data-stu-id="d6779-134">Key Pieces to Understand</span></span>

* <span data-ttu-id="d6779-135">El código asincrónico puede usarse para código tanto enlazado a E/S como enlazado a la CPU, pero de forma distinta en cada escenario.</span><span class="sxs-lookup"><span data-stu-id="d6779-135">Async code can be used for both I/O-bound and CPU-bound code, but differently for each scenario.</span></span>
* <span data-ttu-id="d6779-136">El código asincrónico usa `Task<T>` y `Task`, que son construcciones que se usan para modelar el trabajo que se realiza en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="d6779-136">Async code uses `Task<T>` and `Task`, which are constructs used to model work being done in the background.</span></span>
* <span data-ttu-id="d6779-137">La palabra clave `async` convierte un método en un método asincrónico, lo que permite usar la palabra clave `await` en su cuerpo.</span><span class="sxs-lookup"><span data-stu-id="d6779-137">The `async` keyword turns a method into an async method, which allows you to use the `await` keyword in its body.</span></span>
* <span data-ttu-id="d6779-138">Cuando se aplica la palabra clave `await`, se suspende el método de llamada y se cede el control al autor de la llamada hasta que se completa la tarea esperada.</span><span class="sxs-lookup"><span data-stu-id="d6779-138">When the `await` keyword is applied, it suspends the calling method and yields control back to its caller until the awaited task is complete.</span></span>
* <span data-ttu-id="d6779-139">`await` solo puede usarse dentro de un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="d6779-139">`await` can only be used inside an async method.</span></span>

## <a name="recognize-cpu-bound-and-io-bound-work"></a><span data-ttu-id="d6779-140">Reconocer el trabajo enlazado a la CPU y el enlazado a E/S</span><span class="sxs-lookup"><span data-stu-id="d6779-140">Recognize CPU-Bound and I/O-Bound Work</span></span>

<span data-ttu-id="d6779-141">En los dos primeros ejemplos de esta guía se ha explicado cómo se puede usar `async` y `await` para trabajos enlazados a E/S y a la CPU.</span><span class="sxs-lookup"><span data-stu-id="d6779-141">The first two examples of this guide showed how you can use `async` and `await` for I/O-bound and CPU-bound work.</span></span>  <span data-ttu-id="d6779-142">Resulta fundamental que pueda identificar si el trabajo que debe realizar está enlazado a E/S o a la CPU, ya que esto puede afectar en gran medida al rendimiento del código y podría dar lugar al uso inadecuado de ciertas construcciones.</span><span class="sxs-lookup"><span data-stu-id="d6779-142">It's key that you can identify when a job you need to do is I/O-bound or CPU-bound, because it can greatly affect the performance of your code and could potentially lead to misusing certain constructs.</span></span>

<span data-ttu-id="d6779-143">A continuación, se indican dos preguntas que debe hacerse antes de escribir el código:</span><span class="sxs-lookup"><span data-stu-id="d6779-143">Here are two questions you should ask before you write any code:</span></span>

1. <span data-ttu-id="d6779-144">¿Estará su código "esperando" algo, como datos de una base de datos?</span><span class="sxs-lookup"><span data-stu-id="d6779-144">Will your code be "waiting" for something, such as data from a database?</span></span>

    <span data-ttu-id="d6779-145">Si la respuesta es "sí", su trabajo está **enlazado a E/S**.</span><span class="sxs-lookup"><span data-stu-id="d6779-145">If your answer is "yes", then your work is **I/O-bound**.</span></span>

2. <span data-ttu-id="d6779-146">¿Realizará el código un cálculo muy costoso?</span><span class="sxs-lookup"><span data-stu-id="d6779-146">Will your code be performing a very expensive computation?</span></span>

    <span data-ttu-id="d6779-147">Si la respuesta es "sí", su trabajo está **enlazado a la CPU**.</span><span class="sxs-lookup"><span data-stu-id="d6779-147">If you answered "yes", then your work is **CPU-bound**.</span></span>

<span data-ttu-id="d6779-148">Si el trabajo que tiene está **enlazado a E/S**, use `async` y `await` *sin* `Task.Run`.</span><span class="sxs-lookup"><span data-stu-id="d6779-148">If the work you have is **I/O-bound**, use `async` and `await` *without* `Task.Run`.</span></span>  <span data-ttu-id="d6779-149">*No debe* usar la Biblioteca TPL.</span><span class="sxs-lookup"><span data-stu-id="d6779-149">You *should not* use the Task Parallel Library.</span></span>  <span data-ttu-id="d6779-150">Esto se explica en el artículo [Async en profundidad](../standard/async-in-depth.md).</span><span class="sxs-lookup"><span data-stu-id="d6779-150">The reason for this is outlined in the [Async in Depth article](../standard/async-in-depth.md).</span></span>

<span data-ttu-id="d6779-151">Si el trabajo que tiene está **enlazado a la CPU** y le interesa la capacidad de respuesta, use `async` y `await`, pero genere el trabajo en otro subproceso *con* `Task.Run`.</span><span class="sxs-lookup"><span data-stu-id="d6779-151">If the work you have is **CPU-bound** and you care about responsiveness, use `async` and `await` but spawn the work off on another thread *with* `Task.Run`.</span></span>  <span data-ttu-id="d6779-152">Si el trabajo es adecuado para la simultaneidad y el paralelismo, también debe plantearse el uso de la [biblioteca TPL](../standard/parallel-programming/task-parallel-library-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="d6779-152">If the work is appropriate for concurrency and parallelism, you should also consider using the [Task Parallel Library](../standard/parallel-programming/task-parallel-library-tpl.md).</span></span>

<span data-ttu-id="d6779-153">Además, siempre debe medir la ejecución del código.</span><span class="sxs-lookup"><span data-stu-id="d6779-153">Additionally, you should always measure the execution of your code.</span></span>  <span data-ttu-id="d6779-154">Por ejemplo, puede verse en una situación en la que el trabajo enlazado a la CPU no sea suficientemente costoso en comparación con la sobrecarga de cambios de contexto cuando realice multithreading.</span><span class="sxs-lookup"><span data-stu-id="d6779-154">For example, you may find yourself in a situation where your CPU-bound work is not costly enough compared with the overhead of context switches when multithreading.</span></span>  <span data-ttu-id="d6779-155">Cada opción tiene su compensación y debe elegir el equilibrio correcto para su situación.</span><span class="sxs-lookup"><span data-stu-id="d6779-155">Every choice has its tradeoff, and you should pick the correct tradeoff for your situation.</span></span>

## <a name="more-examples"></a><span data-ttu-id="d6779-156">Más ejemplos</span><span class="sxs-lookup"><span data-stu-id="d6779-156">More Examples</span></span>

<span data-ttu-id="d6779-157">En los ejemplos siguientes se muestran distintas maneras en las que puede escribir código asincrónico en C#.</span><span class="sxs-lookup"><span data-stu-id="d6779-157">The following examples demonstrate various ways you can write async code in C#.</span></span>  <span data-ttu-id="d6779-158">Abarcan algunos escenarios diferentes con los que puede encontrarse.</span><span class="sxs-lookup"><span data-stu-id="d6779-158">They cover a few different scenarios you may come across.</span></span>

### <a name="extracting-data-from-a-network"></a><span data-ttu-id="d6779-159">Extraer datos de una red</span><span class="sxs-lookup"><span data-stu-id="d6779-159">Extracting Data from a Network</span></span>

<span data-ttu-id="d6779-160">Este fragmento de código descarga el HTML desde la página principal en [www.dotnetfoundation.org](https://www.dotnetfoundation.org) y cuenta el número de veces que aparece la cadena ".NET" en el código HTML.</span><span class="sxs-lookup"><span data-stu-id="d6779-160">This snippet downloads the HTML from the homepage at [www.dotnetfoundation.org](https://www.dotnetfoundation.org) and counts the number of times the string ".NET" occurs in the HTML.</span></span>  <span data-ttu-id="d6779-161">Usa ASP.NET MVC para definir un método de controlador web que realiza esta tarea y devuelve el número.</span><span class="sxs-lookup"><span data-stu-id="d6779-161">It uses ASP.NET MVC to define a web controller method which performs this task, returning the number.</span></span>

> [!NOTE]
> <span data-ttu-id="d6779-162">Si tiene previsto realizar un análisis HTML en el código de producción, no use expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="d6779-162">If you plan on doing HTML parsing in production code, don't use regular expressions.</span></span> <span data-ttu-id="d6779-163">Use una biblioteca de análisis en su lugar.</span><span class="sxs-lookup"><span data-stu-id="d6779-163">Use a parsing library instead.</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

[HttpGet]
[Route("DotNetCount")]
public async Task<int> GetDotNetCountAsync()
{
    // Suspends GetDotNetCountAsync() to allow the caller (the web server)
    // to accept another request, rather than blocking on this one.
    var html = await _httpClient.GetStringAsync("https://dotnetfoundation.org");

    return Regex.Matches(html, @"\.NET").Count;
}
```

<span data-ttu-id="d6779-164">Este es el mismo escenario escrito para una aplicación Windows Universal, que realiza la misma tarea cuando se presiona un botón:</span><span class="sxs-lookup"><span data-stu-id="d6779-164">Here's the same scenario written for a Universal Windows App, which performs the same task when a Button is pressed:</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

private async void SeeTheDotNets_Click(object sender, RoutedEventArgs e)
{
    // Capture the task handle here so we can await the background task later.
    var getDotNetFoundationHtmlTask = _httpClient.GetStringAsync("https://www.dotnetfoundation.org");

    // Any other work on the UI thread can be done here, such as enabling a Progress Bar.
    // This is important to do here, before the "await" call, so that the user
    // sees the progress bar before execution of this method is yielded.
    NetworkProgressBar.IsEnabled = true;
    NetworkProgressBar.Visibility = Visibility.Visible;

    // The await operator suspends SeeTheDotNets_Click, returning control to its caller.
    // This is what allows the app to be responsive and not block the UI thread.
    var html = await getDotNetFoundationHtmlTask;
    int count = Regex.Matches(html, @"\.NET").Count;

    DotNetCountLabel.Text = $"Number of .NETs on dotnetfoundation.org: {count}";

    NetworkProgressBar.IsEnabled = false;
    NetworkProgressBar.Visibility = Visibility.Collapsed;
}
```

### <a name="waiting-for-multiple-tasks-to-complete"></a><span data-ttu-id="d6779-165">Esperar a que se completen varias tareas</span><span class="sxs-lookup"><span data-stu-id="d6779-165">Waiting for Multiple Tasks to Complete</span></span>

<span data-ttu-id="d6779-166">Es posible que se vea en una situación en la que necesite recuperar varios fragmentos de datos al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="d6779-166">You may find yourself in a situation where you need to retrieve multiple pieces of data concurrently.</span></span>  <span data-ttu-id="d6779-167">La API `Task` contiene dos métodos, `Task.WhenAll` y `Task.WhenAny`, que permiten escribir código asincrónico que realiza una espera sin bloqueo en varios trabajos en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="d6779-167">The `Task` API contains two methods, `Task.WhenAll` and `Task.WhenAny` which allow you to write asynchronous code which performs a non-blocking wait on multiple background jobs.</span></span>

<span data-ttu-id="d6779-168">En este ejemplo se muestra cómo podría captar datos `User` de un conjunto de elementos `userId`.</span><span class="sxs-lookup"><span data-stu-id="d6779-168">This example shows how you might grab `User` data for a set of `userId`s.</span></span>

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

<span data-ttu-id="d6779-169">Aquí tiene otra manera de escribir lo mismo de una forma más sucinta, con LINQ:</span><span class="sxs-lookup"><span data-stu-id="d6779-169">Here's another way to write this a bit more succinctly, using LINQ:</span></span>

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

<span data-ttu-id="d6779-170">Aunque es menos código, tenga cuidado al combinar LINQ con código asincrónico.</span><span class="sxs-lookup"><span data-stu-id="d6779-170">Although it's less code, take care when mixing LINQ with asynchronous code.</span></span>  <span data-ttu-id="d6779-171">Dado que LINQ usa la ejecución diferida, las llamadas asincrónicas no se realizarán inmediatamente, como lo hacen en un bucle `foreach()`, a menos que fuerce la secuencia generada a procesar una iteración con una llamada a `.ToList()` o `.ToArray()`.</span><span class="sxs-lookup"><span data-stu-id="d6779-171">Because LINQ uses deferred (lazy) execution, async calls won't happen immediately as they do in a `foreach()` loop unless you force the generated sequence to iterate with a call to `.ToList()` or `.ToArray()`.</span></span>

## <a name="important-info-and-advice"></a><span data-ttu-id="d6779-172">Consejos e información importante</span><span class="sxs-lookup"><span data-stu-id="d6779-172">Important Info and Advice</span></span>

<span data-ttu-id="d6779-173">Aunque la programación asincrónica es relativamente sencilla, hay algunos detalles que debe tener en cuenta para evitar un comportamiento inesperado.</span><span class="sxs-lookup"><span data-stu-id="d6779-173">Although async programming is relatively straightforward, there are some details to keep in mind which can prevent unexpected behavior.</span></span>

* <span data-ttu-id="d6779-174">Los métodos `async` **deben tener una palabra clave** `await` **en el cuerpo o nunca proporcionarán resultados**.</span><span class="sxs-lookup"><span data-stu-id="d6779-174">`async` **methods need to have an** `await` **keyword in their body or they will never yield!**</span></span>

<span data-ttu-id="d6779-175">Es importante que tenga esto en cuenta.</span><span class="sxs-lookup"><span data-stu-id="d6779-175">This is important to keep in mind.</span></span>  <span data-ttu-id="d6779-176">Si no se usa `await` en el cuerpo de un método `async`, el compilador de C# generará una advertencia, pero el código se compilará y se ejecutará como si se tratara de un método normal.</span><span class="sxs-lookup"><span data-stu-id="d6779-176">If `await` is not used in the body of an `async` method, the C# compiler will generate a warning, but the code will compile and run as if it were a normal method.</span></span>  <span data-ttu-id="d6779-177">Tenga en cuenta también que esto sería muy ineficaz, ya que la máquina de estados generada por el compilador de C# para el método asincrónico no realizaría nada.</span><span class="sxs-lookup"><span data-stu-id="d6779-177">Note that this would also be incredibly inefficient, as the state machine generated by the C# compiler for the async method would not be accomplishing anything.</span></span>

* <span data-ttu-id="d6779-178">**Debe agregar "Async" como el sufijo de todos los métodos asincrónicos que escriba.**</span><span class="sxs-lookup"><span data-stu-id="d6779-178">**You should add "Async" as the suffix of every async method name you write.**</span></span>

<span data-ttu-id="d6779-179">Se trata de la convención que se usa en .NET para distinguir más fácilmente los métodos sincrónicos de los asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="d6779-179">This is the convention used in .NET to more-easily differentiate synchronous and asynchronous methods.</span></span> <span data-ttu-id="d6779-180">Tenga en cuenta que no se aplican necesariamente ciertos métodos a los que el código no llame explícitamente (como controladores de eventos o métodos de controlador web).</span><span class="sxs-lookup"><span data-stu-id="d6779-180">Note that certain methods which aren’t explicitly called by your code (such as event handlers or web controller methods) don’t necessarily apply.</span></span> <span data-ttu-id="d6779-181">Puesto que el código no los llama explícitamente, resulta importante explicitar sus nombres.</span><span class="sxs-lookup"><span data-stu-id="d6779-181">Because these are not explicitly called by your code, being explicit about their naming isn’t as important.</span></span>

* <span data-ttu-id="d6779-182">`async void` **solo se debe usar para controladores de eventos.**</span><span class="sxs-lookup"><span data-stu-id="d6779-182">`async void` **should only be used for event handlers.**</span></span>

<span data-ttu-id="d6779-183">`async void` es la única manera de permitir a los controladores de eventos asincrónicos trabajar, ya que los eventos no tienen tipos de valor devuelto (por lo tanto, no pueden hacer uso de `Task` y `Task<T>`).</span><span class="sxs-lookup"><span data-stu-id="d6779-183">`async void` is the only way to allow asynchronous event handlers to work because events do not have return types (thus cannot make use of `Task` and `Task<T>`).</span></span> <span data-ttu-id="d6779-184">Cualquier otro uso de `async void` no sigue el modelo de TAP y puede resultar difícil de usar, como:</span><span class="sxs-lookup"><span data-stu-id="d6779-184">Any other use of `async void` does not follow the TAP model and can be challenging to use, such as:</span></span>

* <span data-ttu-id="d6779-185">Las excepciones producidas en un método `async void` no se pueden detectar fuera de ese método.</span><span class="sxs-lookup"><span data-stu-id="d6779-185">Exceptions thrown in an `async void` method can’t be caught outside of that method.</span></span>
* <span data-ttu-id="d6779-186">Los métodos `async void` resultan muy difíciles de probar.</span><span class="sxs-lookup"><span data-stu-id="d6779-186">`async void` methods are very difficult to test.</span></span>
* <span data-ttu-id="d6779-187">Los métodos `async void` pueden provocar efectos secundarios negativos si el autor de la llamada no espera que sean asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="d6779-187">`async void` methods can cause bad side effects if the caller isn’t expecting them to be async.</span></span>

* <span data-ttu-id="d6779-188">**Tenga cuidado al usar lambdas asincrónicas en las expresiones de LINQ.**</span><span class="sxs-lookup"><span data-stu-id="d6779-188">**Tread carefully when using async lambdas in LINQ expressions**</span></span>

<span data-ttu-id="d6779-189">Las expresiones lambda de LINQ usan la ejecución aplazada, lo que implica que el código podría acabar ejecutándose en un momento en que no se lo espere.</span><span class="sxs-lookup"><span data-stu-id="d6779-189">Lambda expressions in LINQ use deferred execution, meaning code could end up executing at a time when you’re not expecting it to.</span></span> <span data-ttu-id="d6779-190">La introducción de las tareas de bloqueo puede dar lugar a un interbloqueo si no se han escrito correctamente.</span><span class="sxs-lookup"><span data-stu-id="d6779-190">The introduction of blocking tasks into this can easily result in a deadlock if not written correctly.</span></span> <span data-ttu-id="d6779-191">Además, el anidamiento de código asincrónico de esta manera también puede hacer que resulte más difícil razonar sobre la ejecución del código.</span><span class="sxs-lookup"><span data-stu-id="d6779-191">Additionally, the nesting of asynchronous code like this can also make it more difficult to reason about the execution of the code.</span></span> <span data-ttu-id="d6779-192">Async y LINQ son eficaces, pero deben usarse conjuntamente con el mayor cuidado y claridad posible.</span><span class="sxs-lookup"><span data-stu-id="d6779-192">Async and LINQ are powerful, but should be used together as carefully and clearly as possible.</span></span>

* <span data-ttu-id="d6779-193">**Escriba código que espere las tareas sin bloqueo.**</span><span class="sxs-lookup"><span data-stu-id="d6779-193">**Write code that awaits Tasks in a non-blocking manner**</span></span>

<span data-ttu-id="d6779-194">Bloquear el subproceso actual como un medio para esperar que se complete una tarea puede dar lugar a interbloqueos y subprocesos de contexto bloqueados, y puede requerir un control de errores mucho más complejo.</span><span class="sxs-lookup"><span data-stu-id="d6779-194">Blocking the current thread as a means to wait for a Task to complete can result in deadlocks and blocked context threads, and can require significantly more complex error-handling.</span></span> <span data-ttu-id="d6779-195">En la tabla siguiente se ofrece orientación sobre cómo abordar la espera de las tareas de una manera que no produzca un bloqueo:</span><span class="sxs-lookup"><span data-stu-id="d6779-195">The following table provides guidance on how to deal with waiting for Tasks in a non-blocking way:</span></span>

| <span data-ttu-id="d6779-196">Use esto...</span><span class="sxs-lookup"><span data-stu-id="d6779-196">Use this...</span></span> | <span data-ttu-id="d6779-197">En vez de esto...</span><span class="sxs-lookup"><span data-stu-id="d6779-197">Instead of this...</span></span> | <span data-ttu-id="d6779-198">Cuando quiera hacer esto</span><span class="sxs-lookup"><span data-stu-id="d6779-198">When wishing to do this</span></span> |
| --- | --- | --- |
| `await` | <span data-ttu-id="d6779-199">`Task.Wait` o `Task.Result`</span><span class="sxs-lookup"><span data-stu-id="d6779-199">`Task.Wait` or `Task.Result`</span></span> | <span data-ttu-id="d6779-200">Recuperar el resultado de una tarea en segundo plano</span><span class="sxs-lookup"><span data-stu-id="d6779-200">Retrieving the result of a background task</span></span> |
| `await Task.WhenAny` | `Task.WaitAny` | <span data-ttu-id="d6779-201">Esperar que finalice cualquier tarea</span><span class="sxs-lookup"><span data-stu-id="d6779-201">Waiting for any task to complete</span></span> |
| `await Task.WhenAll` | `Task.WaitAll` | <span data-ttu-id="d6779-202">Esperar que finalicen todas las tareas</span><span class="sxs-lookup"><span data-stu-id="d6779-202">Waiting for all tasks to complete</span></span> |
| `await Task.Delay` | `Thread.Sleep` | <span data-ttu-id="d6779-203">Esperar un período de tiempo</span><span class="sxs-lookup"><span data-stu-id="d6779-203">Waiting for a period of time</span></span> |

* <span data-ttu-id="d6779-204">**Escriba código con menos estados.**</span><span class="sxs-lookup"><span data-stu-id="d6779-204">**Write less stateful code**</span></span>

<span data-ttu-id="d6779-205">No dependa del estado de los objetos globales o la ejecución de ciertos métodos.</span><span class="sxs-lookup"><span data-stu-id="d6779-205">Don’t depend on the state of global objects or the execution of certain methods.</span></span> <span data-ttu-id="d6779-206">En su lugar, dependa únicamente de los valores devueltos de los métodos.</span><span class="sxs-lookup"><span data-stu-id="d6779-206">Instead, depend only on the return values of methods.</span></span> <span data-ttu-id="d6779-207">¿Por qué?</span><span class="sxs-lookup"><span data-stu-id="d6779-207">Why?</span></span>

* <span data-ttu-id="d6779-208">Le resultará más fácil razonar sobre el código.</span><span class="sxs-lookup"><span data-stu-id="d6779-208">Code will be easier to reason about.</span></span>
* <span data-ttu-id="d6779-209">Le resultará más fácil probar el código.</span><span class="sxs-lookup"><span data-stu-id="d6779-209">Code will be easier to test.</span></span>
* <span data-ttu-id="d6779-210">Resulta mucho más sencillo mezclar código asincrónico y sincrónico.</span><span class="sxs-lookup"><span data-stu-id="d6779-210">Mixing async and synchronous code is far simpler.</span></span>
* <span data-ttu-id="d6779-211">Normalmente se pueden evitar por completo las condiciones de carrera.</span><span class="sxs-lookup"><span data-stu-id="d6779-211">Race conditions can typically be avoided altogether.</span></span>
* <span data-ttu-id="d6779-212">Depender de los valores devueltos facilita la coordinación de código asincrónico.</span><span class="sxs-lookup"><span data-stu-id="d6779-212">Depending on return values makes coordinating async code simple.</span></span>
* <span data-ttu-id="d6779-213">(Extra) Funciona muy bien con la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="d6779-213">(Bonus) it works really well with dependency injection.</span></span>

<span data-ttu-id="d6779-214">Un objetivo recomendado es lograr una [transparencia referencial](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29) completa o casi completa en el código.</span><span class="sxs-lookup"><span data-stu-id="d6779-214">A recommended goal is to achieve complete or near-complete [Referential Transparency](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29) in your code.</span></span> <span data-ttu-id="d6779-215">Esto se traducirá en un código base extremadamente predecible, que se puede probar y es fácil de mantener.</span><span class="sxs-lookup"><span data-stu-id="d6779-215">Doing so will result in an extremely predictable, testable, and maintainable codebase.</span></span>

## <a name="other-resources"></a><span data-ttu-id="d6779-216">Otros recursos</span><span class="sxs-lookup"><span data-stu-id="d6779-216">Other Resources</span></span>

* <span data-ttu-id="d6779-217">En el artículo [Async en profundidad](../standard/async-in-depth.md) se proporciona más información sobre cómo funcionan las tareas.</span><span class="sxs-lookup"><span data-stu-id="d6779-217">[Async in-depth](../standard/async-in-depth.md) provides more information about how Tasks work.</span></span>
* [<span data-ttu-id="d6779-218">Programación asincrónica con async y await (C#)</span><span class="sxs-lookup"><span data-stu-id="d6779-218">Asynchronous programming with async and await (C#)</span></span>](./programming-guide/concepts/async/index.md)
* <span data-ttu-id="d6779-219">Los vídeos [Six Essential Tips for Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async) (Seis consejos esenciales para la programación asincrónica) de Lucian Wischik son un recurso fantástico para este tipo de programación.</span><span class="sxs-lookup"><span data-stu-id="d6779-219">Lucian Wischik's [Six Essential Tips for Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async) are a wonderful resource for async programming</span></span>
