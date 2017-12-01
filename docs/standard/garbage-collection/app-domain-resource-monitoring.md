---
title: "Supervisión de recursos de dominio de aplicación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- monitoring managed memory use by application domain
- application domains, memory use
- memory use, monitoring
- application domains, resource monitoring
ms.assetid: 318bedf8-7f35-4f00-b34a-2b7b8e3fa315
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 62a514f94857044af5020d36a1cfd6ce06741ac7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="application-domain-resource-monitoring"></a>Supervisión de recursos de dominio de aplicación
Recursos de dominio de aplicación (ARM) de supervisión permite a los hosts supervisar el uso de CPU y memoria por dominio de aplicación. Esto es útil para los hosts como ASP.NET que utilizan varios dominios de aplicación en un proceso de ejecución prolongada. El host puede descargar el dominio de aplicación de una aplicación que está afectando el rendimiento de todo el proceso, pero solo si puede identificar la aplicación problemática. ARM proporciona información que puede usarse para ayudar a tomar estas decisiones.  
  
 Por ejemplo, un servicio de hospedaje podría tener muchas aplicaciones que se ejecutan en un servidor ASP.NET. Si una aplicación en el proceso empieza a consumir demasiada memoria o demasiado tiempo de procesador, el servicio de hospedaje puede usar ARM para identificar el dominio de aplicación que está causando el problema.  
  
 ARM es lo bastante ligera para utilizarla en aplicaciones activas. Puede tener acceso a la información mediante el uso de seguimiento de eventos para Windows (ETW) o directamente a través de API administradas o nativas.  
  
## <a name="enabling-resource-monitoring"></a>Habilitar la supervisión de recursos  
 ARM se puede habilitar de cuatro maneras: proporcionando un archivo de configuración cuando se inicia common language runtime (CLR), mediante el uso de no administrado API de hospedaje, mediante código administrado, o escuchando los eventos ETW de ARM.  
  
 Tan pronto como se habilita la ARM, comienza a recopilar datos en todos los dominios de aplicación en el proceso. Si un dominio de aplicación se creó antes de habilita la ARM, datos acumulados se inician cuando se habilita la ARM, no cuando se creó el dominio de aplicación. Una vez habilitada, no se puede deshabilitar ARM.  
  
-   Puede habilitar la ARM al iniciar el CLR agregando el [ \<appDomainResourceMonitoring >](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md) elemento en el archivo de configuración y el establecimiento la `enabled` atribuir a `true`. Un valor de `false` (el valor predeterminado) solo significa que no se habilita la ARM durante el inicio; puede activarla posteriormente mediante uno de los otros mecanismos de activación.  
  
-   El host puede habilitar la ARM solicitando la [ICLRAppDomainResourceMonitor](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interfaz de hospedaje. Una vez que esta interfaz se obtuvo correctamente, se habilita la ARM.  
  
-   Código administrado puede habilitar la ARM estableciendo el método estático (`Shared` en Visual Basic) <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> propiedad `true`. En cuanto se establece la propiedad, se habilita la ARM.  
  
-   Puede habilitar la ARM después del inicio escuchando los eventos ETW. ARM se habilita y comienza a generar eventos para todos los dominios de aplicación cuando se habilita el proveedor público `Microsoft-Windows-DotNETRuntime` mediante el uso de la `AppDomainResourceManagementKeyword` (palabra clave). Para correlacionar datos con dominios de aplicación y los subprocesos, debe habilitar también la `Microsoft-Windows-DotNETRuntimeRundown` proveedor con el `ThreadingKeyword` palabra clave.  
  
## <a name="using-arm"></a>Utilizar la ARM  
 ARM proporciona el tiempo de procesador total que se usa un dominio de aplicación y tres tipos de información sobre el uso de memoria.  
  
-   **Total de tiempo de procesador para un dominio de aplicación, en segundos**: Esto se calcula sumando los tiempos de los subprocesos notificados por el sistema operativo en todos los subprocesos que dedicaron tiempo a ejecutarse en el dominio de aplicación durante su duración. Bloqueada o subprocesos inactivos no usan el tiempo de procesador. Cuando un subproceso llama a código nativo, el tiempo que invierte en el subproceso en código nativo se incluye en el recuento para el dominio de aplicación donde se realiza la llamada.  
  
    -   API administrada: <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> propiedad.  
  
    -   API de hospedaje: [ICLRAppDomainResourceMonitor:: GetCurrentCpuTime](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md) método.  
  
    -   Eventos ETW: `ThreadCreated`, `ThreadAppDomainEnter`, y `ThreadTerminated` eventos. Para obtener información acerca de los proveedores y las palabras clave, vea "Eventos de supervisión de recursos de dominio de aplicación" en [eventos de ETW de CLR](../../../docs/framework/performance/clr-etw-events.md).  
  
-   **Total administrado las asignaciones realizadas por un dominio de aplicación durante su duración, en bytes**: las asignaciones totales no siempre reflejan el uso de memoria de un dominio de aplicación, porque los objetos asignados podrían ser de corta duración. Sin embargo, si una aplicación asigna y libera a grandes cantidades de objetos, el costo de las asignaciones podría ser significativo.  
  
    -   API administrada: <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> propiedad.  
  
    -   API de hospedaje: [ICLRAppDomainResourceMonitor:: GetCurrentAllocated](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md) método.  
  
    -   Eventos ETW: `AppDomainMemAllocated` eventos, `Allocated` campo.  
  
-   **Administra la memoria, expresado en bytes, que se hace referencia a un dominio de aplicación y que sobrevivieron a la última recolección completa de bloqueo**: este número es preciso solo después de una completa colección de bloqueo. (Esto es a diferencia de las recolecciones simultáneas, que se producen en segundo plano y no bloquea la aplicación). Por ejemplo, el <xref:System.GC.Collect?displayProperty=nameWithType> sobrecarga del método hace que una recolección completa de bloqueo.  
  
    -   API administrada: <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> propiedad.  
  
    -   API de hospedaje: [ICLRAppDomainResourceMonitor:: GetCurrentSurvived](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md) método `pAppDomainBytesSurvived` parámetro.  
  
    -   Eventos ETW: `AppDomainMemSurvived` eventos, `Survived` campo.  
  
-   **Total de memoria administrada, en bytes, que hace referencia el proceso y que sobrevivieron a la última recolección completa de bloqueo**: la memoria que sobrevivió para dominios de aplicación individuales se puede comparar con este número.  
  
    -   API administrada: <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType> propiedad.  
  
    -   API de hospedaje: [ICLRAppDomainResourceMonitor:: GetCurrentSurvived](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md) método `pTotalBytesSurvived` parámetro.  
  
    -   Eventos ETW: `AppDomainMemSurvived` eventos, `ProcessSurvived` campo.  
  
### <a name="determining-when-a-full-blocking-collection-occurs"></a>Determinar cuándo un completo, colección de bloqueo se produce  
 Para determinar cuándo son precisos los recuentos de memoria que sobrevivió, necesita saber cuándo solo se produce una recolección completa de bloqueo. El método para hacer esto depende de la API que se utiliza para examinar las estadísticas ARM.  
  
#### <a name="managed-api"></a>API administrada  
 Si utiliza las propiedades de la <xref:System.AppDomain> (clase), puede usar el <xref:System.GC.RegisterForFullGCNotification%2A?displayProperty=nameWithType> método para registrarse para recibir notificaciones de las recolecciones completas. El umbral que se utiliza no es importante, porque se está esperando la finalización de una colección en lugar de con el enfoque de una colección. A continuación, puede llamar a la <xref:System.GC.WaitForFullGCComplete%2A?displayProperty=nameWithType> método, que se bloquea hasta que haya completado una recolección completa. Puede crear un subproceso que llama al método en un bucle y realiza el análisis necesario cada vez que el método devuelve.  
  
 Como alternativa, puede llamar a la <xref:System.GC.CollectionCount%2A?displayProperty=nameWithType> método periódicamente para ver si ha aumentado el número de recolecciones de generación 2. Dependiendo de la frecuencia de sondeo, esta técnica podría no proporcionar tan precisa una indicación de la aparición de una recolección completa.  
  
#### <a name="hosting-api"></a>API de hospedaje  
 Si utiliza la API de hospedaje no administrada, el host debe pasar al CLR una implementación de la [IHostGCManager](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md) interfaz. CLR llama el [IHostGCManager:: SuspensionEnding](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md) método cuando reanuda la ejecución de subprocesos que se han suspendido durante una recolección se produce. El CLR pasa la generación de la recolección completada como un parámetro del método, por lo que el host puede determinar si la colección se completa o parcial. La implementación de la [IHostGCManager:: SuspensionEnding](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md) método puede consultar la memoria que sobrevivió, para asegurarse de que se recuperan los recuentos en cuanto se actualizan.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
 [ICLRAppDomainResourceMonitor (interfaz)](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [\<appDomainResourceMonitoring>](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)  
 [CLR ETW Events (Eventos ETW de CLR)](../../../docs/framework/performance/clr-etw-events.md)
