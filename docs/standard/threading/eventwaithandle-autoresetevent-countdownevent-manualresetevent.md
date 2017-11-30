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
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5c0bcb27ed9c8981665a50c129dfbd824c9612f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a>EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
Los identificadores de espera de evento permiten a los subprocesos sincronizar actividades mediante señales entre sí y mediante la espera de señales de los demás. Estos eventos de sincronización se basan en identificadores de espera Win32 y puede dividirse en dos tipos: los que se restablecen automáticamente cuando reciben señales y los que se restablecen manualmente.  
  
 Identificadores de espera de evento son útiles en muchos de los mismos escenarios de sincronización como el <xref:System.Threading.Monitor> clase. Identificadores de espera de evento son a menudo más fáciles de usar que los <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> y <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> métodos y proporcionan un mayor control sobre la señalización. Los identificadores de espera de evento con nombre pueden usarse también para sincronizar actividades entre dominios de aplicación y procesos, mientras que los monitores son locales a un dominio de aplicación.  
  
## <a name="in-this-section"></a>En esta sección  
 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md)  
 La <xref:System.Threading.EventWaitHandle> clase puede representar cualquier automático o manual de restablecimiento de eventos y eventos locales o con el nombre de eventos del sistema.  
  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 El <xref:System.Threading.AutoResetEvent> clase se deriva de <xref:System.Threading.EventWaitHandle> y representa un evento local que se restablece automáticamente.  
  
 [ManualResetEvent y ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 El <xref:System.Threading.ManualResetEvent> clase se deriva de <xref:System.Threading.EventWaitHandle> y representa un evento local que se debe restablecer manualmente. La <xref:System.Threading.ManualResetEventSlim> clase es una versión ligera y más rápida que puede usarse para los eventos dentro del mismo proceso.  
  
 [CountdownEvent](../../../docs/standard/threading/countdownevent.md)  
 La <xref:System.Threading.CountdownEvent> clase proporciona una manera simplificada de implementar modelos de paralelismo de bifurcación/combinación en código que usa identificadores de espera.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Wait Handles](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489) (Clases WaitHandle)  
 El <xref:System.Threading.WaitHandle> clase es la clase base para la <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore>, y <xref:System.Threading.Mutex> clases. Contiene métodos estáticos como <xref:System.Threading.WaitHandle.SignalAndWait%2A> y <xref:System.Threading.WaitHandle.WaitAll%2A> que son útiles cuando se trabaja con todos los tipos de identificadores de espera.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 [Objetos y características de subprocesos](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Principios básicos del subprocesamiento administrado](../../../docs/standard/threading/managed-threading-basics.md)
