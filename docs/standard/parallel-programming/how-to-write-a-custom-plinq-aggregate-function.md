---
title: "Cómo: Escribir una función de agregado personalizada de PLINQ"
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
helpviewer_keywords: PLINQ queries, how to create aggregate function
ms.assetid: 5a70dd49-ab2a-4798-b551-196ee7042b1a
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8b098f21e29d0d59cd99ddbb64af6246d9953a3a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-custom-plinq-aggregate-function"></a><span data-ttu-id="d438f-102">Cómo: Escribir una función de agregado personalizada de PLINQ</span><span class="sxs-lookup"><span data-stu-id="d438f-102">How to: Write a Custom PLINQ Aggregate Function</span></span>
<span data-ttu-id="d438f-103">Este ejemplo muestra cómo utilizar el <xref:System.Linq.ParallelEnumerable.Aggregate%2A> método para aplicar una función de agregación personalizada a una secuencia de origen.</span><span class="sxs-lookup"><span data-stu-id="d438f-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.Aggregate%2A> method to apply a custom aggregation function to a source sequence.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="d438f-104">La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente.</span><span class="sxs-lookup"><span data-stu-id="d438f-104">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="d438f-105">Para obtener más información acerca de la velocidad, consulte [Introducción a la velocidad en PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="d438f-105">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d438f-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d438f-106">Example</span></span>  
 <span data-ttu-id="d438f-107">En el ejemplo siguiente se calcula la desviación estándar de una secuencia de enteros.</span><span class="sxs-lookup"><span data-stu-id="d438f-107">The following example calculates the standard deviation of a sequence of integers.</span></span>  
  
 [!code-csharp[PLINQ#31](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#31)]
 [!code-vb[PLINQ#31](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#31)]  
  
 <span data-ttu-id="d438f-108">Este ejemplo utiliza una sobrecarga del operador de consulta estándar agregado que sea único en PLINQ.</span><span class="sxs-lookup"><span data-stu-id="d438f-108">This example uses an overload of the Aggregate standard query operator that is unique to PLINQ.</span></span> <span data-ttu-id="d438f-109">Esta sobrecarga toma un archivo extra <xref:System.Func%603?displayProperty=nameWithType> como tercer parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="d438f-109">This overload takes an extra <xref:System.Func%603?displayProperty=nameWithType> as the third input parameter.</span></span> <span data-ttu-id="d438f-110">Este delegado combina los resultados de todos los subprocesos antes de realizar el cálculo final en los resultados agregados.</span><span class="sxs-lookup"><span data-stu-id="d438f-110">This delegate combines the results from all threads before it performs the final calculation on the aggregated results.</span></span> <span data-ttu-id="d438f-111">En este ejemplo se sume las sumas de todos los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="d438f-111">In this example we add together the sums from all the threads.</span></span>  
  
 <span data-ttu-id="d438f-112">Tenga en cuenta que, cuando un cuerpo de la expresión lambda consta de una única expresión, el valor devuelto de la <xref:System.Func%602?displayProperty=nameWithType> delegado es el valor de la expresión.</span><span class="sxs-lookup"><span data-stu-id="d438f-112">Note that when a lambda expression body consists of a single expression, the return value of the <xref:System.Func%602?displayProperty=nameWithType> delegate is the value of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d438f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d438f-113">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="d438f-114">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="d438f-114">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
