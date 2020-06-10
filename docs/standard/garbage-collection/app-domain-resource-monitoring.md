---
title: Supervisión de recursos de dominio de aplicación
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- monitoring managed memory use by application domain
- application domains, memory use
- memory use, monitoring
- application domains, resource monitoring
ms.assetid: 318bedf8-7f35-4f00-b34a-2b7b8e3fa315
ms.openlocfilehash: 12dfdd3ac6d75a3e2a33f93d8847c963ded912e8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286098"
---
# <a name="application-domain-resource-monitoring"></a>Supervisión de recursos de dominio de aplicación

La supervisión de recursos de dominio de aplicación (ARM) permite a los hosts supervisar el uso de CPU y de memoria por parte del dominio de aplicación. Esto es útil para los hosts como ASP.NET que utilizan varios dominios de aplicación en un proceso de ejecución prolongada. El host puede descargar el dominio de aplicación de una aplicación que afecta negativamente al rendimiento de todo el proceso, pero solo si puede identificar la aplicación problemática. ARM proporciona información que puede usarse para ayudar a tomar estas decisiones.

Por ejemplo, un servicio de hospedaje podría tener muchas aplicaciones que se ejecutan en un servidor ASP.NET. Si una aplicación del proceso empieza a consumir demasiada memoria o demasiado tiempo de procesador, el servicio de hospedaje puede usar ARM para identificar el dominio de aplicación que causa el problema.

ARM es lo bastante ligero para utilizarlo en aplicaciones dinámicas. Puede acceder a la información mediante el uso del Seguimiento de eventos para Windows (ETW) o directamente a través de API administradas o nativas.

## <a name="enabling-resource-monitoring"></a>Habilitación de la supervisión de recursos

ARM se puede habilitar de cuatro maneras: proporcionando un archivo de configuración cuando se inicia Common Language Runtime (CLR), mediante el uso de API de hospedaje no administradas, mediante código administrado o escuchando los eventos ETW de ARM.

En cuanto se habilita ARM, comienza a recopilar datos en todos los dominios de aplicación del proceso. Si un dominio de aplicación se creó antes de habilitar ARM, los datos acumulativos se inician cuando se habilita ARM, no cuando se creó el dominio de aplicación. Una vez habilitado ARM, no se puede deshabilitar.

- Puede habilitar ARM al iniciar el CLR agregando el elemento [\<appDomainResourceMonitoring>](../../framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md) al archivo de configuración y estableciendo el atributo `enabled` en `true`. Un valor de `false` (el valor predeterminado) solo significa que no se habilita ARM durante el inicio; puede activarlo posteriormente mediante uno de los otros mecanismos de activación.

- El host puede habilitar ARM solicitando la interfaz de hospedaje [ICLRAppDomainResourceMonitor](../../framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md). Una vez que esta interfaz se obtiene correctamente, se habilita ARM.

- El código administrado puede habilitar ARM estableciendo la propiedad estática <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> (`Shared` en Visual Basic) en `true`. En cuanto se establece la propiedad, se habilita ARM.

- Puede habilitar ARM después del inicio escuchando los eventos ETW. ARM se habilita y comienza a generar eventos para todos los dominios de aplicación cuando se habilita el proveedor público `Microsoft-Windows-DotNETRuntime` mediante el uso de la palabra clave `AppDomainResourceManagementKeyword`. Para correlacionar datos con dominios de aplicación y subprocesos, debe habilitar también el proveedor `Microsoft-Windows-DotNETRuntimeRundown` con la palabra clave `ThreadingKeyword`.

## <a name="using-arm"></a>Uso de ARM

ARM proporciona el tiempo de procesador total que un dominio de aplicación usa y tres tipos de información sobre el uso de memoria.

- **Total de tiempo de procesador para un dominio de aplicación, en segundos**: esto se calcula con la suma de los tiempos de los subprocesos notificados por el sistema operativo en todos los subprocesos que dedicaron tiempo a ejecutarse en el dominio de aplicación durante su vigencia. Los subprocesos bloqueados o inactivos no usan tiempo de procesador. Cuando un subproceso llama a código nativo, el tiempo que el subproceso emplea en el código nativo se incluye en el recuento del dominio de aplicación donde se realizó la llamada.

  - API administrada: propiedad <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>.

  - API de hospedaje: método [ICLRAppDomainResourceMonitor::GetCurrentCpuTime](../../framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md).

  - Eventos ETW: eventos `ThreadCreated`, `ThreadAppDomainEnter` y `ThreadTerminated`. Para obtener información sobre los proveedores y las palabras clave, vea "Eventos de supervisión de recursos de dominio de aplicación" en [Eventos ETW de CLR](../../framework/performance/clr-etw-events.md).

- **Asignaciones administradas totales realizadas por un dominio de aplicación durante su vigencia, en bytes**: el total de asignaciones no siempre refleja la memoria que usa un dominio de aplicación, porque los objetos asignados pueden ser de corta duración. Sin embargo, si una aplicación asigna y libera grandes cantidades de objetos, el costo de las asignaciones podría ser significativo.

  - API administrada: propiedad <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>.

  - API de hospedaje: método [ICLRAppDomainResourceMonitor::GetCurrentAllocated](../../framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md).

  - Eventos ETW: evento `AppDomainMemAllocated`, campo `Allocated`.

- **Memoria administrada, en bytes, a la que hace referencia un dominio de aplicación y que ha sobrevivido a la colección con bloqueo completo más reciente**: este número es preciso solo después de una colección con bloqueo completo. (Esto difiere de las colecciones simultáneas, que se producen en segundo plano y no bloquean la aplicación). Por ejemplo, la sobrecarga del método <xref:System.GC.Collect?displayProperty=nameWithType> genera una colección con bloqueo completo.

  - API administrada: propiedad <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>.

  - API de hospedaje: método [ICLRAppDomainResourceMonitor::GetCurrentSurvived](../../framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md), parámetro `pAppDomainBytesSurvived`.

  - Eventos ETW: evento `AppDomainMemSurvived`, campo `Survived`.

- **Total de memoria administrada, en bytes, a la que hace referencia el proceso cuya duración va más allá de la colección con bloqueo completo más reciente**: la memoria de duración superior para los dominios de aplicación individuales se puede comparar con este número.

  - API administrada: propiedad <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>.

  - API de hospedaje: método [ICLRAppDomainResourceMonitor::GetCurrentSurvived](../../framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md), parámetro `pTotalBytesSurvived`.

  - Eventos ETW: evento `AppDomainMemSurvived`, campo `ProcessSurvived`.

### <a name="determining-when-a-full-blocking-collection-occurs"></a>Determinación de la ocurrencia de una colección con bloqueo completo

Para determinar cuándo son precisos los recuentos de memoria de mayor duración, es necesario saber cuándo se produce una colección con bloqueo completo. El método para hacer esto depende de la API que se utiliza para examinar las estadísticas de ARM.

#### <a name="managed-api"></a>API administrada

Si usa las propiedades de la clase <xref:System.AppDomain>, puede usar el método <xref:System.GC.RegisterForFullGCNotification%2A?displayProperty=nameWithType> para registrar la notificación de las colecciones completas. El umbral utilizado no es importante, ya que se espera a la finalización de una colección y no al enfoque de una colección. A continuación, puede llamar al método <xref:System.GC.WaitForFullGCComplete%2A?displayProperty=nameWithType>, que se bloquea hasta que finaliza una colección completa. Puede crear un subproceso que llame al método en un bucle y que realice cualquier análisis necesario de lo que el método devuelve.

Como alternativa, puede llamar al método <xref:System.GC.CollectionCount%2A?displayProperty=nameWithType> periódicamente para ver si ha aumentado el número de colecciones de generación 2. Dependiendo de la frecuencia de sondeo, esta técnica podría no proporcionar una indicación lo suficientemente precisa de la ocurrencia de una colección completa.

#### <a name="hosting-api"></a>API de hospedaje

Si utiliza la API de hospedaje no administrada, el host debe pasar al CLR una implementación de la interfaz [IHostGCManager](../../framework/unmanaged-api/hosting/ihostgcmanager-interface.md). El CLR llama al método [IHostGCManager::SuspensionEnding](../../framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md) cuando reanuda la ejecución de los subprocesos suspendidos durante la ocurrencia de una colección. El CLR pasa la generación de la colección completada como un parámetro del método, por lo que el host puede determinar si la colección se completó de forma total o parcial. La implementación del método [IHostGCManager::SuspensionEnding](../../framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md) puede consultar la memoria de duración superior, a fin de garantizar la recuperación de los recuentos en cuando se actualizan.

## <a name="see-also"></a>Vea también

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [ICLRAppDomainResourceMonitor (interfaz)](../../framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [\<appDomainResourceMonitoring>](../../framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [CLR ETW Events (Eventos ETW de CLR)](../../framework/performance/clr-etw-events.md)
