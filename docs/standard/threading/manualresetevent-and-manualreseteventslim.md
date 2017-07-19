---
title: "ManualResetEvent and ManualResetEventSlim | Microsoft Docs"
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
  - "threading [.NET Framework], ManualResetEvent class"
  - "ManualResetEvent class, about ManualResetEvent class"
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# ManualResetEvent and ManualResetEventSlim
La clase <xref:System.Threading.ManualResetEvent?displayProperty=fullName> representa un evento de identificador de espera local que se debe restablecer manualmente después de ser señalizado.  Esta clase es un caso especial de su clase base, <xref:System.Threading.EventWaitHandle?displayProperty=fullName>.  Consulte [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) en la documentación conceptual para conocer el uso y las características de los eventos que se restablecen manualmente.  
  
 Un objeto <xref:System.Threading.ManualResetEvent> permanece señalizado hasta que se llame al método <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=fullName>.  Se pueden liberar cualquier número de subprocesos en espera, o de subprocesos que esperan en el evento después de haber sido señalizado, mientras el estado del objeto es señalizado.  <xref:System.Threading.ManualResetEvent> corresponde a una llamada `CreateEvent` de Win32, especificando `true` para el argumento `bManualReset`.  
  
 En [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], puede utilizar la clase de <xref:System.Threading.ManualResetEventSlim?displayProperty=fullName> para mejorar el rendimiento cuando se prevé que los tiempos de espera sean muy cortos y, cuando el evento no cruza un límite de proceso.  <xref:System.Threading.ManualResetEventSlim> utiliza giros de ocupado por poco tiempo mientras espera a que se señale el evento.  Cuando los tiempos de espera son cortos, los giros puedes ser mucho menos costosos que las esperas con identificadores de espera.  Sin embargo, si no se señala el evento dentro de un período de tiempo determinado, <xref:System.Threading.ManualResetEventSlim> recurre a una espera de identificador de evento normal.  
  
## Vea también  
 [Threading](../../../docs/standard/threading/index.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)   
 [Wait Handles](../Topic/Wait%20Handles.md)   
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)   
 [SpinWait](../../../docs/standard/threading/spinwait.md)   
 [Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)