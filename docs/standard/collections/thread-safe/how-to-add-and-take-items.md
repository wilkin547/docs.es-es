---
title: "Cómo: Agregar y tomar elementos de forma individual en una clase BlockingCollection"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, blocking dictionary
ms.assetid: 38f2f3d8-15e5-4bf4-9c83-2b5b6f22bad1
caps.latest.revision: 7
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 66b4e921a4c7285976694f4633ce1eeaadcb7cf9
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-add-and-take-items-individually-from-a-blockingcollection"></a><span data-ttu-id="b2643-102">Cómo: Agregar y tomar elementos de forma individual en una clase BlockingCollection</span><span class="sxs-lookup"><span data-stu-id="b2643-102">How to: Add and Take Items Individually from a BlockingCollection</span></span>
<span data-ttu-id="b2643-103">Este ejemplo muestra cómo agregar y quitar elementos de <xref:System.Collections.Concurrent.BlockingCollection%601> con bloqueo y sin bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b2643-103">This example shows how to add and remove items from a <xref:System.Collections.Concurrent.BlockingCollection%601> in both a blocking and non-blocking manner.</span></span> <span data-ttu-id="b2643-104">Para obtener más información sobre <xref:System.Collections.Concurrent.BlockingCollection%601>, consulte [Información general sobre BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b2643-104">For more information on <xref:System.Collections.Concurrent.BlockingCollection%601>, see [BlockingCollection Overview](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span></span>  
  
 <span data-ttu-id="b2643-105">Para obtener un ejemplo de cómo enumerar un elemento <xref:System.Collections.Concurrent.BlockingCollection%601> hasta que esté vacío y que así no se agreguen más elementos, consulte [Cómo: Utilizar ForEach para quitar elementos de BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md).</span><span class="sxs-lookup"><span data-stu-id="b2643-105">For an example of how to enumerate a <xref:System.Collections.Concurrent.BlockingCollection%601> until it is empty and no more elements will be added, see [How to: Use ForEach to Remove Items in a BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md)</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2643-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b2643-106">Example</span></span>  
 <span data-ttu-id="b2643-107">En este primer ejemplo se muestra cómo agregar y quitar elementos para que las operaciones se bloqueen si la colección está temporalmente vacía (al quitarla) o en su capacidad máxima (al agregarla), o si ha transcurrido el período de tiempo de espera especificado.</span><span class="sxs-lookup"><span data-stu-id="b2643-107">This first example shows how to add and take items so that the operations will block if the collection is either temporarily empty (when taking) or at maximum capacity (when adding), or a specified timeout period has elapsed.</span></span> <span data-ttu-id="b2643-108">Tenga en cuenta que el bloqueo en capacidad máxima solo se habilita cuando el elemento BlockingCollection se crea con una capacidad máxima especificada en el constructor.</span><span class="sxs-lookup"><span data-stu-id="b2643-108">Note that blocking on maximum capacity is only enabled when the BlockingCollection has been created with a maximum capacity specified in the constructor.</span></span>  
  
 <span data-ttu-id="b2643-109">[!code-csharp[CDS_BlockingCollection#01](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example01.cs#01)] [!code-vb[CDS_BlockingCollection#01](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/simpleblocking.vb#01)]</span><span class="sxs-lookup"><span data-stu-id="b2643-109">[!code-csharp[CDS_BlockingCollection#01](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example01.cs#01)] [!code-vb[CDS_BlockingCollection#01](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/simpleblocking.vb#01)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2643-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b2643-110">Example</span></span>  
 <span data-ttu-id="b2643-111">En este segundo ejemplo se muestra cómo agregar y quitar elementos para que las operaciones no se bloqueen.</span><span class="sxs-lookup"><span data-stu-id="b2643-111">This second example shows how to add and take items so that the operations will not block.</span></span> <span data-ttu-id="b2643-112">Si no hay ningún elemento o si se ha alcanzado la capacidad máxima de una colección limitada, o si el periodo de tiempo de espera ya ha transcurrido, la operación <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> o <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> devuelve el resultado “false”.</span><span class="sxs-lookup"><span data-stu-id="b2643-112">If no item is present, or maximum capacity on a bounded collection has been reached, or the timeout period has elapsed, then the <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> or <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> operation returns false.</span></span> <span data-ttu-id="b2643-113">Esto permite al subproceso hacer algún otro trabajo útil durante un rato, para después volver a intentar recuperar un nuevo elemento o intentar agregar el elemento que no se pudo agregar previamente.</span><span class="sxs-lookup"><span data-stu-id="b2643-113">This allows the thread to do some other useful work for awhile and then try again later to either retrieve a new item, or try to add the same item that could not be added previously.</span></span> <span data-ttu-id="b2643-114">Asimismo, el programa también muestra cómo implementar la cancelación cuando se tiene acceso al elemento <xref:System.Collections.Concurrent.BlockingCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="b2643-114">The program also demonstrates how to implement cancellation when accessing a <xref:System.Collections.Concurrent.BlockingCollection%601>.</span></span>  
  
 <span data-ttu-id="b2643-115">[!code-csharp[CDS_BlockingCollection#02](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example02.cs#02)] [!code-vb[CDS_BlockingCollection#02](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/nonblockingbc.vb#02)]</span><span class="sxs-lookup"><span data-stu-id="b2643-115">[!code-csharp[CDS_BlockingCollection#02](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example02.cs#02)] [!code-vb[CDS_BlockingCollection#02](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/nonblockingbc.vb#02)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2643-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2643-116">See Also</span></span>  
 <span data-ttu-id="b2643-117"><xref:System.Collections.Concurrent?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b2643-117"><xref:System.Collections.Concurrent?displayProperty=fullName></span></span>   
 [<span data-ttu-id="b2643-118">Información general sobre BlockingCollection</span><span class="sxs-lookup"><span data-stu-id="b2643-118">BlockingCollection Overview</span></span>](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md)

