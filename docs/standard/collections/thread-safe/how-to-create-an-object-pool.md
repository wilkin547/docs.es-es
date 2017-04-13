---
title: "C&#243;mo: Crear un grupo de objetos usando ConcurrentBag | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "conjunto de objetos, en .NET Framework"
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
caps.latest.revision: 5
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Crear un grupo de objetos usando ConcurrentBag
En este ejemplo se muestra cómo usar un contenedor simultáneo para implementar un grupo de objetos.  Los grupos de objetos pueden mejorar el rendimiento de la aplicación en situaciones donde se necesitan varias instancias de una clase y es costoso crear o destruir la clase.  Cuando un programa cliente solicita un objeto nuevo, el grupo de objetos intenta primero proporcionar uno que ya se haya creado y devuelto ya al grupo.  Si no hay ninguno disponible, solo entonces se crea un objeto nuevo.  
  
 <xref:System.Collections.Concurrent.ConcurrentBag%601> se emplea para almacenar los objetos porque admite la inserción y la eliminación rápidas, sobre todo cuando el mismo subproceso agrega y quita elementos.  Este ejemplo podría ampliarse más alrededor de <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, que la estructura de datos de contenedor implementa, al igual que <xref:System.Collections.Concurrent.ConcurrentQueue%601> y <xref:System.Collections.Concurrent.ConcurrentStack%601>.  
  
## Ejemplo  
 [!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
 [!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]  
  
## Vea también  
 [Colecciones seguras para subprocesos](../../../../docs/standard/collections/thread-safe/index.md)