---
title: "Cómo: Agregar la funcionalidad de límite y bloqueo a una colección"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, custom blocking collections
ms.assetid: 4c2492de-3876-4873-b5a1-000bb404d770
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3258534cb0bf67b180080eca4f7cefc65c609fa4
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-add-bounding-and-blocking-functionality-to-a-collection"></a><span data-ttu-id="75a50-102">Cómo: Agregar la funcionalidad de límite y bloqueo a una colección</span><span class="sxs-lookup"><span data-stu-id="75a50-102">How to: Add Bounding and Blocking Functionality to a Collection</span></span>
<span data-ttu-id="75a50-103">En este ejemplo se muestra cómo agregar la funcionalidad de límite y bloqueo a una clase de colección personalizada. Para ello, se implementa la interfaz <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=fullName> en la clase y, después, se usa una instancia de clase como mecanismo de almacenamiento interno para <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="75a50-103">This example shows how to add bounding and blocking functionality to a custom collection class by implementing the <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=fullName> interface in the class, and then using a class instance as the internal storage mechanism for a <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName>.</span></span> <span data-ttu-id="75a50-104">Para obtener más información acerca de la funcionalidad de límite y bloqueo, consulte [Información general sobre BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="75a50-104">For more information about bounding and blocking, see [BlockingCollection Overview](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="75a50-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="75a50-105">Example</span></span>  
 <span data-ttu-id="75a50-106">La clase de colección personalizada es una cola de prioridad básica en la que los niveles de prioridad se representan como una matriz de objetos <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="75a50-106">The custom collection class is a basic priority queue in which the priority levels are represented as an array of <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName> objects.</span></span> <span data-ttu-id="75a50-107">No se realiza ningún orden adicional en cada cola.</span><span class="sxs-lookup"><span data-stu-id="75a50-107">No additional ordering is performed within each queue.</span></span>  
  
 <span data-ttu-id="75a50-108">En el código de cliente, se inician tres tareas.</span><span class="sxs-lookup"><span data-stu-id="75a50-108">In the client code, three tasks are started.</span></span> <span data-ttu-id="75a50-109">La primera tarea se limita a sondear las pulsaciones de teclado para habilitar la cancelación en cualquier momento durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="75a50-109">The first task just polls for keyboard strokes to enable cancellation at any point during execution.</span></span> <span data-ttu-id="75a50-110">La segunda tarea es el subproceso de productor que agrega nuevos elementos a la colección de bloqueo y proporciona a cada elemento una prioridad basándose en un valor aleatorio.</span><span class="sxs-lookup"><span data-stu-id="75a50-110">The second task is the producer thread; it adds new items to the blocking collection and gives each item a priority based on a random value.</span></span> <span data-ttu-id="75a50-111">La tercera tarea quita elementos de la colección en cuanto estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="75a50-111">The third task removes items from the collection as they become available.</span></span>  
  
 <span data-ttu-id="75a50-112">Puede ajustar el comportamiento de la aplicación haciendo que uno de los subprocesos se ejecute más rápido que el otro.</span><span class="sxs-lookup"><span data-stu-id="75a50-112">You can adjust the behavior of the application by making one of the threads run faster than the other.</span></span> <span data-ttu-id="75a50-113">Si el productor se ejecuta más rápido, observará la funcionalidad de límite porque la colección de bloqueo impide que los elementos se agreguen si ya contiene el número de elementos que se especifican en el constructor.</span><span class="sxs-lookup"><span data-stu-id="75a50-113">If the producer runs faster, you will notice the bounding functionality as the blocking collection prevents items from being added if it already contains the number of items that is specified in the constructor.</span></span> <span data-ttu-id="75a50-114">Si el consumidor se ejecuta más rápido, observará la funcionalidad de bloqueo porque el consumidor espera que se agregue un nuevo elemento.</span><span class="sxs-lookup"><span data-stu-id="75a50-114">If the consumer runs faster, you will notice the blocking functionality as the consumer waits for a new item to be added.</span></span>  
  
 <span data-ttu-id="75a50-115">[!code-csharp[CDS_BlockingCollection#06](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/prodcon.cs#06)]</span><span class="sxs-lookup"><span data-stu-id="75a50-115">[!code-csharp[CDS_BlockingCollection#06](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/prodcon.cs#06)]</span></span>  
  
 <span data-ttu-id="75a50-116">De forma predeterminada, el almacenamiento de <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> es <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="75a50-116">By default, the storage for a <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> is <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75a50-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="75a50-117">See Also</span></span>  
 [<span data-ttu-id="75a50-118">Colecciones seguras para subprocesos</span><span class="sxs-lookup"><span data-stu-id="75a50-118">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)

