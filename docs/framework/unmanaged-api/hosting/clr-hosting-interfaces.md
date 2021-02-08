---
description: 'Más información acerca de: interfaces de hospedaje de CLR'
title: Interfaces de hospedaje de CLR
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
ms.openlocfilehash: f42a74698607ffbed4a981f061d13ea4e9d634d8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799907"
---
# <a name="clr-hosting-interfaces"></a>Interfaces de hospedaje de CLR

En esta sección se describen las interfaces que los hosts no administrados pueden utilizar para integrar el Common Language Runtime (CLR) en sus aplicaciones. La información pertenece a la .NET Framework versión 2,0 y versiones posteriores. Estas interfaces permiten al host controlar muchos más aspectos del tiempo de ejecución que los que era posible en las versiones 1,0 y 1,1, y proporcionan una mayor integración entre CLR y el modelo de ejecución del host.  
  
 En la .NET Framework versión 1,0 y 1,1, el modelo de hospedaje habilitaba un host no administrado para cargar CLR en un proceso, para configurar determinadas opciones y para recibir notificaciones de eventos. Sin embargo, en general, el host y el CLR se ejecutaban de forma independiente en ese proceso. En la .NET Framework versión 2,0 y versiones posteriores, las nuevas capas de abstracción permiten que el host proporcione muchos de los recursos que proporcionan actualmente los tipos del ensamblado Win32 y que amplían el conjunto de capacidades que el host puede configurar.  
  
## <a name="in-this-section"></a>En esta sección  

 [IActionOnCLREvent (Interfaz)](iactiononclrevent-interface.md)  
 Proporciona un método que realiza una devolución de llamada para un evento registrado.  
  
 [IApartmentCallback (Interfaz)](iapartmentcallback-interface.md)  
 Proporciona métodos para crear devoluciones de llamada dentro de un contenedor.  
  
 [IAppDomainBinding (Interfaz)](iappdomainbinding-interface.md)  
 Proporciona métodos para establecer la configuración de tiempo de ejecución.  
  
 [ICatalogServices (Interfaz)](icatalogservices-interface.md)  
 Proporciona métodos para catalogar servicios. (Esta interfaz es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código).  
  
 [ICLRAssemblyIdentityManager (Interfaz)](iclrassemblyidentitymanager-interface.md)  
 Proporciona métodos que admiten la comunicación entre el host y el CLR acerca de los ensamblados.  
  
 [ICLRAssemblyReferenceList (Interfaz)](iclrassemblyreferencelist-interface.md)  
 Administra una lista de ensamblados cargados por el CLR y no por el host.  
  
 [ICLRControl (Interfaz)](iclrcontrol-interface.md)  
 Proporciona métodos para que el host obtenga acceso y configure varios aspectos de CLR.  
  
 [ICLRDebugManager (Interfaz)](iclrdebugmanager-interface.md)  
 Proporciona métodos que permiten a un host asociar un conjunto de tareas con un identificador y un nombre descriptivo.  
  
 [ICLRErrorReportingManager (Interfaz)](iclrerrorreportingmanager-interface.md)  
 Proporciona métodos que permiten al host configurar volcados de montón personalizados para el informe de errores.  
  
 [ICLRGCManager (Interfaz)](iclrgcmanager-interface.md)  
 Proporciona métodos que permiten a un host interactuar con el sistema de recolección de elementos no utilizados de CLR.  
  
 [ICLRHostBindingPolicyManager (Interfaz)](iclrhostbindingpolicymanager-interface.md)  
 Proporciona métodos para que el host evalúe y comunique los cambios en la información de la Directiva para los ensamblados.  
  
 [ICLRHostProtectionManager (Interfaz)](iclrhostprotectionmanager-interface.md)  
 Permite al host bloquear la ejecución de clases, métodos, propiedades y campos administrados específicos en código de confianza parcial.  
  
 [ICLRIoCompletionManager (Interfaz)](iclriocompletionmanager-interface.md)  
 Implementa un método de devolución de llamada que permite al host notificar a CLR el estado de las solicitudes de e/s especificadas.  
  
 [ICLRMemoryNotificationCallback (Interfaz)](iclrmemorynotificationcallback-interface.md)  
 Permite al host notificar las condiciones de presión de memoria mediante un enfoque similar al de la función de Win32 `CreateMemoryResourceNotification` .  
  
 [ICLROnEventManager (Interfaz)](iclroneventmanager-interface.md)  
 Proporciona métodos que permiten al host registrar y anular el registro de las devoluciones de llamada para los eventos CLR.  
  
 [ICLRPolicyManager (Interfaz)](iclrpolicymanager-interface.md)  
 Proporciona métodos que permiten al host especificar las acciones de directiva que deben realizarse en caso de que se produzcan errores y tiempos de espera.  
  
 [ICLRProbingAssemblyEnum (Interfaz)](iclrprobingassemblyenum-interface.md)  
 Proporciona métodos que permiten al host obtener las identidades de sondeo de un ensamblado mediante la información de identidad del ensamblado que es interna del CLR, sin necesidad de crear o comprender esa identidad.  
  
 [ICLRReferenceAssemblyEnum (Interfaz)](iclrreferenceassemblyenum-interface.md)  
 Proporciona métodos que permiten al host manipular el conjunto de ensamblados a los que hace referencia un archivo o una secuencia mediante datos de identidad de ensamblado internos a CLR, sin necesidad de crear o comprender esas identidades.  
  
 [ICLRRuntimeHost (Interfaz)](iclrruntimehost-interface.md)  
 Proporciona funciones similares a [ICorRuntimeHost](icorruntimehost-interface.md), con un método adicional para establecer la interfaz de control host.  
  
 [ICLRSyncManager (Interfaz)](iclrsyncmanager-interface.md)  
 Proporciona métodos para que el host obtenga información sobre las tareas solicitadas y para detectar interbloqueos en su implementación de sincronización.  
  
 [ICLRTask (Interfaz)](iclrtask-interface.md)  
 Proporciona métodos que permiten al host realizar solicitudes de CLR o proporcionar una notificación al CLR sobre la tarea asociada.  
  
 [ICLRTaskManager (Interfaz)](iclrtaskmanager-interface.md)  
 Proporciona métodos que permiten al host solicitar explícitamente que CLR cree una nueva tarea, obtener la tarea que se está ejecutando actualmente y establecer el idioma geográfico y la referencia cultural de la tarea.  
  
 [ICLRValidator (Interfaz)](iclrvalidator-interface.md)  
 Proporciona métodos para validar imágenes ejecutables portables (PE) y notificar errores de validación.  
  
 [ICorConfiguration (Interfaz)](icorconfiguration-interface.md)  
 Proporciona métodos para configurar CLR.  
  
 [ICorThreadpool (Interfaz)](icorthreadpool-interface.md)  
 Proporciona métodos para tener acceso al grupo de subprocesos.  
  
 [IDebuggerInfo (Interfaz)](idebuggerinfo-interface.md)  
 Proporciona métodos para obtener información sobre el estado de los servicios de depuración.  
  
 [IDebuggerThreadControl (Interfaz)](idebuggerthreadcontrol-interface.md)  
 Proporciona métodos para notificar al host el bloqueo y desbloqueo de subprocesos por parte de los servicios de depuración.  
  
 [IGCHost (Interfaz)](igchost-interface.md)  
 Proporciona métodos para obtener información sobre el sistema de recolección de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos no utilizados.  
  
 [IGCHost2 (Interfaz)](igchost2-interface.md)  
 Proporciona el método [setgcstartuplimitsex (](igchost2-setgcstartuplimitsex-method.md) que permite a un host establecer el tamaño del segmento de recolección de elementos no utilizados y el tamaño máximo de la generación cero del sistema de recolección de elementos no utilizados en valores mayores que `DWORD` .  
  
 [IGCHostControl (Interfaz)](igchostcontrol-interface.md)  
 Proporciona un método que permite al recolector de elementos no utilizados solicitar al host que cambie los límites de la memoria virtual.  
  
 [IGCThreadControl (Interfaz)](igcthreadcontrol-interface.md)  
 Proporciona métodos para participar en la programación de subprocesos que de otro modo se bloquearían para la recolección de elementos no utilizados.  
  
 [IHostAssemblyManager (Interfaz)](ihostassemblymanager-interface.md)  
 Proporciona métodos que permiten a un host especificar conjuntos de ensamblados que deben ser cargados por CLR o por el host.  
  
 [IHostAssemblyStore (Interfaz)](ihostassemblystore-interface.md)  
 Proporciona métodos que permiten a un host cargar ensamblados y módulos independientemente de CLR.  
  
 [IHostAutoEvent (Interfaz)](ihostautoevent-interface.md)  
 Proporciona una representación de un evento de restablecimiento automático implementado por el host.  
  
 [IHostControl (Interfaz)](ihostcontrol-interface.md)  
 Proporciona métodos para configurar la carga de ensamblados y para determinar qué interfaces de hospedaje admite el host.  
  
 [IHostCrst (Interfaz)](ihostcrst-interface.md)  
 Actúa como la representación del host de una sección crítica para el subprocesamiento.  
  
 [IHostGCManager (Interfaz)](ihostgcmanager-interface.md)  
 Proporciona métodos que notifican al host de eventos en el mecanismo de recolección de elementos no utilizados implementado por CLR.  
  
 [IHostIoCompletionManager (Interfaz)](ihostiocompletionmanager-interface.md)  
 Proporciona métodos que permiten a CLR interactuar con los puertos de finalización de e/s proporcionados por el host.  
  
 [IHostMalloc (Interfaz)](ihostmalloc-interface.md)  
 Proporciona métodos para que CLR solicite asignaciones específicas desde el montón a través del host.  
  
 [IHostManualEvent (Interfaz)](ihostmanualevent-interface.md)  
 Proporciona la implementación del host de una representación de un evento de restablecimiento manual.  
  
 [IHostMemoryManager (Interfaz)](ihostmemorymanager-interface.md)  
 Proporciona métodos para que CLR realice solicitudes de memoria virtual a través del host, en lugar de usar las funciones estándar de memoria virtual de Win32.  
  
 [IHostPolicyManager (Interfaz)](ihostpolicymanager-interface.md)  
 Proporciona métodos que notifican al host las acciones que CLR realiza en caso de anulaciones, tiempos de espera o errores.  
  
 [IHostSecurityContext (Interfaz)](ihostsecuritycontext-interface.md)  
 Permite que CLR mantenga la información de contexto de seguridad implementada por el host.  
  
 [IHostSecurityManager (Interfaz)](ihostsecuritymanager-interface.md)  
 Proporciona métodos que permiten el acceso y el control sobre el contexto de seguridad del subproceso que se está ejecutando actualmente.  
  
 [IHostSemaphore (Interfaz)](ihostsemaphore-interface.md)  
 Proporciona una representación de un semáforo implementado por el host.  
  
 [IHostSyncManager (Interfaz)](ihostsyncmanager-interface.md)  
 Proporciona métodos para que CLR cree primitivas de sincronización llamando al host, en lugar de usar las funciones de sincronización de Win32.  
  
 [IHostTask (Interfaz)](ihosttask-interface.md)  
 Proporciona métodos que permiten a CLR comunicarse con el host para administrar tareas.  
  
 [IHostTaskManager (Interfaz)](ihosttaskmanager-interface.md)  
 Proporciona métodos que permiten a CLR trabajar con tareas a través del host en lugar de usar las funciones de fibra o de subprocesos estándar del sistema operativo.  
  
 [IHostThreadPoolManager (Interfaz)](ihostthreadpoolmanager-interface.md)  
 Proporciona métodos para que CLR configure el grupo de subprocesos y pone en cola los elementos de trabajo en el grupo de subprocesos.  
  
 [IManagedObject (Interfaz)](imanagedobject-interface.md)  
 Proporciona métodos para controlar un objeto administrado.  
  
 IObjectHandle (  
 Proporciona un método para desempaquetar objetos de cálculo de referencias por valor desde el direccionamiento indirecto.  
  
 [ITypeName (Interfaz)](itypename-interface.md)  
 Proporciona métodos para obtener información sobre el nombre de tipo. (Esta interfaz es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código).  
  
 [ITypeNameBuilder (Interfaz)](itypenamebuilder-interface.md)  
 Proporciona métodos para generar un nombre de tipo. (Esta interfaz es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código).  
  
 [ITypeNameFactory (Interfaz)](itypenamefactory-interface.md)  
 Proporciona métodos para deconstruir un nombre de tipo. (Esta interfaz es compatible con la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código).  
  
 IValidator  
 Proporciona métodos para validar imágenes ejecutables portables (PE) y notificar errores de validación.  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Coclases e interfaces de hospedaje de CLR en desuso](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 Contiene temas que describen las interfaces de hospedaje proporcionadas en la .NET Framework versión 1,0 y 1,1.  
  
 [Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 Contiene temas que describen las interfaces de hospedaje proporcionadas en el .NET Framework 4.
