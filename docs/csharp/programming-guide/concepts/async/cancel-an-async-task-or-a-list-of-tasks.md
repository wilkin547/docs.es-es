---
title: Cancelación de una lista de tareas (C#)
description: Aprenda a usar tokens de cancelación para indicar una solicitud de cancelación a una lista de tareas.
ms.date: 08/19/2020
ms.topic: tutorial
ms.assetid: eec32dbb-70ea-4c88-bd27-fa2e34546914
ms.openlocfilehash: 30bef5d1a5082fbd3757377dbedb8f9b9d17e218
ms.sourcegitcommit: 2560a355c76b0a04cba0d34da870df9ad94ceca3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2020
ms.locfileid: "89053098"
---
# <a name="cancel-a-list-of-tasks-c"></a><span data-ttu-id="caa66-103">Cancelación de una lista de tareas (C#)</span><span class="sxs-lookup"><span data-stu-id="caa66-103">Cancel a list of tasks (C#)</span></span>

<span data-ttu-id="caa66-104">Puede cancelar una aplicación de consola asincrónica si no quiere esperar a que termine.</span><span class="sxs-lookup"><span data-stu-id="caa66-104">You can cancel an async console application if you don't want to wait for it to finish.</span></span> <span data-ttu-id="caa66-105">Mediante el ejemplo de este tema, puede agregar una cancelación a una aplicación que descargue el contenido de una lista de sitios web.</span><span class="sxs-lookup"><span data-stu-id="caa66-105">By following the example in this topic, you can add a cancellation to an application that downloads the contents of a list of websites.</span></span> <span data-ttu-id="caa66-106">Puede cancelar muchas tareas asociando la instancia de <xref:System.Threading.CancellationTokenSource> a cada tarea.</span><span class="sxs-lookup"><span data-stu-id="caa66-106">You can cancel many tasks by associating the <xref:System.Threading.CancellationTokenSource> instance with each task.</span></span> <span data-ttu-id="caa66-107">Si se presiona la tecla <kbd>Entrar</kbd>, se cancelan todas las tareas que aún no se han completado.</span><span class="sxs-lookup"><span data-stu-id="caa66-107">If you select the <kbd>Enter</kbd> key, you cancel all tasks that aren't yet complete.</span></span>

<span data-ttu-id="caa66-108">Esta tutorial abarca lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="caa66-108">This tutorial covers:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="caa66-109">Creación de una aplicación de consola de .NET</span><span class="sxs-lookup"><span data-stu-id="caa66-109">Creating a .NET console application</span></span>
> - <span data-ttu-id="caa66-110">Escritura de una aplicación asincrónica que admite la cancelación</span><span class="sxs-lookup"><span data-stu-id="caa66-110">Writing an async application that supports cancellation</span></span>
> - <span data-ttu-id="caa66-111">Demostración de la señalización de una cancelación</span><span class="sxs-lookup"><span data-stu-id="caa66-111">Demonstrating signaling cancellation</span></span>

## <a name="prerequisites"></a><span data-ttu-id="caa66-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="caa66-112">Prerequisites</span></span>

<span data-ttu-id="caa66-113">Este tutorial requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="caa66-113">This tutorial requires the following:</span></span>

- [<span data-ttu-id="caa66-114">.NET 5.0 o un SDK posterior</span><span class="sxs-lookup"><span data-stu-id="caa66-114">.NET 5.0 or later SDK</span></span>](https://dotnet.microsoft.com/download/dotnet/5.0)
- <span data-ttu-id="caa66-115">Entorno de desarrollo integrado (IDE)</span><span class="sxs-lookup"><span data-stu-id="caa66-115">Integrated development environment (IDE)</span></span>
  - <span data-ttu-id="caa66-116">[Se recomienda usar Visual Studio, Visual Studio Code o Visual Studio para Mac](https://visualstudio.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="caa66-116">[We recommend Visual Studio, Visual Studio Code, or Visual Studio for Mac](https://visualstudio.microsoft.com)</span></span>

### <a name="create-example-application"></a><span data-ttu-id="caa66-117">Creación de una aplicación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="caa66-117">Create example application</span></span>

<span data-ttu-id="caa66-118">Cree una nueva aplicación de consola de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="caa66-118">Create a new .NET Core console application.</span></span> <span data-ttu-id="caa66-119">Puede crear una mediante el comando [`dotnet new console`](../../../../core/tools/dotnet-new.md#console) o desde [Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="caa66-119">You can create one by using the [`dotnet new console`](../../../../core/tools/dotnet-new.md#console) command or from [Visual Studio](/visualstudio/install/install-visual-studio).</span></span> <span data-ttu-id="caa66-120">Abra el archivo *Program.cs* en su editor de código favorito.</span><span class="sxs-lookup"><span data-stu-id="caa66-120">Open the *Program.cs* file in your favorite code editor.</span></span>

### <a name="replace-using-statements"></a><span data-ttu-id="caa66-121">Reemplazo de instrucciones using</span><span class="sxs-lookup"><span data-stu-id="caa66-121">Replace using statements</span></span>

<span data-ttu-id="caa66-122">Reemplace las instrucciones using existentes por estas declaraciones:</span><span class="sxs-lookup"><span data-stu-id="caa66-122">Replace the existing using statements with these declarations:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using System.Threading;
using System.Threading.Tasks;
```

## <a name="add-fields"></a><span data-ttu-id="caa66-123">Adición de campos</span><span class="sxs-lookup"><span data-stu-id="caa66-123">Add fields</span></span>

<span data-ttu-id="caa66-124">Dentro de la definición de la clase `Program`, agregue estos tres campos:</span><span class="sxs-lookup"><span data-stu-id="caa66-124">In the `Program` class definition, add these three fields:</span></span>

```csharp
static readonly CancellationTokenSource s_cts = new CancellationTokenSource();

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

<span data-ttu-id="caa66-125"><xref:System.Threading.CancellationTokenSource> se usa para indicar una cancelación solicitada a un token de cancelación (<xref:System.Threading.CancellationToken>).</span><span class="sxs-lookup"><span data-stu-id="caa66-125">The <xref:System.Threading.CancellationTokenSource> is used to signal a requested cancellation to a <xref:System.Threading.CancellationToken>.</span></span> <span data-ttu-id="caa66-126">`HttpClient` expone la capacidad de enviar solicitudes HTTP y de recibir respuestas HTTP.</span><span class="sxs-lookup"><span data-stu-id="caa66-126">The `HttpClient` exposes the ability to send HTTP requests and receive HTTP responses.</span></span> <span data-ttu-id="caa66-127">`s_urlList` contiene todas las direcciones URL que planea procesar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="caa66-127">The `s_urlList` holds all of the URLs that the application plans to process.</span></span>

## <a name="update-application-entry-point"></a><span data-ttu-id="caa66-128">Actualización del punto de entrada de la aplicación</span><span class="sxs-lookup"><span data-stu-id="caa66-128">Update application entry point</span></span>

<span data-ttu-id="caa66-129">El punto de entrada principal de la aplicación de consola es el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="caa66-129">The main entry point into the console application is the `Main` method.</span></span> <span data-ttu-id="caa66-130">Reemplace el método existente por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="caa66-130">Replace the existing method with the following:</span></span>

```csharp
static async Task Main()
{
    Console.WriteLine("Application started.");
    Console.WriteLine("Press the ENTER key to cancel...\n");

    Task cancelTask = Task.Run(() =>
    {
        while (Console.ReadKey().Key != ConsoleKey.Enter)
        {
            Console.WriteLine("Press the ENTER key to cancel...");
        }

        Console.WriteLine("\nENTER key pressed: cancelling downloads.\n");
        s_cts.Cancel();
    });

    Task sumPageSizesTask = SumPageSizesAsync();

    await Task.WhenAny(new[] { cancelTask, sumPageSizesTask });

    Console.WriteLine("Application ending.");
}
```

<span data-ttu-id="caa66-131">El método `Main` actualizado ahora se considera un método [Async main](../../../whats-new/csharp-7-1.md#async-main), el cual permite un punto de entrada asincrónico en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="caa66-131">The updated `Main` method is now considered an [Async main](../../../whats-new/csharp-7-1.md#async-main), which allows for an asynchronous entry point into the executable.</span></span> <span data-ttu-id="caa66-132">Escribe algunos mensajes informativos en la consola y, luego, declara una instancia de <xref:System.Threading.Tasks.Task> denominada `cancelTask`, la cual leerá las pulsaciones de teclas de la consola.</span><span class="sxs-lookup"><span data-stu-id="caa66-132">It writes a few instructional messages to the console, then declares a <xref:System.Threading.Tasks.Task> instance named `cancelTask`, which will read console key strokes.</span></span> <span data-ttu-id="caa66-133">Si se presiona la tecla <kbd>Entrar</kbd>, se realiza una llamada a <xref:System.Threading.CancellationTokenSource.Cancel?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="caa66-133">If the <kbd>Enter</kbd> key is pressed, a call to <xref:System.Threading.CancellationTokenSource.Cancel?displayProperty=nameWithType> is made.</span></span> <span data-ttu-id="caa66-134">Esto indicará la cancelación.</span><span class="sxs-lookup"><span data-stu-id="caa66-134">This will signal cancellation.</span></span> <span data-ttu-id="caa66-135">Después, se asigna la variable `sumPageSizesTask` desde el método `SumPageSizesAsync`</span><span class="sxs-lookup"><span data-stu-id="caa66-135">Next, the `sumPageSizesTask` variable is assigned from the `SumPageSizesAsync` method.</span></span> <span data-ttu-id="caa66-136">y ambas tareas se pasan a <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])?displayProperty=nameWithType>, que continuará cuando se complete cualquiera de las dos tareas.</span><span class="sxs-lookup"><span data-stu-id="caa66-136">Both tasks are then passed to <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])?displayProperty=nameWithType>, which will continue when any of the two tasks have completed.</span></span>

## <a name="create-the-asynchronous-sum-page-sizes-method"></a><span data-ttu-id="caa66-137">Creación de un método SumPageSizes asincrónico</span><span class="sxs-lookup"><span data-stu-id="caa66-137">Create the asynchronous sum page sizes method</span></span>

<span data-ttu-id="caa66-138">Agregue el método `SumPageSizesAsync` después del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="caa66-138">Below the `Main` method, add the `SumPageSizesAsync` method:</span></span>

```csharp
static async Task SumPageSizesAsync()
{
    var stopwatch = Stopwatch.StartNew();

    int total = 0;
    foreach (string url in s_urlList)
    {
        int contentLength = await ProcessUrlAsync(url, s_client, s_cts.Token);
        total += contentLength;
    }

    stopwatch.Stop();

    Console.WriteLine($"\nTotal bytes returned:  {total:#,#}");
    Console.WriteLine($"Elapsed time:          {stopwatch.Elapsed}\n");
}
```

<span data-ttu-id="caa66-139">El método comienza creando una instancia e iniciando una clase <xref:System.Diagnostics.Stopwatch>.</span><span class="sxs-lookup"><span data-stu-id="caa66-139">The method starts by instantiating and starting a <xref:System.Diagnostics.Stopwatch>.</span></span> <span data-ttu-id="caa66-140">Luego, recorre en bucle cada dirección URL en `s_urlList` y llama a `ProcessUrlAsync`.</span><span class="sxs-lookup"><span data-stu-id="caa66-140">It then loops through each URL in the `s_urlList` and calls `ProcessUrlAsync`.</span></span> <span data-ttu-id="caa66-141">Con cada iteración, se pasa el token `s_cts.Token` al método `ProcessUrlAsync` y el código devuelve una clase <xref:System.Threading.Tasks.Task%601>, donde `TResult` es un entero:</span><span class="sxs-lookup"><span data-stu-id="caa66-141">With each iteration, the `s_cts.Token` is passed into the `ProcessUrlAsync` method and the code returns a <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer:</span></span>

```csharp
int total = 0;
foreach (string url in s_urlList)
{
    int contentLength = await ProcessUrlAsync(url, s_client, s_cts.Token);
    total += contentLength;
}
```

## <a name="add-process-method"></a><span data-ttu-id="caa66-142">Adición de un método de proceso</span><span class="sxs-lookup"><span data-stu-id="caa66-142">Add process method</span></span>

<span data-ttu-id="caa66-143">Agregue el siguiente método `ProcessUrlAsync` después del método `SumPageSizesAsync`:</span><span class="sxs-lookup"><span data-stu-id="caa66-143">Add the following `ProcessUrlAsync` method below the `SumPageSizesAsync` method:</span></span>

```csharp
static async Task<int> ProcessUrlAsync(string url, HttpClient client, CancellationToken token)
{
    HttpResponseMessage response = await client.GetAsync(url, token);
    byte[] content = await response.Content.ReadAsByteArrayAsync(token);
    Console.WriteLine($"{url,-60} {content.Length,10:#,#}");

    return content.Length;
}
```

<span data-ttu-id="caa66-144">Para cualquier dirección URL, el método usará la instancia de `client` proporcionada para obtener la respuesta como `byte[]`.</span><span class="sxs-lookup"><span data-stu-id="caa66-144">For any given URL, the method will use the `client` instance provided to get the response as a `byte[]`.</span></span> <span data-ttu-id="caa66-145">La instancia de <xref:System.Threading.CancellationToken> se pasa a los métodos <xref:System.Net.Http.HttpClient.GetAsync(System.String,System.Threading.CancellationToken)?displayProperty=nameWithType> y <xref:System.Net.Http.HttpContent.ReadAsByteArrayAsync(System.Threading.CancellationToken)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="caa66-145">The <xref:System.Threading.CancellationToken> instance is passed into the <xref:System.Net.Http.HttpClient.GetAsync(System.String,System.Threading.CancellationToken)?displayProperty=nameWithType> and <xref:System.Net.Http.HttpContent.ReadAsByteArrayAsync(System.Threading.CancellationToken)?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="caa66-146">El token (`token`) se usa para registrar la cancelación solicitada.</span><span class="sxs-lookup"><span data-stu-id="caa66-146">The `token` is used to register for requested cancellation.</span></span> <span data-ttu-id="caa66-147">La longitud se devuelve después de que la dirección URL y la longitud se escriban en la consola.</span><span class="sxs-lookup"><span data-stu-id="caa66-147">The length is returned after the URL and length is written to the console.</span></span>

### <a name="example-application-output"></a><span data-ttu-id="caa66-148">Ejemplo de resultado de la aplicación</span><span class="sxs-lookup"><span data-stu-id="caa66-148">Example application output</span></span>

```console
Application started.
Press the ENTER key to cancel...

https://docs.microsoft.com                                       37,357
https://docs.microsoft.com/aspnet/core                           85,589
https://docs.microsoft.com/azure                                398,939
https://docs.microsoft.com/azure/devops                          73,663
https://docs.microsoft.com/dotnet                                67,452
https://docs.microsoft.com/dynamics365                           48,582
https://docs.microsoft.com/education                             22,924

ENTER key pressed: cancelling downloads.

Application ending.
```

## <a name="complete-example"></a><span data-ttu-id="caa66-149">Ejemplo completo</span><span class="sxs-lookup"><span data-stu-id="caa66-149">Complete example</span></span>

<span data-ttu-id="caa66-150">El código siguiente es el texto completo del archivo *Program.cs* para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="caa66-150">The following code is the complete text of the *Program.cs* file for the example.</span></span>

:::code language="csharp" source="snippets/cancel-tasks/cancel-tasks/Program.cs":::

## <a name="see-also"></a><span data-ttu-id="caa66-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="caa66-151">See also</span></span>

- <xref:System.Threading.CancellationToken>
- <xref:System.Threading.CancellationTokenSource>
- [<span data-ttu-id="caa66-152">Programación asincrónica con async y await (C#)</span><span class="sxs-lookup"><span data-stu-id="caa66-152">Asynchronous programming with async and await (C#)</span></span>](index.md)

## <a name="next-steps"></a><span data-ttu-id="caa66-153">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="caa66-153">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="caa66-154">Cancelar tareas asincrónicas tras un período de tiempo (C#)</span><span class="sxs-lookup"><span data-stu-id="caa66-154">Cancel async tasks after a period of time (C#)</span></span>](cancel-async-tasks-after-a-period-of-time.md)
