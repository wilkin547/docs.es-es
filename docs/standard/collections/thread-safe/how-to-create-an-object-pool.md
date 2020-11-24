---
title: Creación de un grupo de objetos mediante ConcurrentBag
ms.date: 05/01/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object pool, in .NET Framework
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
ms.openlocfilehash: c593c9b2011814c49563939f1094b62cd252879c
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822911"
---
# <a name="create-an-object-pool-by-using-a-concurrentbag"></a>Creación de un grupo de objetos mediante ConcurrentBag

En este ejemplo se muestra cómo usar <xref:System.Collections.Concurrent.ConcurrentBag%601> para implementar un grupo de objetos. Los grupos de objetos pueden mejorar el rendimiento de la aplicación en situaciones donde se requieren varias instancias de una clase y cuesta mucho crear o destruir la clase. Cuando un programa cliente solicita un nuevo objeto, el grupo de objetos primero intenta proporcionar uno que ya se ha creado y devuelto al grupo. Si no hay ninguno disponible, solo entonces se crea un nuevo objeto.

<xref:System.Collections.Concurrent.ConcurrentBag%601> se usa para almacenar los objetos porque admite la inserción y eliminación rápidas, especialmente cuando el mismo subproceso agrega y quita elementos. Este ejemplo se podría ampliar aún más para crearse en torno a <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, que implementa la estructura de datos del contenedor, al igual que <xref:System.Collections.Concurrent.ConcurrentQueue%601> y <xref:System.Collections.Concurrent.ConcurrentStack%601>.

> [!TIP]
> En este artículo se define cómo escribir su propia implementación de un grupo de objetos con un tipo simultáneo subyacente a fin de almacenar objetos para su reutilización. Sin embargo, el tipo <xref:Microsoft.Extensions.ObjectPool.ObjectPool%601?displayProperty=nameWithType> ya existe en el espacio de nombres <xref:Microsoft.Extensions.ObjectPool?displayProperty=fullName>. Considere la posibilidad de usar el tipo disponible antes de crear su propia implementación, que incluye muchas características adicionales.

## <a name="example"></a>Ejemplo

[!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
[!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]

## <a name="see-also"></a>Vea también

- [Colecciones seguras para subprocesos](index.md)
