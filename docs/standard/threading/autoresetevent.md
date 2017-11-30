---
title: AutoResetEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 69d16e8c6491b4c66ab5a5452762e73172ebbb77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="autoresetevent"></a>AutoResetEvent
La <xref:System.Threading.AutoResetEvent> clase representa un evento de identificador de espera local que se restablece automáticamente cuando se señala, después de liberar un único subproceso en espera. Esta clase representa un caso especial de su clase base, <xref:System.Threading.EventWaitHandle>. Consulte la documentación conceptual [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) para información sobre el uso y las características de los eventos de restablecimiento automático.  
  
 Un <xref:System.Threading.AutoResetEvent> objeto se restablece automáticamente a no señalado por el sistema después de que se ha liberado un único subproceso en espera. Si no hay subprocesos en espera, el objeto del evento sigue teniendo el estado señalizado. <xref:System.Threading.AutoResetEvent>corresponde a Win32 `CreateEvent` llamar, especificar `false` para el `bManualReset` argumento.  
  
 Para obtener un ejemplo que usa <xref:System.Threading.AutoResetEvent>, consulte [Monitor](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 [Subprocesamiento](../../../docs/standard/threading/index.md)  
 [Objetos y características de subprocesos](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Wait Handles](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489) (Clases WaitHandle)
