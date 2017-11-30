---
title: "Cómo: Desencapsular una tarea anidada"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: tasks, how to unwrap nested tasks
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2da3de912abb693c4342e1ede02f273348e4b571
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-unwrap-a-nested-task"></a><span data-ttu-id="a0a54-102">Cómo: Desencapsular una tarea anidada</span><span class="sxs-lookup"><span data-stu-id="a0a54-102">How to: Unwrap a Nested Task</span></span>
<span data-ttu-id="a0a54-103">Puede devolver una tarea de un método y, a continuación, esperar o continuar a partir de dicha tarea, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a0a54-103">You can return a task from a method, and then wait on or continue from that task, as shown in the following example:</span></span>  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 <span data-ttu-id="a0a54-104">En el ejemplo anterior, el <xref:System.Threading.Tasks.Task%601.Result%2A> propiedad es de tipo `string` (`String` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="a0a54-104">In the previous example, the <xref:System.Threading.Tasks.Task%601.Result%2A> property is of type `string` (`String` in Visual Basic).</span></span>  
  
 <span data-ttu-id="a0a54-105">Sin embargo, en algunos escenarios, puede crear una tarea dentro de otra tarea, y, a continuación, devolver la tarea anidada.</span><span class="sxs-lookup"><span data-stu-id="a0a54-105">However, in some scenarios, you might want to create a task within another task, and then return the nested task.</span></span> <span data-ttu-id="a0a54-106">En este caso, el `TResult` de la tarea indicada es una tarea.</span><span class="sxs-lookup"><span data-stu-id="a0a54-106">In this case, the `TResult` of the enclosing task is itself a task.</span></span> <span data-ttu-id="a0a54-107">En el ejemplo siguiente, la propiedad Result es un `Task<Task<string>>` en C# o `Task(Of Task(Of String))` en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a0a54-107">In the following example, the Result property is a `Task<Task<string>>` in C# or `Task(Of Task(Of String))` in Visual Basic.</span></span>  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 <span data-ttu-id="a0a54-108">Aunque es posible escribir código para desempaquetar la tarea exterior y recuperar la tarea original y su <xref:System.Threading.Tasks.Task%601.Result%2A> propiedad, este código no es fácil de escribir porque se deben controlar las excepciones y también las solicitudes de cancelación.</span><span class="sxs-lookup"><span data-stu-id="a0a54-108">Although it is possible to write code to unwrap the outer task and retrieve the original task and its <xref:System.Threading.Tasks.Task%601.Result%2A> property, such code is not easy to write because you must handle exceptions and also cancellation requests.</span></span> <span data-ttu-id="a0a54-109">En esta situación, se recomienda que realice uno de los <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> métodos de extensión, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a0a54-109">In this situation, we recommend that you use one of the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension methods, as shown in the following example.</span></span>  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 <span data-ttu-id="a0a54-110">El <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> métodos pueden usarse para transformar cualquier `Task<Task>` o `Task<Task<TResult>>` (`Task(Of Task)` o `Task(Of Task(Of TResult))` en Visual Basic) a un `Task` o `Task<TResult>` (`Task(Of TResult)` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="a0a54-110">The <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> methods can be used to transform any `Task<Task>` or `Task<Task<TResult>>` (`Task(Of Task)` or `Task(Of Task(Of TResult))` in Visual Basic) to a `Task` or `Task<TResult>` (`Task(Of TResult)` in Visual Basic).</span></span> <span data-ttu-id="a0a54-111">La nueva tarea totalmente representa la tarea anidada interna e incluye el estado de cancelación y todas las excepciones.</span><span class="sxs-lookup"><span data-stu-id="a0a54-111">The new task fully represents the inner nested task, and includes cancellation state and all exceptions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0a54-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a0a54-112">Example</span></span>  
 <span data-ttu-id="a0a54-113">En el ejemplo siguiente se muestra cómo utilizar el <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> métodos de extensión.</span><span class="sxs-lookup"><span data-stu-id="a0a54-113">The following example demonstrates how to use the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension methods.</span></span>  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## <a name="see-also"></a><span data-ttu-id="a0a54-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0a54-114">See Also</span></span>  
 <xref:System.Threading.Tasks.TaskExtensions?displayProperty=nameWithType>  
 [<span data-ttu-id="a0a54-115">Programación asincrónica basada en tareas</span><span class="sxs-lookup"><span data-stu-id="a0a54-115">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
