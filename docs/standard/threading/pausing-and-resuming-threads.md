---
title: Pausar y reanudar subprocesos
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resuming threads
- threading [.NET Framework], pausing
- pausing threads
ms.assetid: 9fce4859-a19d-4506-b082-7dd0792688ca
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9c2d58576098c83af110f2a713a0a8562e23aec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589128"
---
# <a name="pausing-and-resuming-threads"></a>Pausar y reanudar subprocesos
Las maneras más habituales de sincronizar las actividades de los subprocesos son bloquear y liberar subprocesos, o bloquear objetos o regiones de código. Para más información sobre estos bloqueos y mecanismos de bloque, consulte [Información general sobre los primitivos de sincronización](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 También puede hacer que los subprocesos se pongan en modo de suspensión. Cuando los subprocesos se bloquean o se ponen en modo de suspensión, puede usar una <xref:System.Threading.ThreadInterruptedException> para interrumpir sus estados de espera.  
  
## <a name="the-threadsleep-method"></a>Método Thread.Sleep  
 Al llamar al método <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>, el subproceso actual se bloquea inmediatamente durante el número de milisegundos o el intervalo de tiempo que pase al método, y el resto de su intervalo de tiempo se dedica a otro subproceso. Una vez que transcurre ese intervalo, el subproceso en suspensión vuelve a ejecutarse.  
  
 Un subproceso no puede llamar a <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> en otro subproceso.  <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> es un método estático que siempre hace que el subproceso actual entre en modo de suspensión.  
  
 Al llamar a <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> con un valor de <xref:System.Threading.Timeout.Infinite?displayProperty=nameWithType>, un subproceso entra en modo de suspensión hasta que lo interrumpe otro subproceso que llama al método <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> en el subproceso suspendido o hasta que una llamada al método <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> lo termina.  En el ejemplo siguiente se muestran ambos métodos para interrumpir un subproceso en suspensión.  
  
 [!code-csharp[Conceptual.Threading.Resuming#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Threading.Resuming/cs/Sleep1.cs#1)]
 [!code-vb[Conceptual.Threading.Resuming#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Threading.Resuming/vb/Sleep1.vb#1)]  
  
## <a name="interrupting-threads"></a>Interrumpir subprocesos  
 Puede interrumpir un subproceso en espera llamando al método <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> en el subproceso bloqueado para generar <xref:System.Threading.ThreadInterruptedException>, que saca al subproceso de la llamada de bloqueo. El subproceso debe detectar la <xref:System.Threading.ThreadInterruptedException> y hacer lo que sea necesario para seguir trabajando. Si el subproceso pasa por alto la excepción, el tiempo de ejecución detecta la excepción y detiene el subproceso.  
  
> [!NOTE]
>  Si el subproceso de destino no está bloqueado cuando se llama a <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>, el subproceso no se interrumpe hasta que se bloquea. Si el subproceso nunca se bloquea, puede finalizar sin ser interrumpido.  
  
 Si una espera es administrada, tanto <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> como <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> activan el subproceso inmediatamente. Si una espera es de tipo no administrado (por ejemplo, una llamada de invocación de plataforma a la función [WaitForSingleObject](https://msdn.microsoft.com/library/windows/desktop/ms687032\(v=vs.85\).aspx) de Win32), ni <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> ni <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> pueden tomar el control del subproceso hasta que este vuelva o llame a código administrado. En código administrado, el comportamiento es el siguiente:  
  
-   <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> activa un subproceso de cualquier tipo de espera que pueda haber y hace que se genere una <xref:System.Threading.ThreadInterruptedException> en el subproceso de destino.  
  
-   <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> activa un subproceso de cualquier tipo de espera que pueda haber y hace que se genere <xref:System.Threading.ThreadAbortException> en el subproceso. Para detalles, consulte [Destrucción de subprocesos](../../../docs/standard/threading/destroying-threads.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadInterruptedException>  
 <xref:System.Threading.ThreadAbortException>  
 [Subprocesamiento](../../../docs/standard/threading/index.md)  
 [Usar subprocesos y subprocesamiento](../../../docs/standard/threading/using-threads-and-threading.md)  
 [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md) (Introducción a los primitivos de sincronización)
