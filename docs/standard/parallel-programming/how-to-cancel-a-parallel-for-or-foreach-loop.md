---
title: Procedimiento para cancelar un bucle Parallel.For o ForEach
description: Cancele un bucle Parallel.For o Parallel.ForEach en .NET proporcionando un objeto de token de cancelación al método en el parámetro ParallelOptions.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel foreach loop, how to cancel
- parallel for loops, how to cancel
ms.assetid: 9d19b591-ea95-4418-8ea7-b6266af9905b
ms.openlocfilehash: 0a22794f3c45e685a80d36a42ecd849461936c7b
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769007"
---
# <a name="how-to-cancel-a-parallelfor-or-foreach-loop"></a><span data-ttu-id="a9c9c-103">Procedimiento para cancelar un bucle Parallel.For o ForEach</span><span class="sxs-lookup"><span data-stu-id="a9c9c-103">How to: Cancel a Parallel.For or ForEach Loop</span></span>
<span data-ttu-id="a9c9c-104">Los métodos <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> admiten la cancelación mediante tokens de cancelación.</span><span class="sxs-lookup"><span data-stu-id="a9c9c-104">The <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> methods support cancellation through the use of cancellation tokens.</span></span> <span data-ttu-id="a9c9c-105">Para obtener más información sobre la cancelación, vea [Cancelación](../threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="a9c9c-105">For more information about cancellation in general, see [Cancellation](../threading/cancellation-in-managed-threads.md).</span></span> <span data-ttu-id="a9c9c-106">En un bucle paralelo, se proporciona <xref:System.Threading.CancellationToken> al método en el parámetro <xref:System.Threading.Tasks.ParallelOptions> y, a continuación, incluye la llamada paralela en un bloque try-catch.</span><span class="sxs-lookup"><span data-stu-id="a9c9c-106">In a parallel loop, you supply the <xref:System.Threading.CancellationToken> to the method in the <xref:System.Threading.Tasks.ParallelOptions> parameter and then enclose the parallel call in a try-catch block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9c9c-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a9c9c-107">Example</span></span>  
 <span data-ttu-id="a9c9c-108">En el ejemplo siguiente se muestra cómo cancelar una llamada a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a9c9c-108">The following example shows how to cancel a call to <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a9c9c-109">Puede aplicar el mismo enfoque a una llamada <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a9c9c-109">You can apply the same approach to a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> call.</span></span>  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 <span data-ttu-id="a9c9c-110">Si el token que señala la cancelación es el mismo token que se especifica en la instancia <xref:System.Threading.Tasks.ParallelOptions>, el bucle paralelo producirá una sola clase <xref:System.OperationCanceledException> en la cancelación.</span><span class="sxs-lookup"><span data-stu-id="a9c9c-110">If the token that signals the cancellation is the same token that is specified in the <xref:System.Threading.Tasks.ParallelOptions> instance, then the parallel loop will throw a single <xref:System.OperationCanceledException> on cancellation.</span></span> <span data-ttu-id="a9c9c-111">Si algún otro token produce la cancelación, el bucle producirá una clase <xref:System.AggregateException> con una clase <xref:System.OperationCanceledException> como una excepción interna.</span><span class="sxs-lookup"><span data-stu-id="a9c9c-111">If some other token causes cancellation, the loop will throw an <xref:System.AggregateException> with an <xref:System.OperationCanceledException> as an InnerException.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9c9c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9c9c-112">See also</span></span>

- [<span data-ttu-id="a9c9c-113">Paralelismo de datos</span><span class="sxs-lookup"><span data-stu-id="a9c9c-113">Data Parallelism</span></span>](data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="a9c9c-114">Expresiones lambda en PLINQ y TPL</span><span class="sxs-lookup"><span data-stu-id="a9c9c-114">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
