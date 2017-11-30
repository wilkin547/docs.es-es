---
title: "Cómo: Implementar un particionador para particionamiento estático"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: tasks, how to create a static partitioner
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b28ff0bb8436fefc4956918889435e258ae98b12
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a><span data-ttu-id="f26e2-102">Cómo: Implementar un particionador para particionamiento estático</span><span class="sxs-lookup"><span data-stu-id="f26e2-102">How to: Implement a Partitioner for Static Partitioning</span></span>
<span data-ttu-id="f26e2-103">En el ejemplo siguiente se muestra una manera de implementar a un particionador personalizado simple para PLINQ que realiza la partición estática.</span><span class="sxs-lookup"><span data-stu-id="f26e2-103">The following example shows one way to implement a simple custom partitioner for PLINQ that performs static partitioning.</span></span> <span data-ttu-id="f26e2-104">Dado que el particionador no admite las particiones dinámicas, no resulta Dese <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f26e2-104">Because the partitioner does not support dynamic partitions, it is not consumable from <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f26e2-105">Este particionador determinado podría proporcionar velocidad sobre el particionador de intervalo predeterminado para los orígenes de datos para el que cada elemento necesita una cantidad creciente de tiempo de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="f26e2-105">This particular partitioner might provide speedup over the default range partitioner for data sources for which each element requires an increasing amount of processing time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f26e2-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f26e2-106">Example</span></span>  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 <span data-ttu-id="f26e2-107">Las particiones en este ejemplo se basan en el supuesto de un aumento lineal en tiempo de procesamiento para cada elemento.</span><span class="sxs-lookup"><span data-stu-id="f26e2-107">The partitions in this example are based on the assumption of a linear increase in processing time for each element.</span></span> <span data-ttu-id="f26e2-108">En el mundo real, puede que sea difícil de predecir los tiempos de procesamiento de esta manera.</span><span class="sxs-lookup"><span data-stu-id="f26e2-108">In the real world, it might be difficult to predict processing times in this way.</span></span> <span data-ttu-id="f26e2-109">Si usas un particionador estático con un origen de datos concreto, puede optimizar la fórmula de partición para el origen, agregar lógica de equilibrio de carga o usar un fragmento enfoque de partición como se muestra en [Cómo: implementar las particiones dinámicas](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="f26e2-109">If you are using a static partitioner with a specific data source, you can optimize the partitioning formula for the source, add load-balancing logic, or use a chunk partitioning approach as demonstrated in [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f26e2-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f26e2-110">See Also</span></span>  
 [<span data-ttu-id="f26e2-111">Particionadores personalizados para PLINQ y TPL</span><span class="sxs-lookup"><span data-stu-id="f26e2-111">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
