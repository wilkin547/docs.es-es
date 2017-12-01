---
title: EventWaitHandle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], EventWaitHandle class
- EventWaitHandle class
- event wait handles [.NET Framework]
- threading [.NET Framework], cross-process synchronization
ms.assetid: 11ee0b38-d663-4617-b793-35eb6c64e9fc
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1bd248133bd95ff05246eb36a8e250247fd7ed61
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="eventwaithandle"></a>EventWaitHandle
La <xref:System.Threading.EventWaitHandle> clase permite que los subprocesos se comuniquen entre sí mediante señalización y señales de espera. Identificadores de espera de evento (también denominados simplemente como eventos) son controladores de espera que se pueden señalar con el fin de liberar uno o varios subprocesos en espera. Cuando se envía una señal, se restablece un identificador de espera de evento manual o automáticamente. La <xref:System.Threading.EventWaitHandle> clase puede representar cualquier un evento local identificador de espera (evento local) o identificador (denominado el evento o eventos del sistema, visible para todos los procesos) de espera de un evento del sistema con nombre.  
  
> [!NOTE]
>  Identificadores de espera de eventos no son eventos en el sentido en esa palabra en .NET Framework. No existen los delegados ni controladores de eventos implicados. Se utiliza el término "evento" para describirlos porque ha tradicionalmente se conocía como eventos de sistema operativo y que el acto de señalizar el identificador de espera indica a los subprocesos en espera que se ha producido un evento.  
  
 Ambos identificadores de espera de evento local y con nombre use objetos de sincronización del sistema, que están protegidos por <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle> contenedores para asegurarse de que se liberan los recursos. Puede usar el <xref:System.Threading.WaitHandle.Dispose%2A> método para liberar los recursos inmediatamente cuando haya terminado de utilizar el objeto.  
  
## <a name="event-wait-handles-that-reset-automatically"></a>Identificadores de espera de evento que se restablecen automáticamente  
 Crear un evento de restablecimiento automático especificando <xref:System.Threading.EventResetMode.AutoReset?displayProperty=nameWithType> cuando se crea el <xref:System.Threading.EventWaitHandle> objeto. Como su nombre implica, este evento de sincronización se restablece automáticamente cuando se señala, después de liberar un único subproceso en espera. Señalar el evento mediante una llamada a su <xref:System.Threading.EventWaitHandle.Set%2A> método.  
  
 Eventos de restablecimiento automático se utilizan normalmente para proporcionar acceso exclusivo a un recurso a un único subproceso cada vez. Un subproceso solicita el recurso mediante una llamada a la <xref:System.Threading.WaitHandle.WaitOne%2A> método. Si ningún otro subproceso que contenga el identificador de espera, el método devuelve `true` y el subproceso que realiza la llamada tenga el control del recurso.  
  
> [!IMPORTANT]
>  Al igual que con todos los mecanismos de sincronización, debe asegurarse de que todas las rutas de acceso de código esperen al identificador de espera adecuado antes de obtener acceso a un recurso protegido. Sincronización de subprocesos es cooperativa.  
  
 Si un evento de restablecimiento automático se señaliza cuando no hay ningún subproceso en espera, permanece señalado hasta que un subproceso intente esperar en él. El evento liberará el subproceso y restablecimiento inmediatamente, bloqueando los subprocesos subsiguientes.  
  
## <a name="event-wait-handles-that-reset-manually"></a>Identificadores de espera de evento de restablecimiento manual  
 Crear un evento de restablecimiento manual especificando <xref:System.Threading.EventResetMode.ManualReset?displayProperty=nameWithType> cuando se crea el <xref:System.Threading.EventWaitHandle> objeto. Como su nombre implica, este evento de sincronización debe restablecerse manualmente después de que se ha señalado. Hasta que se restablezca, mediante una llamada a su <xref:System.Threading.EventWaitHandle.Reset%2A> método, subprocesos que esperan en el controlador de eventos se ejecutarán inmediatamente, sin bloquearse.  
  
 Un reinicio manual eventos actúa como la puerta de un establo. Cuando no se señala el evento, bloquean de subprocesos que esperan en él, como los caballos de un establo. Cuando se señala el evento, mediante una llamada a su <xref:System.Threading.EventWaitHandle.Set%2A> método, todos los subprocesos en espera son gratuitas continuar. El evento permanece señalado hasta que su <xref:System.Threading.EventWaitHandle.Reset%2A> se llama al método. Esto hace que el evento de restablecimiento manual una forma ideal de retener subprocesos que tenga que esperar hasta que un subproceso finaliza una tarea.  
  
 Al igual que los caballos de dejar un establo, consume tiempo de los subprocesos liberados programarse por el sistema operativo y para reanudar la ejecución. Si el <xref:System.Threading.EventWaitHandle.Reset%2A> método se llama antes de que todos los subprocesos han reanudado la ejecución, los subprocesos restantes volverán a bloquearse. Qué reanudar subprocesos y qué subprocesos se bloquean depende de factores aleatorios, como la carga del sistema, el número de subprocesos en espera para el programador y así sucesivamente. Esto no es un problema si el subproceso que señala el evento finaliza tras la señalización, que es el patrón de uso más comunes. Si desea que el subproceso que señala el evento para iniciar una nueva tarea después de que todos los subprocesos se reanudación en espera, deben bloquear hasta que se reanudación todos los subprocesos en espera. En caso contrario, se producirá una condición de carrera y el comportamiento del código es imprevisible.  
  
## <a name="features-common-to-automatic-and-manual-events"></a>Características comunes de eventos automáticos y manuales  
 Normalmente, uno o varios subprocesos se bloquean en un <xref:System.Threading.EventWaitHandle> hasta que un subproceso desbloqueado llama el <xref:System.Threading.EventWaitHandle.Set%2A> método, lo que libera uno de los subprocesos en espera (en el caso de los eventos de restablecimiento automático) o todos ellos (en el caso de manual eventos de restablecimiento). Un subproceso puede señalar un <xref:System.Threading.EventWaitHandle> y, a continuación, bloquearse en ella, como una operación atómica, mediante una llamada a estático <xref:System.Threading.WaitHandle.SignalAndWait%2A?displayProperty=nameWithType> método.  
  
 <xref:System.Threading.EventWaitHandle>objetos que se puedan usar con el método estático <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=nameWithType> y <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=nameWithType> métodos. Dado que la <xref:System.Threading.EventWaitHandle> y <xref:System.Threading.Mutex> clases derivan de <xref:System.Threading.WaitHandle>, puede usar ambas clases con estos métodos.  
  
### <a name="named-events"></a>Eventos con nombre  
 El sistema operativo Windows permite que los identificadores de espera de eventos tengan nombres. Un evento con nombre es todo el sistema. Es decir, una vez que se crea el evento con nombre, es visible para todos los subprocesos de todos los procesos. Por lo tanto, los eventos con nombre se pueden utilizar para sincronizar las actividades de procesos, así como de los subprocesos.  
  
 Puede crear un <xref:System.Threading.EventWaitHandle> objeto que representa un evento del sistema con nombre mediante el uso de uno de los constructores que especifica un nombre de evento.  
  
> [!NOTE]
>  Dado que los eventos con nombre son todo el sistema, es posible tener varios <xref:System.Threading.EventWaitHandle> evento con nombre en objetos que representan la misma. Cada vez que se llama a un constructor, o la <xref:System.Threading.EventWaitHandle.OpenExisting%2A> /método siguiente, un nuevo <xref:System.Threading.EventWaitHandle> se crea el objeto. Especificar el mismo nombre repetidamente crea varios objetos que representan el mismo evento con nombre.  
  
 Se recomienda precaución con nombre eventos. Dado que son todo el sistema, otro proceso que usa el mismo nombre puede bloquearse inesperadamente los subprocesos. Si hubiera código malintencionado ejecutándose en el mismo equipo, dicho código podría utilizar esto como base de un ataque de denegación de servicio.  
  
 Utilice la seguridad de control de acceso para proteger un <xref:System.Threading.EventWaitHandle> objeto que representa un evento con nombre, preferiblemente mediante un constructor que especifica un <xref:System.Security.AccessControl.EventWaitHandleSecurity> objeto. También puede aplicar la seguridad de control de acceso mediante el <xref:System.Threading.EventWaitHandle.SetAccessControl%2A> (método), pero esto deja una ventana de vulnerabilidad entre el momento de crea el identificador de espera de evento y la hora en que está protegido. La protección de eventos con el control de acceso seguridad ayuda a evitar ataques malintencionados, pero no soluciona el problema de conflictos involuntarios de nombres.  
  
> [!NOTE]
>  A diferencia de la <xref:System.Threading.EventWaitHandle> (clase), las clases derivadas <xref:System.Threading.AutoResetEvent> y <xref:System.Threading.ManualResetEvent> puede representar solo local identificadores de espera. No se representan eventos del sistema con nombre.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
