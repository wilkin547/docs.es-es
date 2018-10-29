---
title: EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
ms.date: 09/14/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be9c858d7c76fdcc1b3e02485eb0b459f4e7555c
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48583157"
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a>EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent

Los identificadores de espera de evento permiten a los subprocesos sincronizar actividades mediante señales entre sí y mediante la espera de señales de los demás. Estos eventos de sincronización se basan en identificadores de espera del sistema operativo y pueden dividirse en dos tipos: los que se restablecen automáticamente cuando reciben señales y los que se restablecen manualmente.  
  
Los identificadores de espera de evento son útiles en muchos de los mismos escenarios de sincronización que la clase <xref:System.Threading.Monitor>. Los identificadores de espera de eventos suelen ser más fáciles de utilizar que los métodos <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> y <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType>, y ofrecen mayor control de la señalización. Los identificadores de espera de evento con nombre pueden usarse también para sincronizar actividades entre dominios de aplicación y procesos, mientras que los monitores son locales a un dominio de aplicación.  
  
## <a name="in-this-section"></a>En esta sección

 [EventWaitHandle](eventwaithandle.md)  
 La clase <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> puede representar eventos de restablecimiento automático o manual, así como eventos locales o eventos del sistema con nombre.  
  
 [AutoResetEvent](autoresetevent.md)  
 La clase <xref:System.Threading.AutoResetEvent?displayProperty=nameWithType> deriva de <xref:System.Threading.EventWaitHandle> y representa un evento local que se restablece automáticamente.  
  
 [ManualResetEvent y ManualResetEventSlim](manualresetevent-and-manualreseteventslim.md)  
 La clase <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> deriva de <xref:System.Threading.EventWaitHandle> y representa un evento local que se debe restablecer manualmente. La clase <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> es una versión ligera y más rápida que se puede usar en eventos de un mismo proceso.  
  
 [CountdownEvent](countdownevent.md)  
 La clase <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> ofrece una forma simplificada de implementar patrones de paralelismo de bifurcación/combinación en código que usa identificadores de espera.  

## <a name="see-also"></a>Vea también

- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.Threading.Barrier?displayProperty=nameWithType>
- [Objetos y características de subprocesos](threading-objects-and-features.md)
- [Principios básicos del subprocesamiento administrado](managed-threading-basics.md)
