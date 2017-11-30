---
title: CountdownEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: synchronization primitives, CountdownEvent
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9f953f6477abf1f4e0d6aaf79e67005172ff1144
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="countdownevent"></a>CountdownEvent
<xref:System.Threading.CountdownEvent?displayProperty=nameWithType>es una primitiva de sincronización que desbloquea los subprocesos en espera una vez señala un número determinado de veces. <xref:System.Threading.CountdownEvent>está diseñado para escenarios en los que de lo contrario tendría que usar un <xref:System.Threading.ManualResetEvent> o <xref:System.Threading.ManualResetEventSlim> y disminuir manualmente una variable antes de señalar el evento. Por ejemplo, en un escenario de bifurcación/combinación, puede simplemente crear un <xref:System.Threading.CountdownEvent> que tiene un recuento de señal de 5 y, a continuación, iniciar cinco elementos de trabajo en el subproceso de grupo y tienen cada llamada de elemento de trabajo <xref:System.Threading.CountdownEvent.Signal%2A> cuando termina. Cada llamada a <xref:System.Threading.CountdownEvent.Signal%2A> disminuye el recuento señalado en 1. En el subproceso principal, la llamada a <xref:System.Threading.CountdownEvent.Wait%2A> se bloqueará hasta que el recuento de señal es cero.  
  
> [!NOTE]
>  Para el código que no tienen que interactuar con la API de sincronización de .NET Framework heredada, considere el uso de <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objetos o <xref:System.Threading.Tasks.Parallel.Invoke%2A> método para obtener un enfoque para expresar el paralelismo del tipo bifurcar-recombinar con mayor facilidad.  
  
 <xref:System.Threading.CountdownEvent>tiene las siguientes características adicionales:  
  
-   La operación de espera puede cancelarse mediante el uso de tokens de cancelación.  
  
-   Una vez creada la instancia, se puede incrementar su recuento de señal.  
  
-   Pueden reutilizar las instancias después de <xref:System.Threading.CountdownEvent.Wait%2A> ha devuelto mediante una llamada a la <xref:System.Threading.CountdownEvent.Reset%2A> método.  
  
-   Las instancias exponen un <xref:System.Threading.WaitHandle> para la integración con otra API de sincronización de .NET Framework como <xref:System.Threading.WaitHandle.WaitAll%2A>.  
  
## <a name="basic-usage"></a>Uso básico  
 En el ejemplo siguiente se muestra cómo utilizar un <xref:System.Threading.CountdownEvent> con <xref:System.Threading.ThreadPool> los elementos de trabajo.  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## <a name="countdownevent-with-cancellation"></a>CountdownEvent con cancelación  
 En el ejemplo siguiente se muestra cómo cancelar la operación de espera en <xref:System.Threading.CountdownEvent> utilizando un token de cancelación. El patrón básico sigue el modelo de cancelación unificado, que se introdujo en [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]. Para obtener más información, consulte [cancelación en subprocesos administrados](../../../docs/standard/threading/cancellation-in-managed-threads.md).  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 Tenga en cuenta que la operación de espera no cancela los subprocesos que señalan. Normalmente, la cancelación se aplica a una operación lógica y que puede incluir esperar en el evento, así como todos los elementos de trabajo que está sincronizando la espera. En este ejemplo, cada elemento de trabajo se pasa una copia del mismo token de cancelación para que puedan responder a la solicitud de cancelación.  
  
## <a name="see-also"></a>Vea también  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
