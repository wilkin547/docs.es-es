---
title: "Cómo crear un grupo de objetos usando ConcurrentBag | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- object pool, in .NET Framework
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
caps.latest.revision: 5
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: bfe61501586deed112d6a94bf90fd83e84f2639f
ms.lasthandoff: 04/18/2017

---
# <a name="how-to-create-an-object-pool-by-using-a-concurrentbag"></a>Cómo: Crear un grupo de objetos usando ConcurrentBag
Este ejemplo muestra cómo usar un contenedor simultáneo para implementar un grupo de objetos. Los grupos de objetos pueden mejorar el rendimiento de la aplicación en situaciones donde se requieren varias instancias de una clase y cuesta mucho crear o destruir la clase. Cuando un programa cliente solicita un nuevo objeto, el grupo de objetos primero intenta proporcionar uno que ya se ha creado y devuelto al grupo. Si no hay ninguno disponible, solo entonces se crea un nuevo objeto.  
  
 <xref:System.Collections.Concurrent.ConcurrentBag%601> se usa para almacenar los objetos porque admite la inserción y eliminación rápidas, especialmente cuando el mismo subproceso agrega y quita elementos. Este ejemplo podría ampliarse más para compilarlo en relación con <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, que implementa la estructura de datos del contenedor, como <xref:System.Collections.Concurrent.ConcurrentQueue%601> y <xref:System.Collections.Concurrent.ConcurrentStack%601>.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
 [!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]  
  
## <a name="see-also"></a>Vea también  
 [Colecciones seguras para subprocesos](../../../../docs/standard/collections/thread-safe/index.md)
