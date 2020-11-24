---
title: Información general sobre las primitivas de sincronización
description: Obtenga información sobre las primitivas de sincronización de subprocesos .NET utilizadas para sincronizar el acceso a un recurso compartido o controlar la interacción de subprocesos
ms.date: 10/01/2018
helpviewer_keywords:
- synchronization, threads
- threading [.NET],synchronizing threads
- managed threading
ms.assetid: b782bcb8-da6a-4c6a-805f-2eb46d504309
ms.openlocfilehash: 9dfaaa6050cc6e9a6b86f991aa6d2ce2a815959a
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819661"
---
# <a name="overview-of-synchronization-primitives"></a>Información general sobre las primitivas de sincronización

.NET proporciona una variedad de tipos que puede usar para sincronizar el acceso a un recurso compartido o coordinar la interacción de subprocesos.

> [!IMPORTANT]
> Use la misma instancia primitiva de sincronización para proteger el acceso de un recurso compartido. Si usa instancias primitivas de sincronización distintas para proteger el mismo recurso, se evitará la protección proporcionada por una primitiva de sincronización.

## <a name="waithandle-class-and-lightweight-synchronization-types"></a>Clase WaitHandle y tipos de sincronización ligeros

Varias primitivas de sincronización de .NET derivan de la clase <xref:System.Threading.WaitHandle?displayProperty=nameWithType>, que encapsula un controlador de sincronización del sistema operativo nativo y usa un mecanismo de señalización para la interacción de subprocesos. Esas clases incluyen:

- <xref:System.Threading.Mutex?displayProperty=nameWithType>, que concede acceso exclusivo a un recurso compartido. El estado de una exclusión mutua se señala si no es propiedad de ningún subproceso.
- <xref:System.Threading.Semaphore?displayProperty=nameWithType>, que limita el número de subprocesos que pueden tener acceso a un recurso compartido o grupo de recursos simultáneamente. El estado de un semáforo se establece como señalizado cuando su recuento es mayor que cero y como no señalizado cuando su recuento es cero.
- <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>, que representa un evento de sincronización de subprocesos y puede estar en un estado señalizado o no señalizado.
- <xref:System.Threading.AutoResetEvent?displayProperty=nameWithType>, que se deriva de <xref:System.Threading.EventWaitHandle> y, cuando está señalizada, se restablece automáticamente a un estado no señalizado después de liberar un subproceso en espera único.
- <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>, que se deriva de <xref:System.Threading.EventWaitHandle> y, cuando está señalizado, permanece en un estado señalizado hasta que se llama al método <xref:System.Threading.EventWaitHandle.Reset%2A>.

En .NET Framework, como <xref:System.Threading.WaitHandle> deriva de <xref:System.MarshalByRefObject?displayProperty=nameWithType>, estos tipos se pueden usar para sincronizar las actividades de subprocesos entre los límites del dominio de la aplicación.

En .NET Framework, y .NET Core y .NET 5 y versiones posteriores, algunos de estos tipos pueden representar controladores de sincronización del sistema con nombre, que son visibles en todo el sistema operativo y se pueden usar para la sincronización entre procesos:

- <xref:System.Threading.Mutex>
- <xref:System.Threading.Semaphore> (en Windows)
- <xref:System.Threading.EventWaitHandle> (en Windows)

Para más información, vea la referencia de API <xref:System.Threading.WaitHandle>.

Los tipos de sincronización ligeros no se basan en los controladores del sistema operativo subyacentes y suelen proporcionar un mejor rendimiento. Sin embargo, no se pueden usar para la sincronización entre procesos. Utilice esos tipos para la sincronización de subprocesos dentro de una aplicación.

Algunos de esos tipos son alternativas a los tipos derivados de <xref:System.Threading.WaitHandle>. Por ejemplo, <xref:System.Threading.SemaphoreSlim> es una alternativa ligera a <xref:System.Threading.Semaphore>.

## <a name="synchronization-of-access-to-a-shared-resource"></a>Sincronización del acceso a un recurso compartido

.NET proporciona un intervalo de primitivas de sincronización para controlar el acceso a un recurso compartido por varios subprocesos.

### <a name="monitor-class"></a>Monitor (clase)

La clase <xref:System.Threading.Monitor?displayProperty=nameWithType> concede acceso mutuamente exclusivo a un recurso compartido mediante la adquisición o liberación de un bloqueo en el objeto que identifica el recurso. Mientras se mantiene un bloqueo, el subproceso que lo mantiene puede volver a adquirir y liberar dicho bloqueo. Ningún otro subproceso puede adquirir el bloqueo y el método <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> espera hasta que el bloqueo se libera. El método <xref:System.Threading.Monitor.Enter%2A> adquiere un bloqueo liberado. También puede usar el método <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> para especificar la cantidad de tiempo durante el cual un subproceso intenta adquirir un bloqueo. Dado que la clase <xref:System.Threading.Monitor> tiene afinidad de subproceso, el subproceso que adquirió un bloqueo debe liberarlo mediante una llamada al método <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType>.

Puede coordinar la interacción de subprocesos que adquieren un bloqueo en el mismo objeto mediante los métodos <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType>, <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> y <xref:System.Threading.Monitor.PulseAll%2A?displayProperty=nameWithType>.

Para más información, vea la referencia de API <xref:System.Threading.Monitor>.

> [!NOTE]
> Use la instrucción [lock](../../csharp/language-reference/keywords/lock-statement.md) en C# y la instrucción [SyncLock](../../visual-basic/language-reference/statements/synclock-statement.md) en Visual Basic para sincronizar el acceso a un recurso compartido en lugar de usar la clase <xref:System.Threading.Monitor> directamente. Esas instrucciones se implementan mediante los métodos <xref:System.Threading.Monitor.Enter%2A> y <xref:System.Threading.Monitor.Exit%2A>, y usa un bloqueo `try…finally` para asegurarse de que se libere el bloqueo.

### <a name="mutex-class"></a>Mutex (clase)

La clase <xref:System.Threading.Mutex?displayProperty=nameWithType>, como <xref:System.Threading.Monitor>, concede acceso exclusivo a un recurso compartido. Utilice una de las sobrecargas del método [Mutex.WaitOne](<xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=nameWithType>) para solicitar la propiedad de una exclusión mutua. Al igual que <xref:System.Threading.Monitor>, <xref:System.Threading.Mutex> tiene afinidad de subproceso y el subproceso que adquirió una exclusión mutua debe liberarlo llamando al método <xref:System.Threading.Mutex.ReleaseMutex%2A?displayProperty=nameWithType>.

A diferencia de <xref:System.Threading.Monitor>, la clase <xref:System.Threading.Mutex> puede usarse para la sincronización entre procesos. Para ello, use una exclusión mutua con nombre, que es visible en todo el sistema operativo. Para crear una instancia de la exclusión mutua con nombre, use un [constructor de exclusión mutua](<xref:System.Threading.Mutex.%23ctor%2A>) que especifica un nombre. También se puede llamar al método <xref:System.Threading.Mutex.OpenExisting%2A?displayProperty=nameWithType> para abrir una exclusión mutua del sistema existente.
  
Para más información, vea el artículo [Mutexes](mutexes.md) y la referencia de API <xref:System.Threading.Mutex>.

### <a name="spinlock-structure"></a>SpinLock (estructura)

La estructura <xref:System.Threading.SpinLock?displayProperty=nameWithType>, como <xref:System.Threading.Monitor>, concede acceso exclusivo a un recurso compartido en función de la disponibilidad de un bloqueo. Cuando <xref:System.Threading.SpinLock> intenta adquirir un bloqueo que no está disponible, espera en un bucle, y realiza comprobaciones repetidamente hasta que dicho bloqueo esté disponible.

Para más información sobre las ventajas e inconvenientes del uso de un bloqueo de giro, vea el artículo [SpinLock](spinlock.md) y la referencia de API <xref:System.Threading.SpinLock>.

### <a name="readerwriterlockslim-class"></a>ReaderWriterLockSlim (clase)

La clase <xref:System.Threading.ReaderWriterLockSlim?displayProperty=nameWithType> concede acceso exclusivo a un recurso compartido para escritura y permite que varios subprocesos accedan al recurso simultáneamente para lectura. Es posible que desee utilizar <xref:System.Threading.ReaderWriterLockSlim> para sincronizar el acceso a una estructura de datos compartida que admita operaciones de lectura seguras para subprocesos, pero que requiera acceso exclusivo para realizar la operación de escritura. Cuando un subproceso solicita acceso exclusivo (por ejemplo, llamando al método <xref:System.Threading.ReaderWriterLockSlim.EnterWriteLock%2A?displayProperty=nameWithType>), las solicitudes posteriores del lector y el escritor se bloquean hasta que todos los lectores existentes han salido del bloqueo y el escritor ha entrado y salido de dicho bloqueo.
  
Para más información, vea la referencia de API <xref:System.Threading.ReaderWriterLockSlim>.

### <a name="semaphore-and-semaphoreslim-classes"></a>Semaphore y SemaphoreSlim (clases)

Las clases <xref:System.Threading.Semaphore?displayProperty=nameWithType> y <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> limitan el número de subprocesos que pueden tener acceso a un recurso compartido o grupo de recursos simultáneamente. Los demás subprocesos que soliciten el recurso esperarán hasta que un subproceso libere el semáforo. Dado que el semáforo no tiene afinidad de subproceso, un subproceso puede adquirir el semáforo y otro puede liberarlo.

<xref:System.Threading.SemaphoreSlim> es una alternativa ligera a <xref:System.Threading.Semaphore> y solo se puede usar para la sincronización dentro de un límite de un único proceso.

En Windows, puede usar <xref:System.Threading.Semaphore> para la sincronización entre procesos. Para hacerlo, cree una instancia de <xref:System.Threading.Semaphore> que represente un semáforo de sistema con nombre mediante el uso de uno de los [constructores Semaphore](<xref:System.Threading.Semaphore.%23ctor%2A>) que especifica un nombre o el método <xref:System.Threading.Semaphore.OpenExisting%2A?displayProperty=nameWithType>. <xref:System.Threading.SemaphoreSlim> no es compatible con los semáforos con nombre del sistema.

Para más información, consulte el artículo [Semaphore y SemaphoreSlim](semaphore-and-semaphoreslim.md) y la referencia de API <xref:System.Threading.Semaphore> o <xref:System.Threading.SemaphoreSlim>.

## <a name="thread-interaction-or-signaling"></a>Interacción de subprocesos o señalización

Interacción de subprocesos (o señalización de subprocesos) significa que un subproceso debe esperar la notificación o una señal de uno o varios subprocesos para poder continuar. Por ejemplo, si un subproceso A llama al método <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> del subproceso B, un subproceso A se bloquea hasta que el subproceso B finaliza. Las primitivas de sincronización descritas en la sección anterior proporcionan un mecanismo diferente para la señalización: al liberar un bloqueo, un subproceso notifica a otro subproceso que puede continuar adquiriendo el bloqueo.

En esta sección se describen construcciones adicionales de señalización proporcionados por. NET.

### <a name="eventwaithandle-autoresetevent-manualresetevent-and-manualreseteventslim-classes"></a>EventWaitHandle, AutoResetEvent, ManualResetEvent y ManualResetEventSlim (clases)

La clase <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> representa un evento de sincronización de subprocesos.

Un evento de sincronización puede estar en un estado de no señalizado o señalizado. Cuando el estado de un evento es señalizado, un subproceso que llama a la sobrecarga <xref:System.Threading.WaitHandle.WaitOne%2A?> del evento se bloquea hasta que un evento se señaliza. El método <xref:System.Threading.EventWaitHandle.Set%2A?displayProperty=nameWithType> establece el estado de un evento en señalizado.

El comportamiento de una clase <xref:System.Threading.EventWaitHandle> que se haya señalizado depende de su modo de restablecimiento:

- Una clase <xref:System.Threading.EventWaitHandle> creada con la marca <xref:System.Threading.EventResetMode.AutoReset?displayProperty=nameWithType> se restablece automáticamente después de liberar un subproceso en espera único. Es como un torniquete que permite solo un subproceso cada vez que se señaliza. La clase <xref:System.Threading.AutoResetEvent?displayProperty=nameWithType>, que deriva de <xref:System.Threading.EventWaitHandle>, representa ese comportamiento.
- Una clase <xref:System.Threading.EventWaitHandle> creada con la marca <xref:System.Threading.EventResetMode.ManualReset?displayProperty=nameWithType> permanece señalizada hasta que se llama a su método <xref:System.Threading.EventWaitHandle.Reset%2A>. Es como una puerta que está cerrada hasta que se señaliza y a partir de entonces permanece abierta hasta que alguien la cierra. La clase <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>, que deriva de <xref:System.Threading.EventWaitHandle>, representa ese comportamiento. La clase <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> es una alternativa ligera a <xref:System.Threading.ManualResetEvent>.

En Windows, puede usar <xref:System.Threading.EventWaitHandle> para la sincronización entre procesos. Para hacerlo, cree una instancia de <xref:System.Threading.EventWaitHandle> que represente un semáforo de sincronización del sistema con nombre mediante el uso de uno de los [constructores EventWaitHandle](<xref:System.Threading.EventWaitHandle.%23ctor%2A>) que especifica un nombre o el método <xref:System.Threading.EventWaitHandle.OpenExisting%2A?displayProperty=nameWithType>.

Para obtener más información, consulte el artículo [EventWaitHandle](eventwaithandle.md). Para la referencia de API, consulte <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.AutoResetEvent>, <xref:System.Threading.ManualResetEvent> y <xref:System.Threading.ManualResetEventSlim>.

### <a name="countdownevent-class"></a>Clase CountdownEvent

La clase <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> representa un evento que se establece cuando su recuento es cero. Mientras <xref:System.Threading.CountdownEvent.CurrentCount?displayProperty=nameWithType> sea mayor que cero, un subproceso que llama a <xref:System.Threading.CountdownEvent.Wait%2A?displayProperty=nameWithType> está bloqueado. Llame a <xref:System.Threading.CountdownEvent.Signal%2A?displayProperty=nameWithType> para reducir el recuento de un evento.

En contraposición a <xref:System.Threading.ManualResetEvent> o <xref:System.Threading.ManualResetEventSlim>, que puede usar para desbloquear varios subprocesos con una señal de un subproceso, puede usar <xref:System.Threading.CountdownEvent> para desbloquear uno o varios subprocesos con las señales de varios subprocesos.

Para más información, vea el artículo [CountdownEvent](countdownevent.md) y la referencia de API <xref:System.Threading.CountdownEvent>.

### <a name="barrier-class"></a>Barrier (clase)

La clase <xref:System.Threading.Barrier?displayProperty=nameWithType> representa una barrera de ejecución de subprocesos. Un subproceso que llama al método <xref:System.Threading.Barrier.SignalAndWait%2A?displayProperty=nameWithType> indica que ha alcanzado la barrera y espera hasta que otros subprocesos participantes alcancen la barrera. Cuando todos los subprocesos participantes alcancen la barrera, continúan y la barrera se restablece y se puede volver a usar.

Puede usar <xref:System.Threading.Barrier> cuando uno o más subprocesos requieren los resultados de otros subprocesos antes de continuar con la siguiente fase del cálculo.

Para más información, vea el artículo [Barrier](barrier.md) y la referencia de API <xref:System.Threading.Barrier>.

## <a name="interlocked-class"></a>Interlocked (clase)

La clase <xref:System.Threading.Interlocked?displayProperty=nameWithType> proporciona métodos estáticos que realizan operaciones atómicas simples en una variable. Esas operaciones atómicas incluyen la adición, el incremento y el decremento, el intercambio y el intercambio condicional que depende de una comparación, y la operación de lectura de un valor entero de 64 bits.

Para más información, vea la referencia de API <xref:System.Threading.Interlocked>.

## <a name="spinwait-structure"></a>SpinWait (estructura)

La estructura <xref:System.Threading.SpinWait?displayProperty=nameWithType> proporciona compatibilidad para la espera basada en ciclos. Puede que le interese utilizarla cuando un subproceso tiene que esperar a que se señalice un evento o se cumpla una condición, pero cuando el tiempo de espera real deba ser menor que el tiempo de espera necesario usando un identificador de espera o bloqueando de otro modo el subproceso. Si usa <xref:System.Threading.SpinWait>, puede especificar un breve período de tiempo para girar durante la espera y después ceder (por ejemplo, esperando o entrando en modo de suspensión) solo si la condición no se cumplió en el tiempo especificado.

Para más información, vea el artículo [SpinWait](spinwait.md) y la referencia de API <xref:System.Threading.SpinWait>.

## <a name="see-also"></a>Vea también

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [Colecciones seguras para subprocesos](../collections/thread-safe/index.md)
- [Objetos y características de subprocesos](threading-objects-and-features.md)
