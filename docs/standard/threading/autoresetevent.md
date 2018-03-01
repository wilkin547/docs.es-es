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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 71933d0be804fdf68b0dc602902343f2d88b8c82
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="autoresetevent"></a>AutoResetEvent
La clase <xref:System.Threading.AutoResetEvent> representa un evento de identificador de espera local que se restablece automáticamente cuando se le señala, después de liberar un subproceso en espera único. Esta clase representa un caso especial de su clase base, <xref:System.Threading.EventWaitHandle>. Consulte la documentación conceptual [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) para información sobre el uso y las características de los eventos de restablecimiento automático.  
  
 Un objeto <xref:System.Threading.AutoResetEvent> se restablece automáticamente a no señalado por el sistema una vez que se ha liberado un subproceso en espera único. Si no hay subprocesos en espera, el objeto del evento sigue teniendo el estado señalizado. <xref:System.Threading.AutoResetEvent> corresponde a una llamada a `CreateEvent` de Win32, definiendo `false` para el argumento `bManualReset`.  
  
 Para obtener un ejemplo que use <xref:System.Threading.AutoResetEvent>, vea [Monitor](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 [Subprocesamiento](../../../docs/standard/threading/index.md)  
 [Objetos y características de subprocesos](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Wait Handles](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489) (Clases WaitHandle)
