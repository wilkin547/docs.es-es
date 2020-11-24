---
title: 'Cómo: Implementar un particionador para particionamiento estático'
ms.date: 03/30/2017
helpviewer_keywords:
- tasks, how to create a static partitioner
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
ms.openlocfilehash: 1593f1bc3c17f162b20f8bd9f645d51393f2198c
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817138"
---
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a><span data-ttu-id="23fea-102">Cómo: Implementar un particionador para particionamiento estático</span><span class="sxs-lookup"><span data-stu-id="23fea-102">How to: Implement a Partitioner for Static Partitioning</span></span>
<span data-ttu-id="23fea-103">En el ejemplo siguiente se muestra una forma de implementar un particionador personalizado sencillo para PLINQ que realiza una partición estática.</span><span class="sxs-lookup"><span data-stu-id="23fea-103">The following example shows one way to implement a simple custom partitioner for PLINQ that performs static partitioning.</span></span> <span data-ttu-id="23fea-104">Dado que el particionador no admite las particiones dinámicas, no se puede usar desde <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="23fea-104">Because the partitioner does not support dynamic partitions, it is not consumable from <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="23fea-105">Este particionador particular puede proporcionar velocidad con respecto al particionador por rangos predeterminado para los orígenes de datos, para los que cada elemento requieren una cantidad creciente de tiempo de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="23fea-105">This particular partitioner might provide speedup over the default range partitioner for data sources for which each element requires an increasing amount of processing time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23fea-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="23fea-106">Example</span></span>  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 <span data-ttu-id="23fea-107">Las particiones de este ejemplo se basan en el supuesto de un aumento lineal del tiempo de procesamiento de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="23fea-107">The partitions in this example are based on the assumption of a linear increase in processing time for each element.</span></span> <span data-ttu-id="23fea-108">En el mundo real, puede que sea difícil predecir los tiempos de procesamiento de esta manera.</span><span class="sxs-lookup"><span data-stu-id="23fea-108">In the real world, it might be difficult to predict processing times in this way.</span></span> <span data-ttu-id="23fea-109">Si usa un particionador estático con un origen de datos específico, puede optimizar la fórmula de partición del origen, agregar la lógica de equilibrio de carga o usar un enfoque de partición por fragmentos, como se explica en [Cómo: Implementar las particiones dinámicas](how-to-implement-dynamic-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="23fea-109">If you are using a static partitioner with a specific data source, you can optimize the partitioning formula for the source, add load-balancing logic, or use a chunk partitioning approach as demonstrated in [How to: Implement Dynamic Partitions](how-to-implement-dynamic-partitions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23fea-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="23fea-110">See also</span></span>

- [<span data-ttu-id="23fea-111">Particionadores personalizados para PLINQ y TPL</span><span class="sxs-lookup"><span data-stu-id="23fea-111">Custom Partitioners for PLINQ and TPL</span></span>](custom-partitioners-for-plinq-and-tpl.md)
