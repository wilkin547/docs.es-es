---
title: Procedimiento para medir el rendimiento de consultas PLINQ
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to measure performance
ms.assetid: 491ba43b-2c10-473d-9aab-e2cb96446711
ms.openlocfilehash: 43f83a34531b853d108785052f637d9568c45280
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826884"
---
# <a name="how-to-measure-plinq-query-performance"></a><span data-ttu-id="5c92a-102">Procedimiento para medir el rendimiento de consultas PLINQ</span><span class="sxs-lookup"><span data-stu-id="5c92a-102">How to: Measure PLINQ Query Performance</span></span>

<span data-ttu-id="5c92a-103">En este ejemplo se muestra cómo utilizar la clase <xref:System.Diagnostics.Stopwatch> para medir el tiempo que tarda en ejecutarse una consulta PLINQ.</span><span class="sxs-lookup"><span data-stu-id="5c92a-103">This example shows how to use the <xref:System.Diagnostics.Stopwatch> class to measure the time it takes for a PLINQ query to execute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c92a-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5c92a-104">Example</span></span>  
 <span data-ttu-id="5c92a-105">Este ejemplo utiliza un bucle `foreach` vacío (`For Each` en Visual Basic) para medir el tiempo que tarda en ejecutarse la consulta.</span><span class="sxs-lookup"><span data-stu-id="5c92a-105">This example uses an empty `foreach` loop (`For Each` in Visual Basic) to measure the time it takes for the query to execute.</span></span> <span data-ttu-id="5c92a-106">En el código real, el bucle normalmente contiene pasos de procesamiento adicional que se agregan al tiempo de ejecución de consulta total.</span><span class="sxs-lookup"><span data-stu-id="5c92a-106">In real-world code, the loop typically contains additional processing steps that add to the total query execution time.</span></span> <span data-ttu-id="5c92a-107">Verá que el cronómetro no se inicia hasta justo antes del bucle, ya que ese es el momento en el que comienza la ejecución de las consultas.</span><span class="sxs-lookup"><span data-stu-id="5c92a-107">Notice that the stopwatch is not started until just before the loop, because that's when the query execution begins.</span></span> <span data-ttu-id="5c92a-108">Si necesita una medición más específica, puede utilizar la propiedad `ElapsedTicks` en lugar de `ElapsedMilliseconds`.</span><span class="sxs-lookup"><span data-stu-id="5c92a-108">If you require more fine-grained measurement, you can use the `ElapsedTicks` property instead of `ElapsedMilliseconds`.</span></span>  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 <span data-ttu-id="5c92a-109">El tiempo de ejecución total es una métrica útil cuando se experimenta con implementaciones de consulta, pero no siempre muestra todo el panorama.</span><span class="sxs-lookup"><span data-stu-id="5c92a-109">The total execution time is a useful metric when you are experimenting with query implementations, but it doesn't always tell the whole story.</span></span> <span data-ttu-id="5c92a-110">Para obtener una vista más detallada y completa de la interacción de los subprocesos de consulta entre sí y con otros procesos en ejecución, use el [Visualizador de simultaneidad](/visualstudio/profiling/concurrency-visualizer).</span><span class="sxs-lookup"><span data-stu-id="5c92a-110">To get a deeper and richer view of the interaction of the query threads with one another and with other running processes, use the [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c92a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c92a-111">See also</span></span>

- [<span data-ttu-id="5c92a-112">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="5c92a-112">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
