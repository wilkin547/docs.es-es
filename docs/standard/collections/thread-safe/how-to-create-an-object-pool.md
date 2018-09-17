---
title: 'Cómo: Crear un grupo de objetos usando ConcurrentBag'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object pool, in .NET Framework
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0bc0c6bebbab6e84c165f41300a4cb16c8746a07
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45597308"
---
# <a name="how-to-create-an-object-pool-by-using-a-concurrentbag"></a><span data-ttu-id="8ba40-102">Cómo: Crear un grupo de objetos usando ConcurrentBag</span><span class="sxs-lookup"><span data-stu-id="8ba40-102">How to: Create an Object Pool by Using a ConcurrentBag</span></span>
<span data-ttu-id="8ba40-103">Este ejemplo muestra cómo usar un contenedor simultáneo para implementar un grupo de objetos.</span><span class="sxs-lookup"><span data-stu-id="8ba40-103">This example shows how to use a concurrent bag to implement an object pool.</span></span> <span data-ttu-id="8ba40-104">Los grupos de objetos pueden mejorar el rendimiento de la aplicación en situaciones donde se requieren varias instancias de una clase y cuesta mucho crear o destruir la clase.</span><span class="sxs-lookup"><span data-stu-id="8ba40-104">Object pools can improve application performance in situations where you require multiple instances of a class and the class is expensive to create or destroy.</span></span> <span data-ttu-id="8ba40-105">Cuando un programa cliente solicita un nuevo objeto, el grupo de objetos primero intenta proporcionar uno que ya se ha creado y devuelto al grupo.</span><span class="sxs-lookup"><span data-stu-id="8ba40-105">When a client program requests a new object, the object pool first attempts to provide one that has already been created and returned to the pool.</span></span> <span data-ttu-id="8ba40-106">Si no hay ninguno disponible, solo entonces se crea un nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="8ba40-106">If none is available, only then is a new object created.</span></span>  
  
 <span data-ttu-id="8ba40-107"><xref:System.Collections.Concurrent.ConcurrentBag%601> se usa para almacenar los objetos porque admite la inserción y eliminación rápidas, especialmente cuando el mismo subproceso agrega y quita elementos.</span><span class="sxs-lookup"><span data-stu-id="8ba40-107"><xref:System.Collections.Concurrent.ConcurrentBag%601> is used to store the objects because it supports fast insertion and removal, especially when the same thread is both adding and removing items.</span></span> <span data-ttu-id="8ba40-108">Este ejemplo se podría ampliar aún más para crearse en torno a <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, que implementa la estructura de datos del contenedor, al igual que <xref:System.Collections.Concurrent.ConcurrentQueue%601> y <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span><span class="sxs-lookup"><span data-stu-id="8ba40-108">This example could be further augmented to be built around a <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, which the bag data structure implements, as do <xref:System.Collections.Concurrent.ConcurrentQueue%601> and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ba40-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ba40-109">Example</span></span>  
 [!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
 [!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]  
  
## <a name="see-also"></a><span data-ttu-id="8ba40-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ba40-110">See also</span></span>

- [<span data-ttu-id="8ba40-111">Colecciones seguras para subprocesos</span><span class="sxs-lookup"><span data-stu-id="8ba40-111">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)
