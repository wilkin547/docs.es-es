---
title: Procedimiento para usar matrices de colecciones de bloqueo en una canalización
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, blocking collections in pipeline
ms.assetid: a39c7ec3-3ad7-4f4d-8fe4-b3e9dbabe2ed
ms.openlocfilehash: 397c438bacd1cfed1613efef61e9d7266d55ea47
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711264"
---
# <a name="how-to-use-arrays-of-blocking-collections-in-a-pipeline"></a><span data-ttu-id="b1155-102">Procedimiento para usar matrices de colecciones de bloqueo en una canalización</span><span class="sxs-lookup"><span data-stu-id="b1155-102">How to: Use Arrays of Blocking Collections in a Pipeline</span></span>
<span data-ttu-id="b1155-103">En el ejemplo siguiente se muestra cómo usar matrices de objetos de <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> con métodos estáticos como <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> y <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A> para implementar una transferencia de datos rápida y flexible entre los componentes.</span><span class="sxs-lookup"><span data-stu-id="b1155-103">The following example shows how to use arrays of <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> objects with static methods such as <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> and <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A> to implement fast and flexible data transfer between components.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1155-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b1155-104">Example</span></span>  
 <span data-ttu-id="b1155-105">En el ejemplo siguiente se muestra una implementación de canalización básica en la que cada objeto obtiene simultáneamente datos de la colección de entrada, los transforma y los pasa a la colección de salida.</span><span class="sxs-lookup"><span data-stu-id="b1155-105">The following example demonstrates a basic pipeline implementation in which each object is concurrently taking data from the input collection, transforming it, and passing it to the output collection.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#07](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example07.cs#07)]
 [!code-vb[CDS_BlockingCollection#07](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/bcpipeline.vb#07)]  
  
## <a name="see-also"></a><span data-ttu-id="b1155-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1155-106">See also</span></span>

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [<span data-ttu-id="b1155-107">Colecciones seguras para subprocesos</span><span class="sxs-lookup"><span data-stu-id="b1155-107">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)
