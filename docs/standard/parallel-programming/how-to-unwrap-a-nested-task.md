---
title: 'Cómo: Desencapsular una tarea anidada'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to unwrap nested tasks
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
ms.openlocfilehash: 3eec3b7e8cc76ee171d88a7886b4983000848084
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722627"
---
# <a name="how-to-unwrap-a-nested-task"></a><span data-ttu-id="dcb14-102">Cómo: Desencapsular una tarea anidada</span><span class="sxs-lookup"><span data-stu-id="dcb14-102">How to: Unwrap a Nested Task</span></span>

<span data-ttu-id="dcb14-103">Puede devolver una tarea de un método y, a continuación, esperar o continuar a partir de dicha tarea, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dcb14-103">You can return a task from a method, and then wait on or continue from that task, as shown in the following example:</span></span>  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 <span data-ttu-id="dcb14-104">En el ejemplo anterior, la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> es de tipo `string` (`String` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="dcb14-104">In the previous example, the <xref:System.Threading.Tasks.Task%601.Result%2A> property is of type `string` (`String` in Visual Basic).</span></span>  
  
 <span data-ttu-id="dcb14-105">Sin embargo, en algunos escenarios, puede crear una tarea dentro de otra tarea y, a continuación, devolver la tarea anidada.</span><span class="sxs-lookup"><span data-stu-id="dcb14-105">However, in some scenarios, you might want to create a task within another task, and then return the nested task.</span></span> <span data-ttu-id="dcb14-106">En este caso, el delegado `TResult` de la tarea indicada es una tarea.</span><span class="sxs-lookup"><span data-stu-id="dcb14-106">In this case, the `TResult` of the enclosing task is itself a task.</span></span> <span data-ttu-id="dcb14-107">En el ejemplo siguiente, la propiedad Result es un delegado `Task<Task<string>>` en C# o `Task(Of Task(Of String))` en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="dcb14-107">In the following example, the Result property is a `Task<Task<string>>` in C# or `Task(Of Task(Of String))` in Visual Basic.</span></span>  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 <span data-ttu-id="dcb14-108">Aunque es posible escribir código para desajustar la tarea exterior y recuperar la tarea original y su propiedad <xref:System.Threading.Tasks.Task%601.Result%2A>, este código no es fácil de escribir porque se deben controlar las excepciones y también las solicitudes de cancelación.</span><span class="sxs-lookup"><span data-stu-id="dcb14-108">Although it is possible to write code to unwrap the outer task and retrieve the original task and its <xref:System.Threading.Tasks.Task%601.Result%2A> property, such code is not easy to write because you must handle exceptions and also cancellation requests.</span></span> <span data-ttu-id="dcb14-109">En esta situación, se recomienda que use uno de los métodos de extensión <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="dcb14-109">In this situation, we recommend that you use one of the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension methods, as shown in the following example.</span></span>  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 <span data-ttu-id="dcb14-110">Los métodos <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> se pueden usar para transformar cualquier delegado `Task<Task>` o `Task<Task<TResult>>` (`Task(Of Task)` o `Task(Of Task(Of TResult))` en Visual Basic) en un delegado `Task` o `Task<TResult>` (`Task(Of TResult)` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="dcb14-110">The <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> methods can be used to transform any `Task<Task>` or `Task<Task<TResult>>` (`Task(Of Task)` or `Task(Of Task(Of TResult))` in Visual Basic) to a `Task` or `Task<TResult>` (`Task(Of TResult)` in Visual Basic).</span></span> <span data-ttu-id="dcb14-111">La nueva tarea representa totalmente la tarea anidada interna e incluye el estado de cancelación y todas las excepciones.</span><span class="sxs-lookup"><span data-stu-id="dcb14-111">The new task fully represents the inner nested task, and includes cancellation state and all exceptions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dcb14-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dcb14-112">Example</span></span>  

 <span data-ttu-id="dcb14-113">En el ejemplo siguiente se muestra cómo usar los métodos de extensión <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>.</span><span class="sxs-lookup"><span data-stu-id="dcb14-113">The following example demonstrates how to use the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension methods.</span></span>  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## <a name="see-also"></a><span data-ttu-id="dcb14-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcb14-114">See also</span></span>

- <xref:System.Threading.Tasks.TaskExtensions?displayProperty=nameWithType>
- [<span data-ttu-id="dcb14-115">Programación asincrónica basada en tareas</span><span class="sxs-lookup"><span data-stu-id="dcb14-115">Task-based Asynchronous Programming</span></span>](task-based-asynchronous-programming.md)
