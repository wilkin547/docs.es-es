---
title: Cancelación de tareas asincrónicas tras un período de tiempo (C#)
description: Obtenga información sobre cómo programar la cancelación de cualquier tarea asociada que no se complete en un período de tiempo determinado.
ms.date: 02/03/2021
ms.topic: tutorial
ms.assetid: 194282c2-399f-46da-a7a6-96674e00b0b3
ms.openlocfilehash: 98c42a2df6153d668b99b6dec49ffe380293b205
ms.sourcegitcommit: 65af0f0ad316858882845391d60ef7e303b756e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "99585382"
---
# <a name="cancel-async-tasks-after-a-period-of-time-c"></a><span data-ttu-id="9597d-103">Cancelar tareas asincrónicas tras un período de tiempo (C#)</span><span class="sxs-lookup"><span data-stu-id="9597d-103">Cancel async tasks after a period of time (C#)</span></span>

<span data-ttu-id="9597d-104">Puede cancelar una operación asincrónica después de un período de tiempo con el método <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> si no quiere esperar a que finalice la operación.</span><span class="sxs-lookup"><span data-stu-id="9597d-104">You can cancel an asynchronous operation after a period of time by using the <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> method if you don't want to wait for the operation to finish.</span></span> <span data-ttu-id="9597d-105">Este método programa la cancelación de las tareas asociadas que no se completen en el período de tiempo designado por la expresión `CancelAfter`.</span><span class="sxs-lookup"><span data-stu-id="9597d-105">This method schedules the cancellation of any associated tasks that aren't complete within the period of time that's designated by the `CancelAfter` expression.</span></span>

<span data-ttu-id="9597d-106">Este ejemplo se agrega al código que se desarrolla en el tutorial [Cancelación de una lista de tareas (C#)](cancel-an-async-task-or-a-list-of-tasks.md) para descargar una lista de sitios web y mostrar la longitud del contenido de cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="9597d-106">This example adds to the code that's developed in [Cancel a list of tasks (C#)](cancel-an-async-task-or-a-list-of-tasks.md) to download a list of websites and to display the length of the contents of each one.</span></span>

<span data-ttu-id="9597d-107">Esta tutorial abarca lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9597d-107">This tutorial covers:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="9597d-108">Actualización de una aplicación de consola .NET existente</span><span class="sxs-lookup"><span data-stu-id="9597d-108">Updating an existing .NET console application</span></span>
> - <span data-ttu-id="9597d-109">Programación de una cancelación</span><span class="sxs-lookup"><span data-stu-id="9597d-109">Scheduling a cancellation</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9597d-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9597d-110">Prerequisites</span></span>

<span data-ttu-id="9597d-111">Este tutorial requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9597d-111">This tutorial requires the following:</span></span>

- <span data-ttu-id="9597d-112">Que haya creado una aplicación en el tutorial [Cancelación de una lista de tareas (C#)](cancel-an-async-task-or-a-list-of-tasks.md)</span><span class="sxs-lookup"><span data-stu-id="9597d-112">You're expected to have created an application in the [Cancel a list of tasks (C#)](cancel-an-async-task-or-a-list-of-tasks.md) tutorial</span></span>
- [<span data-ttu-id="9597d-113">.NET 5.0 o un SDK posterior</span><span class="sxs-lookup"><span data-stu-id="9597d-113">.NET 5.0 or later SDK</span></span>](https://dotnet.microsoft.com/download/dotnet/5.0)
- <span data-ttu-id="9597d-114">Entorno de desarrollo integrado (IDE)</span><span class="sxs-lookup"><span data-stu-id="9597d-114">Integrated development environment (IDE)</span></span>
  - <span data-ttu-id="9597d-115">[Se recomienda usar Visual Studio, Visual Studio Code o Visual Studio para Mac](https://visualstudio.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="9597d-115">[We recommend Visual Studio, Visual Studio Code, or Visual Studio for Mac](https://visualstudio.microsoft.com)</span></span>

## <a name="update-application-entry-point"></a><span data-ttu-id="9597d-116">Actualización del punto de entrada de la aplicación</span><span class="sxs-lookup"><span data-stu-id="9597d-116">Update application entry point</span></span>

<span data-ttu-id="9597d-117">Reemplace el método `Main` existente por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9597d-117">Replace the existing `Main` method with the following:</span></span>

```csharp
static async Task Main()
{
    Console.WriteLine("Application started.");

    try
    {
        s_cts.CancelAfter(3500);

        await SumPageSizesAsync();
    }
    catch (TaskCanceledException)
    {
        Console.WriteLine("\nTasks cancelled: timed out.\n");
    }
    finally
    {
        s_cts.Dispose();
    }

    Console.WriteLine("Application ending.");
}
```

<span data-ttu-id="9597d-118">El método actualizado `Main` escribe algunos mensajes informativos en la consola.</span><span class="sxs-lookup"><span data-stu-id="9597d-118">The updated `Main` method writes a few instructional messages to the console.</span></span> <span data-ttu-id="9597d-119">En la instrucción [try catch](../../../language-reference/keywords/try-catch.md), una llamada a <xref:System.Threading.CancellationTokenSource.CancelAfter(System.Int32)?displayProperty=nameWithType> programa una cancelación.</span><span class="sxs-lookup"><span data-stu-id="9597d-119">Within the [try catch](../../../language-reference/keywords/try-catch.md), a call to <xref:System.Threading.CancellationTokenSource.CancelAfter(System.Int32)?displayProperty=nameWithType> schedules a cancellation.</span></span> <span data-ttu-id="9597d-120">Esto indicará la cancelación pasado un período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="9597d-120">This will signal cancellation after a period of time.</span></span>

<span data-ttu-id="9597d-121">Después, se espera al método `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="9597d-121">Next, the `SumPageSizesAsync` method is awaited.</span></span> <span data-ttu-id="9597d-122">Si el procesamiento de todas las direcciones URL se produce más rápido que la cancelación programada, la aplicación finaliza.</span><span class="sxs-lookup"><span data-stu-id="9597d-122">If processing all of the URLs occurs faster than the scheduled cancellation, the application ends.</span></span> <span data-ttu-id="9597d-123">Pero si la cancelación programada se desencadena antes de que se procesen todas las direcciones URL, se produce una excepción <xref:System.Threading.Tasks.TaskCanceledException>.</span><span class="sxs-lookup"><span data-stu-id="9597d-123">However, if the scheduled cancellation is triggered before all of the URLs are processed, a <xref:System.Threading.Tasks.TaskCanceledException> is thrown.</span></span>

### <a name="example-application-output"></a><span data-ttu-id="9597d-124">Ejemplo de resultado de la aplicación</span><span class="sxs-lookup"><span data-stu-id="9597d-124">Example application output</span></span>

```console
Application started.

https://docs.microsoft.com                                       37,357
https://docs.microsoft.com/aspnet/core                           85,589
https://docs.microsoft.com/azure                                398,939
https://docs.microsoft.com/azure/devops                          73,663

Tasks cancelled: timed out.

Application ending.
```

## <a name="complete-example"></a><span data-ttu-id="9597d-125">Ejemplo completo</span><span class="sxs-lookup"><span data-stu-id="9597d-125">Complete example</span></span>

<span data-ttu-id="9597d-126">El código siguiente es el texto completo del archivo *Program.cs* para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9597d-126">The following code is the complete text of the *Program.cs* file for the example.</span></span>

:::code language="csharp" source="snippets/cancel-tasks/cancel-task-after-period-of-time/Program.cs":::

## <a name="see-also"></a><span data-ttu-id="9597d-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="9597d-127">See also</span></span>

- <xref:System.Threading.CancellationToken>
- <xref:System.Threading.CancellationTokenSource>
- [<span data-ttu-id="9597d-128">Programación asincrónica con async y await (C#)</span><span class="sxs-lookup"><span data-stu-id="9597d-128">Asynchronous programming with async and await (C#)</span></span>](index.md)
- [<span data-ttu-id="9597d-129">Cancelación de una lista de tareas (C#)</span><span class="sxs-lookup"><span data-stu-id="9597d-129">Cancel a list of tasks (C#)</span></span>](cancel-an-async-task-or-a-list-of-tasks.md)
