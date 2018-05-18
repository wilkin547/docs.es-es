---
title: Grupo de subprocesos administrados
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- thread pooling [.NET Framework]
- thread pools [.NET Framework]
- threading [.NET Framework], thread pool
- threading [.NET Framework], pooling
ms.assetid: 2be05b06-a42e-4c9d-a739-96c21d673927
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3894229ff5561e50d42a36f576a89ee7bf01c067
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="the-managed-thread-pool"></a>Grupo de subprocesos administrados
La clase <xref:System.Threading.ThreadPool> proporciona a la aplicación un grupo de subprocesos de trabajo administrados por el sistema, que le permite concentrarse en las tareas de la aplicación en lugar de en la administración de los subprocesos. Si tiene tareas cortas que requieran procesamiento en segundo plano, el grupo de subprocesos administrados permite aprovechar fácilmente las ventajas de varios subprocesos. Por ejemplo, a partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], puede crear objetos <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601>, que realizan tareas asincrónicas en los subprocesos del grupo de subprocesos.  
  
> [!NOTE]
>  A partir de [!INCLUDE[net_v20SP1_long](../../../includes/net-v20sp1-long-md.md)], mejora considerablemente el rendimiento del grupo de subprocesos en tres áreas clave que se identificaron como cuellos de botella en las versiones anteriores de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]: poner tareas en cola, enviar subprocesos del grupo de subprocesos y enviar subprocesos de finalización de E/S. Para utilizar esta funcionalidad, la aplicación debe utilizar [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)] o posterior como destino.  
  
 Para las tareas en segundo plano que interactúan con la interfaz de usuario, la versión 2.0 de .NET Framework también proporciona la clase <xref:System.ComponentModel.BackgroundWorker>, que se comunica mediante eventos generados en el subproceso de la interfaz de usuario.  
  
 .NET Framework utiliza los subprocesos del grupo de subprocesos para muchos fines, incluida la finalización de E/S asincrónica, las devoluciones de llamada del temporizador, las operaciones de espera registradas, las llamadas de métodos asincrónicos mediante delegados y las conexiones de socket <xref:System.Net>.  
  
## <a name="when-not-to-use-thread-pool-threads"></a>Cuándo no usar subprocesos del grupo de subprocesos  
 Hay varios escenarios en los que es adecuado crear y administrar sus propios subprocesos en lugar de utilizar subprocesos del grupo de subprocesos:  
  
-   Necesita un subproceso en primer plano.  
  
-   Necesita que un subproceso tenga una prioridad determinada.  
  
-   Tiene tareas que hacen que el subproceso se bloquee durante largos períodos de tiempo. El grupo de subprocesos tiene un número máximo de subprocesos, por lo que si hay un gran número de subprocesos del grupo de subprocesos bloqueados, esto puede impedir que se inicien las tareas.  
  
-   Debe colocar los subprocesos en un contenedor uniproceso. Todos los subprocesos <xref:System.Threading.ThreadPool> están en el contenedor multiproceso.  
  
-   Debe tener una identidad estable asociada al subproceso o dedicar un subproceso a una tarea.  
  
## <a name="thread-pool-characteristics"></a>Características del grupo de subprocesos  
 Los subprocesos del grupo de subprocesos son subprocesos en segundo plano. Consulte [Subprocesos de primer y segundo plano](../../../docs/standard/threading/foreground-and-background-threads.md). Cada subproceso utiliza el tamaño de pila predeterminado, se ejecuta con la prioridad predeterminada y está en el contenedor multiproceso.  
  
 Hay solo un grupo de subprocesos por cada proceso.  
  
### <a name="exceptions-in-thread-pool-threads"></a>Excepciones en los subprocesos del grupo de subprocesos  
 Las excepciones no controladas en los subprocesos del grupo de subprocesos finalizan el proceso. Hay tres excepciones de esta regla:  
  
-   Se genera un <xref:System.Threading.ThreadAbortException> en un subproceso del grupo de subprocesos, porque se llamó a <xref:System.Threading.Thread.Abort%2A>.  
  
-   Se genera un <xref:System.AppDomainUnloadedException> en un subproceso del grupo de subprocesos, porque se está descargando el dominio de aplicación.  
  
-   Common Language Runtime o un proceso de host finaliza el subproceso.  
  
 Para más información, consulte [Excepciones en subprocesos administrados](../../../docs/standard/threading/exceptions-in-managed-threads.md).  
  
> [!NOTE]
>  En las versiones 1.0 y 1.1 de .NET Framework, Common Language Runtime intercepta silenciosamente las excepciones no controladas en los subprocesos del grupo de subprocesos. Esto puede dañar el estado de la aplicación y puede acabar haciendo que las aplicaciones no respondan, lo cual puede ser muy difícil de depurar.  
  
### <a name="maximum-number-of-thread-pool-threads"></a>Número máximo de subprocesos del grupo de subprocesos  
 El número de operaciones que pueden ponerse en la cola del grupo de subprocesos está limitado solamente por la memoria disponible. Sin embargo, el grupo de subprocesos limita el número de subprocesos que pueden estar activos en el proceso de forma simultánea. A partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], el tamaño predeterminado del grupo de subprocesos de un proceso depende de varios factores, como el tamaño del espacio de direcciones virtuales. Un proceso puede llamar al método <xref:System.Threading.ThreadPool.GetMaxThreads%2A> para determinar el número de subprocesos.  
  
 El número máximo de subprocesos se puede controlar con los métodos <xref:System.Threading.ThreadPool.GetMaxThreads%2A> y <xref:System.Threading.ThreadPool.SetMaxThreads%2A>.  
  
> [!NOTE]
>  En las versiones 1.0 y 1.1 de .NET Framework, el tamaño del grupo de subprocesos no se puede establecer desde el código administrado. El código que hospeda Common Language Runtime puede establecer el tamaño con `CorSetMaxThreads`, definido en mscoree.h.  
  
### <a name="thread-pool-minimums"></a>Mínimos del grupo de subprocesos  
 El grupo de subprocesos ofrece nuevos subprocesos de trabajo o subprocesos de finalización de E/S a petición hasta que llega a un mínimo especificado para cada categoría. Puede utilizar el método <xref:System.Threading.ThreadPool.GetMinThreads%2A> para obtener estos valores mínimos.  
  
> [!NOTE]
>  Cuando la demanda es baja, el número real de subprocesos del grupo de subprocesos puede descender por debajo de los valores mínimos.  
  
 Cuando se alcanza el mínimo, el grupo de subprocesos puede crear subprocesos adicionales o esperar hasta que se completen algunas tareas. A partir de [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], el grupo de subprocesos crea y destruye subprocesos de trabajo para optimizar el rendimiento, definido como el número de tareas que se completan por unidad de tiempo. Si hay demasiados pocos subprocesos, puede que los recursos disponibles no se usen de manera óptima, mientras que si hay demasiados subprocesos, puede aumentar la contención de recursos.  
  
> [!CAUTION]
>  Puede utilizar el método <xref:System.Threading.ThreadPool.SetMinThreads%2A> para aumentar el número mínimo de subprocesos inactivos. Sin embargo, aumentar innecesariamente estos valores puede causar problemas de rendimiento. Si se inician demasiadas tareas al mismo tiempo, puede que todas ellas parezcan funcionar con lentitud. En la mayoría de los casos, el grupo de subprocesos funciona mejor con su propio algoritmo de asignación de subprocesos.  
  
## <a name="skipping-security-checks"></a>Omisión de comprobaciones de seguridad  
 El grupo de subprocesos también proporciona los métodos <xref:System.Threading.ThreadPool.UnsafeQueueUserWorkItem%2A?displayProperty=nameWithType> y <xref:System.Threading.ThreadPool.UnsafeRegisterWaitForSingleObject%2A?displayProperty=nameWithType>. Utilice estos métodos solamente cuando tenga la seguridad de que la pila del llamador es irrelevante para las comprobaciones de seguridad que se realizan durante la ejecución de la tarea en cola. <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> y <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> capturan la pila del llamador, que se combina en la pila del subproceso del grupo de subprocesos cuando el subproceso empieza a ejecutar una tarea. Si es necesaria una comprobación de seguridad, debe comprobarse toda la pila. La comprobación proporciona seguridad, pero también supone un coste para el rendimiento.  
  
## <a name="using-the-thread-pool"></a>Uso del grupo de subprocesos  
 A partir de [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], la manera más fácil de usar el grupo de subprocesos es utilizar la [Biblioteca TPL](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md). De forma predeterminada, los tipos de biblioteca de procesamiento paralelo, como <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601>, utilizan subprocesos del grupo de subprocesos para ejecutar tareas. También puede utilizar el grupo de subprocesos llamando a <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> desde código administrado (o `CorQueueUserWorkItem` desde código no administrado) y pasando un delegado <xref:System.Threading.WaitCallback> que represente al método que realiza la tarea. Otra forma de usar el grupo de subprocesos es poner en cola los elementos de trabajo que están relacionados con una operación de espera mediante el método <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> y pasar un <xref:System.Threading.WaitHandle> que, cuando se señala o cuando se agota el tiempo de espera, llame al método representado por el delegado <xref:System.Threading.WaitOrTimerCallback>. Los subprocesos del grupo de subprocesos se usan para invocar métodos de devolución de llamada.  
  
## <a name="threadpool-examples"></a>Ejemplos de ThreadPool  
 Los ejemplos de código de esta sección muestran el grupo de subprocesos con la clase <xref:System.Threading.Tasks.Task>, el método <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> y el método <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType>.  
  
-   [Ejecutar tareas asincrónicas con la biblioteca TPL](#TaskParallelLibrary)  
  
-   [Ejecutar código de forma asincrónica con QueueUserWorkItem](#ExecuteCodeWithQUWI)  
  
-   [Proporcionar datos de tareas para QueueUserWorkItem](#TaskDataForQUWI)  
  
-   [Uso de RegisterWaitForSingleObject](#RegisterWaitForSingleObject)  
  
<a name="TaskParallelLibrary"></a>   
### <a name="executing-asynchronous-tasks-with-the-task-parallel-library"></a>Ejecutar tareas asincrónicas con la biblioteca TPL  
 En el siguiente ejemplo, se muestra cómo crear y usar un objeto <xref:System.Threading.Tasks.Task> para llamar al método <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>. Para ver un ejemplo que utiliza la clase <xref:System.Threading.Tasks.Task%601> con el fin de devolver un valor de una tarea asincrónica, consulte [Cómo: Devolver un valor de una tarea](../../../docs/standard/parallel-programming/how-to-return-a-value-from-a-task.md).  
  
 [!code-csharp[System.Threading.Tasks.Task#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.task/cs/startnew.cs#01)]
 [!code-vb[System.Threading.Tasks.Task#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.task/vb/startnew.vb#01)]  
  
<a name="ExecuteCodeWithQUWI"></a>   
### <a name="executing-code-asynchronously-with-queueuserworkitem"></a>Ejecutar código de forma asincrónica con QueueUserWorkItem  
 En el ejemplo siguiente, se pone en cola una tarea muy sencilla, representada por el método `ThreadProc`, con el método <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>.  
  
 [!code-cpp[Conceptual.ThreadPool#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.threadpool/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.ThreadPool#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.threadpool/cs/source1.cs#1)]
 [!code-vb[Conceptual.ThreadPool#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.threadpool/vb/source1.vb#1)]  
  
<a name="TaskDataForQUWI"></a>   
### <a name="supplying-task-data-for-queueuserworkitem"></a>Proporcionar datos de tareas para QueueUserWorkItem  
 El siguiente ejemplo de código utiliza el método <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> para poner en cola una tarea y proporcionar los datos de la tarea.  
  
 [!code-cpp[Conceptual.ThreadPool#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.threadpool/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.ThreadPool#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.threadpool/cs/source2.cs#2)]
 [!code-vb[Conceptual.ThreadPool#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.threadpool/vb/source2.vb#2)]  
  
<a name="RegisterWaitForSingleObject"></a>   
### <a name="using-registerwaitforsingleobject"></a>Uso de RegisterWaitForSingleObject  
 En el ejemplo siguiente se muestran diversas características de subprocesamiento:  
  
-   Poner en cola una tarea para que la ejecuten <xref:System.Threading.ThreadPool> subprocesos, con el método <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A>.  
  
-   Señalar una tarea para su ejecución, con <xref:System.Threading.AutoResetEvent>. Vea [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md).  
  
-   Controlar los tiempos de espera y las señales con un delegado <xref:System.Threading.WaitOrTimerCallback>.  
  
-   Cancelar una tarea en cola con <xref:System.Threading.RegisteredWaitHandle>.  
  
 [!code-cpp[Conceptual.ThreadPool#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.threadpool/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.ThreadPool#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.threadpool/cs/source3.cs#3)]
 [!code-vb[Conceptual.ThreadPool#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.threadpool/vb/source3.vb#3)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.ThreadPool>  
 <xref:System.Threading.Tasks.Task>  
 <xref:System.Threading.Tasks.Task%601>  
 [Biblioteca TPL](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 [Biblioteca TPL](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 [Devolver un valor a partir de una tarea](../../../docs/standard/parallel-programming/how-to-return-a-value-from-a-task.md)  
 [Objetos y características de subprocesos](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Subprocesos y subprocesamiento](../../../docs/standard/threading/threads-and-threading.md)  
 [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md) (E/S de archivos asincrónica)  
 [Timers](../../../docs/standard/threading/timers.md) (Temporizadores)
