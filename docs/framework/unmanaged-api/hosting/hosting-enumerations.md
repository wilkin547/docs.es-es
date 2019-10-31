---
title: Enumeraciones para hosts
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged enumerations [.NET Framework], hosting
- enumerations [.NET Framework hosting]
- hosting enumerations [.NET Framework]
ms.assetid: e09131eb-1f7d-4f52-ae42-7393e9b62ef6
ms.openlocfilehash: 67a3617335db395b9d8f43c804c4eda65894723b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127003"
---
# <a name="hosting-enumerations"></a>Enumeraciones para hosts
En esta sección se describen las enumeraciones no administradas que utiliza la API de hospedaje.  
  
## <a name="in-this-section"></a>En esta sección  
 [CLSID_RESOLUTION_FLAGS (enumeración)](../../../../docs/framework/unmanaged-api/hosting/clsid-resolution-flags-enumeration.md)  
 Contiene valores que indican cómo el Common Language Runtime (CLR) debe resolver un `CLSID`.  
  
 [COR_GC_STAT_TYPES (enumeración)](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)  
 Especifica las estadísticas que se van a registrar para una recolección de elementos no utilizados.  
  
 [COR_GC_THREAD_STATS_TYPES (enumeración)](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-types-enumeration.md)  
 Indica las estadísticas de recolección de elementos no utilizados de un subproceso.  
  
 [EApiCategories (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 Describe las categorías de funciones de las que el host puede bloquear la ejecución en código de confianza parcial.  
  
 [EBindPolicyLevels (enumeración)](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md)  
 Proporciona marcas que especifican el nivel en el que se va a aplicar o modificar la Directiva de ensamblado.  
  
 [ECLRAssemblyIdentityFlags (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md)  
 Indica el tipo de la identidad de un ensamblado.  
  
 [EClrEvent (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 Describe los eventos de CLR para los que el host puede registrar devoluciones de llamada.  
  
 [EClrFailure (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 Describe el conjunto de errores para los que un host puede establecer acciones de directiva.  
  
 [EClrOperation (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 Describe el conjunto de operaciones para las que un host puede aplicar acciones de directiva.  
  
 [EClrUnhandledException (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)  
 Describe las opciones disponibles para administrar excepciones que no se controlan en el código de usuario.  
  
 [EContextType (enumeración)](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)  
 Describe el contexto de seguridad del subproceso que se está ejecutando actualmente.  
  
 [ECustomDumpFlavor (enumeración)](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)  
 Contiene valores que indican qué elementos se van a incluir en un subconjunto personalizado de un volcado del montón cuando se notifican errores.  
  
 [ECustomDumpItemKind (enumeración)](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 Reservado para la extensión futura de la estructura de [estructura customdumpitem (](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) .  
  
 [EHostApplicationPolicy (enumeración)](../../../../docs/framework/unmanaged-api/hosting/ehostapplicationpolicy-enumeration.md)  
 Indica cómo modificar un objeto de interfaz de [interfaz IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md) . Esta enumeración está en desuso.  
  
 [EHostBindingPolicyModifyFlags (enumeración)](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md)  
 Permite al host especificar el tipo de redirección que debe realizar CLR al aplicar modificaciones de directiva de un ensamblado de origen a un ensamblado de destino.  
  
 [EInitializeNewDomainFlags (enumeración)](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)  
 Permite al host proporcionar información sobre la inicialización de un dominio de aplicación en el tiempo de ejecución.  
  
 [EMemoryAvailable (enumeración)](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md)  
 Contiene valores que indican la cantidad de memoria física disponible en el equipo.  
  
 [EMemoryCriticalLevel (enumeración)](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md)  
 Contiene valores que indican el impacto de un error cuando se ha solicitado una determinada asignación de memoria, pero no se puede satisfacer.  
  
 [EPolicyAction (enumeración)](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 Describe las acciones de directiva que el host puede establecer para las operaciones descritas por la [enumeración de EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) y los errores descritos por la [enumeración eclrfailure (](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).  
  
 [ESymbolReadingPolicy (enumeración)](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md)  
 Contiene valores que establecen la Directiva para leer archivos de base de datos de programa (PDB).  
  
 [ETaskType (enumeración)](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md)  
 Contiene valores que indican el tipo de tarea representada por una [interfaz ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) o una interfaz de [interfaz IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) .  
  
 [HOST_TYPE (enumeración)](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md)  
 Contiene valores que especifican el tipo de host que está iniciando una aplicación.  
  
 [MALLOC_TYPE (enumeración)](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md)  
 Contiene valores que especifican las características de la memoria que se va a asignar.  
  
 [METAHOST_CONFIG_FLAGS (enumeración)](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md)  
 Describe las posibles marcas devueltas en el parámetro `pdwConfigFlags` del método [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) .  
  
 [METAHOST_POLICY_FLAGS (enumeración)](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)  
 Proporciona directivas de enlace que son comunes a la mayoría de los hosts en tiempo de ejecución.  
  
 [RUNTIME_INFO_FLAGS (enumeración)](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md)  
 Contiene valores que indican qué información sobre el CLR se debe devolver.  
  
 [StackOverflowType (enumeración)](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md)  
 Contiene valores que indican la causa subyacente de un evento de desbordamiento de pila.  
  
 [STARTUP_FLAGS (enumeración)](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)  
 Contiene valores que indican el comportamiento de inicio de CLR.  
  
 [ValidatorFlags (enumeración)](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md)  
 Contiene valores que indican el tipo de validación que se debe realizar en una llamada al [método Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md).  
  
 [WAIT_OPTION (enumeración)](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)  
 Indica la acción que debe realizar un host si se bloquea una operación solicitada por CLR.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Coclases para el hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
  
 [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [Estructuras de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
