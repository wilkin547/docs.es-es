---
title: "Cómo: Acelerar cuerpos de bucle pequeños"
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
helpviewer_keywords: parallel loops, how to speed up
ms.assetid: c7a66677-cb59-4cbf-969a-d2e8fc61a6ce
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d38d8beedf342720d4dc68026297edb457f5ed35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-speed-up-small-loop-bodies"></a><span data-ttu-id="5e43d-102">Cómo: Acelerar cuerpos de bucle pequeños</span><span class="sxs-lookup"><span data-stu-id="5e43d-102">How to: Speed Up Small Loop Bodies</span></span>
<span data-ttu-id="5e43d-103">Cuando un <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> bucle tiene un cuerpo pequeño, puede realizar más lentamente que el bucle secuencial equivalente, como el [para](~/docs/csharp/language-reference/keywords/for.md) bucle en C# y la [para](http://msdn.microsoft.com/en-us/c470a263-9b49-4308-8fd6-8592b84a7980) en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5e43d-103">When a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> loop has a small body, it might perform more slowly than the equivalent sequential loop, such as the [for](~/docs/csharp/language-reference/keywords/for.md) loop in C# and the [For](http://msdn.microsoft.com/en-us/c470a263-9b49-4308-8fd6-8592b84a7980) loop in Visual Basic.</span></span> <span data-ttu-id="5e43d-104">El menor rendimiento se debe a la sobrecarga implicada en la partición de los datos y al costo de invocar un delegado en cada iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="5e43d-104">Slower performance is caused by the overhead involved in partitioning the data and the cost of invoking a delegate on each loop iteration.</span></span> <span data-ttu-id="5e43d-105">Para abordar estos escenarios, la clase <xref:System.Collections.Concurrent.Partitioner> proporciona el método <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType>, que permite proporcionar un bucle secuencial para el cuerpo del delegado de manera que el delegado solo se invoque una sola vez por partición, en lugar de una vez por cada iteración.</span><span class="sxs-lookup"><span data-stu-id="5e43d-105">To address such scenarios, the <xref:System.Collections.Concurrent.Partitioner> class provides the <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> method, which enables you to provide a sequential loop for the delegate body, so that the delegate is invoked only once per partition, instead of once per iteration.</span></span> <span data-ttu-id="5e43d-106">Para más información, consulte [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md) (Particionadores personalizados para PLINQ y TPL).</span><span class="sxs-lookup"><span data-stu-id="5e43d-106">For more information, see [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e43d-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5e43d-107">Example</span></span>  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 <span data-ttu-id="5e43d-108">El enfoque que se muestra en este ejemplo resulta útil cuando el bucle realiza una cantidad mínima de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5e43d-108">The approach demonstrated in this example is useful when the loop performs a minimal amount of work.</span></span> <span data-ttu-id="5e43d-109">A medida que el trabajo requiere más procesamiento, probablemente obtendrá un rendimiento igual o mejor usando un bucle <xref:System.Threading.Tasks.Parallel.For%2A> o <xref:System.Threading.Tasks.Parallel.ForEach%2A> con el particionador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5e43d-109">As the work becomes more computationally expensive, you will probably get the same or better performance by using a <xref:System.Threading.Tasks.Parallel.For%2A> or <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop with the default partitioner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e43d-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e43d-110">See Also</span></span>  
 <span data-ttu-id="5e43d-111">[Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md) (Paralelismo de datos)</span><span class="sxs-lookup"><span data-stu-id="5e43d-111">[Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)</span></span>  
 [<span data-ttu-id="5e43d-112">Particionadores personalizados para PLINQ y TPL</span><span class="sxs-lookup"><span data-stu-id="5e43d-112">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
 [<span data-ttu-id="5e43d-113">Iteradores</span><span class="sxs-lookup"><span data-stu-id="5e43d-113">Iterators</span></span>](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)  
 <span data-ttu-id="5e43d-114">[Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md) (Expresiones lambda en PLINQ y TPL)</span><span class="sxs-lookup"><span data-stu-id="5e43d-114">[Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)</span></span>
