---
title: "How to: Synchronize Concurrent Operations with a Barrier | Microsoft Docs"
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
  - "Barrier, how to use"
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Synchronize Concurrent Operations with a Barrier
En el ejemplo siguiente se muestra cómo sincronizar tareas simultáneas con <xref:System.Threading.Barrier>.  
  
## Ejemplo  
 El siguiente programa tiene como propósito contar cuántas iteraciones \(o fases\) se requieren para que dos subprocesos busquen cada uno su mitad de la solución en la misma fase utilizando un algoritmo de aleatoriedad para reorganizar las palabras.  Después de que cada subproceso haya organizado sus palabras, en la fase posterior a la barrera se comparan los dos resultados para determinar si todas las palabras de la frase están correctamente ordenadas.  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 <xref:System.Threading.Barrier> es un objeto que impide que las tareas individuales de una operación paralela continúen hasta que todas las tareas alcancen la barrera.  Es útil cuando una operación paralela tiene lugar en fases y cada fase requiere sincronización entre las tareas.  En este ejemplo hay dos fases en la operación.  En la primera fase, cada tarea rellena su sección del búfer con datos.  Cuando cada tarea termina de rellenar su sección, la tarea señaliza a la barrera que está lista para continuar y espera.  Cuando todas las tareas han señalizado la barrera, se desbloquean y comienza la segunda fase.  La barrera es necesaria porque la segunda fase requiere que cada tarea obtenga acceso a todos los datos generados hasta este momento.  Sin la barrera, las primeras tareas en completarse podrían intentar leer de búferes que otras tareas no han rellenado todavía.  Es posible sincronizar cualquier número de fases de esta manera.  
  
## Vea también  
 [Data Structures for Parallel Programming](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)