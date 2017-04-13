---
title: "CountdownEvent | Microsoft Docs"
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
  - "synchronization primitives, CountdownEvent"
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# CountdownEvent
<xref:System.Threading.CountdownEvent?displayProperty=fullName> es una primitiva de sincronización que desbloquea los subprocesos en espera después de haber sido señalada cierto número de veces.  <xref:System.Threading.CountdownEvent> se ha diseñado para escenarios en los que, de lo contrario, habría que utilizar <xref:System.Threading.ManualResetEvent> o <xref:System.Threading.ManualResetEventSlim> y disminuir manualmente una variable antes de señalar el evento.  Por ejemplo, en un escenario de bifurcación\/combinación, puede crear un <xref:System.Threading.CountdownEvent> que tiene un recuento señalado de 5 y, a continuación, iniciar cinco elementos de trabajo en el grupo de subprocesos y hacer que cada elemento de trabajo llame a <xref:System.Threading.CountdownEvent.Signal%2A> cuando se complete.  Cada llamada a <xref:System.Threading.CountdownEvent.Signal%2A> disminuye el recuento señalado en 1.  En el subproceso principal, la llamada a <xref:System.Threading.CountdownEvent.Wait%2A> se bloqueará hasta que el recuento señalado sea cero.  
  
> [!NOTE]
>  Para el código que no tiene que interactuar con las API de sincronización de .NET Framework heredadas, considere el uso de objetos <xref:System.Threading.Tasks.Task?displayProperty=fullName> o del método <xref:System.Threading.Tasks.Parallel.Invoke%2A> para un planteamiento aún más sencillo para expresar el paralelismo bifurcación\/combinación.  
  
 <xref:System.Threading.CountdownEvent> tiene estas características adicionales:  
  
-   La operación de espera puede cancelarse con los token de cancelación.  
  
-   Se puede incrementar su recuento señalado una vez creada la instancia.  
  
-   Se pueden reutilizar las instancias después de que <xref:System.Threading.CountdownEvent.Wait%2A> haya vuelto mediante la llamada al método <xref:System.Threading.CountdownEvent.Reset%2A>.  
  
-   Las instancias exponen un <xref:System.Threading.WaitHandle> para la integración con otras API de sincronización de .NET Framework, como <xref:System.Threading.WaitHandle.WaitAll%2A>.  
  
## Uso básico  
 En el ejemplo siguiente se muestra la forma de utilizar un <xref:System.Threading.CountdownEvent> con elementos de trabajo <xref:System.Threading.ThreadPool>.  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## CountdownEvent con cancelación  
 En el siguiente ejemplo se muestra cómo cancelar la operación de espera en <xref:System.Threading.CountdownEvent> utilizando un token de cancelación.  El modelo básico sigue el modelo de la cancelación unificada, que se presentó en [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].  Para obtener más información, vea [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md).  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 Observe que la operación de espera no cancela los subprocesos que la señalan.  Normalmente, la cancelación se aplica a una operación lógica, lo que puede incluir esperar el evento y todos los elementos de trabajo que la espera esté sincronizando.  En este ejemplo, a cada elemento de trabajo se pasa una copia del mismo token de cancelación para que pueda responder a la solicitud de cancelación.  
  
## Vea también  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)