---
title: Procedimiento para implementar particiones dinámicas
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 792488e53ffb7f870e21fdd1ad3ef94bf0303b1a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720241"
---
# <a name="how-to-implement-dynamic-partitions"></a><span data-ttu-id="610ee-102">Procedimiento para implementar particiones dinámicas</span><span class="sxs-lookup"><span data-stu-id="610ee-102">How to: Implement Dynamic Partitions</span></span>
<span data-ttu-id="610ee-103">En el ejemplo siguiente se muestra cómo implementar una clase <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> personalizada que implementa la partición dinámica y que puede usarse desde determinadas sobrecargas <xref:System.Threading.Tasks.Parallel.ForEach%2A> y desde PLINQ.</span><span class="sxs-lookup"><span data-stu-id="610ee-103">The following example shows how to implement a custom <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> that implements dynamic partitioning and can be used from certain overloads <xref:System.Threading.Tasks.Parallel.ForEach%2A> and from PLINQ.</span></span>  
  
## <a name="example"></a><span data-ttu-id="610ee-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="610ee-104">Example</span></span>  
 <span data-ttu-id="610ee-105">Cada vez que se llama a una partición <xref:System.Collections.IEnumerator.MoveNext%2A> en el enumerador, este proporciona la partición con un elemento de lista.</span><span class="sxs-lookup"><span data-stu-id="610ee-105">Each time a partition calls <xref:System.Collections.IEnumerator.MoveNext%2A> on the enumerator, the enumerator provides the partition with one list element.</span></span> <span data-ttu-id="610ee-106">En el caso de PLINQ y <xref:System.Threading.Tasks.Parallel.ForEach%2A>, la partición es una instancia <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="610ee-106">In the case of PLINQ and <xref:System.Threading.Tasks.Parallel.ForEach%2A>, the partition is a <xref:System.Threading.Tasks.Task> instance.</span></span> <span data-ttu-id="610ee-107">Dado que las solicitudes se producen simultáneamente en varios subprocesos, se sincroniza el acceso al índice actual.</span><span class="sxs-lookup"><span data-stu-id="610ee-107">Because requests are happening concurrently on multiple threads, access to the current index is synchronized.</span></span>  
  
 [!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#04)]
 [!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  
  
 <span data-ttu-id="610ee-108">Este es un ejemplo de creación de particiones por fragmentos, donde cada fragmento consta de un elemento.</span><span class="sxs-lookup"><span data-stu-id="610ee-108">This is an example of chunk partitioning, with each chunk consisting of one element.</span></span> <span data-ttu-id="610ee-109">Proporcionando más elementos a la vez, podría reducir la contención sobre el bloqueo y teóricamente lograr un rendimiento más rápido.</span><span class="sxs-lookup"><span data-stu-id="610ee-109">By providing more elements at a time, you could reduce the contention over the lock and theoretically achieve faster performance.</span></span> <span data-ttu-id="610ee-110">Sin embargo, en algún momento, los fragmentos más grandes podrían requerir lógica de equilibrio de carga adicional con el fin de mantener todos los subprocesos ocupados hasta que se completa todo el trabajo.</span><span class="sxs-lookup"><span data-stu-id="610ee-110">However, at some point, larger chunks might require additional load-balancing logic in order to keep all threads busy until all the work is done.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="610ee-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="610ee-111">See also</span></span>

- [<span data-ttu-id="610ee-112">Particionadores personalizados para PLINQ y TPL</span><span class="sxs-lookup"><span data-stu-id="610ee-112">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
- [<span data-ttu-id="610ee-113">Cómo: Implementar un particionador para particionamiento estático</span><span class="sxs-lookup"><span data-stu-id="610ee-113">How to: Implement a Partitioner for Static Partitioning</span></span>](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
