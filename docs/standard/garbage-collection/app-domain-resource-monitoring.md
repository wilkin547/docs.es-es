---
title: "Application Domain Resource Monitoring | Microsoft Docs"
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
  - "monitoring managed memory use by application domain"
  - "application domains, memory use"
  - "memory use, monitoring"
  - "application domains, resource monitoring"
ms.assetid: 318bedf8-7f35-4f00-b34a-2b7b8e3fa315
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Application Domain Resource Monitoring
La supervisión de recursos de dominio de aplicación \(ARM\) permite a los hosts supervisar el uso de la CPU y la memoria por dominio de aplicación.  Esto resulta útil para los hosts como ASP.NET, que utilizan muchos dominios de aplicación en un proceso de ejecución prolongada.  El host puede descargar el dominio de aplicación de una aplicación que afecta negativamente al rendimiento del proceso completo, pero únicamente si puede identificar la aplicación problemática.  La ARM proporciona información que se puede utilizar para ayudar a tomar este tipo de decisiones.  
  
 Por ejemplo, un servicio de hospedaje podría tener muchas aplicaciones que se ejecutan en un servidor ASP.NET.  Si una aplicación del proceso empieza a utilizar demasiada memoria o demasiado tiempo de procesador, el servicio de hospedaje puede utilizar la ARM para identificar el dominio de aplicación que está produciendo el problema.  
  
 La ARM es lo bastante ligera para utilizarla en aplicaciones activas.  Se puede tener acceso a la información mediante el Seguimiento de eventos para Windows \(ETW\) o directamente a través de API administradas o nativas.  
  
## Habilitar la supervisión de recursos  
 La ARM se puede habilitar de cuatro maneras: proporcionando un archivo de configuración cuando se inicia el Common Language Runtime \(CLR\); utilizando una API de hospedaje no administrada; utilizando código administrado; o escuchando eventos ETW de ARM.  
  
 Tan pronto como se habilita la ARM, empieza a recolectar datos en todos los dominios de aplicación del proceso.  Si se ha creado un dominio de aplicación antes de habilitar la ARM, los datos acumulativos se inician cuando se habilita la ARM, no cuando se creó el dominio de aplicación. Una vez habilitada, la ARM no se puede deshabilitar.  
  
-   Puede habilitar la ARM en el inicio de CLR agregando el elemento de [\<el appDomainResourceMonitoring\>](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md) al archivo de configuración, y estableciendo el atributo de `enabled` a `true`.  Un valor de `false` \(el valor predeterminado\) significa solamente que la ARM no se habilita al iniciar; puede activarla posteriormente mediante alguno de los demás mecanismos de activación.  
  
-   El host puede habilitar la ARM solicitando la interfaz de hospedaje [ICLRAppDomainResourceMonitor](../../../ocs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md).  Una vez obtenida correctamente esta interfaz, se habilita la ARM.  
  
-   El código administrado puede habilitar la ARM estableciendo la propiedad <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=fullName> estática \(`Shared` en Visual Basic\) en `true`.  En cuanto se establece la propiedad, se habilita la ARM.  
  
-   Puede habilitar la ARM después del inicio escuchando los eventos ETW.  La ARM se habilita y comienza a generar eventos para todos los dominios de aplicación cuando se habilitar el proveedor público `Microsoft-Windows-DotNETRuntime` mediante la palabra clave `AppDomainResourceManagementKeyword`.  Para poner en correlación los datos con los dominios de aplicación y subprocesos, debe habilitar también el proveedor `Microsoft-Windows-DotNETRuntimeRundown` con la palabra clave `ThreadingKeyword`.  
  
## Utilizar ARM  
 La ARM proporciona el tiempo total del procesador que utiliza un dominio de aplicación y tres tipos de información sobre el uso de la memoria.  
  
-   **Tiempo total del procesador para un dominio de aplicación, en segundos**: se calcula sumando los tiempos de los subprocesos notificados por el sistema operativo para todos los subprocesos que dedicaron tiempo a ejecutarse en el dominio de aplicación a lo largo de su duración.  Los subprocesos bloqueados o en suspensión no consumen tiempo de procesador.  Cuando un subproceso llama al código nativo, el tiempo que el subproceso pasa en el código nativo se incluye en el recuento del dominio de aplicación donde se realizó la llamada.  
  
    -   API administrada: propiedad <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=fullName>.  
  
    -   API de hospedaje: método [ICLRAppDomainResourceMonitor::GetCurrentCpuTime](../Topic/ICLRAppDomainResourceMonitor::GetCurrentCpuTime%20Method.md).  
  
    -   Eventos ETW: eventos `ThreadCreated`, `ThreadAppDomainEnter` y `ThreadTerminated`.  Para obtener información acerca de los proveedores y las palabras clave, vea el apartado sobre eventos de supervisión de recursos de AppDomain en [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md).  
  
-   **Asignaciones administradas totales realizadas por un dominio de aplicación durante su duración, en bytes**: las asignaciones totales no siempre reflejan el uso de la memoria por un dominio de aplicación, porque los objetos asignados podrían ser de corta duración.  Sin embargo, si una aplicación asigna y libera grandes cantidades de objetos, el costo de las asignaciones podría ser significativo.  
  
    -   API administrada: propiedad <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=fullName>.  
  
    -   API de hospedaje: método [ICLRAppDomainResourceMonitor::GetCurrentAllocated](../Topic/ICLRAppDomainResourceMonitor::GetCurrentAllocated%20Method.md).  
  
    -   Eventos ETW: evento `AppDomainMemAllocated`, campo `Allocated`.  
  
-   **Memoria administrada, en bytes, a la que hace referencia un dominio de aplicación y que ha sobrevivido a la recolección completa de bloqueo más reciente**: este número solo es preciso después de una recolección completa de bloqueo. \(Por oposición a las recolecciones simultáneas, que se producen en segundo plano y no bloquean la aplicación.\) Por ejemplo, la sobrecarga del método <xref:System.GC.Collect?displayProperty=fullName> provoca una recolección completa de bloqueo.  
  
    -   API administrada: propiedad <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=fullName>.  
  
    -   API de hospedaje: método [ICLRAppDomainResourceMonitor::GetCurrentSurvived](../Topic/ICLRAppDomainResourceMonitor::GetCurrentSurvived%20Method.md), parámetro `pAppDomainBytesSurvived`.  
  
    -   Eventos ETW: evento `AppDomainMemSurvived`, campo `Survived`.  
  
-   **Memoria total administrada, en bytes, a la que hace referencia el proceso y que ha sobrevivido a la recolección completa de bloqueo más reciente**: la memoria que ha sobrevivido para los dominios de aplicación individuales se puede comparar con este número.  
  
    -   API administrada: propiedad <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=fullName>.  
  
    -   API de hospedaje: método [ICLRAppDomainResourceMonitor::GetCurrentSurvived](../Topic/ICLRAppDomainResourceMonitor::GetCurrentSurvived%20Method.md), parámetro `pTotalBytesSurvived`.  
  
    -   Eventos ETW: evento `AppDomainMemSurvived`, campo `ProcessSurvived`.  
  
### Determinar cuándo se produce una recolección completa de bloqueo  
 Para determinar cuándo son precisos los recuentos de memoria que ha sobrevivido, es preciso saber cuándo se acaba de producir una recolección completa de bloqueo.  El método para ello depende de la API que se utiliza para examinar las estadísticas de ARM.  
  
#### API administrada  
 Si utiliza las propiedades de la clase <xref:System.AppDomain>, puede utilizar el método <xref:System.GC.RegisterForFullGCNotification%2A?displayProperty=fullName> para registrarse y obtener notificaciones de las recolecciones completas.  El umbral que se utiliza no es importante, porque se espera a que se complete una recolección, y no a que esté próxima su realización.  A continuación, puede llamar al método <xref:System.GC.WaitForFullGCComplete%2A?displayProperty=fullName>, que se bloquea hasta que finaliza una recolección completa.  Puede crear un subproceso que llama al método en un bucle y realiza el análisis necesario cada vez que se devuelve el método.  
  
 Como alternativa, puede llamar periódicamente al método <xref:System.GC.CollectionCount%2A?displayProperty=fullName> para ver si ha aumentado el recuento de las recolecciones de la generación 2.  Según la frecuencia de sondeo, esta técnica podría no proporcionar una indicación tan precisa de cuándo se produce una recolección completa.  
  
#### API de hospedaje  
 Si se utiliza la API de hospedaje no administrada, el host debe pasar al CLR una implementación de la interfaz [IHostGCManager](../../../ocs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md).  El CLR llama al método [IHostGCManager::SuspensionEnding](../Topic/IHostGCManager::SuspensionEnding%20Method.md) cuando reanuda la ejecución de los subprocesos que se han suspendido durante una recolección.  El CLR pasa la generación de la recolección completada como un parámetro del método, de modo que el host pueda determinar si la colección ha sido completa o parcial.  Su implementación del método [IHostGCManager::SuspensionEnding](../Topic/IHostGCManager::SuspensionEnding%20Method.md) puede consultar la memoria que ha sobrevivido, a fin de asegurarse de que se recuperan los recuentos en cuanto están actualizados.  
  
## Vea también  
 <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=fullName>   
 [ICLRAppDomainResourceMonitor \(Interfaz\)](../../../ocs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)   
 [\<el appDomainResourceMonitoring\>](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)   
 [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md)