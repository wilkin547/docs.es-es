---
title: Interfaces de hospedaje de CLR
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03839a2c6e52f9d2dcdd2e0941ff4fdbeb8a3a17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="clr-hosting-interfaces"></a>Interfaces de hospedaje de CLR
Esta sección describen las interfaces que no administrada de hosts pueden usar para integrar common language runtime (CLR) en sus aplicaciones. La información pertenece a la versión de .NET Framework 2.0 y versiones posteriores. Estas interfaces permiten al host controlar muchos más aspectos del tiempo de ejecución que era posible en las versiones 1.0 y 1.1 y proporcionan mucho una mayor integración entre CLR y el modelo de ejecución del host.  
  
 En la versión 1.0 y 1.1 de .NET Framework, el modelo de hospedaje habilita un host no administrado cargar CLR en un proceso, para configurar ciertas opciones de configuración y para recibir notificaciones de eventos. Sin embargo, en general, el host y CLR se ejecutaban por separado en ese proceso. En la versión de .NET Framework 2.0 y versiones posteriores, nuevas capas de abstracción permiten al host proporcionar muchos de los recursos proporcionados actualmente por los tipos del ensamblado de Win32 y ampliar el conjunto de funciones que puede configurar el host.  
  
## <a name="in-this-section"></a>En esta sección  
 [IActionOnCLREvent (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 Proporciona un método que realiza una devolución de llamada para un evento registrado.  
  
 [IApartmentCallback (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)  
 Proporciona métodos para hacer que las devoluciones de llamada dentro de un apartamento.  
  
 [IAppDomainBinding (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)  
 Proporciona métodos para establecer la configuración de tiempo de ejecución.  
  
 [ICatalogServices (interfaz)](../../../../docs/framework/unmanaged-api/hosting/icatalogservices-interface.md)  
 Proporciona métodos para servicios de catálogo. (Esta interfaz admite la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código).  
  
 [ICLRAssemblyIdentityManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 Proporciona métodos que admiten la comunicación entre el host y CLR acerca de los ensamblados.  
  
 [ICLRAssemblyReferenceList (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 Administra una lista de ensamblados que se cargan en el CLR y no por el host.  
  
 [ICLRControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 Proporciona métodos para el host obtener acceso a y configurar varios aspectos de CLR.  
  
 [ICLRDebugManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 Proporciona métodos que permiten a un host asociar un conjunto de tareas a un identificador y un nombre descriptivo.  
  
 [ICLRErrorReportingManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 Proporciona métodos que permiten al host configurar los volcados del montón personalizados para el informe de errores.  
  
 [ICLRGCManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 Proporciona métodos que permiten al host interactuar con el sistema de recopilación de elementos no utilizados de CLR.  
  
 [ICLRHostBindingPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 Proporciona métodos para el host evaluar y comunicar los cambios en la información de directiva para los ensamblados.  
  
 [ICLRHostProtectionManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 Permite al host bloquear clases administradas específicas, métodos, propiedades y campos de ejecución en el código de confianza parcial.  
  
 [ICLRIoCompletionManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 Implementa un método de devolución de llamada que permite al host informar a CLR del estado de las solicitudes de E/S especificados.  
  
 [ICLRMemoryNotificationCallback (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 Permite que el host para situaciones de presión de memoria de informe mediante un enfoque similar de Win32 `CreateMemoryResourceNotification` función.  
  
 [ICLROnEventManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 Proporciona métodos que permiten al host registrar y anular el registro de las devoluciones de llamada para los eventos CLR.  
  
 [ICLRPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 Proporciona métodos que permiten al host especificar acciones de directiva que se realizarán en el caso de errores y tiempos de espera.  
  
 [ICLRProbingAssemblyEnum (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 Proporciona métodos que permiten al host obtener las identidades de sondeo de un ensamblado mediante el uso de información de identidad del ensamblado que es interna de CLR, sin necesidad de crear o reconocer dicha identidad.  
  
 [ICLRReferenceAssemblyEnum (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)  
 Proporciona métodos que permiten al host manipular el conjunto de ensamblados que se hace referencia a un archivo o una secuencia utilizando los datos de identidad de ensamblado que están internas de CLR, sin necesidad de crear o entender dichas identidades.  
  
 [ICLRRuntimeHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 Proporciona funciones similares a [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), con un método adicional para establecer la interfaz de control de host.  
  
 [ICLRSyncManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 Proporciona métodos para el host para obtener información sobre las tareas solicitadas y detectar interbloqueos en su implementación de la sincronización.  
  
 [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 Proporciona métodos que permiten al host para realizar solicitudes de CLR o para proporcionar una notificación a CLR de la tarea asociada.  
  
 [ICLRTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 Proporciona métodos que permiten al host solicitar explícitamente que CLR cree una nueva tarea, obtener la tarea que se está ejecuta actualmente y establecer el idioma geográfico y la referencia cultural para la tarea.  
  
 [ICLRValidator (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)  
 Proporciona métodos para validar imágenes portables de ejecutable (PE) e informar de errores de validación.  
  
 [ICorConfiguration (interfaz)](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)  
 Proporciona métodos para configurar el CLR.  
  
 [ICorThreadpool (interfaz)](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)  
 Proporciona métodos para tener acceso el grupo de subprocesos.  
  
 [IDebuggerInfo (interfaz)](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)  
 Proporciona métodos para obtener información sobre el estado de los servicios de depuración.  
  
 [IDebuggerThreadControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)  
 Proporciona métodos para notificar al host el bloqueo y desbloqueo de subprocesos por los servicios de depuración.  
  
 [IGCHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)  
 Proporciona métodos para obtener información sobre el sistema de recopilación de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos.  
  
 [IGCHost2 (interfaz)](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)  
 Proporciona el [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) método que permite a un host establecer el tamaño del segmento de recopilación de elementos no utilizados y el tamaño máximo de generación cero del sistema de recopilación de elementos no utilizados en valores mayor `DWORD`.  
  
 [IGCHostControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)  
 Proporciona un método que permite que el recolector de elementos no utilizados solicitar al host que cambie los límites de memoria virtual.  
  
 [IGCThreadControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)  
 Proporciona métodos para participar en la programación de subprocesos que de lo contrario se bloquearía para la recolección.  
  
 [IHostAssemblyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 Proporciona métodos que permiten a un host especificar los conjuntos de ensamblados que se deben cargar CLR o el host.  
  
 [IHostAssemblyStore (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 Proporciona métodos que permiten a un host cargar ensamblados y módulos con independencia de CLR.  
  
 [IHostAutoEvent (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 Proporciona una representación de un evento de restablecimiento automático implementado por el host.  
  
 [IHostControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 Proporciona métodos para configurar la carga de ensamblados y para determinar qué interfaces de hospedaje admite el host.  
  
 [IHostCrst (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 Actúa como la representación del host de una sección crítica para el subprocesamiento.  
  
 [IHostGCManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
 Proporciona métodos que notifican al host de eventos en el mecanismo de recopilación de elementos no utilizados implementado por CLR.  
  
 [IHostIoCompletionManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 Proporciona métodos que permiten a CLR interactuar con los puertos de finalización de E/S proporcionados por el host.  
  
 [IHostMalloc (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 Proporciona métodos para el CLR debe solicitar asignaciones concretas del montón a través del host.  
  
 [IHostManualEvent (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 Proporciona la implementación del host de una representación de un evento de restablecimiento manual.  
  
 [IHostMemoryManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 Proporciona métodos para el CLR realizar solicitudes de memoria virtual a través del host, en lugar de utilizar las funciones estándar de memoria virtual de Win32.  
  
 [IHostPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 Proporciona métodos que notifican al host de las acciones que CLR realiza en caso de anulaciones, tiempos de espera o errores.  
  
 [IHostSecurityContext (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 Permite que el CLR para conservar la información de contexto de seguridad implementado por el host.  
  
 [IHostSecurityManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 Proporciona métodos que permiten el acceso a y controlan sobre el contexto de seguridad del subproceso actualmente en ejecución.  
  
 [IHostSemaphore (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 Proporciona una representación de un semáforo implementado por el host.  
  
 [IHostSyncManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 Proporciona métodos para el CLR crear a las primitivas de sincronización llamando al host, en lugar de utilizar las funciones de sincronización de Win32.  
  
 [IHostTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 Proporciona métodos que permiten a CLR para comunicarse con el host para administrar las tareas.  
  
 [IHostTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 Proporciona métodos que permiten a CLR trabajar con tareas a través del host en lugar de utilizar las funciones de sistema operativo estándar de subprocesos o fibras.  
  
 [IHostThreadPoolManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 Proporciona métodos para el CLR para configurar el grupo de subprocesos y poner en cola los elementos de trabajo al grupo de subprocesos.  
  
 [IManagedObject (interfaz)](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)  
 Proporciona métodos para controlar un objeto administrado.  
  
 "IObjectHandle"  
 Proporciona un método para desencapsular objetos de cálculo de referencias por valor de direccionamiento indirecto.  
  
 [ITypeName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/itypename-interface.md)  
 Proporciona métodos para obtener información de nombre de tipo. (Esta interfaz admite la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código).  
  
 [ITypeNameBuilder (interfaz)](../../../../docs/framework/unmanaged-api/hosting/itypenamebuilder-interface.md)  
 Proporciona métodos para crear un nombre de tipo. (Esta interfaz admite la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código).  
  
 [ITypeNameFactory (interfaz)](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)  
 Proporciona métodos para anular la construcción un nombre de tipo. (Esta interfaz admite la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código).  
  
 "IValidator"  
 Proporciona métodos para validar imágenes portables de ejecutable (PE) e informar de errores de validación.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Coclases e interfaces de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 Contiene temas que describen las interfaces de hospedaje proporcionadas en la versión 1.0 y 1.1 de .NET Framework.  
  
 [Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 Contiene temas que describen las interfaces de hospedaje proporcionadas en el [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].
