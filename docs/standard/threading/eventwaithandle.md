---
title: EventWaitHandle
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET], EventWaitHandle class
- EventWaitHandle class
- event wait handles [.NET]
- threading [.NET], cross-process synchronization
ms.assetid: 11ee0b38-d663-4617-b793-35eb6c64e9fc
ms.openlocfilehash: d8c4745af9c5336d013dc0ca7ef1030b208c8b68
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188346"
---
# <a name="eventwaithandle"></a>EventWaitHandle

La clase <xref:System.Threading.EventWaitHandle> permite que los subprocesos se comuniquen entre sí mediante señalización y espera de señales. Los identificadores de espera de eventos (también denominados simplemente como eventos) son identificadores de espera que se pueden señalar con el fin de liberar uno o varios subprocesos en espera. Cuando se envía una señal, se restablece un identificador de espera de evento de forma manual o automática. La clase <xref:System.Threading.EventWaitHandle> puede representar cualquier identificador de espera de evento local (evento local) o identificador de espera de evento del sistema con nombre (denominado evento o evento del sistema y visible para todos los procesos).  
  
> [!NOTE]
> Los identificadores de espera de evento no son [eventos](../events/index.md) de .NET. No existen delegados ni controladores de eventos implicados. Se utiliza el término "evento" para describirlos porque tradicionalmente se ha hecho referencia a ellos como eventos del sistema operativo y porque el acto de señalar el indicador de espera indica a los subprocesos en espera que se ha producido un evento.  
  
 Ambos identificadores de espera de evento local y con nombre usan objetos de sincronización del sistema, protegidos por contenedores <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle> para garantizar la liberación de los recursos. Puede usar el método <xref:System.Threading.WaitHandle.Dispose%2A> para liberar los recursos inmediatamente cuando haya terminado de utilizar el objeto.  
  
## <a name="event-wait-handles-that-reset-automatically"></a>Identificadores de espera de evento que se restablecen automáticamente  
 Cree un evento de restablecimiento automático definiendo <xref:System.Threading.EventResetMode.AutoReset?displayProperty=nameWithType> al crear el objeto <xref:System.Threading.EventWaitHandle>. Como su nombre implica, este evento de sincronización se restablece automáticamente cuando se señala, después de liberar un único subproceso en espera. Señale el evento mediante una llamada a su método <xref:System.Threading.EventWaitHandle.Set%2A>.  
  
 Los eventos de restablecimiento automático se utilizan normalmente para proporcionar acceso exclusivo a un recurso a un único subproceso cada vez. Un subproceso solicita el recurso mediante una llamada al método <xref:System.Threading.WaitHandle.WaitOne%2A>. Si ningún otro subproceso contiene el identificador de espera, el método devuelve `true` y el subproceso que realiza la llamada tiene el control del recurso.  
  
> [!IMPORTANT]
> Al igual que con todos los mecanismos de sincronización, debe asegurarse de que todas las rutas de acceso de código esperen al identificador de espera adecuado antes de obtener acceso a un recurso protegido. La sincronización de subprocesos es cooperativa.  
  
 Si un evento de restablecimiento automático se señaliza cuando no hay ningún subproceso en espera, permanece señalado hasta que un subproceso intenta esperar en él. El evento libera el subproceso y lo restablece inmediatamente, bloqueando los subprocesos subsiguientes.  
  
## <a name="event-wait-handles-that-reset-manually"></a>Identificadores de espera de evento que se restablecen manualmente  
 Cree un evento de restablecimiento manual definiendo <xref:System.Threading.EventResetMode.ManualReset?displayProperty=nameWithType> al crear el objeto <xref:System.Threading.EventWaitHandle>. Como su nombre implica, este evento de sincronización debe restablecerse manualmente después de que se haya señalado. Hasta que se restablezca, mediante una llamada a su método <xref:System.Threading.EventWaitHandle.Reset%2A>, los subprocesos que esperan en el identificador de evento se ejecutarán inmediatamente, sin bloquearse.  
  
 Un evento de restablecimiento manual funciona como la puerta de un establo. Si no se señala un evento, los subprocesos que esperan en él se bloquean, como los caballos de un establo. Cuando se señala el evento, mediante una llamada a su método <xref:System.Threading.EventWaitHandle.Set%2A>, todos los subprocesos en espera pueden continuar libremente. El evento permanece señalado hasta que se llama a su método <xref:System.Threading.EventWaitHandle.Reset%2A>. Esto hace que el evento de restablecimiento manual sea una forma ideal de retener subprocesos que necesitan esperar hasta que un subproceso finaliza una tarea.  
  
 Como los caballos cuando dejan un establo, lleva tiempo que el sistema operativo programe los subprocesos liberados y reanudar su ejecución. Si se llama al método <xref:System.Threading.EventWaitHandle.Reset%2A> antes de que se reanude la ejecución de los subprocesos, los subprocesos restantes se vuelven a bloquear. Los subprocesos que se reanudan y los subprocesos que se bloquean es una cuestión que depende de factores aleatorios, como la carga del sistema, el número de subprocesos que esperan al programador, etc. Esto no plantea ningún problema si el subproceso que señala el evento termina después de la señalización, que es el patrón de uso más común. Si desea que el subproceso que señaló el evento inicie una nueva tarea después de que todos los subprocesos en espera se hayan reanudado, debe bloquearlo hasta que todos los subprocesos en espera se hayan reanudado. En caso contrario, se produce una condición de carrera y el comportamiento del código es imprevisible.  
  
## <a name="features-common-to-automatic-and-manual-events"></a>Características comunes de eventos automáticos y manuales  
 Normalmente, uno o varios subprocesos se bloquean en <xref:System.Threading.EventWaitHandle> hasta que un subproceso desbloqueado llama al método <xref:System.Threading.EventWaitHandle.Set%2A>, lo que libera uno de los subprocesos en espera (en el caso de los eventos de restablecimiento automático) o todos ellos (en el caso de eventos de restablecimiento manual). Un subproceso puede señalar <xref:System.Threading.EventWaitHandle> y, a continuación, bloquearse ahí, como una operación atómica, mediante una llamada al método estático <xref:System.Threading.WaitHandle.SignalAndWait%2A?displayProperty=nameWithType>.  
  
 Los objetos <xref:System.Threading.EventWaitHandle> pueden usarse con los métodos estáticos <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=nameWithType> y <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=nameWithType>. Dado que las clases <xref:System.Threading.EventWaitHandle> y <xref:System.Threading.Mutex> se derivan de <xref:System.Threading.WaitHandle>, puede usar las dos con estos métodos.  
  
### <a name="named-events"></a>Eventos con nombre  
 El sistema operativo Windows permite que los identificadores de espera de evento tengan nombres. Un evento con nombre abarca todo el sistema. Es decir, una vez creado el evento con nombre, es visible para todos los subprocesos de todos los procesos. Por lo tanto, los eventos con nombre pueden utilizarse para sincronizar tanto las actividades de procesos como las de subprocesos.  
  
 Puede crear un objeto <xref:System.Threading.EventWaitHandle> que represente un evento de sistema con nombre mediante el uso de uno de los constructores que especifica un nombre de evento.  
  
> [!NOTE]
> Dado que los eventos con nombre abarcan todo el sistema, es posible tener varios objetos <xref:System.Threading.EventWaitHandle> que representan el mismo evento con nombre. Cada vez que llama a un constructor o al método <xref:System.Threading.EventWaitHandle.OpenExisting%2A>, se crea un objeto <xref:System.Threading.EventWaitHandle>. Si se especifica el mismo nombre repetidamente, se crean varios objetos que representan el mismo evento con nombre.  
  
 Se recomienda actuar con precaución en el uso de los eventos con nombre. Dado que abarcan todo el sistema, otro proceso que utilice el mismo nombre puede bloquear los subprocesos inesperadamente. Si hubiera código malintencionado ejecutándose en el mismo equipo, dicho código podría utilizar esto como base de un ataque de denegación de servicio.  
  
 Utilice la seguridad de control de acceso para proteger un objeto <xref:System.Threading.EventWaitHandle> que representa un evento con nombre, a poder ser mediante un constructor que especifique un objeto <xref:System.Security.AccessControl.EventWaitHandleSecurity>. También puede aplicar la seguridad de control de acceso mediante el método <xref:System.Threading.EventWaitHandle.SetAccessControl%2A>, pero esto deja una ventana de vulnerabilidad entre el momento en que se crea el identificador de espera de evento y el momento en que se protege. Proteger los eventos con seguridad de control de acceso ayuda a evitar ataques malintencionados, pero no soluciona el problema de conflictos involuntarios de nombres.  
  
> [!NOTE]
> A diferencia de la clase <xref:System.Threading.EventWaitHandle>, las clases derivadas <xref:System.Threading.AutoResetEvent> y <xref:System.Threading.ManualResetEvent> pueden representar solo identificadores de espera locales. No pueden representar eventos del sistema con nombre.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.EventWaitHandle>
- <xref:System.Threading.WaitHandle>
- <xref:System.Threading.AutoResetEvent>
- <xref:System.Threading.ManualResetEvent>
