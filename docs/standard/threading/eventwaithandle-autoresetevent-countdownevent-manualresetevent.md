---
title: EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6c545f9ebc924c0a12ee2e76fdb6c725c25e2353
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a>EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
Los identificadores de espera de evento permiten a los subprocesos sincronizar actividades mediante señales entre sí y mediante la espera de señales de los demás. Estos eventos de sincronización se basan en identificadores de espera Win32 y puede dividirse en dos tipos: los que se restablecen automáticamente cuando reciben señales y los que se restablecen manualmente.  
  
 Los identificadores de espera de evento son útiles en muchos de los mismos escenarios de sincronización que la clase <xref:System.Threading.Monitor>. Los identificadores de espera de eventos suelen ser más fáciles de utilizar que los métodos <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> y <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType>, y ofrecen mayor control de la señalización. Los identificadores de espera de evento con nombre pueden usarse también para sincronizar actividades entre dominios de aplicación y procesos, mientras que los monitores son locales a un dominio de aplicación.  
  
## <a name="in-this-section"></a>En esta sección  
 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md)  
 La clase <xref:System.Threading.EventWaitHandle> puede representar eventos de restablecimiento automático o manual, así como eventos locales o eventos del sistema con nombre.  
  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 La clase <xref:System.Threading.AutoResetEvent> deriva de <xref:System.Threading.EventWaitHandle> y representa un evento local que se restablece automáticamente.  
  
 [ManualResetEvent y ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 La clase <xref:System.Threading.ManualResetEvent> deriva de <xref:System.Threading.EventWaitHandle> y representa un evento local que se debe restablecer manualmente. La clase <xref:System.Threading.ManualResetEventSlim> es una versión ligera y más rápida que se puede usar en eventos de un mismo proceso.  
  
 [CountdownEvent](../../../docs/standard/threading/countdownevent.md)  
 La clase <xref:System.Threading.CountdownEvent> ofrece una forma simplificada de implementar patrones de paralelismo de bifurcación/combinación en código que usa identificadores de espera.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Wait Handles](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489) (Clases WaitHandle)  
 La clase <xref:System.Threading.WaitHandle> es la clase base para las clases <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore> y <xref:System.Threading.Mutex>. Contiene métodos estáticos como <xref:System.Threading.WaitHandle.SignalAndWait%2A> y <xref:System.Threading.WaitHandle.WaitAll%2A> que son útiles cuando se trabaja con todos los tipos de identificadores de espera.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 [Objetos y características de subprocesos](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Principios básicos del subprocesamiento administrado](../../../docs/standard/threading/managed-threading-basics.md)
