---
title: 'Cómo: Usar matrices de colecciones de bloqueo en una canalización'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, blocking collections in pipeline
ms.assetid: a39c7ec3-3ad7-4f4d-8fe4-b3e9dbabe2ed
ms.openlocfilehash: 397c438bacd1cfed1613efef61e9d7266d55ea47
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "75711264"
---
# <a name="how-to-use-arrays-of-blocking-collections-in-a-pipeline"></a><span data-ttu-id="90a43-102">Cómo: Usar matrices de colecciones de bloqueo en una canalización</span><span class="sxs-lookup"><span data-stu-id="90a43-102">How to: Use Arrays of Blocking Collections in a Pipeline</span></span>
<span data-ttu-id="90a43-103">En el ejemplo siguiente se muestra cómo usar matrices de objetos de <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> con métodos estáticos como <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> y <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A> para implementar una transferencia de datos rápida y flexible entre los componentes.</span><span class="sxs-lookup"><span data-stu-id="90a43-103">The following example shows how to use arrays of <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> objects with static methods such as <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> and <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A> to implement fast and flexible data transfer between components.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90a43-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="90a43-104">Example</span></span>  
 <span data-ttu-id="90a43-105">En el ejemplo siguiente se muestra una implementación de canalización básica en la que cada objeto obtiene simultáneamente datos de la colección de entrada, los transforma y los pasa a la colección de salida.</span><span class="sxs-lookup"><span data-stu-id="90a43-105">The following example demonstrates a basic pipeline implementation in which each object is concurrently taking data from the input collection, transforming it, and passing it to the output collection.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#07](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example07.cs#07)]
 [!code-vb[CDS_BlockingCollection#07](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/bcpipeline.vb#07)]  
  
## <a name="see-also"></a><span data-ttu-id="90a43-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="90a43-106">See also</span></span>

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [<span data-ttu-id="90a43-107">Colecciones seguras para subprocesos</span><span class="sxs-lookup"><span data-stu-id="90a43-107">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)
