---
description: 'Más información acerca de: Fine-Tuning la aplicación asincrónica (Visual Basic)'
title: Ajustar una aplicación asincrónica
ms.date: 07/20/2015
ms.assetid: 4c3e7997-a95f-4fbe-a6ac-60ba042d30b9
ms.openlocfilehash: 1e31ffdee4d2af9379e8073010ed2b1925023e43
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100464422"
---
# <a name="fine-tuning-your-async-application-visual-basic"></a><span data-ttu-id="3d6d7-103">Fine-Tuning Your Async Application (Visual Basic) (Ajuste de una aplicación asincrónica [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="3d6d7-103">Fine-Tuning Your Async Application (Visual Basic)</span></span>

<span data-ttu-id="3d6d7-104">Puede agregar precisión y flexibilidad a sus aplicaciones asincrónicas mediante los métodos y las propiedades que el tipo <xref:System.Threading.Tasks.Task> pone a su disposición.</span><span class="sxs-lookup"><span data-stu-id="3d6d7-104">You can add precision and flexibility to your async applications by using the methods and properties that the <xref:System.Threading.Tasks.Task> type makes available.</span></span> <span data-ttu-id="3d6d7-105">Los temas de esta sección muestran ejemplos que usan <xref:System.Threading.CancellationToken> y métodos `Task` importantes como <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3d6d7-105">The topics in this section show examples that use <xref:System.Threading.CancellationToken> and important `Task` methods such as <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="3d6d7-106">Con `WhenAny` y `WhenAll`, puede iniciar más fácilmente varias tareas y esperar su finalización mediante la supervisión de una sola tarea.</span><span class="sxs-lookup"><span data-stu-id="3d6d7-106">By using `WhenAny` and `WhenAll`, you can more easily start multiple tasks and await their completion by monitoring a single task.</span></span>  
  
- <span data-ttu-id="3d6d7-107">`WhenAny` devuelve una tarea que se completa cuando se complete cualquier tarea de una colección.</span><span class="sxs-lookup"><span data-stu-id="3d6d7-107">`WhenAny` returns a task that completes when any task in a collection is complete.</span></span>  
  
     <span data-ttu-id="3d6d7-108">Para obtener ejemplos que usan `WhenAny` , consulte  [cancelar las tareas asincrónicas restantes una vez completado (Visual Basic)](cancel-remaining-async-tasks-after-one-is-complete.md)e [iniciar varias tareas asincrónicas y procesarlas a medida que se completan (Visual Basic)](start-multiple-async-tasks-and-process-them-as-they-complete.md).</span><span class="sxs-lookup"><span data-stu-id="3d6d7-108">For examples that use `WhenAny`, see  [Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](cancel-remaining-async-tasks-after-one-is-complete.md)and [Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)](start-multiple-async-tasks-and-process-them-as-they-complete.md).</span></span>  
  
- <span data-ttu-id="3d6d7-109">`WhenAll` devuelve una tarea que se completa cuando se completen todas las tareas de una colección.</span><span class="sxs-lookup"><span data-stu-id="3d6d7-109">`WhenAll` returns a task that completes when all tasks in a collection are complete.</span></span>  
  
     <span data-ttu-id="3d6d7-110">Para obtener más información y un ejemplo que usa `WhenAll` , consulte [Cómo: ampliar el tutorial de Async mediante Task. WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="3d6d7-110">For more information and an example that uses `WhenAll`, see [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
 <span data-ttu-id="3d6d7-111">Esta sección contiene los siguientes ejemplos:</span><span class="sxs-lookup"><span data-stu-id="3d6d7-111">This section includes the following examples.</span></span>  
  
- <span data-ttu-id="3d6d7-112">[Cancelar una tarea asincrónica o una lista de tareas (Visual Basic)](cancel-an-async-task-or-a-list-of-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="3d6d7-112">[Cancel an Async Task or a List of Tasks (Visual Basic)](cancel-an-async-task-or-a-list-of-tasks.md).</span></span>  
  
- <span data-ttu-id="3d6d7-113">[Cancel Async Tasks after a Period of Time (Visual Basic)](cancel-async-tasks-after-a-period-of-time.md) (Cancelación de tareas asincrónicas tras un período de tiempo [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="3d6d7-113">[Cancel Async Tasks after a Period of Time (Visual Basic)](cancel-async-tasks-after-a-period-of-time.md)</span></span>  
  
- <span data-ttu-id="3d6d7-114">[Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](cancel-remaining-async-tasks-after-one-is-complete.md) (Cancelación de tareas asincrónicas restantes [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="3d6d7-114">[Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](cancel-remaining-async-tasks-after-one-is-complete.md)</span></span>  
  
- <span data-ttu-id="3d6d7-115">[Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)](start-multiple-async-tasks-and-process-them-as-they-complete.md) (Inicio de varias tareas asincrónicas y cómo procesarlas a medida que se completan [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="3d6d7-115">[Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)](start-multiple-async-tasks-and-process-them-as-they-complete.md)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d6d7-116">Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior instalados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="3d6d7-116">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
 <span data-ttu-id="3d6d7-117">Los proyectos crean una interfaz de usuario que contiene un botón que inicia el proceso y un botón que lo cancela, tal como se muestra en la imagen siguiente.</span><span class="sxs-lookup"><span data-stu-id="3d6d7-117">The projects create a UI that contains a button that starts the process and a button that cancels it, as the following image shows.</span></span> <span data-ttu-id="3d6d7-118">Los botones se denominan `startButton` y `cancelButton`.</span><span class="sxs-lookup"><span data-stu-id="3d6d7-118">The buttons are named `startButton` and `cancelButton`.</span></span>  
  
 <span data-ttu-id="3d6d7-119">![Ventana de WPF con el botón Cancelar](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "Cuadro de diálogo con un botón de inicio y detención")</span><span class="sxs-lookup"><span data-stu-id="3d6d7-119">![WPF window with Cancel button](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "Dialog box with a Start and Stop button")</span></span>  
  
 <span data-ttu-id="3d6d7-120">Puede descargar los proyectos completos de Windows Presentation Foundation (WPF) desde [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo de async: Ajuste de la aplicación).</span><span class="sxs-lookup"><span data-stu-id="3d6d7-120">You can download the complete Windows Presentation Foundation (WPF) projects from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d6d7-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d6d7-121">See also</span></span>

- [<span data-ttu-id="3d6d7-122">Programación asincrónica con Async y Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d6d7-122">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](index.md)
