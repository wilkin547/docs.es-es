---
title: "Cómo: Crear un grupo de objetos usando ConcurrentBag"
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
helpviewer_keywords: object pool, in .NET Framework
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f7cb18157122d8bc053f34b21f623f3ab1e14305
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-an-object-pool-by-using-a-concurrentbag"></a><span data-ttu-id="8016a-102">Cómo: Crear un grupo de objetos usando ConcurrentBag</span><span class="sxs-lookup"><span data-stu-id="8016a-102">How to: Create an Object Pool by Using a ConcurrentBag</span></span>
<span data-ttu-id="8016a-103">Este ejemplo muestra cómo usar un contenedor simultáneo para implementar un grupo de objetos.</span><span class="sxs-lookup"><span data-stu-id="8016a-103">This example shows how to use a concurrent bag to implement an object pool.</span></span> <span data-ttu-id="8016a-104">Los grupos de objetos pueden mejorar el rendimiento de la aplicación en situaciones donde se requieren varias instancias de una clase y cuesta mucho crear o destruir la clase.</span><span class="sxs-lookup"><span data-stu-id="8016a-104">Object pools can improve application performance in situations where you require multiple instances of a class and the class is expensive to create or destroy.</span></span> <span data-ttu-id="8016a-105">Cuando un programa cliente solicita un nuevo objeto, el grupo de objetos primero intenta proporcionar uno que ya se ha creado y devuelto al grupo.</span><span class="sxs-lookup"><span data-stu-id="8016a-105">When a client program requests a new object, the object pool first attempts to provide one that has already been created and returned to the pool.</span></span> <span data-ttu-id="8016a-106">Si no hay ninguno disponible, solo entonces se crea un nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="8016a-106">If none is available, only then is a new object created.</span></span>  
  
 <span data-ttu-id="8016a-107"><xref:System.Collections.Concurrent.ConcurrentBag%601> se usa para almacenar los objetos porque admite la inserción y eliminación rápidas, especialmente cuando el mismo subproceso agrega y quita elementos.</span><span class="sxs-lookup"><span data-stu-id="8016a-107"><xref:System.Collections.Concurrent.ConcurrentBag%601> is used to store the objects because it supports fast insertion and removal, especially when the same thread is both adding and removing items.</span></span> <span data-ttu-id="8016a-108">Este ejemplo se podría ampliar aún más para crearse en torno a <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, que implementa la estructura de datos del contenedor, al igual que <xref:System.Collections.Concurrent.ConcurrentQueue%601> y <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span><span class="sxs-lookup"><span data-stu-id="8016a-108">This example could be further augmented to be built around a <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, which the bag data structure implements, as do <xref:System.Collections.Concurrent.ConcurrentQueue%601> and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8016a-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8016a-109">Example</span></span>  
 [!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
 [!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]  
  
## <a name="see-also"></a><span data-ttu-id="8016a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="8016a-110">See Also</span></span>  
 [<span data-ttu-id="8016a-111">Colecciones seguras para subprocesos</span><span class="sxs-lookup"><span data-stu-id="8016a-111">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)
