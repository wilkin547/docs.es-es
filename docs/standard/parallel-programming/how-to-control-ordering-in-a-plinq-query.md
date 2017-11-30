---
title: "Cómo: Controlar la ordenación en una consulta PLINQ"
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
helpviewer_keywords: PLINQ queries, how to control ordering
ms.assetid: c67eccc7-004d-4b2f-987e-919cbbd62ef7
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9e29aa825a68154e32a34a23ca170258092b88a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-ordering-in-a-plinq-query"></a><span data-ttu-id="ade1e-102">Cómo: Controlar la ordenación en una consulta PLINQ</span><span class="sxs-lookup"><span data-stu-id="ade1e-102">How to: Control Ordering in a PLINQ Query</span></span>
<span data-ttu-id="ade1e-103">Estos ejemplos muestra cómo controlar la ordenación en una consulta PLINQ usando el <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> método de extensión.</span><span class="sxs-lookup"><span data-stu-id="ade1e-103">These examples show how to control the ordering in a PLINQ query by using the <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> extension method.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="ade1e-104">Estos ejemplos están pensados principalmente para mostrar el uso y pueden o no pueden ejecutarse más rápido que LINQ secuencial equivalente a las consultas de objetos.</span><span class="sxs-lookup"><span data-stu-id="ade1e-104">These examples are primarily intended to demonstrate usage, and may or may not run faster than the equivalent sequential LINQ to Objects queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ade1e-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ade1e-105">Example</span></span>  
 <span data-ttu-id="ade1e-106">En el ejemplo siguiente se conserva el orden de la secuencia de origen.</span><span class="sxs-lookup"><span data-stu-id="ade1e-106">The following example preserves the ordering of the source sequence.</span></span> <span data-ttu-id="ade1e-107">Esto a veces es necesario; Por ejemplo, algunos operadores de consulta requieren una secuencia de origen ordenadas para generar resultados correctos.</span><span class="sxs-lookup"><span data-stu-id="ade1e-107">This is sometimes necessary; for example some query operators require an ordered source sequence to produce correct results.</span></span>  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="ade1e-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ade1e-108">Example</span></span>  
 <span data-ttu-id="ade1e-109">El ejemplo siguiente muestra algunas cuya secuencia de origen es muy probable que se ordenan de operadores de consulta.</span><span class="sxs-lookup"><span data-stu-id="ade1e-109">The following example shows some query operators whose source sequence is probably expected to be ordered.</span></span> <span data-ttu-id="ade1e-110">Estos operadores pueden funcionar en secuencias no ordenadas, pero podría producir resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="ade1e-110">These operators will work on unordered sequences, but they might produce unexpected results.</span></span>  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 <span data-ttu-id="ade1e-111">Para ejecutar este método, péguelo en la clase PLINQDataSample el [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) del proyecto y presione F5.</span><span class="sxs-lookup"><span data-stu-id="ade1e-111">To run this method, paste it into the PLINQDataSample class in the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project and press F5.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ade1e-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ade1e-112">Example</span></span>  
 <span data-ttu-id="ade1e-113">En el ejemplo siguiente se muestra cómo se conserva el orden de la primera parte de una consulta, a continuación, quita el orden para aumentar el rendimiento de una cláusula de combinación y, a continuación, volver a aplicar el orden de la secuencia del resultado final.</span><span class="sxs-lookup"><span data-stu-id="ade1e-113">The following example shows how to preserve ordering for the first part of a query, then remove the ordering to increase the performance of a join clause, and then reapply ordering to the final result sequence.</span></span>  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 <span data-ttu-id="ade1e-114">Para ejecutar este método, péguelo en la clase PLINQDataSample el [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) del proyecto y presione F5.</span><span class="sxs-lookup"><span data-stu-id="ade1e-114">To run this method, paste it into the PLINQDataSample class in the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ade1e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ade1e-115">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="ade1e-116">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="ade1e-116">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
