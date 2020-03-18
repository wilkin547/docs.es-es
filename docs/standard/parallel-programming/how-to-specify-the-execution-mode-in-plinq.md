---
title: 'Cómo: Especificar el modo de ejecución en PLINQ'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
ms.openlocfilehash: c602aba6e18f80b007b15cd61dfd2b48a36dd2c8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139241"
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a><span data-ttu-id="54e4b-102">Cómo: Especificar el modo de ejecución en PLINQ</span><span class="sxs-lookup"><span data-stu-id="54e4b-102">How to: Specify the Execution Mode in PLINQ</span></span>
<span data-ttu-id="54e4b-103">En este ejemplo se muestra cómo forzar a PLINQ a omitir su heurística predeterminada y paralelizar una consulta, independientemente de la forma de la consulta.</span><span class="sxs-lookup"><span data-stu-id="54e4b-103">This example shows how to force PLINQ to bypass its default heuristics and parallelize a query regardless of the query's shape.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="54e4b-104">La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente.</span><span class="sxs-lookup"><span data-stu-id="54e4b-104">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="54e4b-105">Para más información sobre la velocidad, vea [Introducción a la velocidad en PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="54e4b-105">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="54e4b-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54e4b-106">Example</span></span>  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 <span data-ttu-id="54e4b-107">PLINQ está diseñado para aprovechar las oportunidades para la paralelización.</span><span class="sxs-lookup"><span data-stu-id="54e4b-107">PLINQ is designed to exploit opportunities for parallelization.</span></span> <span data-ttu-id="54e4b-108">Sin embargo, no todas las consultas se beneficiarán de la ejecución en paralelo.</span><span class="sxs-lookup"><span data-stu-id="54e4b-108">However, not all queries benefit from parallel execution.</span></span> <span data-ttu-id="54e4b-109">Por ejemplo, cuando una consulta contiene un delegado de usuario único que realiza muy poco trabajo, la consulta normalmente se ejecutará con mayor rapidez de forma secuencial.</span><span class="sxs-lookup"><span data-stu-id="54e4b-109">For example, when a query contains a single user delegate that does very little work, the query will usually run faster sequentially.</span></span> <span data-ttu-id="54e4b-110">Esto se debe a que la sobrecarga necesaria para habilitar la ejecución en paralelo es más cara que la velocidad con que se obtiene.</span><span class="sxs-lookup"><span data-stu-id="54e4b-110">This is because the overhead involved in enabling parallelizing execution is more expensive than the speedup that is obtained.</span></span> <span data-ttu-id="54e4b-111">Por lo tanto, PLINQ no paraleliza automáticamente todas las consultas.</span><span class="sxs-lookup"><span data-stu-id="54e4b-111">Therefore, PLINQ does not automatically parallelize every query.</span></span> <span data-ttu-id="54e4b-112">Primero examina la forma de la consulta y los diversos operadores que la componen.</span><span class="sxs-lookup"><span data-stu-id="54e4b-112">It first examines the shape of the query and the various operators that comprise it.</span></span> <span data-ttu-id="54e4b-113">En función de este análisis, PLINQ en el modo de ejecución predeterminado puede decidir ejecutar algunas o todas las consultas de forma secuencial.</span><span class="sxs-lookup"><span data-stu-id="54e4b-113">Based on this analysis, PLINQ in the default execution mode may decide to execute some or all of the query sequentially.</span></span> <span data-ttu-id="54e4b-114">Sin embargo, en algunos casos, puede saber más sobre su consulta de lo que PLINQ es capaz de determinar a partir de su análisis.</span><span class="sxs-lookup"><span data-stu-id="54e4b-114">However, in some cases you may know more about your query than PLINQ is able to determine from its analysis.</span></span> <span data-ttu-id="54e4b-115">Por ejemplo, puede saber que un delegado es muy caro y que la consulta se beneficiará definitivamente de la paralelización.</span><span class="sxs-lookup"><span data-stu-id="54e4b-115">For example, you may know that a delegate is very expensive, and that the query will definitely benefit from parallelization.</span></span> <span data-ttu-id="54e4b-116">En tales casos, puede usar el método <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> y especificar el valor <xref:System.Linq.ParallelExecutionMode.ForceParallelism> para indicar a PLINQ que ejecute siempre la consulta de forma paralela.</span><span class="sxs-lookup"><span data-stu-id="54e4b-116">In such cases, you can use the <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> method and specify the <xref:System.Linq.ParallelExecutionMode.ForceParallelism> value to instruct PLINQ to always run the query as parallel.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="54e4b-117">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="54e4b-117">Compiling the Code</span></span>  
 <span data-ttu-id="54e4b-118">Corte y pegue este código en el [ejemplo de datos de PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) y llame al método desde `Main`.</span><span class="sxs-lookup"><span data-stu-id="54e4b-118">Cut and paste this code into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) and call the method from `Main`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54e4b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="54e4b-119">See also</span></span>

- <xref:System.Linq.ParallelEnumerable.AsSequential%2A>
- [<span data-ttu-id="54e4b-120">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="54e4b-120">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
