---
title: "EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent | Microsoft Docs"
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
  - "wait handles"
  - "threading [.NET Framework], EventWaitHandle class"
  - "event wait handles [.NET Framework]"
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
Los identificadores de espera de evento permiten a los subprocesos sincronizar las actividades señalizándose entre sí y esperando señales de los demás.  Estos eventos de sincronización se basan en identificadores de espera Win32 y se pueden dividir en dos tipos: los que se restablecen automáticamente cuando reciben una señal y los que se restablecen manualmente.  
  
 Los identificadores de espera de evento son útiles en muchos de los mismos escenarios de sincronización que los de la clase <xref:System.Threading.Monitor>.  Los identificadores de espera de evento son a menudo más fáciles de utilizar que los métodos <xref:System.Threading.Monitor.Wait%2A?displayProperty=fullName> y <xref:System.Threading.Monitor.Pulse%2A?displayProperty=fullName> y proporcionan un mayor control sobre la señalización.  Los identificadores de espera de evento con nombre también se pueden utilizar para sincronizar las actividades entre los dominios de aplicación y procesos, mientras que los monitores son locales a un dominio de aplicación.  
  
## En esta sección  
 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md)  
 La clase <xref:System.Threading.EventWaitHandle> puede representar eventos de reinicio automáticos o manuales y eventos locales o eventos del sistema con nombre.  
  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 La clase <xref:System.Threading.AutoResetEvent> deriva de <xref:System.Threading.EventWaitHandle> y representa un evento local que se restablece automáticamente.  
  
 [ManualResetEvent and ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 La clase <xref:System.Threading.ManualResetEvent> deriva de <xref:System.Threading.EventWaitHandle> y representa un evento local que se debe restablecer manualmente.  La clase <xref:System.Threading.ManualResetEventSlim> es una versión ligera y más rápida que se puede usar para eventos dentro del mismo proceso.  
  
 [CountdownEvent](../../../docs/standard/threading/countdownevent.md)  
 La clase <xref:System.Threading.CountdownEvent> proporciona una manera simplificada de implementar modelos de paralelismo de bifurcación\/combinación en código que usa identificadores de espera.  
  
## Secciones relacionadas  
 [Wait Handles](../Topic/Wait%20Handles.md)  
 La clase <xref:System.Threading.WaitHandle> es la clase base de las clases <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore> y <xref:System.Threading.Mutex>.  Contiene métodos estáticos como <xref:System.Threading.WaitHandle.SignalAndWait%2A> y <xref:System.Threading.WaitHandle.WaitAll%2A> que son útiles al trabajar con todos los tipos de identificadores de la espera.  
  
## Vea también  
 <xref:System.Threading.EventWaitHandle>   
 <xref:System.Threading.WaitHandle>   
 <xref:System.Threading.AutoResetEvent>   
 <xref:System.Threading.ManualResetEvent>   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)   
 [Managed Threading Basics](../../../docs/standard/threading/managed-threading-basics.md)