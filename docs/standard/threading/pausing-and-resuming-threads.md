---
title: Pausar y reanudar subprocesos
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
helpviewer_keywords:
- resuming threads
- threading [.NET Framework], pausing
- pausing threads
ms.assetid: 9fce4859-a19d-4506-b082-7dd0792688ca
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b146987d2491f044e1f5794eba17d02d8f5e478c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="pausing-and-resuming-threads"></a>Pausar y reanudar subprocesos
Las maneras más habituales de sincronizar las actividades de los subprocesos son bloquear y liberar subprocesos, o bloquear objetos o regiones de código. Para más información sobre estos bloqueos y mecanismos de bloque, consulte [Información general sobre los primitivos de sincronización](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 También puede hacer que los subprocesos se pongan en modo de suspensión. Cuando los subprocesos se bloquean o se ponen en modo de suspensión, puede usar una <xref:System.Threading.ThreadInterruptedException> para interrumpir sus estados de espera.  
  
## <a name="the-threadsleep-method"></a>Método Thread.Sleep  
 Llamar a la <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> método hace que el subproceso actual se bloquea inmediatamente durante el número de milisegundos o el intervalo de tiempo que se pasan al método y se produce el resto de su porción de tiempo a otro subproceso. Una vez que transcurre ese intervalo, el subproceso en suspensión vuelve a ejecutarse.  
  
 Un subproceso no puede llamar a <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> en otro subproceso.  <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>es un método estático que siempre hace que el subproceso actual en modo de suspensión.  
  
 Al llamar a <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> con un valor de <xref:System.Threading.Timeout.Infinite?displayProperty=nameWithType> hace que un subproceso en modo de suspensión hasta que lo interrumpe otro subproceso que llama el <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> método en el subproceso inactivo, o hasta que se termina por una llamada a su <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> método.  En el ejemplo siguiente se muestran ambos métodos para interrumpir un subproceso en suspensión.  
  
 [!code-csharp[Conceptual.Threading.Resuming#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Threading.Resuming/cs/Sleep1.cs#1)]
 [!code-vb[Conceptual.Threading.Resuming#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Threading.Resuming/vb/Sleep1.vb#1)]  
  
## <a name="interrupting-threads"></a>Interrumpir subprocesos  
 Puede interrumpir un subproceso en espera llamando a la <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> método en el subproceso bloqueado para producir un <xref:System.Threading.ThreadInterruptedException>, que saca al subproceso de la llamada de bloqueo. El subproceso debe detectar la <xref:System.Threading.ThreadInterruptedException> y hacer lo que sea necesario para seguir trabajando. Si el subproceso pasa por alto la excepción, el tiempo de ejecución detecta la excepción y detiene el subproceso.  
  
> [!NOTE]
>  Si el subproceso de destino no está bloqueado cuando se llama a <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>, el subproceso no se interrumpe hasta que se bloquea. Si el subproceso nunca se bloquea, puede finalizar sin ser interrumpido.  
  
 Si una espera es administrada, tanto <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> como <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> activan el subproceso inmediatamente. Si una espera es de tipo no administrado (por ejemplo, una plataforma de llamada de invocación a Win32 [WaitForSingleObject](https://msdn.microsoft.com/library/windows/desktop/ms687032\(v=vs.85\).aspx) función), ni <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> ni <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> puede tomar el control del subproceso hasta que este vuelva o llame a código administrado. En código administrado, el comportamiento es el siguiente:  
  
-   <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> activa un subproceso de cualquier tipo de espera que pueda haber y hace que se genere una <xref:System.Threading.ThreadInterruptedException> en el subproceso de destino.  
  
-   <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>activa un subproceso de cualquier tipo de espera pueda haber y hace un <xref:System.Threading.ThreadAbortException> que se produzca en el subproceso. Para detalles, consulte [Destrucción de subprocesos](../../../docs/standard/threading/destroying-threads.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadInterruptedException>  
 <xref:System.Threading.ThreadAbortException>  
 [Subprocesamiento](../../../docs/standard/threading/index.md)  
 [Usar subprocesos y subprocesamiento](../../../docs/standard/threading/using-threads-and-threading.md)  
 [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md) (Introducción a los primitivos de sincronización)
