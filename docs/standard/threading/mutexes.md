---
title: "Mutexes | Microsoft Docs"
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
  - "wait handles"
  - "threading [.NET Framework], Mutex class"
  - "Mutex class, about Mutex class"
  - "threading [.NET Framework], cross-process synchronization"
ms.assetid: 9dd06e25-12c0-4a9e-855a-452dc83803e2
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Mutexes
Puede utilizar un objeto <xref:System.Threading.Mutex> para proporcionar acceso exclusivo a un recurso.  La clase <xref:System.Threading.Mutex> utiliza más recursos del sistema que la clase <xref:System.Threading.Monitor>, pero pueden calcularse las referencias de la misma a través de los límites del dominio de aplicación, puede utilizarse con varias esperas y puede utilizarse para sincronizar subprocesos de distintos procesos.  Encontrará una comparación de los mecanismos de sincronización administrados en [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 Para obtener ejemplos de código, consulte la documentación de referencia de los constructores <xref:System.Threading.Mutex.%23ctor%2A>.  
  
## Usar exclusiones mutuas  
 Un subproceso llama al método <xref:System.Threading.WaitHandle.WaitOne%2A> de una exclusión mutua para solicitar su propiedad.  La llamada se bloquea hasta que la exclusión mutua queda disponible o hasta que transcurre el intervalo de tiempo de espera opcional.  Si una exclusión mutua no pertenece a ningún subproceso, el estado de la misma se señaliza.  
  
 Un subproceso libera una exclusión mutua llamando a su método <xref:System.Threading.Mutex.ReleaseMutex%2A>.  Las exclusiones mutuas cuentan con afinidad de subproceso; es decir, el subproceso que posee la exclusión mutua es el único que puede liberarla.  Si un subproceso libera una exclusión mutua que no posee, se produce una excepción <xref:System.ApplicationException> en el subproceso.  
  
 Como la clase <xref:System.Threading.Mutex> se deriva de <xref:System.Threading.WaitHandle>, también puede llamar al método estático <xref:System.Threading.WaitHandle.WaitAll%2A> o <xref:System.Threading.WaitHandle.WaitAny%2A> de <xref:System.Threading.WaitHandle> para solicitar la propiedad de <xref:System.Threading.Mutex> en combinación con otros controladores de espera.  
  
 Si un subproceso posee un objeto <xref:System.Threading.Mutex>, dicho subproceso puede especificar el mismo <xref:System.Threading.Mutex> en llamadas repetidas de solicitud de espera sin bloquear su ejecución; no obstante, deberá liberar <xref:System.Threading.Mutex> las veces que sean necesarias para liberar su propiedad.  
  
## Exclusiones mutuas abandonadas  
 Si un subproceso finaliza sin liberar <xref:System.Threading.Mutex>, la exclusión mutua se considera abandonada.  Esto normalmente pone de manifiesto un error de programación grave porque el recurso al que protege la exclusión mutua podría quedarse en un estado incoherente.  En la versión 2.0 de .NET Framework, se produce una excepción <xref:System.Threading.AbandonedMutexException> en el siguiente subproceso que adquiere la exclusión mutua.  
  
> [!NOTE]
>  En las versiones 1.0 y 1.1 de .NET Framework, un objeto <xref:System.Threading.Mutex> abandonado se establece en estado señalado y el siguiente subproceso en espera obtiene su propiedad.  Si no hay ningún subproceso en espera, <xref:System.Threading.Mutex> permanece en estado señalado.  No se produce ninguna excepción.  
  
 En el caso de una exclusión mutua en todo el sistema, una exclusión mutua abandonada podría indicar que una aplicación ha finalizado de forma abrupta \(por ejemplo, mediante el Administrador de tareas de Windows\).  
  
## Exclusiones mutuas locales y del sistema  
 Las exclusiones mutuas son de dos tipos: exclusiones mutuas locales y exclusiones mutuas del sistema con nombre.  Si crea un objeto <xref:System.Threading.Mutex> mediante el uso de un constructor que acepta un nombre, quedará asociado a un objeto del sistema operativo con ese nombre.  Las exclusiones mutuas del sistema con nombre son visibles en todo el sistema operativo y pueden utilizarse para sincronizar las actividades de los procesos.  Puede crear varios objetos <xref:System.Threading.Mutex> que representen la misma exclusión mutua del sistema con nombre y puede utilizar el método <xref:System.Threading.Mutex.OpenExisting%2A> para abrir una exclusión mutua del sistema con nombre existente.  
  
 Una exclusión mutua local sólo existe dentro de su proceso.  Puede utilizarla cualquier subproceso del proceso que tenga una referencia al objeto <xref:System.Threading.Mutex> local.  Cada objeto <xref:System.Threading.Mutex> es una exclusión mutua local independiente.  
  
### Seguridad de control de acceso para exclusiones mutuas del sistema  
 La versión 2.0 de .NET Framework proporciona la posibilidad de consultar y establecer seguridad de control de acceso de Windows para los objetos del sistema con nombre.  Es recomendable proteger las exclusiones mutuas del sistema desde el momento de su creación porque los objetos del sistema son globales y, por lo tanto, un código distinto del suyo propio es capaz de bloquearlas.  
  
 Para obtener información sobre la seguridad de control de acceso para las exclusiones mutuas, vea las clases <xref:System.Security.AccessControl.MutexSecurity> y <xref:System.Security.AccessControl.MutexAccessRule>, la enumeración <xref:System.Security.AccessControl.MutexRights>, los métodos <xref:System.Threading.Mutex.GetAccessControl%2A>, <xref:System.Threading.Mutex.SetAccessControl%2A> y <xref:System.Threading.Mutex.OpenExisting%2A> de la clase <xref:System.Threading.Mutex> y el constructor <xref:System.Threading.Mutex.%23ctor%28System.Boolean%2CSystem.String%2CSystem.Boolean%40%2CSystem.Security.AccessControl.MutexSecurity%29>.  
  
## Vea también  
 <xref:System.Threading.Mutex>   
 <xref:System.Threading.Mutex.%23ctor%2A>   
 <xref:System.Security.AccessControl.MutexSecurity>   
 <xref:System.Security.AccessControl.MutexAccessRule>   
 [Threading](../../../docs/standard/threading/index.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)   
 [Monitores](../Topic/Monitors.md)   
 [Threads and Threading](../../../docs/standard/threading/threads-and-threading.md)