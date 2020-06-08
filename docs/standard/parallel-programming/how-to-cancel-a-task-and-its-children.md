---
title: 'Cómo: Cancelar una tarea y sus elementos secundarios'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to cancel
ms.assetid: 08574301-8331-4719-ad50-9cf7f6ff3048
ms.openlocfilehash: ca6b5f10840d935aa45cb660da86685d1c90554b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290037"
---
# <a name="how-to-cancel-a-task-and-its-children"></a><span data-ttu-id="ae7da-102">Cómo: Cancelar una tarea y sus elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ae7da-102">How to: Cancel a Task and Its Children</span></span>
<span data-ttu-id="ae7da-103">En estos ejemplos se muestra cómo realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ae7da-103">These examples show how to perform the following tasks:</span></span>  
  
1. <span data-ttu-id="ae7da-104">Crear e iniciar una tarea cancelable.</span><span class="sxs-lookup"><span data-stu-id="ae7da-104">Create and start a cancelable task.</span></span>  
  
2. <span data-ttu-id="ae7da-105">Pasar un token de cancelación a un delegado de usuario y, opcionalmente, a la instancia de la tarea.</span><span class="sxs-lookup"><span data-stu-id="ae7da-105">Pass a cancellation token to your user delegate and optionally to the task instance.</span></span>  
  
3. <span data-ttu-id="ae7da-106">Observar y responder a la solicitud de cancelación en el delegado de usuario.</span><span class="sxs-lookup"><span data-stu-id="ae7da-106">Notice and respond to the cancellation request in your user delegate.</span></span>  
  
4. <span data-ttu-id="ae7da-107">Opcionalmente, observar en el subproceso que realiza la llamada que la tarea se canceló.</span><span class="sxs-lookup"><span data-stu-id="ae7da-107">Optionally notice on the calling thread that the task was canceled.</span></span>  
  
 <span data-ttu-id="ae7da-108">El subproceso que realiza la llamada no finaliza la tarea forzosamente, sino que solo señala que se solicita la cancelación.</span><span class="sxs-lookup"><span data-stu-id="ae7da-108">The calling thread does not forcibly end the task; it only signals that cancellation is requested.</span></span> <span data-ttu-id="ae7da-109">Si la tarea ya se está ejecutando, es el delegado de usuario el que debe observar la solicitud y responder según corresponda.</span><span class="sxs-lookup"><span data-stu-id="ae7da-109">If the task is already running, it is up to the user delegate to notice the request and respond appropriately.</span></span> <span data-ttu-id="ae7da-110">Si la cancelación se solicita antes de ejecutarse la tarea, el delegado de usuario nunca se ejecuta y el objeto de tarea pasa al estado Cancelado.</span><span class="sxs-lookup"><span data-stu-id="ae7da-110">If cancellation is requested before the task runs, then the user delegate is never executed and the task object transitions into the Canceled state.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae7da-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ae7da-111">Example</span></span>  
 <span data-ttu-id="ae7da-112">En este ejemplo se muestra cómo finalizar un objeto <xref:System.Threading.Tasks.Task> y sus elementos secundarios en respuesta a una solicitud de cancelación.</span><span class="sxs-lookup"><span data-stu-id="ae7da-112">This example shows how to terminate a <xref:System.Threading.Tasks.Task> and its children in response to a cancellation request.</span></span> <span data-ttu-id="ae7da-113">También se muestra que, cuando un delegado de usuario finaliza con una excepción <xref:System.Threading.Tasks.TaskCanceledException>, el subproceso que realiza la llamada puede usar opcionalmente el método <xref:System.Threading.Tasks.Task.Wait%2A> o el método <xref:System.Threading.Tasks.Task.WaitAll%2A> para esperar a que las tareas finalicen.</span><span class="sxs-lookup"><span data-stu-id="ae7da-113">It also shows that when a user delegate terminates by throwing a <xref:System.Threading.Tasks.TaskCanceledException>, the calling thread can optionally use the <xref:System.Threading.Tasks.Task.Wait%2A> method or <xref:System.Threading.Tasks.Task.WaitAll%2A> method to wait for the tasks to finish.</span></span> <span data-ttu-id="ae7da-114">En este caso, se debe usar un bloque `try/catch` para controlar las excepciones en el subproceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="ae7da-114">In this case, you must use a `try/catch` block to handle the exceptions on the calling thread.</span></span>  
  
 [!code-csharp[TPL_Cancellation#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/cancel1.cs#04)]
 [!code-vb[TPL_Cancellation#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/cancel1.vb#04)]  
  
 <span data-ttu-id="ae7da-115">La clase <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> está totalmente integrada con el modelo de cancelación basado en los tipos <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> y <xref:System.Threading.CancellationToken?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ae7da-115">The <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> class is fully integrated with the cancellation model that is based on the <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> and <xref:System.Threading.CancellationToken?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="ae7da-116">Para más información, consulte el tema sobre la [cancelación en subprocesos administrados](../threading/cancellation-in-managed-threads.md) y la [cancelación de tareas](task-cancellation.md).</span><span class="sxs-lookup"><span data-stu-id="ae7da-116">For more information, see [Cancellation in Managed Threads](../threading/cancellation-in-managed-threads.md) and [Task Cancellation](task-cancellation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae7da-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae7da-117">See also</span></span>

- <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>
- <xref:System.Threading.CancellationToken?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>
- [<span data-ttu-id="ae7da-118">Programación asincrónica basada en tareas</span><span class="sxs-lookup"><span data-stu-id="ae7da-118">Task-based Asynchronous Programming</span></span>](task-based-asynchronous-programming.md)
- <span data-ttu-id="ae7da-119">[Attached and Detached Child Tasks](attached-and-detached-child-tasks.md) (Tareas secundarias asociadas y desasociadas)</span><span class="sxs-lookup"><span data-stu-id="ae7da-119">[Attached and Detached Child Tasks](attached-and-detached-child-tasks.md)</span></span>
- [<span data-ttu-id="ae7da-120">Expresiones lambda en PLINQ y TPL</span><span class="sxs-lookup"><span data-stu-id="ae7da-120">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
