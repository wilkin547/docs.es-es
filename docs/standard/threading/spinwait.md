---
title: SpinWait
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
helpviewer_keywords: synchronization primitives, SpinWait
ms.assetid: 36012f42-34e5-4f86-adf4-973f433ed6c6
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cfaf85c0fe1de3be89618ae540e9c183b66a11eb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="spinwait"></a>SpinWait
<xref:System.Threading.SpinWait?displayProperty=nameWithType>es un tipo de sincronización ligero que puede usar en escenarios de bajo nivel para evitar los costosos cambios de contexto y las transiciones de kernel que se requieren para los eventos de kernel. En los equipos con varios núcleos, cuando no se espera un recurso que se pueden mantener durante largos períodos de tiempo, puede ser más eficaz para un subproceso en espera gire en modo de usuario durante unos días o unos pocos centenares de ciclos y, a continuación, vuelva a intentar para adquirir el recurso. Si el recurso está disponible después de girar, a continuación, se han guardado varios miles de ciclos. Si el recurso está todavía no está disponible, a continuación, ha dedicado sólo unos ciclos y se puede escribir una espera basada en kernel. Esta combinación de giro y espera se denomina a veces un *operación de espera de dos fases*.  
  
 <xref:System.Threading.SpinWait>está diseñado para utilizarse junto con los tipos de .NET Framework que contienen eventos de kernel como <xref:System.Threading.ManualResetEvent>. <xref:System.Threading.SpinWait>También puede utilizarse por sí solo para la funcionalidad del giro básica en un único programa.  
  
 <xref:System.Threading.SpinWait>es algo más que un bucle vacío. Se implementa con cuidado para proporcionar un comportamiento de giro correcto para el caso general e iniciará por sí mismo cambios de contexto si gira durante el tiempo suficiente (aproximadamente el período de tiempo necesario para una transición del kernel). Por ejemplo, en equipos de un único núcleo, <xref:System.Threading.SpinWait> da como resultado el intervalo de tiempo del subproceso inmediatamente porque girar se bloquea el progreso en todos los subprocesos de avance. <xref:System.Threading.SpinWait>También se produce incluso en equipos de varios núcleos para evitar que el subproceso en espera de bloqueo de subprocesos de mayor prioridad o por el recolector de elementos no utilizados. Por lo tanto, si usas un <xref:System.Threading.SpinWait> en una operación de espera de dos fases, recomendamos que invoque la espera del kernel antes de la <xref:System.Threading.SpinWait> propio inicia un cambio de contexto. <xref:System.Threading.SpinWait>proporciona el <xref:System.Threading.SpinWait.NextSpinWillYield%2A> propiedad, que puede comprobar antes de cada llamada a <xref:System.Threading.SpinWait.SpinOnce%2A>. Cuando se devuelve la propiedad `true`, inicie su propia operación de espera. Para obtener un ejemplo, vea [Cómo: usar SpinWait para implementar una operación de espera de ejecución en dos fases](../../../docs/standard/threading/how-to-use-spinwait-to-implement-a-two-phase-wait-operation.md).  
  
 Si no se está realizando una operación de espera de dos fases, pero solo están girando hasta que una condición es true, puede habilitar <xref:System.Threading.SpinWait> realizar su contexto se activa para que sea un buen ciudadano en el entorno de sistema operativo de Windows. El siguiente ejemplo básico se muestra un <xref:System.Threading.SpinWait> en una pila sin bloqueo. Si necesita una pila de subprocesos de alto rendimiento, considere el uso de <xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType>.  
  
 [!code-csharp[CDS_SpinWait#05](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait.cs#05)]
 [!code-vb[CDS_SpinWait#05](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/cds_spinwait1.vb#05)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.Thread.SpinWait%2A>  
 [Objetos y características de subprocesos](../../../docs/standard/threading/threading-objects-and-features.md)
