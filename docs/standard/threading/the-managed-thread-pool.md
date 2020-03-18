---
title: Grupo de subprocesos administrado
description: Información sobre el grupo de subprocesos de .NET que proporciona subprocesos de trabajo en segundo plano
ms.date: 08/02/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- thread pooling [.NET]
- thread pools [.NET]
- threading [.NET], thread pool
- threading [.NET], pooling
ms.assetid: 2be05b06-a42e-4c9d-a739-96c21d673927
ms.openlocfilehash: 2671ce7c9721b15de8a3805da27040e973a62804
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79398560"
---
# <a name="the-managed-thread-pool"></a>Grupo de subprocesos administrado

La clase <xref:System.Threading.ThreadPool?displayProperty=nameWithType> proporciona a la aplicación un grupo de subprocesos de trabajo administrados por el sistema, que le permite concentrarse en las tareas de la aplicación en lugar de en la administración de los subprocesos. Si tiene tareas cortas que requieran procesamiento en segundo plano, el grupo de subprocesos administrados permite aprovechar fácilmente las ventajas de varios subprocesos. El uso del grupo de subprocesos es notablemente más sencilla en .NET Framework 4 y versiones posteriores, ya que puede crear objetos <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601> que realizan tareas asincrónicas en los subprocesos del grupo de subprocesos.  
  
.NET usa los subprocesos del grupo de subprocesos para muchos fines, incluidas operaciones de [biblioteca TPL](../parallel-programming/task-parallel-library-tpl.md), la finalización de E/S asincrónica, las devoluciones de llamada del [temporizador](timers.md), las operaciones de espera registradas, las llamadas de métodos asincrónicos mediante delegados y las conexiones de socket <xref:System.Net?displayProperty=nameWithType>.  

## <a name="thread-pool-characteristics"></a>Características del grupo de subprocesos

Los subprocesos del grupo de subprocesos son subprocesos [en segundo plano](foreground-and-background-threads.md). Cada subproceso utiliza el tamaño de pila predeterminado, se ejecuta con la prioridad predeterminada y está en el contenedor multiproceso. Una vez que un subproceso del grupo de subprocesos finaliza su tarea, se devuelve a una cola de subprocesos en espera. Desde este momento se puede reutilizar. Esta reutilización permite que las aplicaciones eviten el costo que significa crear un nuevo subproceso para cada tarea.
  
Hay solo un grupo de subprocesos por cada proceso.  
  
### <a name="exceptions-in-thread-pool-threads"></a>Excepciones en los subprocesos del grupo de subprocesos

Las excepciones no controladas en los subprocesos del grupo de subprocesos finalizan el proceso. Hay tres excepciones de esta regla:  
  
- Se genera un <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> en un subproceso del grupo de subprocesos, porque se llamó a <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.  
- Se genera un <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> en un subproceso del grupo de subprocesos, porque se está descargando el dominio de aplicación.  
- Common Language Runtime o un proceso de host finaliza el subproceso.  
  
Para más información, consulte [Excepciones en subprocesos administrados](exceptions-in-managed-threads.md).  
  
### <a name="maximum-number-of-thread-pool-threads"></a>Número máximo de subprocesos del grupo de subprocesos

El número de operaciones que se pueden poner en cola en el grupo de subprocesos está limitado únicamente por la memoria disponible. Sin embargo, el grupo de subprocesos limita el número de subprocesos que pueden estar activos en el proceso de forma simultánea. Si todos los subprocesos del grupo de subprocesos están ocupados, los elementos de trabajo adicionales se pondrán en cola hasta que estén disponibles subprocesos para ejecutarlos. A partir de .NET Framework 4, el tamaño predeterminado del grupo de subprocesos de un proceso depende de varios factores, como el tamaño del espacio de direcciones virtuales. Un proceso puede llamar al método <xref:System.Threading.ThreadPool.GetMaxThreads%2A?displayProperty=nameWithType> para determinar el número de subprocesos.  
  
El número máximo de subprocesos se puede controlar con los métodos <xref:System.Threading.ThreadPool.GetMaxThreads%2A?displayProperty=nameWithType> y <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>.  

> [!NOTE]
> El código que hospeda Common Language Runtime puede establecer el tamaño con el método [`ICorThreadpool::CorSetMaxThreads`](../../framework/unmanaged-api/hosting/icorthreadpool-corsetmaxthreads-method.md).  
  
### <a name="thread-pool-minimums"></a>Mínimos del grupo de subprocesos

El grupo de subprocesos ofrece nuevos subprocesos de trabajo o subprocesos de finalización de E/S a petición hasta que llega a un mínimo especificado para cada categoría. Puede utilizar el método <xref:System.Threading.ThreadPool.GetMinThreads%2A?displayProperty=nameWithType> para obtener estos valores mínimos.  
  
> [!NOTE]
> Cuando la demanda es baja, el número real de subprocesos del grupo de subprocesos puede descender por debajo de los valores mínimos.  
  
Cuando se alcanza el mínimo, el grupo de subprocesos puede crear subprocesos adicionales o esperar hasta que se completen algunas tareas. A partir de .NET Framework 4, el grupo de subprocesos crea y destruye subprocesos de trabajo para optimizar el rendimiento, definido como el número de tareas que se completan por unidad de tiempo. Si hay demasiados pocos subprocesos, puede que los recursos disponibles no se usen de manera óptima, mientras que si hay demasiados subprocesos, puede aumentar la contención de recursos.  
  
> [!CAUTION]
> Puede utilizar el método <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> para aumentar el número mínimo de subprocesos inactivos. Sin embargo, aumentar innecesariamente estos valores puede causar problemas de rendimiento. Si se inician demasiadas tareas al mismo tiempo, puede que todas ellas parezcan funcionar con lentitud. En la mayoría de los casos, el grupo de subprocesos funciona mejor con su propio algoritmo de asignación de subprocesos.  

## <a name="using-the-thread-pool"></a>Uso del grupo de subprocesos

A partir de .NET Framework 4, la manera más fácil de usar el grupo de subprocesos es utilizar la [Biblioteca TPL](../parallel-programming/task-parallel-library-tpl.md). De forma predeterminada, los tipos de biblioteca TPL, como <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601>, usan subprocesos del grupo de subprocesos para ejecutar tareas.

También puede utilizar el grupo de subprocesos llamando a <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> desde código administrado (o [`ICorThreadpool::CorQueueUserWorkItem`](../../framework/unmanaged-api/hosting/icorthreadpool-corqueueuserworkitem-method.md) desde código no administrado) y pasando un delegado <xref:System.Threading.WaitCallback?displayProperty=nameWithType> que represente al método que realiza la tarea.

Otra forma de usar el grupo de subprocesos es poner en cola los elementos de trabajo que están relacionados con una operación de espera mediante el método <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> y pasar un <xref:System.Threading.WaitHandle?displayProperty=nameWithType> que, cuando se señala o cuando se agota el tiempo de espera, llame al método representado por el delegado <xref:System.Threading.WaitOrTimerCallback?displayProperty=nameWithType>. Los subprocesos del grupo de subprocesos se usan para invocar métodos de devolución de llamada.  

Para ver los ejemplos, consulte las páginas de la API a la que se hace referencia.
  
## <a name="skipping-security-checks"></a>Omisión de comprobaciones de seguridad

El grupo de subprocesos también proporciona los métodos <xref:System.Threading.ThreadPool.UnsafeQueueUserWorkItem%2A?displayProperty=nameWithType> y <xref:System.Threading.ThreadPool.UnsafeRegisterWaitForSingleObject%2A?displayProperty=nameWithType>. Utilice estos métodos solamente cuando tenga la seguridad de que la pila del llamador es irrelevante para las comprobaciones de seguridad que se realizan durante la ejecución de la tarea en cola. <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> y <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> capturan la pila del llamador, que se combina en la pila del subproceso del grupo de subprocesos cuando el subproceso empieza a ejecutar una tarea. Si es necesaria una comprobación de seguridad, debe comprobarse toda la pila. La comprobación proporciona seguridad, pero también supone un coste para el rendimiento.  

## <a name="when-not-to-use-thread-pool-threads"></a>Cuándo no usar subprocesos del grupo de subprocesos

Hay varios escenarios en los que es adecuado crear y administrar sus propios subprocesos en lugar de utilizar subprocesos del grupo de subprocesos:  
  
- Necesita un subproceso en primer plano.  
- Necesita que un subproceso tenga una prioridad determinada.  
- Tiene tareas que hacen que el subproceso se bloquee durante largos períodos de tiempo. El grupo de subprocesos tiene un número máximo de subprocesos, por lo que si hay un gran número de subprocesos del grupo de subprocesos bloqueados, esto puede impedir que se inicien las tareas.  
- Debe colocar los subprocesos en un contenedor uniproceso. Todos los subprocesos <xref:System.Threading.ThreadPool> están en el contenedor multiproceso.  
- Debe tener una identidad estable asociada al subproceso o dedicar un subproceso a una tarea.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>
- [Biblioteca TPL](../parallel-programming/task-parallel-library-tpl.md)
- [How to: Return a Value from a Task](../parallel-programming/how-to-return-a-value-from-a-task.md) (Devolver un valor a partir de una tarea)
- [Objetos y características de subprocesos](threading-objects-and-features.md)
- [Subprocesos y subprocesamiento](threads-and-threading.md)
- [Asynchronous File I/O](../io/asynchronous-file-i-o.md)
- [Timers](timers.md) (Temporizadores)
