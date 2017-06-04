---
title: "EventWaitHandle | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "threading [.NET Framework], EventWaitHandle class"
  - "EventWaitHandle class"
  - "event wait handles [.NET Framework]"
  - "threading [.NET Framework], cross-process synchronization"
ms.assetid: 11ee0b38-d663-4617-b793-35eb6c64e9fc
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# EventWaitHandle
La clase <xref:System.Threading.EventWaitHandle> permite que los subprocesos se comuniquen entre sí a través de señales y a través de la espera de señales.  Los controladores de espera de eventos \(a los que también se conoce simplemente como eventos\) son controladores de espera que pueden señalizarse para liberar uno o varios subprocesos en espera.  Un controlador de espera de eventos, una vez señalizado, se restablece manual o automáticamente.  La clase <xref:System.Threading.EventWaitHandle> puede representar un controlador de espera de eventos \(evento local\) o un controlador de espera de eventos del sistema con nombre \(evento con nombre o evento del sistema, visible para todos los procesos\).  
  
> [!NOTE]
>  Los controladores de espera de eventos no son eventos en el sentido en que se utiliza este término en .NET Framework;  no hay delegados ni controladores de eventos implicados.  Se utiliza el término "evento" para describirlos porque tradicionalmente se les conocía como eventos del sistema operativo y porque el acto de señalizar el controlador de espera indica a los subprocesos en espera que se ha producido un evento.  
  
 Tanto los controladores de espera de eventos locales como los de eventos con nombre utilizan objetos de sincronización del sistema, que están protegidos mediante contenedores <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle> para garantizar que se liberen los recursos.  Puede utilizar el método <xref:System.Threading.WaitHandle.System%23IDisposable%23Dispose%2A> para liberar inmediatamente los recursos cuando haya terminado de utilizar el objeto.  
  
## Controladores de espera de eventos de restablecimiento automático  
 Puede crear un evento de restablecimiento automático especificando <xref:System.Threading.EventResetMode?displayProperty=fullName> al crear el objeto <xref:System.Threading.EventWaitHandle>.  Como su propio nombre indica, este evento de sincronización se restablece automáticamente cuando se señaliza, después de liberar un único subproceso en espera.  Señalice el evento llamando a su método <xref:System.Threading.EventWaitHandle.Set%2A>.  
  
 Los eventos de restablecimiento automático se utilizan normalmente para proporcionar acceso exclusivo a un recurso a un único subproceso cada vez.  Un subproceso solicita el recurso llamando al método <xref:System.Threading.WaitHandle.WaitOne%2A>.  Si no hay ningún otro subproceso que contenga el controlador de espera, el método devolverá `true` y el subproceso de llamada tomará el control del recurso.  
  
> [!IMPORTANT]
>  Como ocurre con todos los mecanismos de sincronización, deberá asegurarse de que todas las rutas de acceso al código se mantengan a la espera en el controlador de espera adecuado antes de obtener acceso a un recurso protegido.  La sincronización de subprocesos es operación cooperativa.  
  
 Si un evento de restablecimiento automático se señaliza cuando no hay ningún subproceso en espera, permanecerá señalizado hasta que algún subproceso intente esperar en él.  El evento liberará el subproceso e, inmediatamente después, se restablecerá, de modo que bloqueará los subprocesos posteriores.  
  
## Controladores de espera de eventos de restablecimiento manual  
 Puede crear un evento de restablecimiento manual especificando <xref:System.Threading.EventResetMode?displayProperty=fullName> al crear el objeto <xref:System.Threading.EventWaitHandle>.  Cuando su propio nombre indica, este evento de sincronización debe restablecerse manualmente tras su señalización.  Hasta que no se restablezca mediante una llamada al método <xref:System.Threading.EventWaitHandle.Reset%2A>, los subprocesos que se mantengan a la espera en el controlador de eventos se ejecutarán inmediatamente, sin bloquearse.  
  
 El funcionamiento de un evento de restablecimiento manual se asemeja al de la puerta de un establo.  Si el evento no está señalizado, los subprocesos en espera se bloquean mutuamente, como los caballos de un establo.  Cuando el evento se señaliza mediante una llamada al método <xref:System.Threading.EventWaitHandle.Set%2A>, todos los subprocesos en espera quedan libres para su ejecución.  El evento permanece señalizado hasta que se llama al método <xref:System.Threading.EventWaitHandle.Reset%2A>.  Esto hace del evento de restablecimiento manual una forma ideal de retener subprocesos que deben esperar a que otro subproceso finalice una tarea.  
  
 Como en el ejemplo de los caballos que salen del establo, el sistema operativo tarda cierto tiempo en programar los subprocesos liberados y reanudar su ejecución.  Si se llama al método <xref:System.Threading.EventWaitHandle.Reset%2A> antes de que se haya reanudado la ejecución de todos los subprocesos, los subprocesos restantes volverán a bloquearse.  No se puede determinar qué procesos se reanudarán y cuáles se bloquearán ya que depende de una serie de factores aleatorios, como la carga del sistema, el número de subprocesos en espera de programación, etc.  Esto no supone ningún problema si el subproceso que señaliza el evento finaliza tras la señalización, que es el patrón de uso más común.  Si desea que el subproceso que señalizaba el evento inicie una nueva tarea una vez reanudados todos los subprocesos en espera, deberá bloquearlo hasta que se hayan reanudado todos los subprocesos en espera.  De lo contrario, se producirá una condición de carrera y el comportamiento del código será imprevisible.  
  
## Características comunes de los eventos automáticos y manuales  
 Normalmente, uno o varios subprocesos se bloquean en <xref:System.Threading.EventWaitHandle> hasta que un subproceso desbloqueado llama al método <xref:System.Threading.EventWaitHandle.Set%2A>, que libera uno de los subprocesos en espera \(en el caso de los eventos de restablecimiento automático\) o todos los subprocesos \(en el caso de los eventos de restablecimiento manual\).  Un subproceso puede señalizar un controlador <xref:System.Threading.EventWaitHandle> y, a continuación, bloquearse en el mismo, como una operación atómica, llamando al método <xref:System.Threading.WaitHandle.SignalAndWait%2A?displayProperty=fullName> estático.  
  
 Los objetos <xref:System.Threading.EventWaitHandle> pueden utilizarse con los métodos <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=fullName> y <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=fullName> estáticos.  Como las clases <xref:System.Threading.EventWaitHandle> y <xref:System.Threading.Mutex> se derivan de <xref:System.Threading.WaitHandle>, se pueden utilizar ambas clases con estos métodos.  
  
### Eventos con nombre  
 El sistema operativo Windows permite que los controladores de espera de eventos tengan nombres.  Un evento con nombre afecta a todo el sistema,  es decir, una vez que se crea, es visible para todos los subprocesos en todos los procesos.  Por tanto, los eventos con nombre pueden utilizarse para sincronizar las actividades de los procesos y de los subprocesos.  
  
 Se puede crear un objeto <xref:System.Threading.EventWaitHandle> que represente un evento con nombre del sistema utilizando uno de los constructores que especifica un nombre de evento.  
  
> [!NOTE]
>  Como los eventos con nombre afectan a todo el sistema, es posible disponer de varios objetos <xref:System.Threading.EventWaitHandle> que representen al mismo evento con nombre.  Cada vez que se llame a un constructor, o al método <xref:System.Threading.EventWaitHandle.OpenExisting%2A>, se creará un nuevo objeto <xref:System.Threading.EventWaitHandle>.  Si se especifica repetidamente el mismo nombre, se crean varios objetos que representan el mismo evento con nombre.  
  
 Se recomienda utilizar con precaución los eventos con nombre.  Como son válidos para todo el sistema, si otro proceso utiliza el mismo nombre podrían bloquearse inesperadamente los subprocesos.  Cualquier código malintencionado ejecutado en el mismo equipo podría utilizar esto como base de un ataque por denegación de servicio.  
  
 Utilice la seguridad de control de acceso para proteger un objeto <xref:System.Threading.EventWaitHandle> que represente un evento con nombre, preferiblemente utilizando un constructor que especifique un objeto <xref:System.Security.AccessControl.EventWaitHandleSecurity>.  También puede aplicar la seguridad de control de acceso mediante el método <xref:System.Threading.EventWaitHandle.SetAccessControl%2A>, pero daría cabida a un margen de vulnerabilidad entre el momento de creación del controlador de espera de eventos y el momento de su protección.  La protección de eventos por medio de la seguridad de control de acceso contribuye a evitar ataques malintencionados, pero no resuelve el problema de conflictos de nombres involuntarios.  
  
> [!NOTE]
>  A diferencia de la clase <xref:System.Threading.EventWaitHandle>, las clases derivadas <xref:System.Threading.AutoResetEvent> y <xref:System.Threading.ManualResetEvent> sólo pueden representar controladores de espera locales.  No pueden representar eventos con nombre del sistema.  
  
## Vea también  
 <xref:System.Threading.EventWaitHandle>   
 <xref:System.Threading.WaitHandle>   
 <xref:System.Threading.AutoResetEvent>   
 <xref:System.Threading.ManualResetEvent>   
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)