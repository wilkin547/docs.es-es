---
title: "How to: Implement Dynamic Partitions | Microsoft Docs"
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
  - "tasks, how to create a dynamic partitioner"
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 5
---
# How to: Implement Dynamic Partitions
En el siguiente ejemplo se muestra cómo implementar un <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=fullName> personalizado que implementa la creación de particiones dinámicas y que se puede utilizar desde algunas sobrecargas de <xref:System.Threading.Tasks.Parallel.ForEach%2A> y de PLINQ.  
  
## Ejemplo  
 Cada vez que una partición llama a <xref:System.Collections.IEnumerator.MoveNext%2A> en el enumerador, éste proporciona un elemento de lista a la partición.  En el caso de PLINQ y <xref:System.Threading.Tasks.Parallel.ForEach%2A>, la partición es una instancia de <xref:System.Threading.Tasks.Task>.  Dado que las solicitudes se producen simultáneamente en varios subprocesos, se sincroniza el acceso al índice actual.  
  
 [!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#04)]
 [!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  
  
 Éste es un ejemplo de creación de particiones de fragmentos, y cada fragmento se compone de un elemento.  Proporcionando más elementos a la vez, podría reducir la contención sobre el bloqueo y teóricamente lograr un rendimiento más rápido.  Sin embargo, en algún punto, los fragmentos mayores podrían requerir lógica de equilibrio de carga adicional para mantener todos los subprocesos ocupados hasta que se finalice todo el trabajo.  
  
## Vea también  
 [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)   
 [How to: Implement a Partitioner for Static Partitioning](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)