---
title: Estados de subprocesos administrados
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], states
ms.assetid: 63890d5e-6025-4a7c-aaf0-d8bfd54b455f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a55409cd2c3bed2bc09db10622de1cceab934112
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2018
ms.locfileid: "47235288"
---
# <a name="managed-thread-states"></a>Estados de subprocesos administrados
La propiedad <xref:System.Threading.Thread.ThreadState%2A?displayProperty=nameWithType> proporciona una máscara de bits que indica el estado del subproceso actual. Un subproceso está siempre en al menos uno de los estados posibles en la enumeración <xref:System.Threading.ThreadState> y puede estar en varios estados al mismo tiempo.  
  
> [!IMPORTANT]
>  El estado de los subprocesos solo es de interés en algunos escenarios de depuración. El código nunca debe usar el estado de los subprocesos para sincronizar las actividades de los subprocesos.  
  
 Cuando se crea un subproceso administrado, este se encuentra en el estado <xref:System.Threading.ThreadState.Unstarted> . El subproceso permanece en el estado <xref:System.Threading.ThreadState.Unstarted> hasta que se cambia al estado iniciado por el sistema operativo. Llamar a <xref:System.Threading.Thread.Start%2A> permite que el sistema operativo sepa que se puede iniciar el subproceso; no cambia el estado del subproceso.  
  
 Los subprocesos no administrados que entran en el entorno administrado ya están en el estado iniciado. Una vez que un subproceso está en estado iniciado, varias acciones pueden provocar que los estados cambien. En la tabla siguiente se enumeran las acciones que provocan un cambio de estado, junto con el nuevo estado correspondiente.  
  
|Acción|Nuevo estado resultante|  
|------------|-------------------------|  
|Se llama al constructor de la clase <xref:System.Threading.Thread> .|<xref:System.Threading.ThreadState.Unstarted>|  
|Otro subproceso llama a <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>.|<xref:System.Threading.ThreadState.Unstarted>|  
|El subproceso responde a <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> y empieza a ejecutarse.|<xref:System.Threading.ThreadState.Running>|  
|El subproceso llama a <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>.|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|El subproceso llama a <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> en otro objeto.|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|El subproceso llama a <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> en otro subproceso.|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|Otro subproceso llama a <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>.|<xref:System.Threading.ThreadState.SuspendRequested>|  
|El subproceso responde a una solicitud <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>.|<xref:System.Threading.ThreadState.Suspended>|  
|Otro subproceso llama a <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType>.|<xref:System.Threading.ThreadState.Running>|  
|Otro subproceso llama a <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.|<xref:System.Threading.ThreadState.AbortRequested>|  
|El subproceso responde a <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.|<xref:System.Threading.ThreadState.Aborted>y después <xref:System.Threading.ThreadState.Stopped>|  
  
 Dado que el estado <xref:System.Threading.ThreadState.Running> tiene un valor de 0, no es posible realizar una prueba de bits para descubrirlo. En su lugar, se puede usar la siguiente prueba (en seudocódigo):  
  
```  
if ((state & (Unstarted | Stopped)) == 0)   // implies Running     
```  
  
 A menudo, los subprocesos están en más de un estado en un momento dado. Por ejemplo, si un subproceso se bloquea en una llamada de <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> y otro subproceso llama a <xref:System.Threading.Thread.Abort%2A> en el mismo subproceso, el subproceso estará en ambos estados <xref:System.Threading.ThreadState.WaitSleepJoin> y <xref:System.Threading.ThreadState.AbortRequested> al mismo tiempo. En ese caso, en cuanto el subproceso vuelva de la llamada a <xref:System.Threading.Monitor.Wait%2A> o se interrumpa, recibirá una excepción <xref:System.Threading.ThreadAbortException>.  
  
 Una vez que un subproceso abandona el estado <xref:System.Threading.ThreadState.Unstarted> como resultado de una llamada a <xref:System.Threading.Thread.Start%2A>, nunca puede volver al estado <xref:System.Threading.ThreadState.Unstarted> . Un subproceso nunca puede abandonar el estado <xref:System.Threading.ThreadState.Stopped> .  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.ThreadAbortException>  
- <xref:System.Threading.Thread>  
- <xref:System.Threading.ThreadState>  
- [Subprocesamiento](../../../docs/standard/threading/index.md)
