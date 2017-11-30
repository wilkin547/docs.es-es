---
title: "Cómo: Especificar el modo de ejecución en PLINQ"
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
helpviewer_keywords: PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 745ceae9832582c7b66a56075d128f9cf1c8ff69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a><span data-ttu-id="4222e-102">Cómo: Especificar el modo de ejecución en PLINQ</span><span class="sxs-lookup"><span data-stu-id="4222e-102">How to: Specify the Execution Mode in PLINQ</span></span>
<span data-ttu-id="4222e-103">En este ejemplo se muestra cómo forzar a PLINQ a omitir su heurística predeterminada y ejecutar una consulta, independientemente de la forma de la consulta en paralelo.</span><span class="sxs-lookup"><span data-stu-id="4222e-103">This example shows how to force PLINQ to bypass its default heuristics and parallelize a query regardless of the query's shape.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="4222e-104">La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente.</span><span class="sxs-lookup"><span data-stu-id="4222e-104">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="4222e-105">Para obtener más información acerca de la velocidad, consulte [Introducción a la velocidad en PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="4222e-105">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4222e-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4222e-106">Example</span></span>  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 <span data-ttu-id="4222e-107">PLINQ está diseñado para aprovechar las oportunidades para la ejecución en paralelo.</span><span class="sxs-lookup"><span data-stu-id="4222e-107">PLINQ is designed to exploit opportunities for parallelization.</span></span> <span data-ttu-id="4222e-108">Sin embargo, no todas las consultas se beneficiarán de la ejecución en paralelo.</span><span class="sxs-lookup"><span data-stu-id="4222e-108">However, not all queries benefit from parallel execution.</span></span> <span data-ttu-id="4222e-109">Por ejemplo, cuando una consulta contiene un delegado de usuario único que realiza mucho trabajo, la consulta normalmente se ejecutará con mayor rapidez secuencialmente.</span><span class="sxs-lookup"><span data-stu-id="4222e-109">For example, when a query contains a single user delegate that does very little work, the query will usually run faster sequentially.</span></span> <span data-ttu-id="4222e-110">Esto es porque la sobrecarga necesaria para habilitar la ejecución en paralelo es más cara que la velocidad a la que se obtiene.</span><span class="sxs-lookup"><span data-stu-id="4222e-110">This is because the overhead involved in enabling parallelizing execution is more expensive than the speedup that is obtained.</span></span> <span data-ttu-id="4222e-111">Por lo tanto, PLINQ no paralelizar automáticamente todas las consultas.</span><span class="sxs-lookup"><span data-stu-id="4222e-111">Therefore, PLINQ does not automatically parallelize every query.</span></span> <span data-ttu-id="4222e-112">Primero examina la forma de la consulta y los diversos operadores que lo componen.</span><span class="sxs-lookup"><span data-stu-id="4222e-112">It first examines the shape of the query and the various operators that comprise it.</span></span> <span data-ttu-id="4222e-113">En función de este análisis, PLINQ en el modo de ejecución predeterminado puede decidir ejecutar algunos o todos de la consulta de forma secuencial.</span><span class="sxs-lookup"><span data-stu-id="4222e-113">Based on this analysis, PLINQ in the default execution mode may decide to execute some or all of the query sequentially.</span></span> <span data-ttu-id="4222e-114">Sin embargo, en algunos casos puede saber más acerca de la consulta que PLINQ es capaz de determinar su análisis.</span><span class="sxs-lookup"><span data-stu-id="4222e-114">However, in some cases you may know more about your query than PLINQ is able to determine from its analysis.</span></span> <span data-ttu-id="4222e-115">Por ejemplo, puede saber que un delegado es muy caro, y que la consulta se beneficiará definitivamente de la ejecución en paralelo.</span><span class="sxs-lookup"><span data-stu-id="4222e-115">For example, you may know that a delegate is very expensive, and that the query will definitely benefit from parallelization.</span></span> <span data-ttu-id="4222e-116">En tales casos, puede usar el <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> método y especifique la <xref:System.Linq.ParallelExecutionMode.ForceParallelism> valor para indicar a PLINQ que ejecute siempre la consulta de forma paralela.</span><span class="sxs-lookup"><span data-stu-id="4222e-116">In such cases, you can use the <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> method and specify the <xref:System.Linq.ParallelExecutionMode.ForceParallelism> value to instruct PLINQ to always run the query as parallel.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4222e-117">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="4222e-117">Compiling the Code</span></span>  
 <span data-ttu-id="4222e-118">Corte y pegue este código en el [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) y llame al método desde `Main`.</span><span class="sxs-lookup"><span data-stu-id="4222e-118">Cut and paste this code into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) and call the method from `Main`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4222e-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="4222e-119">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable.AsSequential%2A>  
 [<span data-ttu-id="4222e-120">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="4222e-120">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
