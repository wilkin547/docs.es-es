---
title: Creación de un grupo de objetos mediante ConcurrentBag
ms.date: 05/01/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object pool, in .NET Framework
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
ms.openlocfilehash: 2c060dc901f8d06a5f9c51db1cd563cb28e4fda3
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728472"
---
# <a name="create-an-object-pool-by-using-a-concurrentbag"></a><span data-ttu-id="2c0d4-102">Creación de un grupo de objetos mediante ConcurrentBag</span><span class="sxs-lookup"><span data-stu-id="2c0d4-102">Create an object pool by using a ConcurrentBag</span></span>

<span data-ttu-id="2c0d4-103">En este ejemplo se muestra cómo usar <xref:System.Collections.Concurrent.ConcurrentBag%601> para implementar un grupo de objetos.</span><span class="sxs-lookup"><span data-stu-id="2c0d4-103">This example shows how to use a <xref:System.Collections.Concurrent.ConcurrentBag%601> to implement an object pool.</span></span> <span data-ttu-id="2c0d4-104">Los grupos de objetos pueden mejorar el rendimiento de la aplicación en situaciones donde se requieren varias instancias de una clase y cuesta mucho crear o destruir la clase.</span><span class="sxs-lookup"><span data-stu-id="2c0d4-104">Object pools can improve application performance in situations where you require multiple instances of a class and the class is expensive to create or destroy.</span></span> <span data-ttu-id="2c0d4-105">Cuando un programa cliente solicita un nuevo objeto, el grupo de objetos primero intenta proporcionar uno que ya se ha creado y devuelto al grupo.</span><span class="sxs-lookup"><span data-stu-id="2c0d4-105">When a client program requests a new object, the object pool first attempts to provide one that has already been created and returned to the pool.</span></span> <span data-ttu-id="2c0d4-106">Si no hay ninguno disponible, solo entonces se crea un nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="2c0d4-106">If none is available, only then is a new object created.</span></span>

<span data-ttu-id="2c0d4-107"><xref:System.Collections.Concurrent.ConcurrentBag%601> se usa para almacenar los objetos porque admite la inserción y eliminación rápidas, especialmente cuando el mismo subproceso agrega y quita elementos.</span><span class="sxs-lookup"><span data-stu-id="2c0d4-107">The <xref:System.Collections.Concurrent.ConcurrentBag%601> is used to store the objects because it supports fast insertion and removal, especially when the same thread is both adding and removing items.</span></span> <span data-ttu-id="2c0d4-108">Este ejemplo se podría ampliar aún más para crearse en torno a <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, que implementa la estructura de datos del contenedor, al igual que <xref:System.Collections.Concurrent.ConcurrentQueue%601> y <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span><span class="sxs-lookup"><span data-stu-id="2c0d4-108">This example could be further augmented to be built around a <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, which the bag data structure implements, as do <xref:System.Collections.Concurrent.ConcurrentQueue%601> and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>

> [!TIP]
> <span data-ttu-id="2c0d4-109">En este artículo se define cómo escribir su propia implementación de un grupo de objetos con un tipo simultáneo subyacente a fin de almacenar objetos para su reutilización.</span><span class="sxs-lookup"><span data-stu-id="2c0d4-109">This article defines how to write your own implementation of an object pool with an underlying concurrent type to store objects for reuse.</span></span> <span data-ttu-id="2c0d4-110">Sin embargo, el tipo <xref:Microsoft.Extensions.ObjectPool.ObjectPool%601?displayProperty=nameWithType> ya existe en el espacio de nombres <xref:Microsoft.Extensions.ObjectPool?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="2c0d4-110">However, the <xref:Microsoft.Extensions.ObjectPool.ObjectPool%601?displayProperty=nameWithType> type already exists under the <xref:Microsoft.Extensions.ObjectPool?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="2c0d4-111">Considere la posibilidad de usar el tipo disponible antes de crear su propia implementación, que incluye muchas características adicionales.</span><span class="sxs-lookup"><span data-stu-id="2c0d4-111">Consider using the available type before creating your own implementation, which includes many additional features.</span></span>

## <a name="example"></a><span data-ttu-id="2c0d4-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2c0d4-112">Example</span></span>

[!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
[!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]

## <a name="see-also"></a><span data-ttu-id="2c0d4-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c0d4-113">See also</span></span>

- [<span data-ttu-id="2c0d4-114">Colecciones seguras para subprocesos</span><span class="sxs-lookup"><span data-stu-id="2c0d4-114">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)
