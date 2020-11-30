---
title: Procedimiento para combinar consultas LINQ paralelas y secuenciales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
ms.openlocfilehash: dc7536aad46e2edcc5c20400ed872ee4e0ad836d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713163"
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a><span data-ttu-id="852d9-102">Procedimiento para combinar consultas LINQ paralelas y secuenciales</span><span class="sxs-lookup"><span data-stu-id="852d9-102">How to: Combine Parallel and Sequential LINQ Queries</span></span>

<span data-ttu-id="852d9-103">Este ejemplo muestra cómo utilizar el método <xref:System.Linq.ParallelEnumerable.AsSequential%2A> para indicar a PLINQ que procese secuencialmente todos los operadores subsiguientes en la consulta.</span><span class="sxs-lookup"><span data-stu-id="852d9-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.AsSequential%2A> method to instruct PLINQ to process all subsequent operators in the query sequentially.</span></span> <span data-ttu-id="852d9-104">Aunque el procesamiento secuencial suele ser más lento que el paralelo, a veces es necesario para generar resultados correctos.</span><span class="sxs-lookup"><span data-stu-id="852d9-104">Although sequential processing is often slower than parallel, sometimes it's necessary to produce correct results.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="852d9-105">La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente.</span><span class="sxs-lookup"><span data-stu-id="852d9-105">This example is intended to demonstrate usage and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="852d9-106">Para más información sobre la velocidad, vea [Introducción a la velocidad en PLINQ](understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="852d9-106">For more information about speedup, see [Understanding Speedup in PLINQ](understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="852d9-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="852d9-107">Example</span></span>  

 <span data-ttu-id="852d9-108">En el ejemplo siguiente se muestra un escenario en el que <xref:System.Linq.ParallelEnumerable.AsSequential%2A> es necesario, concretamente, para conservar el orden que se estableció en una cláusula de la consulta anterior.</span><span class="sxs-lookup"><span data-stu-id="852d9-108">The following example shows one scenario in which <xref:System.Linq.ParallelEnumerable.AsSequential%2A> is required, namely to preserve the ordering that was established in a previous clause of the query.</span></span>  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="852d9-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="852d9-109">Compiling the Code</span></span>  

 <span data-ttu-id="852d9-110">Para compilar y ejecutar este código, péguelo en el proyecto de [ejemplo de datos PLINQ](plinq-data-sample.md), agregue una línea para llamar al método desde `Main` y presione **F5**.</span><span class="sxs-lookup"><span data-stu-id="852d9-110">To compile and run this code, paste it into the [PLINQ Data Sample](plinq-data-sample.md) project, add a line to call the method from `Main`, and press **F5**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="852d9-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="852d9-111">See also</span></span>

- [<span data-ttu-id="852d9-112">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="852d9-112">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
