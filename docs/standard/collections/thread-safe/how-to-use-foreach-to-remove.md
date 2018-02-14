---
title: "Cómo: Utilizar ForEach para quitar elementos de BlockingCollection"
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
helpviewer_keywords:
- thread-safe collections, how to enumerate blocking collectoin
ms.assetid: 2096103c-22f7-420d-b631-f102bc33a6dd
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 823cde5ddd06d3b5cc2ad03327fc38e7651ed74d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-use-foreach-to-remove-items-in-a-blockingcollection"></a><span data-ttu-id="f6b42-102">Cómo: Utilizar ForEach para quitar elementos de BlockingCollection</span><span class="sxs-lookup"><span data-stu-id="f6b42-102">How to: Use ForEach to Remove Items in a BlockingCollection</span></span>
<span data-ttu-id="f6b42-103">Además de obtener los elementos de <xref:System.Collections.Concurrent.BlockingCollection%601> mediante los métodos <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> y <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A>, también puede usar [foreach](~/docs/csharp/language-reference/keywords/foreach-in.md) ([For Each](~/docs/visual-basic/language-reference/statements/for-each-next-statement.md) en Visual Basic) para quitar elementos hasta que se complete la adición y se vacíe la colección.</span><span class="sxs-lookup"><span data-stu-id="f6b42-103">In addition to taking items from a <xref:System.Collections.Concurrent.BlockingCollection%601> by using the <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> and <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> method, you can also use a [foreach](~/docs/csharp/language-reference/keywords/foreach-in.md) ([For Each](~/docs/visual-basic/language-reference/statements/for-each-next-statement.md) in Visual Basic) to remove items until adding is completed and the collection is empty.</span></span> <span data-ttu-id="f6b42-104">Esto se denomina una *enumeración de mutación* o *enumeración de consumo* porque, a diferencia de un bucle `foreach` (`For Each`) típico, este enumerador modifica la colección de origen mediante la eliminación de elementos.</span><span class="sxs-lookup"><span data-stu-id="f6b42-104">This is called a *mutating enumeration* or *consuming enumeration* because, unlike a typical `foreach` (`For Each`) loop, this enumerator modifies the source collection by removing items.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6b42-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f6b42-105">Example</span></span>  
 <span data-ttu-id="f6b42-106">En el ejemplo siguiente se muestra cómo se quitan todos los elementos de <xref:System.Collections.Concurrent.BlockingCollection%601> mediante un bucle `foreach` (`For Each`).</span><span class="sxs-lookup"><span data-stu-id="f6b42-106">The following example shows how to remove all the items in a <xref:System.Collections.Concurrent.BlockingCollection%601> by using a `foreach` (`For Each`) loop.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)]
 [!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]  
  
 <span data-ttu-id="f6b42-107">Este ejemplo usa un bucle de `foreach` con el método <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType> en el subproceso de consumo, lo que provoca que se quite cada elemento de la colección según se enumera.</span><span class="sxs-lookup"><span data-stu-id="f6b42-107">This example uses a `foreach` loop with the <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType> method in the consuming thread, which causes each item to be removed from the collection as it is enumerated.</span></span> <span data-ttu-id="f6b42-108"><xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> limita el número máximo de elementos que se encuentran en la colección en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="f6b42-108"><xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> limits the maximum number of items that are in the collection at any time.</span></span> <span data-ttu-id="f6b42-109">Al enumerar la colección de esta forma, bloquea el subproceso consumidor si no hay elementos disponibles o si la colección está vacía.</span><span class="sxs-lookup"><span data-stu-id="f6b42-109">Enumerating the collection in this way blocks the consumer thread if no items are available or if the collection is empty.</span></span> <span data-ttu-id="f6b42-110">En este ejemplo, el bloqueo no constituye un problema porque el subproceso de productor agrega elementos más rápido de lo que se pueden consumir.</span><span class="sxs-lookup"><span data-stu-id="f6b42-110">In this example blocking is not a concern because the producer thread adds items faster than they can be consumed.</span></span>  
  
 <span data-ttu-id="f6b42-111">No hay ninguna garantía de que los elementos se enumeren en el mismo orden en que los agregan los subprocesos de productor.</span><span class="sxs-lookup"><span data-stu-id="f6b42-111">There is no guarantee that the items are enumerated in the same order in which they are added by the producer threads.</span></span>  
  
 <span data-ttu-id="f6b42-112">Para enumerar la colección sin modificación alguna, simplemente use `foreach` (`For Each`) sin el método <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A>.</span><span class="sxs-lookup"><span data-stu-id="f6b42-112">To enumerate the collection without modifying it, just use `foreach` (`For Each`) without the <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A> method.</span></span> <span data-ttu-id="f6b42-113">Pero es importante comprender que este tipo de enumeración representa una instantánea de la colección en un momento concreto.</span><span class="sxs-lookup"><span data-stu-id="f6b42-113">However, it is important to understand that this kind of enumeration represents a snapshot of the collection at a precise point in time.</span></span> <span data-ttu-id="f6b42-114">Si otros subprocesos agregan o quitan elementos mientras se ejecuta el bucle, este no podría representar el estado real de la colección.</span><span class="sxs-lookup"><span data-stu-id="f6b42-114">If other threads are adding or removing items concurrently while you are executing the loop, then the loop might not represent the actual state of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6b42-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6b42-115">See Also</span></span>  
 <xref:System.Collections.Concurrent?displayProperty=nameWithType>  
 [<span data-ttu-id="f6b42-116">Programación en paralelo</span><span class="sxs-lookup"><span data-stu-id="f6b42-116">Parallel Programming</span></span>](../../../../docs/standard/parallel-programming/index.md)
