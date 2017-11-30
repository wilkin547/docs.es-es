---
title: "Cómo: Implementar las particiones dinámicas"
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
helpviewer_keywords: tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1e5dc93997918e0f7da29fa1f94c434a556f19f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-dynamic-partitions"></a><span data-ttu-id="915ab-102">Cómo: Implementar las particiones dinámicas</span><span class="sxs-lookup"><span data-stu-id="915ab-102">How to: Implement Dynamic Partitions</span></span>
<span data-ttu-id="915ab-103">En el ejemplo siguiente se muestra cómo implementar un personalizado <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> que implementa la creación de particiones dinámicas y pueden usarse desde determinadas sobrecargas <xref:System.Threading.Tasks.Parallel.ForEach%2A> y de PLINQ.</span><span class="sxs-lookup"><span data-stu-id="915ab-103">The following example shows how to implement a custom <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> that implements dynamic partitioning and can be used from certain overloads <xref:System.Threading.Tasks.Parallel.ForEach%2A> and from PLINQ.</span></span>  
  
## <a name="example"></a><span data-ttu-id="915ab-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="915ab-104">Example</span></span>  
 <span data-ttu-id="915ab-105">Cada vez que se llama a una partición <xref:System.Collections.IEnumerator.MoveNext%2A> en el enumerador, el enumerador proporciona la partición con un elemento de lista.</span><span class="sxs-lookup"><span data-stu-id="915ab-105">Each time a partition calls <xref:System.Collections.IEnumerator.MoveNext%2A> on the enumerator, the enumerator provides the partition with one list element.</span></span> <span data-ttu-id="915ab-106">En el caso de PLINQ y <xref:System.Threading.Tasks.Parallel.ForEach%2A>, la partición es un <xref:System.Threading.Tasks.Task> instancia.</span><span class="sxs-lookup"><span data-stu-id="915ab-106">In the case of PLINQ and <xref:System.Threading.Tasks.Parallel.ForEach%2A>, the partition is a <xref:System.Threading.Tasks.Task> instance.</span></span> <span data-ttu-id="915ab-107">Dado que las solicitudes se producen simultáneamente en varios subprocesos, se sincroniza el acceso al índice actual.</span><span class="sxs-lookup"><span data-stu-id="915ab-107">Because requests are happening concurrently on multiple threads, access to the current index is synchronized.</span></span>  
  
 [!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#04)]
 [!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  
  
 <span data-ttu-id="915ab-108">Este es un ejemplo de creación de particiones, con cada fragmento se compone de un elemento del fragmento.</span><span class="sxs-lookup"><span data-stu-id="915ab-108">This is an example of chunk partitioning, with each chunk consisting of one element.</span></span> <span data-ttu-id="915ab-109">Proporcionando más elementos a la vez, podría reducir la contención sobre el bloqueo y teóricamente lograr un rendimiento más rápido.</span><span class="sxs-lookup"><span data-stu-id="915ab-109">By providing more elements at a time, you could reduce the contention over the lock and theoretically achieve faster performance.</span></span> <span data-ttu-id="915ab-110">Sin embargo, en algún momento, los fragmentos mayores podrían requerir lógica de equilibrio de carga adicional con el fin de mantener todos los subprocesos ocupados hasta que se completa todo el trabajo.</span><span class="sxs-lookup"><span data-stu-id="915ab-110">However, at some point, larger chunks might require additional load-balancing logic in order to keep all threads busy until all the work is done.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="915ab-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="915ab-111">See Also</span></span>  
 [<span data-ttu-id="915ab-112">Particionadores personalizados para PLINQ y TPL</span><span class="sxs-lookup"><span data-stu-id="915ab-112">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
 [<span data-ttu-id="915ab-113">Implementar un particionador para particionamiento estático</span><span class="sxs-lookup"><span data-stu-id="915ab-113">How to: Implement a Partitioner for Static Partitioning</span></span>](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
