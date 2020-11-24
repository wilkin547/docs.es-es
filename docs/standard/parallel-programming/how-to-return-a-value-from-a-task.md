---
title: Procedimiento para devolver un valor a partir de una tarea
description: Vea cómo el tipo System.Threading.Tasks.Task<TResult> devuelve un valor de la propiedad Result en .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to return a value
ms.assetid: c4bc0f44-eba2-4e96-9e03-1cc787461e61
ms.openlocfilehash: c7a4a683545c9ef0448d9cdce769aae79215aecf
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825616"
---
# <a name="how-to-return-a-value-from-a-task"></a><span data-ttu-id="6f5f9-103">Procedimiento para devolver un valor a partir de una tarea</span><span class="sxs-lookup"><span data-stu-id="6f5f9-103">How to: Return a Value from a Task</span></span>
<span data-ttu-id="6f5f9-104">En este ejemplo se muestra cómo se usa el tipo <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> para devolver un valor de la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A>.</span><span class="sxs-lookup"><span data-stu-id="6f5f9-104">This example shows how to use the <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> type to return a value from the <xref:System.Threading.Tasks.Task%601.Result%2A> property.</span></span> <span data-ttu-id="6f5f9-105">Requiere que exista el directorio de C:\Usuarios\Pública\Imágenes\Imágenes de muestra\ y que contenga archivos.</span><span class="sxs-lookup"><span data-stu-id="6f5f9-105">It requires that the C:\Users\Public\Pictures\Sample Pictures\ directory exists, and that it contains files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f5f9-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f5f9-106">Example</span></span>  
 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 <span data-ttu-id="6f5f9-107">La propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> bloquea el subproceso que realiza la llamada hasta que la tarea finaliza.</span><span class="sxs-lookup"><span data-stu-id="6f5f9-107">The <xref:System.Threading.Tasks.Task%601.Result%2A> property blocks the calling thread until the task finishes.</span></span>  
  
 <span data-ttu-id="6f5f9-108">Para ver cómo se pasa el resultado de <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> a una tarea de continuación, consulte [Encadenar tareas mediante tareas de continuación](chaining-tasks-by-using-continuation-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="6f5f9-108">To see how to pass the result of one <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> to a continuation task, see [Chaining Tasks by Using Continuation Tasks](chaining-tasks-by-using-continuation-tasks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f5f9-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f5f9-109">See also</span></span>

- [<span data-ttu-id="6f5f9-110">Programación asincrónica basada en tareas</span><span class="sxs-lookup"><span data-stu-id="6f5f9-110">Task-based Asynchronous Programming</span></span>](task-based-asynchronous-programming.md)
- [<span data-ttu-id="6f5f9-111">Expresiones lambda en PLINQ y TPL</span><span class="sxs-lookup"><span data-stu-id="6f5f9-111">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
