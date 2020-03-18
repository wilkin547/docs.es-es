---
title: 'Cómo: Controlar la ordenación en una consulta PLINQ'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to control ordering
ms.assetid: c67eccc7-004d-4b2f-987e-919cbbd62ef7
ms.openlocfilehash: d38c039fa99433d9476d62c1e96dff7e306fd766
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73123122"
---
# <a name="how-to-control-ordering-in-a-plinq-query"></a><span data-ttu-id="8f2b8-102">Cómo: Controlar la ordenación en una consulta PLINQ</span><span class="sxs-lookup"><span data-stu-id="8f2b8-102">How to: Control Ordering in a PLINQ Query</span></span>
<span data-ttu-id="8f2b8-103">En estos ejemplos se muestra cómo controlar la ordenación de una consulta PLINQ con el método de extensión <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>.</span><span class="sxs-lookup"><span data-stu-id="8f2b8-103">These examples show how to control the ordering in a PLINQ query by using the <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> extension method.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="8f2b8-104">La finalidad principal de estos ejemplos es mostrar el uso, y puede que su ejecución sea o no tan rápida como la de las consultas LINQ to Objects secuenciales equivalentes.</span><span class="sxs-lookup"><span data-stu-id="8f2b8-104">These examples are primarily intended to demonstrate usage, and may or may not run faster than the equivalent sequential LINQ to Objects queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f2b8-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8f2b8-105">Example</span></span>  
 <span data-ttu-id="8f2b8-106">En el ejemplo siguiente se conserva el orden de la secuencia de origen.</span><span class="sxs-lookup"><span data-stu-id="8f2b8-106">The following example preserves the ordering of the source sequence.</span></span> <span data-ttu-id="8f2b8-107">Esto a veces es necesario; por ejemplo, algunos operadores de consulta requieren una secuencia de origen ordenada para generar resultados correctos.</span><span class="sxs-lookup"><span data-stu-id="8f2b8-107">This is sometimes necessary; for example some query operators require an ordered source sequence to produce correct results.</span></span>  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="8f2b8-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8f2b8-108">Example</span></span>  
 <span data-ttu-id="8f2b8-109">En el ejemplo siguiente se muestran algunos operadores de consulta cuya secuencia de origen probablemente se espera que esté ordenada.</span><span class="sxs-lookup"><span data-stu-id="8f2b8-109">The following example shows some query operators whose source sequence is probably expected to be ordered.</span></span> <span data-ttu-id="8f2b8-110">Estos operadores pueden funcionar en secuencias no ordenadas, pero podrían producir resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="8f2b8-110">These operators will work on unordered sequences, but they might produce unexpected results.</span></span>  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 <span data-ttu-id="8f2b8-111">Para ejecutar este método, péguelo en la clase PLINQDataSample en el [ejemplo de datos de PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) del proyecto y presione F5.</span><span class="sxs-lookup"><span data-stu-id="8f2b8-111">To run this method, paste it into the PLINQDataSample class in the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project and press F5.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f2b8-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8f2b8-112">Example</span></span>  
 <span data-ttu-id="8f2b8-113">En el ejemplo siguiente se muestra cómo se conserva el orden de la primera parte de una consulta, después se quita el orden para aumentar el rendimiento de una cláusula de combinación y, por último, se vuelve a aplicar el orden de la secuencia del resultado final.</span><span class="sxs-lookup"><span data-stu-id="8f2b8-113">The following example shows how to preserve ordering for the first part of a query, then remove the ordering to increase the performance of a join clause, and then reapply ordering to the final result sequence.</span></span>  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 <span data-ttu-id="8f2b8-114">Para ejecutar este método, péguelo en la clase PLINQDataSample en el [ejemplo de datos de PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) del proyecto y presione F5.</span><span class="sxs-lookup"><span data-stu-id="8f2b8-114">To run this method, paste it into the PLINQDataSample class in the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f2b8-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f2b8-115">See also</span></span>

- <xref:System.Linq.ParallelEnumerable>
- [<span data-ttu-id="8f2b8-116">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="8f2b8-116">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
