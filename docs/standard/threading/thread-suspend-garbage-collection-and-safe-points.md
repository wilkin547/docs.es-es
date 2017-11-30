---
title: "Thread.Suspend, recolección de elementos no utilizados y puntos de seguridad"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- suspending threads
- safe points
- threading [.NET Framework], suspending
- threading [.NET Framework], garbage collection
- garbage collection, threads
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e47674ef8d1b1a7487e42765bcbce4b33cf98769
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="threadsuspend-garbage-collection-and-safe-points"></a>Thread.Suspend, recolección de elementos no utilizados y puntos de seguridad
Cuando se llama a <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> en un subproceso, el sistema detecta que la suspensión de un subproceso se ha solicitado y permite al subproceso de ejecución hasta que ha alcanzado un punto seguro antes de suspenderlo el subproceso. Un punto de seguridad para un subproceso es un punto en su ejecución y en qué elementos no utilizados puede realizarse la colección.  
  
 Una vez que se alcanza un punto seguro, el tiempo de ejecución garantiza que el subproceso suspendido no realizará ningún progreso adicional en código administrado. Un subproceso que se ejecuta fuera de código administrado siempre es seguro para la recolección y su ejecución continúa hasta que intenta reanudar la ejecución del código administrado.  
  
> [!NOTE]
>  Para realizar una recolección de elementos no utilizados, el tiempo de ejecución debe suspender todos los subprocesos salvo el subproceso que realiza la recolección. Cada subproceso debe llevarse a un punto de seguridad antes de que se pueda suspender.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.Thread>  
 <xref:System.GC>  
 [Subprocesamiento](../../../docs/standard/threading/index.md)  
 [Administración automática de la memoria](../../../docs/standard/automatic-memory-management.md)
