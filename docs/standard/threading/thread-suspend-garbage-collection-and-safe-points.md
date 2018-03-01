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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: fdd56763712dee9c6fa1f292eb3bbb2f0ccbf505
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="threadsuspend-garbage-collection-and-safe-points"></a>Thread.Suspend, recolección de elementos no utilizados y puntos de seguridad
Cuando se llama a <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> en un subproceso, el sistema detecta que la suspensión de un subproceso se ha solicitado y permite la ejecución del subproceso hasta que ha alcanzado un punto seguro antes de suspender realmente el subproceso. Un punto seguro de un subproceso es un punto en su ejecución en que se puede ejecutar la recolección de elementos no utilizados.  
  
 Una vez que se alcanza un punto seguro, el tiempo de ejecución garantiza que el subproceso suspendido no realizará ningún progreso adicional en el código administrado. Un subproceso que se ejecuta fuera del código administrado siempre es seguro para la recolección de elementos no utilizados y su ejecución continúa hasta que intenta reanudar la ejecución del código administrado.  
  
> [!NOTE]
>  Para realizar una recolección de elementos no utilizados, el tiempo de ejecución debe suspender todos los subprocesos salvo el subproceso que realiza la recolección. Cada subproceso debe llevarse a un punto seguro antes de que se pueda suspender.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.Thread>  
 <xref:System.GC>  
 [Subprocesamiento](../../../docs/standard/threading/index.md)  
 [Administración automática de la memoria](../../../docs/standard/automatic-memory-management.md)
