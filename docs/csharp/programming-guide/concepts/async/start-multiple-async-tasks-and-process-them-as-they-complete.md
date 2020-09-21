---
title: Procesamiento de tareas asincrónicas a medida que se completan
description: En este ejemplo se muestra cómo usar Task.WhenAny en C# para iniciar varias tareas y procesar los resultados a medida que finalizan, en lugar de procesarlos en el orden en que se inician.
ms.date: 08/19/2020
ms.assetid: 25331850-35a7-43b3-ab76-3908e4346b9d
ms.openlocfilehash: 520953eaf851dc82440e39b348aa4b246255e126
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557312"
---
# <a name="process-asynchronous-tasks-as-they-complete-c"></a><span data-ttu-id="061bb-103">Iniciar varias tareas asincrónicas y procesarlas a medida que se completan (C#)</span><span class="sxs-lookup"><span data-stu-id="061bb-103">Process asynchronous tasks as they complete (C#)</span></span>

<span data-ttu-id="061bb-104">Si usa <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, puede iniciar varias tareas a la vez y procesarlas una por una a medida que se completen, en lugar de procesarlas en el orden en el que se han iniciado.</span><span class="sxs-lookup"><span data-stu-id="061bb-104">By using <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, you can start multiple tasks at the same time and process them one by one as they're completed rather than process them in the order in which they're started.</span></span>

<span data-ttu-id="061bb-105">En el siguiente ejemplo se usa una consulta para crear una colección de tareas.</span><span class="sxs-lookup"><span data-stu-id="061bb-105">The following example uses a query to create a collection of tasks.</span></span> <span data-ttu-id="061bb-106">Cada tarea descarga el contenido de un sitio web especificado.</span><span class="sxs-lookup"><span data-stu-id="061bb-106">Each task downloads the contents of a specified website.</span></span> <span data-ttu-id="061bb-107">En cada iteración de un bucle while, una llamada awaited a <xref:System.Threading.Tasks.Task.WhenAny%2A> devuelve la tarea en la colección de tareas que termine primero su descarga.</span><span class="sxs-lookup"><span data-stu-id="061bb-107">In each iteration of a while loop, an awaited call to <xref:System.Threading.Tasks.Task.WhenAny%2A> returns the task in the collection of tasks that finishes its download first.</span></span> <span data-ttu-id="061bb-108">Esa tarea se quita de la colección y se procesa.</span><span class="sxs-lookup"><span data-stu-id="061bb-108">That task is removed from the collection and processed.</span></span> <span data-ttu-id="061bb-109">El bucle se repite hasta que la colección no contiene más tareas.</span><span class="sxs-lookup"><span data-stu-id="061bb-109">The loop repeats until the collection contains no more tasks.</span></span>

## <a name="create-example-application"></a><span data-ttu-id="061bb-110">Creación de una aplicación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="061bb-110">Create example application</span></span>

<span data-ttu-id="061bb-111">Cree una nueva aplicación de consola de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="061bb-111">Create a new .NET Core console application.</span></span> <span data-ttu-id="061bb-112">Puede crear una mediante el comando [dotnet new console](../../../../core/tools/dotnet-new.md#console) o desde [Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="061bb-112">You can create one by using the [dotnet new console](../../../../core/tools/dotnet-new.md#console) command or from [Visual Studio](/visualstudio/install/install-visual-studio).</span></span> <span data-ttu-id="061bb-113">Abra el archivo *Program.cs* en su editor de código favorito.</span><span class="sxs-lookup"><span data-stu-id="061bb-113">Open the *Program.cs* file in your favorite code editor.</span></span>

### <a name="replace-using-statements"></a><span data-ttu-id="061bb-114">Reemplazo de instrucciones using</span><span class="sxs-lookup"><span data-stu-id="061bb-114">Replace using statements</span></span>

<span data-ttu-id="061bb-115">Reemplace las instrucciones using existentes por estas declaraciones:</span><span class="sxs-lookup"><span data-stu-id="061bb-115">Replace the existing using statements with these declarations:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Linq;
using System.Net.Http;
using System.Threading.Tasks;
```

## <a name="add-fields"></a><span data-ttu-id="061bb-116">Adición de campos</span><span class="sxs-lookup"><span data-stu-id="061bb-116">Add fields</span></span>

<span data-ttu-id="061bb-117">Dentro de la definición de la clase `Program`, agregue los dos campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="061bb-117">In the `Program` class definition, add the following two fields:</span></span>

```csharp
static readonly HttpClient s_client = new HttpClient
{
    MaxResponseContentBufferSize = 1_000_000
};

static readonly IEnumerable<string> s_urlList = new string[]
{
    "https://docs.microsoft.com",
    "https://docs.microsoft.com/aspnet/core",
    "https://docs.microsoft.com/azure",
    "https://docs.microsoft.com/azure/devops",
    "https://docs.microsoft.com/dotnet",
    "https://docs.microsoft.com/dynamics365",
    "https://docs.microsoft.com/education",
    "https://docs.microsoft.com/enterprise-mobility-security",
    "https://docs.microsoft.com/gaming",
    "https://docs.microsoft.com/graph",
    "https://docs.microsoft.com/microsoft-365",
    "https://docs.microsoft.com/office",
    "https://docs.microsoft.com/powershell",
    "https://docs.microsoft.com/sql",
    "https://docs.microsoft.com/surface",
    "https://docs.microsoft.com/system-center",
    "https://docs.microsoft.com/visualstudio",
    "https://docs.microsoft.com/windows",
    "https://docs.microsoft.com/xamarin"
};
```

<span data-ttu-id="061bb-118">`HttpClient` expone la capacidad de enviar solicitudes HTTP y de recibir respuestas HTTP.</span><span class="sxs-lookup"><span data-stu-id="061bb-118">The `HttpClient` exposes the ability to send HTTP requests and receive HTTP responses.</span></span> <span data-ttu-id="061bb-119">`s_urlList` contiene todas las direcciones URL que planea procesar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="061bb-119">The `s_urlList` holds all of the URLs that the application plans to process.</span></span>

## <a name="update-application-entry-point"></a><span data-ttu-id="061bb-120">Actualización del punto de entrada de la aplicación</span><span class="sxs-lookup"><span data-stu-id="061bb-120">Update application entry point</span></span>

<span data-ttu-id="061bb-121">El punto de entrada principal de la aplicación de consola es el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="061bb-121">The main entry point into the console application is the `Main` method.</span></span> <span data-ttu-id="061bb-122">Reemplace el método existente por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="061bb-122">Replace the existing method with the following:</span></span>

```csharp
static Task Main() => SumPageSizesAsync();
```

<span data-ttu-id="061bb-123">El método `Main` actualizado ahora se considera un método [Async main](../../../whats-new/csharp-7-1.md#async-main), el cual permite un punto de entrada asincrónico en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="061bb-123">The updated `Main` method is now considered an [Async main](../../../whats-new/csharp-7-1.md#async-main), which allows for an asynchronous entry point into the executable.</span></span> <span data-ttu-id="061bb-124">Se trata de una llamada a `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="061bb-124">It is expressed a call to `SumPageSizesAsync`.</span></span>

## <a name="create-the-asynchronous-sum-page-sizes-method"></a><span data-ttu-id="061bb-125">Creación de un método SumPageSizes asincrónico</span><span class="sxs-lookup"><span data-stu-id="061bb-125">Create the asynchronous sum page sizes method</span></span>

<span data-ttu-id="061bb-126">Agregue el método `SumPageSizesAsync` después del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="061bb-126">Below the `Main` method, add the `SumPageSizesAsync` method:</span></span>

```csharp
static async Task SumPageSizesAsync()
{
    var stopwatch = Stopwatch.StartNew();

    IEnumerable<Task<int>> downloadTasksQuery =
        from url in s_urlList
        select ProcessUrlAsync(url, s_client);

    List<Task<int>> downloadTasks = downloadTasksQuery.ToList();

    int total = 0;
    while (downloadTasks.Any())
    {
        Task<int> finishedTask = await Task.WhenAny(downloadTasks);
        downloadTasks.Remove(finishedTask);
        total += await finishedTask;
    }

    stopwatch.Stop();

    Console.WriteLine($"\nTotal bytes returned:  {total:#,#}");
    Console.WriteLine($"Elapsed time:          {stopwatch.Elapsed}\n");
}
```

<span data-ttu-id="061bb-127">El método comienza creando una instancia e iniciando una clase <xref:System.Diagnostics.Stopwatch>.</span><span class="sxs-lookup"><span data-stu-id="061bb-127">The method starts by instantiating and starting a <xref:System.Diagnostics.Stopwatch>.</span></span> <span data-ttu-id="061bb-128">Después, incluye una consulta que, cuando se ejecuta, crea una colección de tareas.</span><span class="sxs-lookup"><span data-stu-id="061bb-128">It then includes a query that, when executed, creates a collection of tasks.</span></span> <span data-ttu-id="061bb-129">Cada llamada a `ProcessUrlAsync` en el siguiente código devuelve un objeto <xref:System.Threading.Tasks.Task%601>, donde `TResult` es un entero:</span><span class="sxs-lookup"><span data-stu-id="061bb-129">Each call to `ProcessUrlAsync` in the following code returns a <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer:</span></span>

```csharp
IEnumerable<Task<int>> downloadTasksQuery =
    from url in s_urlList
    select ProcessUrlAsync(url, s_client);
```

<span data-ttu-id="061bb-130">Debido a la [ejecución diferida](../../../../standard/linq/deferred-execution-example.md) con LINQ, se llama a <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> para iniciar cada tarea.</span><span class="sxs-lookup"><span data-stu-id="061bb-130">Due to [deferred execution](../../../../standard/linq/deferred-execution-example.md) with the LINQ, you call <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> to start each task.</span></span>

```csharp
List<Task<int>> downloadTasks = downloadTasksQuery.ToList();
```

<span data-ttu-id="061bb-131">El bucle `while` realiza los pasos siguientes para cada tarea de la colección:</span><span class="sxs-lookup"><span data-stu-id="061bb-131">The `while` loop performs the following steps for each task in the collection:</span></span>

1. <span data-ttu-id="061bb-132">Espera una llamada a `WhenAny` para identificar la primera tarea de la colección que ha finalizado su descarga.</span><span class="sxs-lookup"><span data-stu-id="061bb-132">Awaits a call to `WhenAny` to identify the first task in the collection that has finished its download.</span></span>

    ```csharp
    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);
    ```

1. <span data-ttu-id="061bb-133">Quita la tarea de la colección.</span><span class="sxs-lookup"><span data-stu-id="061bb-133">Removes that task from the collection.</span></span>

    ```csharp
    downloadTasks.Remove(firstFinishedTask);
    ```

1. <span data-ttu-id="061bb-134">Espera `finishedTask`, que se devuelve mediante una llamada a `ProcessUrlAsync`.</span><span class="sxs-lookup"><span data-stu-id="061bb-134">Awaits `finishedTask`, which is returned by a call to `ProcessUrlAsync`.</span></span> <span data-ttu-id="061bb-135">La variable `finishedTask` es un <xref:System.Threading.Tasks.Task%601> donde `TResult` es un entero.</span><span class="sxs-lookup"><span data-stu-id="061bb-135">The `finishedTask` variable is a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span> <span data-ttu-id="061bb-136">La tarea ya está completa, pero la espera para recuperar la longitud del sitio web descargado, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="061bb-136">The task is already complete, but you await it to retrieve the length of the downloaded website, as the following example shows.</span></span> <span data-ttu-id="061bb-137">Si se produce un error en la tarea, `await` iniciará la primera excepción secundaria almacenada en `AggregateException`, en lugar de leer la propiedad <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> que iniciaría la excepción `AggregateException`.</span><span class="sxs-lookup"><span data-stu-id="061bb-137">If the task is faulted, `await` will throw the first child exception stored in the `AggregateException`, unlike reading the <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> property, which would throw the `AggregateException`.</span></span>

    ```csharp
    total += await finishedTask;
    ```

## <a name="add-process-method"></a><span data-ttu-id="061bb-138">Adición de un método de proceso</span><span class="sxs-lookup"><span data-stu-id="061bb-138">Add process method</span></span>

<span data-ttu-id="061bb-139">Agregue el siguiente método `ProcessUrlAsync` después del método `SumPageSizesAsync`:</span><span class="sxs-lookup"><span data-stu-id="061bb-139">Add the following `ProcessUrlAsync` method below the `SumPageSizesAsync` method:</span></span>

```csharp
static async Task<int> ProcessUrlAsync(string url, HttpClient client)
{
    byte[] content = await client.GetByteArrayAsync(url);
    Console.WriteLine($"{url,-60} {content.Length,10:#,#}");

    return content.Length;
}
```

<span data-ttu-id="061bb-140">Para cualquier dirección URL, el método usará la instancia de `client` proporcionada para obtener la respuesta como `byte[]`.</span><span class="sxs-lookup"><span data-stu-id="061bb-140">For any given URL, the method will use the `client` instance provided to get the response as a `byte[]`.</span></span> <span data-ttu-id="061bb-141">La longitud se devuelve después de que la dirección URL y la longitud se escriban en la consola.</span><span class="sxs-lookup"><span data-stu-id="061bb-141">The length is returned after the URL and length is written to the console.</span></span>

<span data-ttu-id="061bb-142">Ejecute el programa varias veces para comprobar que las longitudes que se han descargado no aparecen siempre en el mismo orden.</span><span class="sxs-lookup"><span data-stu-id="061bb-142">Run the program several times to verify that the downloaded lengths don't always appear in the same order.</span></span>

> [!CAUTION]
> <span data-ttu-id="061bb-143">Puede usar `WhenAny` en un bucle, como se describe en el ejemplo, para solucionar problemas que implican un número reducido de tareas.</span><span class="sxs-lookup"><span data-stu-id="061bb-143">You can use `WhenAny` in a loop, as described in the example, to solve problems that involve a small number of tasks.</span></span> <span data-ttu-id="061bb-144">Sin embargo, otros enfoques son más eficaces si hay que procesar un gran número de tareas.</span><span class="sxs-lookup"><span data-stu-id="061bb-144">However, other approaches are more efficient if you have a large number of tasks to process.</span></span> <span data-ttu-id="061bb-145">Para más información y ejemplos, vea [Processing Tasks as they complete](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete) (Procesar tareas a medida que se completan).</span><span class="sxs-lookup"><span data-stu-id="061bb-145">For more information and examples, see [Processing tasks as they complete](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete).</span></span>

## <a name="complete-example"></a><span data-ttu-id="061bb-146">Ejemplo completo</span><span class="sxs-lookup"><span data-stu-id="061bb-146">Complete example</span></span>

<span data-ttu-id="061bb-147">El código siguiente es el texto completo del archivo *Program.cs* para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="061bb-147">The following code is the complete text of the *Program.cs* file for the example.</span></span>

:::code language="csharp" source="snippets/multiple-tasks/Program.cs":::

## <a name="see-also"></a><span data-ttu-id="061bb-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="061bb-148">See also</span></span>

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [<span data-ttu-id="061bb-149">Programación asincrónica con async y await (C#)</span><span class="sxs-lookup"><span data-stu-id="061bb-149">Asynchronous programming with async and await (C#)</span></span>](index.md)
