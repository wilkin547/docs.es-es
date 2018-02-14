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
helpviewer_keywords:
- object pool, in .NET Framework
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 66cde52d7453e149510d0c2e1d63f9e9182e3e99
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-create-an-object-pool-by-using-a-concurrentbag"></a>Cómo: Crear un grupo de objetos usando ConcurrentBag
Este ejemplo muestra cómo usar un contenedor simultáneo para implementar un grupo de objetos. Los grupos de objetos pueden mejorar el rendimiento de la aplicación en situaciones donde se requieren varias instancias de una clase y cuesta mucho crear o destruir la clase. Cuando un programa cliente solicita un nuevo objeto, el grupo de objetos primero intenta proporcionar uno que ya se ha creado y devuelto al grupo. Si no hay ninguno disponible, solo entonces se crea un nuevo objeto.  
  
 <xref:System.Collections.Concurrent.ConcurrentBag%601> se usa para almacenar los objetos porque admite la inserción y eliminación rápidas, especialmente cuando el mismo subproceso agrega y quita elementos. Este ejemplo se podría ampliar aún más para crearse en torno a <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, que implementa la estructura de datos del contenedor, al igual que <xref:System.Collections.Concurrent.ConcurrentQueue%601> y <xref:System.Collections.Concurrent.ConcurrentStack%601>.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
 [!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]  
  
## <a name="see-also"></a>Vea también  
 [Colecciones seguras para subprocesos](../../../../docs/standard/collections/thread-safe/index.md)
