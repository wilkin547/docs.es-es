---
title: CountdownEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, CountdownEvent
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
ms.openlocfilehash: de9b49de86eb6489181afc8d8f5fbb1222bf877d
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188411"
---
# <a name="countdownevent"></a>CountdownEvent

<xref:System.Threading.CountdownEvent?displayProperty=nameWithType> es un primitivo de sincronización que desbloquea los subprocesos de espera después de haber sido señalado un número de veces determinado. <xref:System.Threading.CountdownEvent> está diseñado para escenarios en los que de lo contrario se tendría que usar <xref:System.Threading.ManualResetEvent> o <xref:System.Threading.ManualResetEventSlim> y disminuir manualmente una variable antes de señalar el evento. Por ejemplo, en un escenario de bifurcación/combinación, puede crear simplemente una clase <xref:System.Threading.CountdownEvent> que tiene un recuento de señal de 5 y, a continuación, iniciar cinco elementos de trabajo del grupo de subprocesos y realizar cada llamada <xref:System.Threading.CountdownEvent.Signal%2A> del elemento de trabajo cuando se completa. Cada llamada a <xref:System.Threading.CountdownEvent.Signal%2A> disminuye el recuento de señales en 1. En el subproceso principal, la llamada a <xref:System.Threading.CountdownEvent.Wait%2A> se bloqueará hasta que el recuento de señales sea cero.  
  
> [!NOTE]
> Para el código que no tiene que interactuar con las API de sincronización de .NET Framework heredadas, considere el uso de objetos <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> o del método <xref:System.Threading.Tasks.Parallel.Invoke%2A> para disponer de un método más sencillo para expresar el paralelismo bifurcación-combinación.  
  
 <xref:System.Threading.CountdownEvent> tiene estas características adicionales:  
  
- La operación de espera puede cancelarse mediante el uso de tokens de cancelación.  
  
- Una vez creada la instancia, se puede incrementar su recuento de señales.  
  
- Las instancias se pueden reutilizar después de que se devuelva <xref:System.Threading.CountdownEvent.Wait%2A> tras una llamada al método <xref:System.Threading.CountdownEvent.Reset%2A>.  
  
- Las instancias exponen <xref:System.Threading.WaitHandle> para la integración con otras API de sincronización de .NET como <xref:System.Threading.WaitHandle.WaitAll%2A>.  
  
## <a name="basic-usage"></a>Uso básico  
 En el siguiente ejemplo se muestra cómo se usa <xref:System.Threading.CountdownEvent> con los elementos de trabajo <xref:System.Threading.ThreadPool>.  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## <a name="countdownevent-with-cancellation"></a>CountdownEvent con cancelación  
 En el ejemplo siguiente se muestra cómo cancelar la operación de espera en <xref:System.Threading.CountdownEvent> utilizando un token de cancelación. El patrón básico sigue el modelo de cancelación unificada, que se presentó en .NET Framework 4. Para más información, consulte el tema sobre la [cancelación en subprocesos administrados](cancellation-in-managed-threads.md).  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 Tenga en cuenta que la operación de espera no cancela los subprocesos que la señalan. Normalmente, la cancelación se aplica a una operación lógica que puede incluir la espera del evento, así como todos los elementos de trabajo que la espera sincroniza. En este ejemplo, a cada elemento de trabajo se le pasa una copia del mismo token de cancelación, para que pueda responder a la solicitud de cancelación.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.Semaphore?displayProperty=nameWithType>
