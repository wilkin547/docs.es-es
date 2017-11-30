---
title: "Cómo: Cancelar un bucle Parallel.For o ForEach"
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
helpviewer_keywords:
- parallel foreach loop, how to cancel
- parallel for loops, how to cancel
ms.assetid: 9d19b591-ea95-4418-8ea7-b6266af9905b
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3f82c5758e02b4beebf035fe8f43f856447855a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-parallelfor-or-foreach-loop"></a><span data-ttu-id="ba47c-102">Cómo: Cancelar un bucle Parallel.For o ForEach</span><span class="sxs-lookup"><span data-stu-id="ba47c-102">How to: Cancel a Parallel.For or ForEach Loop</span></span>
<span data-ttu-id="ba47c-103">El <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> métodos admiten la cancelación mediante tokens de cancelación.</span><span class="sxs-lookup"><span data-stu-id="ba47c-103">The <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> methods support cancellation through the use of cancellation tokens.</span></span> <span data-ttu-id="ba47c-104">Para obtener más información sobre la cancelación en general, vea [cancelación](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="ba47c-104">For more information about cancellation in general, see [Cancellation](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span> <span data-ttu-id="ba47c-105">En un bucle paralelo, se proporciona el <xref:System.Threading.CancellationToken> al método en el <xref:System.Threading.Tasks.ParallelOptions> parámetro y, a continuación, incluya la llamada paralela en un bloque try-catch.</span><span class="sxs-lookup"><span data-stu-id="ba47c-105">In a parallel loop, you supply the <xref:System.Threading.CancellationToken> to the method in the <xref:System.Threading.Tasks.ParallelOptions> parameter and then enclose the parallel call in a try-catch block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba47c-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba47c-106">Example</span></span>  
 <span data-ttu-id="ba47c-107">En el ejemplo siguiente se muestra cómo cancelar una llamada a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ba47c-107">The following example shows how to cancel a call to <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ba47c-108">Puede aplicar el mismo enfoque a una <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> llamar.</span><span class="sxs-lookup"><span data-stu-id="ba47c-108">You can apply the same approach to a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> call.</span></span>  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 <span data-ttu-id="ba47c-109">Si el token que señala la cancelación es el mismo símbolo (token) que se especifica en el <xref:System.Threading.Tasks.ParallelOptions> de instancias, el bucle paralelo producirá una sola <xref:System.OperationCanceledException> de cancelación.</span><span class="sxs-lookup"><span data-stu-id="ba47c-109">If the token that signals the cancellation is the same token that is specified in the <xref:System.Threading.Tasks.ParallelOptions> instance, then the parallel loop will throw a single <xref:System.OperationCanceledException> on cancellation.</span></span> <span data-ttu-id="ba47c-110">Si algún otro token produce la cancelación, el bucle producirá una <xref:System.AggregateException> con un <xref:System.OperationCanceledException> como una excepción interna.</span><span class="sxs-lookup"><span data-stu-id="ba47c-110">If some other token causes cancellation, the loop will throw an <xref:System.AggregateException> with an <xref:System.OperationCanceledException> as an InnerException.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba47c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba47c-111">See Also</span></span>  
 <span data-ttu-id="ba47c-112">[Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md) (Paralelismo de datos)</span><span class="sxs-lookup"><span data-stu-id="ba47c-112">[Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)</span></span>  
 <span data-ttu-id="ba47c-113">[Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md) (Expresiones lambda en PLINQ y TPL)</span><span class="sxs-lookup"><span data-stu-id="ba47c-113">[Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)</span></span>
