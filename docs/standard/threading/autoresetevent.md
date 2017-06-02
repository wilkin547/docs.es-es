---
title: "AutoResetEvent | Microsoft Docs"
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
  - "threading [.NET Framework], AutoResetEvent class"
  - "AutoResetEvent class"
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# AutoResetEvent
La clase <xref:System.Threading.AutoResetEvent> representa un evento de identificador de espera local que se restablece automáticamente cuando se le señala, después de liberar un subproceso en espera único.  Esta clase es un caso especial de su clase base, <xref:System.Threading.EventWaitHandle>.  Consulte la documentación conceptual [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) para obtener información sobre el uso y las características de los eventos de restablecimiento automático.  
  
 Un objeto <xref:System.Threading.AutoResetEvent> se restablece automáticamente a no señalado por el sistema una vez que se ha liberado un subproceso en espera único.  Si no hay subprocesos en espera, el objeto del evento sigue teniendo el estado señalizado.  <xref:System.Threading.AutoResetEvent> corresponde a una llamada `CreateEvent` de Win32, especificando `false` para el argumento `bManualReset`.  
  
 Para obtener un ejemplo de utilización <xref:System.Threading.AutoResetEvent>, vea [Monitor](../Topic/Monitors.md).  
  
## Vea también  
 <xref:System.Threading.ManualResetEvent>   
 <xref:System.Threading.Monitor>   
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)   
 [Threading](../../../docs/standard/threading/index.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)   
 [Wait Handles](../Topic/Wait%20Handles.md)