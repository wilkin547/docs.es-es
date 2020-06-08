---
title: SpinWait
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, SpinWait
ms.assetid: 36012f42-34e5-4f86-adf4-973f433ed6c6
ms.openlocfilehash: 8b98e7d8b8ea4578fb446a0587f9a46ba4271348
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291115"
---
# <a name="spinwait"></a>SpinWait
<xref:System.Threading.SpinWait?displayProperty=nameWithType> es un tipo de sincronización ligero que puede usar en escenarios de bajo nivel para evitar los costosos cambios de contexto y las transiciones de kernel que se requieren para los eventos de kernel. En los equipos con varios núcleos, cuando no se espera que un recurso se mantenga durante largos períodos de tiempo, puede resultar más eficaz que un subproceso en espera itere en modo de usuario en unas docenas o centenas de ciclos y que luego vuelva a intentar adquirir el recurso. Si el recurso está disponible después de girar, entonces habrá guardado varios miles de ciclos. Si el recurso aún no está disponible, habrá empleado solo algunos ciclos y podrá activar aún una espera basada en el kernel. A esta combinación de giro y espera se le denomina a veces una *operación de espera de dos fases*.  
  
 <xref:System.Threading.SpinWait> está diseñado para utilizarse junto con los tipos de .NET Framework que contienen eventos de kernel como <xref:System.Threading.ManualResetEvent>. <xref:System.Threading.SpinWait> también puede utilizarse por sí solo para la funcionalidad de giro básica en un único programa.  
  
 <xref:System.Threading.SpinWait> es algo más que un bucle vacío. Se implementa con cuidado para proporcionar un comportamiento de giro correcto para el caso general e iniciará por sí mismo cambios de contexto si gira durante el tiempo suficiente (aproximadamente el período de tiempo necesario para una transición del kernel). Por ejemplo, en equipos de un único núcleo, <xref:System.Threading.SpinWait> da como resultado el intervalo de tiempo del subproceso inmediatamente porque el giro bloquea el progreso en todos los subprocesos. <xref:System.Threading.SpinWait> también se produce incluso en equipos de varios núcleos para evitar que el subproceso en espera bloquee subprocesos de mayor prioridad o el recolector de elementos no utilizados. Por lo tanto, si usa <xref:System.Threading.SpinWait> en una operación de espera de dos fases, recomendamos que invoque la espera del kernel antes de que <xref:System.Threading.SpinWait> inicie un cambio de contexto. <xref:System.Threading.SpinWait> proporciona la propiedad <xref:System.Threading.SpinWait.NextSpinWillYield%2A>, que puede comprobar antes de cada llamada a <xref:System.Threading.SpinWait.SpinOnce%2A>. Cuando se devuelve la propiedad `true`, inicie su propia operación de espera. Para consultar un ejemplo, vea [Usar SpinWait para implementar una operación de espera de dos fases](how-to-use-spinwait-to-implement-a-two-phase-wait-operation.md).  
  
 Si no se está realizando una operación de espera de dos fases, sino que solo gira hasta que una condición sea true, puede habilitar <xref:System.Threading.SpinWait> para realizar sus cambios de contexto, para actuar correctamente en el entorno del sistema operativo Windows. En el siguiente ejemplo básico, se muestra <xref:System.Threading.SpinWait> en una pila sin bloqueo. Si necesita una pila segura para subprocesos y de alto rendimiento, considere la posibilidad de usar <xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType>.  
  
 [!code-csharp[CDS_SpinWait#05](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait.cs#05)]
 [!code-vb[CDS_SpinWait#05](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/cds_spinwait1.vb#05)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.Thread.SpinWait%2A>
- [Objetos y características de subprocesos](threading-objects-and-features.md)
