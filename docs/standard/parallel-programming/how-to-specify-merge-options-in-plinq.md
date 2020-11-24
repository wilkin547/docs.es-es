---
title: 'Cómo: Especificar opciones de combinación en PLINQ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to use merge options
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
ms.openlocfilehash: 91c5ac91538942368b66399bf0bc0132a15bf667
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825603"
---
# <a name="how-to-specify-merge-options-in-plinq"></a><span data-ttu-id="cac70-102">Cómo: Especificar opciones de combinación en PLINQ</span><span class="sxs-lookup"><span data-stu-id="cac70-102">How to: Specify Merge Options in PLINQ</span></span>
<span data-ttu-id="cac70-103">En este ejemplo se muestra cómo especificar las opciones de combinación que se aplicarán a todos los operadores subsiguientes en una consulta PLINQ.</span><span class="sxs-lookup"><span data-stu-id="cac70-103">This example shows how to specify the merge options that will apply to all subsequent operators in a PLINQ query.</span></span> <span data-ttu-id="cac70-104">No es necesario establecer las opciones de combinación explícitamente, pero, en caso de establecerlas, se puede mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="cac70-104">You do not have to set merge options explicitly, but doing so may improve performance.</span></span> <span data-ttu-id="cac70-105">Para más información sobre las opciones de combinación, consulte las [opciones de combinación en PLINQ](merge-options-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="cac70-105">For more information about merge options, see [Merge Options in PLINQ](merge-options-in-plinq.md).</span></span>  
  
> [!WARNING]
> <span data-ttu-id="cac70-106">La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente.</span><span class="sxs-lookup"><span data-stu-id="cac70-106">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="cac70-107">Para más información sobre la velocidad, vea [Introducción a la velocidad en PLINQ](understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="cac70-107">For more information about speedup, see [Understanding Speedup in PLINQ](understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cac70-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cac70-108">Example</span></span>  
 <span data-ttu-id="cac70-109">En el ejemplo siguiente se muestra el comportamiento de las opciones de combinación en un escenario básico que tiene un origen no ordenado y aplica una función cara a cada elemento.</span><span class="sxs-lookup"><span data-stu-id="cac70-109">The following example demonstrates the behavior of merge options in a basic scenario that has an unordered source and applies an expensive function to every element.</span></span>  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 <span data-ttu-id="cac70-110">En casos donde la opción <xref:System.Linq.ParallelMergeOptions.AutoBuffered> incurre en una latencia indeseable antes de que se produzca el primer elemento, pruebe la opción <xref:System.Linq.ParallelMergeOptions.NotBuffered> para proporcionar elementos de resultados más rápido y sin problemas.</span><span class="sxs-lookup"><span data-stu-id="cac70-110">In cases where the <xref:System.Linq.ParallelMergeOptions.AutoBuffered> option incurs an undesirable latency before the first element is yielded, try the <xref:System.Linq.ParallelMergeOptions.NotBuffered> option to yield result elements faster and more smoothly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cac70-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="cac70-111">See also</span></span>

- <xref:System.Linq.ParallelMergeOptions>
- [<span data-ttu-id="cac70-112">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="cac70-112">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
