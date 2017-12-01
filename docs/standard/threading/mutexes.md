---
title: Mutexes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wait handles
- threading [.NET Framework], Mutex class
- Mutex class, about Mutex class
- threading [.NET Framework], cross-process synchronization
ms.assetid: 9dd06e25-12c0-4a9e-855a-452dc83803e2
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a1d69c1b943d15b9ad8c80b4d7dbafebc54990ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="mutexes"></a>Mutexes
Puede usar un <xref:System.Threading.Mutex> objeto para proporcionar acceso exclusivo a un recurso. El <xref:System.Threading.Mutex> clase utiliza más recursos del sistema que la <xref:System.Threading.Monitor> clase, pero puede calcularse en los límites del dominio de aplicación, se puede utilizar con varias esperas y puede utilizarse para sincronizar subprocesos en procesos diferentes. Para ver una comparación de los mecanismos de sincronización administrados, consulte [Información general sobre los primitivos de sincronización](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 Para obtener ejemplos de código, vea la documentación de referencia para el <xref:System.Threading.Mutex.%23ctor%2A> constructores.  
  
## <a name="using-mutexes"></a>Uso de las exclusiones mutuas  
 Un subproceso llama a la <xref:System.Threading.WaitHandle.WaitOne%2A> método de una exclusión mutua que solicite la propiedad. La llamada se bloquea hasta que está disponible la exclusión mutua o hasta que transcurre el intervalo de tiempo de espera opcional. El estado de una exclusión mutua se señala si no es propiedad de ningún subproceso.  
  
 Un subproceso libera una exclusión mutua mediante una llamada a su <xref:System.Threading.Mutex.ReleaseMutex%2A> método. Las exclusiones mutuas tienen afinidad de subprocesos, es decir, solo el subproceso propietario de la exclusión mutua puede liberarla. Si un subproceso libera una exclusión mutua no es el propietario, un <xref:System.ApplicationException> se produce en el subproceso.  
  
 Dado que la <xref:System.Threading.Mutex> clase se deriva de <xref:System.Threading.WaitHandle>, también puede llamar el método estático <xref:System.Threading.WaitHandle.WaitAll%2A> o <xref:System.Threading.WaitHandle.WaitAny%2A> métodos de <xref:System.Threading.WaitHandle> que solicite la propiedad de un <xref:System.Threading.Mutex> en combinación con otros controladores de espera.  
  
 Si un subproceso posee un <xref:System.Threading.Mutex>, que el subproceso puede especificar el mismo <xref:System.Threading.Mutex> en llamadas repetidas de solicitud de espera sin bloquear su ejecución; no obstante, debe liberar el <xref:System.Threading.Mutex> tantas veces para liberar la propiedad.  
  
## <a name="abandoned-mutexes"></a>Exclusiones mutuas abandonadas  
 Si un subproceso finaliza sin liberar un <xref:System.Threading.Mutex>, la exclusión mutua se considera abandonada. A menudo, esto indica un grave error de programación porque el recurso al que protege la exclusión mutua podría quedar con un estado no coherente. En .NET Framework versión 2.0, un <xref:System.Threading.AbandonedMutexException> se produce en el siguiente subproceso que adquiere la exclusión mutua.  
  
> [!NOTE]
>  En las versiones de .NET Framework 1.0 y 1.1, un abandonado <xref:System.Threading.Mutex> espera establecido en el estado señalado y el siguiente subproceso que obtiene la propiedad. Si ningún subproceso en espera, el <xref:System.Threading.Mutex> permanece en un estado señalado. No se inicia ninguna excepción.  
  
 En el caso de una exclusión mutua en todo el sistema, una exclusión mutua abandonada podría indicar que una aplicación finalizó inesperadamente (por ejemplo, con el Administrador de tareas de Windows).  
  
## <a name="local-and-system-mutexes"></a>Exclusiones mutuas locales y del sistema  
 Hay dos tipos de exclusiones mutuas: exclusiones mutuas locales y exclusiones mutuas del sistema con nombre. Si crea un <xref:System.Threading.Mutex> utilizando un constructor que acepta un nombre de objeto está asociado a un objeto de sistema operativo de ese nombre. Las exclusiones mutuas del sistema con nombre son visibles en todo el sistema operativo y se pueden usar para sincronizar las actividades de los procesos. Puede crear varias <xref:System.Threading.Mutex> objetos que representan la misma denominado exclusión mutua del sistema y puede usar el <xref:System.Threading.Mutex.OpenExisting%2A> método para abrir una existente denominado exclusión mutua del sistema.  
  
 Una exclusión mutua local solo existe dentro del proceso. Se puede utilizar con cualquier subproceso en el proceso que tiene una referencia a la variable local <xref:System.Threading.Mutex> objeto. Cada <xref:System.Threading.Mutex> objeto es una exclusión mutua local independiente.  
  
### <a name="access-control-security-for-system-mutexes"></a>Seguridad de control de acceso para exclusiones mutuas del sistema  
 La versión 2.0 de .NET Framework proporciona la capacidad de consultar y establecer la seguridad de control de acceso Windows para objetos de sistema con nombre. Se recomienda proteger las exclusiones mutuas del sistema desde el momento en que se crean, porque los objetos de sistema son globales y, por lo tanto, puede bloquearlos un código distinto del suyo.  
  
 Para obtener información sobre la seguridad de control de acceso para las exclusiones mutuas, vea el <xref:System.Security.AccessControl.MutexSecurity> y <xref:System.Security.AccessControl.MutexAccessRule> clases, el <xref:System.Security.AccessControl.MutexRights> enumeración, el <xref:System.Threading.Mutex.GetAccessControl%2A>, <xref:System.Threading.Mutex.SetAccessControl%2A>, y <xref:System.Threading.Mutex.OpenExisting%2A> métodos de la <xref:System.Threading.Mutex> clase y el <xref:System.Threading.Mutex.%23ctor%28System.Boolean%2CSystem.String%2CSystem.Boolean%40%2CSystem.Security.AccessControl.MutexSecurity%29> constructor.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.Mutex>  
 <xref:System.Threading.Mutex.%23ctor%2A>  
 <xref:System.Security.AccessControl.MutexSecurity>  
 <xref:System.Security.AccessControl.MutexAccessRule>  
 [Subprocesamiento](../../../docs/standard/threading/index.md)  
 [Objetos y características de subprocesos](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Monitors](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db) (Clases Monitor)  
 [Subprocesos y subprocesamiento](../../../docs/standard/threading/threads-and-threading.md)
