---
title: Barrier
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, Barrier
ms.assetid: 613a8bc7-6a28-4795-bd6c-1abd9050478f
ms.openlocfilehash: 4eab74ef07ac56a4d3ff65e67bb9fbd45dbfc9bc
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819947"
---
# <a name="barrier"></a>Barrier

<xref:System.Threading.Barrier?displayProperty=nameWithType> es un primitivo de sincronización que permite que varios subprocesos (conocidos como *participantes*) trabajen simultáneamente en un algoritmo por fases. Cada participante se ejecuta hasta que alcanza el punto de barrera en el código. La barrera representa el final de una fase de trabajo. Cuando un participante alcanza la barrera, se bloquea hasta que todos los participantes alcancen la misma barrera. Cuando todos los participantes alcanzan la barrera, opcionalmente puede invocar una acción posterior a la fase. Esta acción posterior a la fase puede usarse para realizar acciones con un solo subproceso mientras todos los demás subprocesos siguen bloqueados. Una vez ejecutada la acción, se desbloquean todos los participantes.  
  
 El fragmento de código siguiente muestra un modelo de barrera básico.  
  
 [!code-csharp[CDS_Barrier#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#02)]
 [!code-vb[CDS_Barrier#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#02)]  
  
 Para obtener un ejemplo completo, vea [Sincronizar operaciones simultáneas con una clase Barrier](how-to-synchronize-concurrent-operations-with-a-barrier.md).  
  
## <a name="adding-and-removing-participants"></a>Agregar y quitar participantes

 Cuando cree una instancia de <xref:System.Threading.Barrier>, especifique el número de participantes. También puede agregar o quitar participantes dinámicamente en cualquier momento. Por ejemplo, si un participante resuelve su parte del problema, puede almacenar el resultado, detener la ejecución de ese subproceso y llamar a <xref:System.Threading.Barrier.RemoveParticipant%2A?displayProperty=nameWithType> para reducir el número de participantes en la barrera. Cuando se agrega un participante mediante una llamada a <xref:System.Threading.Barrier.AddParticipant%2A?displayProperty=nameWithType>, el valor devuelto especifica el número de fase actual, que puede ser útil para inicializar el trabajo del nuevo participante.  
  
## <a name="broken-barriers"></a>Barreras rotas

 Si un participante no consigue alcanzar la barrera, pueden producirse interbloqueos. Para evitar estos interbloqueos, use las sobrecargas del método <xref:System.Threading.Barrier.SignalAndWait%2A?displayProperty=nameWithType> para especificar un período de tiempo de espera y un token de cancelación. Estas sobrecargas devuelven un valor booleano que cada participante puede comprobar antes de continuar con la fase siguiente.  
  
## <a name="post-phase-exceptions"></a>Excepciones posteriores a la fase

 Si el delegado posterior a la fase produce una excepción, se encapsula en un objeto <xref:System.Threading.BarrierPostPhaseException> que después se propaga a todos los participantes.  
  
## <a name="barrier-versus-continuewhenall"></a>Barrier frente a ContinueWhenAll

 Las barreras resultan especialmente útiles cuando los subprocesos realizan varias fases en bucles. Si el código solo requiere una o dos fases de trabajo, piense en usar objetos <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> con cualquier tipo de unión implícita, incluidas:  
  
- <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>  
  
 Para más información, consulte [Chaining Tasks by Using Continuation Tasks](../parallel-programming/chaining-tasks-by-using-continuation-tasks.md) (Encadenar tareas mediante tareas de continuación).  
  
## <a name="see-also"></a>Vea también

- [Objetos y características de subprocesos](threading-objects-and-features.md)
- [Sincronizar operaciones simultáneas con una clase Barrier](how-to-synchronize-concurrent-operations-with-a-barrier.md)
