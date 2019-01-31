---
title: Procedimiento para devolver un valor a partir de una tarea
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to return a value
ms.assetid: c4bc0f44-eba2-4e96-9e03-1cc787461e61
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: df928ec6494da6da368b3cef1f1d25a84a692aa2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741790"
---
# <a name="how-to-return-a-value-from-a-task"></a><span data-ttu-id="95ea8-102">Procedimiento para devolver un valor a partir de una tarea</span><span class="sxs-lookup"><span data-stu-id="95ea8-102">How to: Return a Value from a Task</span></span>
<span data-ttu-id="95ea8-103">En este ejemplo se muestra cómo se usa el tipo <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> para devolver un valor de la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A>.</span><span class="sxs-lookup"><span data-stu-id="95ea8-103">This example shows how to use the <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> type to return a value from the <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="95ea8-104">Requiere que exista el directorio de C:\Usuarios\Pública\Imágenes\Imágenes de muestra\ y que contenga archivos.</span><span class="sxs-lookup"><span data-stu-id="95ea8-104">It requires that the C:\Users\Public\Pictures\Sample Pictures\ directory exists, and that it contains files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95ea8-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="95ea8-105">Example</span></span>  
 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 <span data-ttu-id="95ea8-106">La propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> bloquea el subproceso que realiza la llamada hasta que la tarea finaliza.</span><span class="sxs-lookup"><span data-stu-id="95ea8-106">The <xref:System.Threading.Tasks.Task%601.Result%2A> property blocks the calling thread until the task finishes.</span></span>  
  
 <span data-ttu-id="95ea8-107">Para ver cómo se pasa el resultado de <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> a una tarea de continuación, consulte [Encadenar tareas mediante tareas de continuación](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="95ea8-107">To see how to pass the result of one <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> to a continuation task, see [Chaining Tasks by Using Continuation Tasks](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95ea8-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="95ea8-108">See also</span></span>

- [<span data-ttu-id="95ea8-109">Programación asincrónica basada en tareas</span><span class="sxs-lookup"><span data-stu-id="95ea8-109">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
- [<span data-ttu-id="95ea8-110">Expresiones lambda en PLINQ y TPL</span><span class="sxs-lookup"><span data-stu-id="95ea8-110">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
