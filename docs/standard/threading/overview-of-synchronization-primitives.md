---
title: Información general sobre los primitivos de sincronización
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- synchronization, threads
- threading [.NET Framework],synchronizing threads
- managed threading
ms.assetid: b782bcb8-da6a-4c6a-805f-2eb46d504309
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5098eea86ee910baad57115419e147df02e41ed9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485539"
---
# <a name="overview-of-synchronization-primitives"></a>Información general sobre los primitivos de sincronización
<a name="top"></a> .NET Framework proporciona un intervalo de primitivas de sincronización para controlar las interacciones de subprocesos y evitar las condiciones de carrera. En líneas generales, estas pueden dividirse en tres categorías: operaciones de bloqueos, de señalización y de interbloqueos.  
  
 Las categorías no están bien organizadas ni claramente definidas: algunos mecanismos de sincronización tienen características de varias categorías; los eventos que liberan un solo subproceso de cada vez son funcionalmente como bloqueos; la liberación de cualquier bloqueo puede considerarse una señal; y las operaciones de interbloqueos pueden usarse para construir bloqueos. Sin embargo, las categorías siguen siendo útiles.  
  
 Es importante recordar que la sincronización de subprocesos es cooperativa. Si un solo subproceso omite un mecanismo de sincronización y accede directamente al recurso protegido, ese mecanismo de sincronización no puede ser eficaz.  
  
 Esta información general contiene las siguientes secciones:  
  
-   [Bloqueo](#locking)  
  
-   [Señalización](#signaling)  
  
-   [Tipos de sincronización ligeros](#lightweight_synchronization_types)  
  
-   [SpinWait](#spinwait)  
  
-   [Operaciones de bloqueo](#interlocked_operations)  
  
<a name="locking"></a>   
## <a name="locking"></a>Bloqueo  
 Los bloqueos proporcionan el control de un recurso a un subproceso a la vez o a un número especificado de subprocesos. Un subproceso que solicita un bloqueo exclusivo cuando el bloqueo está en uso se bloquea hasta que el bloqueo esté disponible.  
  
### <a name="exclusive-locks"></a>Bloqueos exclusivos  
 La forma más sencilla de bloqueo es la instrucción `lock` en C# y la instrucción `SyncLock` en Visual Basic, que controlan el acceso a un bloque de código. Con frecuencia, estos bloques se conocen como una sección crítica. La instrucción `lock` se implementa mediante los métodos <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> y <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType>, y usa un bloqueo `try…finally` para asegurarse de que se libere el bloqueo.  
  
 En general, la mejor forma de usar la clase <xref:System.Threading.Monitor> consiste en usar la instrucción `lock` o `SyncLock` para proteger pequeños bloques de código, sin abarcar más de un método. Aunque eficaz, la clase <xref:System.Threading.Monitor> es propensa a bloqueos huérfanos e interbloqueos.  
  
#### <a name="monitor-class"></a>Clase Monitor  
 La clase <xref:System.Threading.Monitor> proporciona funcionalidad adicional, que se puede usar junto con la instrucción `lock`:  
  
-   El método <xref:System.Threading.Monitor.TryEnter%2A> permite que un subproceso bloqueado en espera del recurso se interrumpa una vez transcurrido un intervalo especificado. Devuelve un valor booleano que indica si la operación se ha realizado correctamente o no, que se puede usar para detectar y evitar posibles interbloqueos.  
  
-   Un subproceso de una sección crítica llama al método <xref:System.Threading.Monitor.Wait%2A>. Interrumpe el control del recurso y se bloquea hasta que el recurso esté disponible de nuevo.  
  
-   Los métodos <xref:System.Threading.Monitor.Pulse%2A> y <xref:System.Threading.Monitor.PulseAll%2A> permiten que un subproceso que está a punto de liberar el bloqueo o de llamar a <xref:System.Threading.Monitor.Wait%2A> ponga uno o varios subprocesos en la cola de subprocesos listos, de modo que puedan adquirir el bloqueo.  
  
 Los tiempos de espera de las sobrecargas del método <xref:System.Threading.Monitor.Wait%2A> permiten a los subprocesos en espera situarse en la cola de subprocesos listos.  
  
 La clase <xref:System.Threading.Monitor> puede proporcionar el bloqueo en varios dominios de aplicación si el objeto usado para el bloqueo deriva de <xref:System.MarshalByRefObject>.  
  
 <xref:System.Threading.Monitor> tiene afinidad de subprocesos. Es decir, un subproceso que entró el monitor debe salir llamando a <xref:System.Threading.Monitor.Exit%2A> o <xref:System.Threading.Monitor.Wait%2A>.  
  
 La clase <xref:System.Threading.Monitor> no es instanciable. Sus métodos son estáticos (`Shared` en Visual Basic) y actúan sobre un objeto de bloqueo instanciable.  
  
 Para información conceptual, consulte [Monitores](https://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).  
  
#### <a name="mutex-class"></a>Mutex (Clase)  
 Los subprocesos solicitan <xref:System.Threading.Mutex> llamando a una sobrecarga de su método <xref:System.Threading.WaitHandle.WaitOne%2A>. Se proporcionan sobrecargas con tiempos de espera, para permitir que los subprocesos renuncien a la espera. A diferencia de la clase <xref:System.Threading.Monitor>, una exclusión mutua puede ser local o global. Las exclusiones mutuas globales, también denominadas exclusiones mutuas, son visibles en todo el sistema operativo y se pueden usar para sincronizar subprocesos en varios procesos o dominios de aplicación. Las exclusiones mutuas locales derivan de <xref:System.MarshalByRefObject> y se pueden usar en los límites del dominio de aplicación.  
  
 Además, <xref:System.Threading.Mutex> deriva de <xref:System.Threading.WaitHandle>, lo que significa que se puede usar con los mecanismos de señalización proporcionados por <xref:System.Threading.WaitHandle>, como los métodos <xref:System.Threading.WaitHandle.WaitAll%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A> y <xref:System.Threading.WaitHandle.SignalAndWait%2A>.  
  
 Al igual que <xref:System.Threading.Monitor>, <xref:System.Threading.Mutex> tiene afinidad de subprocesos. A diferencia de <xref:System.Threading.Monitor>, <xref:System.Threading.Mutex> es un objeto instanciable.  
  
 Para información conceptual, consulte [Exclusiones mutuas](../../../docs/standard/threading/mutexes.md).  
  
#### <a name="spinlock-class"></a>Clase SpinLock  
 A partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], puede usar la clase <xref:System.Threading.SpinLock> cuando la sobrecarga requerida por <xref:System.Threading.Monitor> degrade el rendimiento. Cuando <xref:System.Threading.SpinLock> encuentra una sección crítica bloqueada, simplemente gira en un bucle hasta que el bloqueo esté disponible. Si el bloqueo se mantiene durante un tiempo muy breve, el giro puede proporcionar un mejor rendimiento que el bloqueo. Sin embargo, si el bloqueo se mantiene durante más de unas decenas de ciclos, <xref:System.Threading.SpinLock> tiene el mismo rendimiento que <xref:System.Threading.Monitor>, pero usará más ciclos de CPU y, por lo tanto, puede degradar el rendimiento de otros subprocesos o procesos.  
  
### <a name="other-locks"></a>Otros bloqueos  
 No hace falta que los bloqueos sean exclusivos. A menudo resulta útil permitir que un número limitado de subprocesos tengan acceso simultáneo a un recurso. Los semáforos y los bloqueos de lector y escritor están diseñados para controlar este tipo de acceso a los recursos agrupados.  
  
#### <a name="readerwriterlock-class"></a>Clase ReaderWriterLock  
 La clase <xref:System.Threading.ReaderWriterLockSlim> está pensada para los casos en que un subproceso que cambia los datos (el escritor) debe tener acceso exclusivo a un recurso. Cuando el escritor no está activo, cualquier número de lectores puede acceder al recurso (por ejemplo, llamando al método <xref:System.Threading.ReaderWriterLockSlim.EnterReadLock%2A>). Cuando un subproceso solicita acceso exclusivo (por ejemplo, llamando al método <xref:System.Threading.ReaderWriterLockSlim.EnterWriteLock%2A>), las solicitudes posteriores del lector se bloquean hasta que todos los lectores existentes salgan del bloqueo y el escritor entre y salga del bloqueo.  
  
 <xref:System.Threading.ReaderWriterLockSlim> tiene afinidad de subprocesos.  
  
 Para información conceptual, consulte [Bloqueos de lector y escritor](../../../docs/standard/threading/reader-writer-locks.md).  
  
#### <a name="semaphore-class"></a>Semaphore (clase)  
 La clase <xref:System.Threading.Semaphore> permite que un número especificado de subprocesos acceda a un recurso. Los demás subprocesos que soliciten el recurso se bloquearán hasta que un subproceso libere el semáforo.  
  
 Al igual que la clase <xref:System.Threading.Mutex>, <xref:System.Threading.Semaphore> deriva de <xref:System.Threading.WaitHandle>. Asimismo, al igual que <xref:System.Threading.Mutex>, un <xref:System.Threading.Semaphore> puede ser local o global. También se puede usar en los límites del dominio de aplicación.  
  
 A diferencia de <xref:System.Threading.Monitor>, <xref:System.Threading.Mutex> y <xref:System.Threading.ReaderWriterLock>, <xref:System.Threading.Semaphore> no tiene afinidad de subprocesos. Esto significa que se puede usar en escenarios en los que un subproceso adquiere el semáforo y otro lo libera.  
  
 Para información conceptual, consulte [Semaphore y SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md).  
  
 <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> es un semáforo ligero para la sincronización dentro del límite de un único proceso.  
  
 [Volver al principio](#top)  
  
<a name="signaling"></a>   
## <a name="signaling"></a>Signaling  
 La manera más sencilla de esperar una señal de otro subproceso consiste en llamar al método <xref:System.Threading.Thread.Join%2A>, que se bloquea hasta que finaliza el otro subproceso. <xref:System.Threading.Thread.Join%2A> tiene dos sobrecargas que permiten que el subproceso bloqueado salga de la espera una vez transcurrido un intervalo especificado.  
  
 Los identificadores de espera proporcionan un conjunto mucho más completo de capacidades espera y señalización.  
  
### <a name="wait-handles"></a>Controladores de espera  
 Los identificadores de espera derivan de la clase <xref:System.Threading.WaitHandle>, que a su vez deriva de <xref:System.MarshalByRefObject>. Por lo tanto, los identificadores de espera se pueden usar para sincronizar las actividades de subprocesos en los límites del dominio de aplicación.  
  
 Los subprocesos se bloquean en los identificadores de espera llamando al método de instancia <xref:System.Threading.WaitHandle.WaitOne%2A> o a uno de los métodos estáticos <xref:System.Threading.WaitHandle.WaitAll%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A> o <xref:System.Threading.WaitHandle.SignalAndWait%2A>. La manera en que se liberan depende del método que se llamase y del tipo de identificadores de espera.  
  
 Para información conceptual, consulte [Identificadores de espera](https://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489).  
  
#### <a name="event-wait-handles"></a>Identificadores de espera de evento  
 Los identificadores de espera de evento incluyen la clase <xref:System.Threading.EventWaitHandle> y sus clases derivadas, <xref:System.Threading.AutoResetEvent> y <xref:System.Threading.ManualResetEvent>. Los subprocesos se liberan desde un identificador de espera de evento cuando este se señaliza llamando a su método <xref:System.Threading.EventWaitHandle.Set%2A> o mediante el método <xref:System.Threading.WaitHandle.SignalAndWait%2A>.  
  
 Los identificadores de espera de evento pueden restablecerse automáticamente, como un torniquete que permite el paso de un solo subproceso cada vez que se señala, o bien deben restablecerse manualmente, como una puerta que está cerrada hasta que se señala y, a continuación, queda abierta hasta que alguien la cierra. Tal como indican sus nombres, <xref:System.Threading.AutoResetEvent> y <xref:System.Threading.ManualResetEvent> representan lo primer y lo segundo respectivamente. <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> es un evento ligero para la sincronización dentro del límite de un único proceso.  
  
 <xref:System.Threading.EventWaitHandle> puede representar cualquier tipo de evento, y puede ser local o global. Las clases derivadas <xref:System.Threading.AutoResetEvent> y <xref:System.Threading.ManualResetEvent> siempre son locales.  
  
 Los identificadores de espera de evento no tienen afinidad de subprocesos. Cualquier subproceso puede señalar un identificador de espera de evento.  
  
 Para información conceptual, consulte [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md).  
  
#### <a name="mutex-and-semaphore-classes"></a>Clases Mutex y Semaphore  
 Dado que las clases <xref:System.Threading.Mutex> y <xref:System.Threading.Semaphore> derivan de <xref:System.Threading.WaitHandle>, se pueden usar con los métodos estáticos de <xref:System.Threading.WaitHandle>. Por ejemplo, un subproceso puede usar el método <xref:System.Threading.WaitHandle.WaitAll%2A> para esperar hasta que las tres circunstancias siguientes sean verdaderas: se señala <xref:System.Threading.EventWaitHandle>, se libera <xref:System.Threading.Mutex> y se libera <xref:System.Threading.Semaphore>. De forma similar, un subproceso puede usar el método <xref:System.Threading.WaitHandle.WaitAny%2A> para esperar hasta que se cumpla alguna de esas condiciones.  
  
 En el caso de <xref:System.Threading.Mutex> o <xref:System.Threading.Semaphore>, el hecho de que los señalen significa que los liberan. Si cualquiera de estos tipos se usa como el primer argumento del método <xref:System.Threading.WaitHandle.SignalAndWait%2A>, se libera. En el caso de <xref:System.Threading.Mutex>, que tiene afinidad de subprocesos, se produce una excepción si el subproceso que realiza la llamada no posee la exclusión mutua. Como se indicó anteriormente, los semáforos no tienen afinidad de subprocesos.  
  
#### <a name="barrier"></a>Barrier  
 La clase <xref:System.Threading.Barrier> proporciona una manera de sincronizar cíclicamente varios subprocesos de modo que todos se bloqueen en el mismo punto y esperen a que los demás subprocesos se completen. Una barrera es útil cuando uno o más subprocesos requieren los resultados de otro subproceso antes de continuar con la siguiente fase de un algoritmo. Para más información, consulte [Barrier](../../../docs/standard/threading/barrier.md).  
  
 [Volver al principio](#top)  
  
<a name="lightweight_synchronization_types"></a>   
## <a name="lightweight-synchronization-types"></a>Tipos de sincronización ligeros  
 A partir de [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], puede usar primitivas de sincronización que proporcionan un rendimiento rápido al evitar el costoso uso de objetos de kernel Win32, como los identificadores de espera, siempre que sea posible. En general, debe usar estos tipos cuando los tiempos de espera son cortos y solo cuando los tipos de sincronización originales se probaron y no resultaron satisfactorios. Los tipos ligeros no se puede usar en escenarios que requieren comunicación entre procesos.  
  
-   <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> es una versión ligera de <xref:System.Threading.Semaphore?displayProperty=nameWithType>.  
  
-   <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> es una versión ligera de <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>.  
  
-   <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> representa un evento que se señaliza cuando su recuento es cero.  
  
-   <xref:System.Threading.Barrier?displayProperty=nameWithType> permite que varios subprocesos se sincronicen entre sí sin necesidad de control por parte un subproceso principal. Una barrera impide que un subproceso continúe hasta que todos los subprocesos hayan alcanzado un punto especificado.  
  
 [Volver al principio](#top)  
  
<a name="spinwait"></a>   
## <a name="spinwait"></a>SpinWait  
 A partir de [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], se puede usar la estructura <xref:System.Threading.SpinWait?displayProperty=nameWithType> cuando un subproceso tiene que esperar a que se señalice un evento o se cumpla una condición, pero cuando el tiempo de espera real deba ser menor que el tiempo de espera necesario usando un identificador de espera o bloqueando de otro modo el subproceso actual. Si usa <xref:System.Threading.SpinWait>, puede especificar un breve período de tiempo para girar durante la espera y después ceder (por ejemplo, esperando o entrando en modo de suspensión) solo si la condición no se cumplió en el tiempo especificado.  
  
 [Volver al principio](#top)  
  
<a name="interlocked_operations"></a>   
## <a name="interlocked-operations"></a>Operaciones de bloqueo  
 Las operaciones de interbloqueos son operaciones atómicas simples realizadas en una ubicación de memoria por métodos estáticos de la clase <xref:System.Threading.Interlocked>. Esas operaciones atómicas incluyen la adición, el incremento y el decremento, el intercambio, el intercambio condicional en función de una comparación y las operaciones de lectura para los valores de 64 bits en plataformas de 32 bits.  
  
> [!NOTE]
>  La garantía de atomicidad está limitada a operaciones individuales; cuando deben realizarse varias operaciones como una unidad, se debe usar un mecanismo de sincronización más general.  
  
 Aunque ninguna de estas operaciones son bloqueos o señales, se pueden usar para construir bloqueos y señales. Dado que son nativas para el sistema operativo Windows, las operaciones de interbloqueos son sumamente rápidas.  
  
 Las operaciones de interbloqueos se pueden usar con garantías de memoria volátil para escribir aplicaciones que poseen una simultaneidad sin bloqueo eficaz. Sin embargo, requieren una programación de bajo nivel sofisticada, por lo que los bloqueos simples son una mejor opción para la mayoría de los casos.  
  
 Para información conceptual, consulte [Operaciones de bloqueo](../../../docs/standard/threading/interlocked-operations.md).  
  
## <a name="see-also"></a>Vea también  
 [Sincronizar datos para subprocesamiento múltiple](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 [Monitors](https://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db) (Clases Monitor)  
 [Mutexes](../../../docs/standard/threading/mutexes.md) (Clases Mutex)  
 [Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md) (Clases Semaphore y SemaphoreSlim)  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 [Wait Handles](https://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489) (Clases WaitHandle)  
 [Interlocked Operations](../../../docs/standard/threading/interlocked-operations.md) (Operaciones Interlocked)  
 [Reader-Writer Locks](../../../docs/standard/threading/reader-writer-locks.md) (Clase ReaderWriterLockSlim)  
 [Barrier](../../../docs/standard/threading/barrier.md) (Barrera)  
 [SpinWait](../../../docs/standard/threading/spinwait.md)  
 [SpinLock](../../../docs/standard/threading/spinlock.md)
