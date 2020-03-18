---
title: 'Cómo: Cancelar un bucle Parallel.For o ForEach'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel foreach loop, how to cancel
- parallel for loops, how to cancel
ms.assetid: 9d19b591-ea95-4418-8ea7-b6266af9905b
ms.openlocfilehash: 67f1f91f235cc88deaa97d412f368819ae0a8cda
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73134247"
---
# <a name="how-to-cancel-a-parallelfor-or-foreach-loop"></a><span data-ttu-id="c0764-102">Cómo: Cancelar un bucle Parallel.For o ForEach</span><span class="sxs-lookup"><span data-stu-id="c0764-102">How to: Cancel a Parallel.For or ForEach Loop</span></span>
<span data-ttu-id="c0764-103">Los métodos <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> admiten la cancelación mediante tokens de cancelación.</span><span class="sxs-lookup"><span data-stu-id="c0764-103">The <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> methods support cancellation through the use of cancellation tokens.</span></span> <span data-ttu-id="c0764-104">Para obtener más información sobre la cancelación, vea [Cancelación](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="c0764-104">For more information about cancellation in general, see [Cancellation](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span> <span data-ttu-id="c0764-105">En un bucle paralelo, se proporciona <xref:System.Threading.CancellationToken> al método en el parámetro <xref:System.Threading.Tasks.ParallelOptions> y, a continuación, incluye la llamada paralela en un bloque try-catch.</span><span class="sxs-lookup"><span data-stu-id="c0764-105">In a parallel loop, you supply the <xref:System.Threading.CancellationToken> to the method in the <xref:System.Threading.Tasks.ParallelOptions> parameter and then enclose the parallel call in a try-catch block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0764-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0764-106">Example</span></span>  
 <span data-ttu-id="c0764-107">En el ejemplo siguiente se muestra cómo cancelar una llamada a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c0764-107">The following example shows how to cancel a call to <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c0764-108">Puede aplicar el mismo enfoque a una llamada <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c0764-108">You can apply the same approach to a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> call.</span></span>  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 <span data-ttu-id="c0764-109">Si el token que señala la cancelación es el mismo token que se especifica en la instancia <xref:System.Threading.Tasks.ParallelOptions>, el bucle paralelo producirá una sola clase <xref:System.OperationCanceledException> en la cancelación.</span><span class="sxs-lookup"><span data-stu-id="c0764-109">If the token that signals the cancellation is the same token that is specified in the <xref:System.Threading.Tasks.ParallelOptions> instance, then the parallel loop will throw a single <xref:System.OperationCanceledException> on cancellation.</span></span> <span data-ttu-id="c0764-110">Si algún otro token produce la cancelación, el bucle producirá una clase <xref:System.AggregateException> con una clase <xref:System.OperationCanceledException> como una excepción interna.</span><span class="sxs-lookup"><span data-stu-id="c0764-110">If some other token causes cancellation, the loop will throw an <xref:System.AggregateException> with an <xref:System.OperationCanceledException> as an InnerException.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0764-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0764-111">See also</span></span>

- <span data-ttu-id="c0764-112">[Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md) (Paralelismo de datos)</span><span class="sxs-lookup"><span data-stu-id="c0764-112">[Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)</span></span>
- [<span data-ttu-id="c0764-113">Expresiones lambda en PLINQ y TPL</span><span class="sxs-lookup"><span data-stu-id="c0764-113">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
