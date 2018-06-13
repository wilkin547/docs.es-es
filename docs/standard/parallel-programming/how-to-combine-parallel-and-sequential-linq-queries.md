---
title: 'Cómo: Combinar consultas LINQ paralelas y secuenciales'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c69d4d423bbdf72f2af7dad38812aa508df0067c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33580255"
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a><span data-ttu-id="3bf6b-102">Cómo: Combinar consultas LINQ paralelas y secuenciales</span><span class="sxs-lookup"><span data-stu-id="3bf6b-102">How to: Combine Parallel and Sequential LINQ Queries</span></span>
<span data-ttu-id="3bf6b-103">Este ejemplo muestra cómo utilizar el método <xref:System.Linq.ParallelEnumerable.AsSequential%2A> para indicar a PLINQ que procese secuencialmente todos los operadores subsiguientes en la consulta.</span><span class="sxs-lookup"><span data-stu-id="3bf6b-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.AsSequential%2A> method to instruct PLINQ to process all subsequent operators in the query sequentially.</span></span> <span data-ttu-id="3bf6b-104">Aunque el procesamiento secuencial es normalmente más lento que el paralelo, a veces es necesario para generar resultados correctos.</span><span class="sxs-lookup"><span data-stu-id="3bf6b-104">Although sequential processing is generally slower than parallel, sometimes it is necessary to produce correct results.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="3bf6b-105">La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente.</span><span class="sxs-lookup"><span data-stu-id="3bf6b-105">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="3bf6b-106">Para más información sobre la velocidad, vea [Introducción a la velocidad en PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="3bf6b-106">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bf6b-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3bf6b-107">Example</span></span>  
 <span data-ttu-id="3bf6b-108">En el ejemplo siguiente se muestra un escenario en el que <xref:System.Linq.ParallelEnumerable.AsSequential%2A> es necesario, concretamente, para conservar el orden que se estableció en una cláusula de la consulta anterior.</span><span class="sxs-lookup"><span data-stu-id="3bf6b-108">The following example shows one scenario in which <xref:System.Linq.ParallelEnumerable.AsSequential%2A> is required, namely to preserve the ordering that was established in a previous clause of the query.</span></span>  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3bf6b-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="3bf6b-109">Compiling the Code</span></span>  
 <span data-ttu-id="3bf6b-110">Para compilar y ejecutar este código, péguelo en el [ejemplo de datos PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) del proyecto, agregue una línea para llamar al método desde `Main` y presione F5.</span><span class="sxs-lookup"><span data-stu-id="3bf6b-110">To compile and run this code, paste it into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project, add a line to call the method from `Main`, and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bf6b-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3bf6b-111">See Also</span></span>  
 [<span data-ttu-id="3bf6b-112">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="3bf6b-112">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
