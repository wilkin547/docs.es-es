---
title: ManualResetEvent y ManualResetEventSlim
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f663dd17b063f77e2f9ce6bd4bbd0f8859ba4116
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="manualresetevent-and-manualreseteventslim"></a>ManualResetEvent y ManualResetEventSlim
La <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> clase representa un evento de identificador de espera local que se debe restablecer manualmente después de que se envía una señal. Esta clase representa un caso especial de su clase base, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>. Consulte la documentación conceptual [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) para información sobre el uso las características de los eventos de restablecimiento manual.  
  
 A <xref:System.Threading.ManualResetEvent> objeto permanece señalado hasta que su <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> se llama al método. Se puede liberar cualquier número de subprocesos en espera, o subprocesos que esperan el evento una vez señalado, mientras se señala el estado del objeto. <xref:System.Threading.ManualResetEvent>corresponde a Win32 `CreateEvent` llamar, especificar `true` para el `bManualReset` argumento.  
  
 En el [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], puede utilizar el <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> de clase para mejorar el rendimiento cuando se espera que los tiempos de espera sean muy cortos y cuando el evento no atraviesa un límite de proceso. <xref:System.Threading.ManualResetEventSlim>usa ocupado girando durante un período corto mientras se espera que se señaliza el evento. Cuando los tiempos de espera son breves, los giros pueden ser mucho más económicos que si se espera con identificadores de espera. Sin embargo, si no se señaliza el evento en un período determinado de tiempo, <xref:System.Threading.ManualResetEventSlim> recurre a una espera de identificador de evento habitual.  
  
## <a name="see-also"></a>Vea también  
 [Subprocesamiento](../../../docs/standard/threading/index.md)  
 [Objetos y características de subprocesos](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Wait Handles](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489) (Clases WaitHandle)  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 [SpinWait](../../../docs/standard/threading/spinwait.md)  
 [Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md) (Clases Semaphore y SemaphoreSlim)
