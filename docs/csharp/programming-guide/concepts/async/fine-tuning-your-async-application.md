---
title: Ajustar una aplicación asincrónica (C#)
description: En estos ejemplos de C# se usa CancellationToken y métodos Task importantes, como Task.WhenAll y Task.WhenAny, para ajustar las aplicaciones asincrónicas.
ms.date: 07/20/2015
ms.assetid: 97696eb9-81fc-4940-9655-84daa8eb4d5c
ms.openlocfilehash: 46457f889a78932e306d2bd21dca666625d744eb
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925324"
---
# <a name="fine-tuning-your-async-application-c"></a><span data-ttu-id="af4b5-103">Ajustar una aplicación asincrónica (C#)</span><span class="sxs-lookup"><span data-stu-id="af4b5-103">Fine-Tuning Your Async Application (C#)</span></span>
<span data-ttu-id="af4b5-104">Puede agregar precisión y flexibilidad a sus aplicaciones asincrónicas mediante los métodos y las propiedades que el tipo <xref:System.Threading.Tasks.Task> pone a su disposición.</span><span class="sxs-lookup"><span data-stu-id="af4b5-104">You can add precision and flexibility to your async applications by using the methods and properties that the <xref:System.Threading.Tasks.Task> type makes available.</span></span> <span data-ttu-id="af4b5-105">Los temas de esta sección muestran ejemplos que usan <xref:System.Threading.CancellationToken> y métodos `Task` importantes como <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="af4b5-105">The topics in this section show examples that use <xref:System.Threading.CancellationToken> and important `Task` methods such as <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="af4b5-106">Con `WhenAny` y `WhenAll`, puede iniciar más fácilmente varias tareas y esperar su finalización mediante la supervisión de una sola tarea.</span><span class="sxs-lookup"><span data-stu-id="af4b5-106">By using `WhenAny` and `WhenAll`, you can more easily start multiple tasks and await their completion by monitoring a single task.</span></span>  
  
- <span data-ttu-id="af4b5-107">`WhenAny` devuelve una tarea que se completa cuando se complete cualquier tarea de una colección.</span><span class="sxs-lookup"><span data-stu-id="af4b5-107">`WhenAny` returns a task that completes when any task in a collection is complete.</span></span>  
  
     <span data-ttu-id="af4b5-108">Para obtener ejemplos del uso de `WhenAny`, vea [Cancelar las tareas asincrónicas restantes cuando se completa una (C#)](./cancel-remaining-async-tasks-after-one-is-complete.md) y [Iniciar varias tareas asincrónicas y procesarlas a medida que se completan (C#)](./start-multiple-async-tasks-and-process-them-as-they-complete.md).</span><span class="sxs-lookup"><span data-stu-id="af4b5-108">For examples that use `WhenAny`, see [Cancel Remaining Async Tasks after One Is Complete (C#)](./cancel-remaining-async-tasks-after-one-is-complete.md) and [Start Multiple Async Tasks and Process Them As They Complete (C#)](./start-multiple-async-tasks-and-process-them-as-they-complete.md).</span></span>  
  
- <span data-ttu-id="af4b5-109">`WhenAll` devuelve una tarea que se completa cuando se completen todas las tareas de una colección.</span><span class="sxs-lookup"><span data-stu-id="af4b5-109">`WhenAll` returns a task that completes when all tasks in a collection are complete.</span></span>  
  
     <span data-ttu-id="af4b5-110">Para obtener más información y un ejemplo del uso de `WhenAll`, vea [Procedimiento para ampliar el tutorial de async usando Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="af4b5-110">For more information and an example that uses `WhenAll`, see [How to extend the async walkthrough by using Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>
  
 <span data-ttu-id="af4b5-111">Esta sección contiene los siguientes ejemplos:</span><span class="sxs-lookup"><span data-stu-id="af4b5-111">This section includes the following examples.</span></span>  
  
- <span data-ttu-id="af4b5-112">[Cancelar una tarea asincrónica o una lista de tareas (C#)](./cancel-an-async-task-or-a-list-of-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="af4b5-112">[Cancel an Async Task or a List of Tasks (C#)](./cancel-an-async-task-or-a-list-of-tasks.md).</span></span>  
  
- [<span data-ttu-id="af4b5-113">Cancelar tareas asincrónicas tras un período de tiempo (C#)</span><span class="sxs-lookup"><span data-stu-id="af4b5-113">Cancel Async Tasks after a Period of Time (C#)</span></span>](./cancel-async-tasks-after-a-period-of-time.md)  
  
- [<span data-ttu-id="af4b5-114">Cancelar las tareas asincrónicas restantes cuando se completa una (C#)</span><span class="sxs-lookup"><span data-stu-id="af4b5-114">Cancel Remaining Async Tasks after One Is Complete (C#)</span></span>](./cancel-remaining-async-tasks-after-one-is-complete.md)  
  
- [<span data-ttu-id="af4b5-115">Iniciar varias tareas asincrónicas y procesarlas a medida que se completan (C#)</span><span class="sxs-lookup"><span data-stu-id="af4b5-115">Start Multiple Async Tasks and Process Them As They Complete (C#)</span></span>](./start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
> <span data-ttu-id="af4b5-116">Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior instalados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="af4b5-116">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
 <span data-ttu-id="af4b5-117">Los proyectos crean una interfaz de usuario que contiene un botón que inicia el proceso y un botón que lo cancela, tal como se muestra en la imagen siguiente.</span><span class="sxs-lookup"><span data-stu-id="af4b5-117">The projects create a UI that contains a button that starts the process and a button that cancels it, as the following image shows.</span></span> <span data-ttu-id="af4b5-118">Los botones se denominan `startButton` y `cancelButton`.</span><span class="sxs-lookup"><span data-stu-id="af4b5-118">The buttons are named `startButton` and `cancelButton`.</span></span>  
  
 <span data-ttu-id="af4b5-119">![Ventana de WPF con el botón Cancelar](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "Cuadro de diálogo con un botón de inicio y detención")</span><span class="sxs-lookup"><span data-stu-id="af4b5-119">![WPF window with Cancel button](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "Dialog box with a Start and Stop button")</span></span>  
  
 <span data-ttu-id="af4b5-120">Puede descargar los proyectos completos de Windows Presentation Foundation (WPF) desde [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo de async: Ajuste de la aplicación).</span><span class="sxs-lookup"><span data-stu-id="af4b5-120">You can download the complete Windows Presentation Foundation (WPF) projects from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af4b5-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="af4b5-121">See also</span></span>

- [<span data-ttu-id="af4b5-122">Programación asincrónica con Async y Await (C#)</span><span class="sxs-lookup"><span data-stu-id="af4b5-122">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
