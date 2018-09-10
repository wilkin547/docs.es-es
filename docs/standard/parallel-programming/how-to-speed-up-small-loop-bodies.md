---
title: 'Cómo: Acelerar cuerpos de bucle pequeños'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to speed up
ms.assetid: c7a66677-cb59-4cbf-969a-d2e8fc61a6ce
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5cb872acbe496f1f27ee9065dd3b276bbed349b
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44208418"
---
# <a name="how-to-speed-up-small-loop-bodies"></a><span data-ttu-id="5ebd9-102">Cómo: Acelerar cuerpos de bucle pequeños</span><span class="sxs-lookup"><span data-stu-id="5ebd9-102">How to: Speed Up Small Loop Bodies</span></span>
<span data-ttu-id="5ebd9-103">Si un bucle <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> tiene un cuerpo pequeño, su rendimiento puede ser menor que el del bucle secuencial equivalente, como el bucle [for](~/docs/csharp/language-reference/keywords/for.md) de C# y el bucle [For](https://msdn.microsoft.com/library/c470a263-9b49-4308-8fd6-8592b84a7980) de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5ebd9-103">When a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> loop has a small body, it might perform more slowly than the equivalent sequential loop, such as the [for](~/docs/csharp/language-reference/keywords/for.md) loop in C# and the [For](https://msdn.microsoft.com/library/c470a263-9b49-4308-8fd6-8592b84a7980) loop in Visual Basic.</span></span> <span data-ttu-id="5ebd9-104">El menor rendimiento se debe a la sobrecarga implicada en la partición de los datos y al costo de invocar un delegado en cada iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="5ebd9-104">Slower performance is caused by the overhead involved in partitioning the data and the cost of invoking a delegate on each loop iteration.</span></span> <span data-ttu-id="5ebd9-105">Para abordar estos escenarios, la clase <xref:System.Collections.Concurrent.Partitioner> proporciona el método <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType>, que permite proporcionar un bucle secuencial para el cuerpo del delegado de manera que el delegado solo se invoque una sola vez por partición, en lugar de una vez por cada iteración.</span><span class="sxs-lookup"><span data-stu-id="5ebd9-105">To address such scenarios, the <xref:System.Collections.Concurrent.Partitioner> class provides the <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> method, which enables you to provide a sequential loop for the delegate body, so that the delegate is invoked only once per partition, instead of once per iteration.</span></span> <span data-ttu-id="5ebd9-106">Para más información, consulte [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md) (Particionadores personalizados para PLINQ y TPL).</span><span class="sxs-lookup"><span data-stu-id="5ebd9-106">For more information, see [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ebd9-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5ebd9-107">Example</span></span>  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 <span data-ttu-id="5ebd9-108">El enfoque que se muestra en este ejemplo resulta útil cuando el bucle realiza una cantidad mínima de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5ebd9-108">The approach demonstrated in this example is useful when the loop performs a minimal amount of work.</span></span> <span data-ttu-id="5ebd9-109">A medida que el trabajo requiere más procesamiento, probablemente obtendrá un rendimiento igual o mejor usando un bucle <xref:System.Threading.Tasks.Parallel.For%2A> o <xref:System.Threading.Tasks.Parallel.ForEach%2A> con el particionador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5ebd9-109">As the work becomes more computationally expensive, you will probably get the same or better performance by using a <xref:System.Threading.Tasks.Parallel.For%2A> or <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop with the default partitioner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ebd9-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ebd9-110">See also</span></span>

- <span data-ttu-id="5ebd9-111">[Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md) (Paralelismo de datos)</span><span class="sxs-lookup"><span data-stu-id="5ebd9-111">[Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)</span></span>  
- [<span data-ttu-id="5ebd9-112">Particionadores personalizados para PLINQ y TPL</span><span class="sxs-lookup"><span data-stu-id="5ebd9-112">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
- [<span data-ttu-id="5ebd9-113">Iteradores</span><span class="sxs-lookup"><span data-stu-id="5ebd9-113">Iterators</span></span>](https://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)  
- [<span data-ttu-id="5ebd9-114">Expresiones lambda en PLINQ y TPL</span><span class="sxs-lookup"><span data-stu-id="5ebd9-114">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
