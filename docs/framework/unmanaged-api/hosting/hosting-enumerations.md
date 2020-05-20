---
title: Enumeraciones para hosts
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged enumerations [.NET Framework], hosting
- enumerations [.NET Framework hosting]
- hosting enumerations [.NET Framework]
ms.assetid: e09131eb-1f7d-4f52-ae42-7393e9b62ef6
ms.openlocfilehash: e6fb22f91d57a356a9a7c3749e44a9fb3c36b699
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616117"
---
# <a name="hosting-enumerations"></a>Enumeraciones para hosts
En esta sección se describen las enumeraciones no administradas que utiliza la API de hospedaje.  
  
## <a name="in-this-section"></a>En esta sección  
 [CLSID_RESOLUTION_FLAGS (Enumeración)](clsid-resolution-flags-enumeration.md)  
 Contiene valores que indican cómo debe resolver el Common Language Runtime (CLR) `CLSID` .  
  
 [COR_GC_STAT_TYPES (enumeración)](cor-gc-stat-types-enumeration.md)  
 Especifica las estadísticas que se van a registrar para una recolección de elementos no utilizados.  
  
 [COR_GC_THREAD_STATS_TYPES (enumeración)](cor-gc-thread-stats-types-enumeration.md)  
 Indica las estadísticas de recolección de elementos no utilizados de un subproceso.  
  
 [EApiCategories (Enumeración)](eapicategories-enumeration.md)  
 Describe las categorías de funciones de las que el host puede bloquear la ejecución en código de confianza parcial.  
  
 [EBindPolicyLevels (Enumeración)](ebindpolicylevels-enumeration.md)  
 Proporciona marcas que especifican el nivel en el que se va a aplicar o modificar la Directiva de ensamblado.  
  
 [ECLRAssemblyIdentityFlags (Enumeración)](eclrassemblyidentityflags-enumeration.md)  
 Indica el tipo de la identidad de un ensamblado.  
  
 [EClrEvent (Enumeración)](eclrevent-enumeration.md)  
 Describe los eventos de CLR para los que el host puede registrar devoluciones de llamada.  
  
 [EClrFailure (Enumeración)](eclrfailure-enumeration.md)  
 Describe el conjunto de errores para los que un host puede establecer acciones de directiva.  
  
 [EClrOperation (Enumeración)](eclroperation-enumeration.md)  
 Describe el conjunto de operaciones para las que un host puede aplicar acciones de directiva.  
  
 [EClrUnhandledException (Enumeración)](eclrunhandledexception-enumeration.md)  
 Describe las opciones disponibles para administrar excepciones que no se controlan en el código de usuario.  
  
 [EContextType (Enumeración)](econtexttype-enumeration.md)  
 Describe el contexto de seguridad del subproceso que se está ejecutando actualmente.  
  
 [ECustomDumpFlavor (Enumeración)](ecustomdumpflavor-enumeration.md)  
 Contiene valores que indican qué elementos se van a incluir en un subconjunto personalizado de un volcado del montón cuando se notifican errores.  
  
 [ECustomDumpItemKind (Enumeración)](ecustomdumpitemkind-enumeration.md)  
 Reservado para la extensión futura de la estructura de [estructura customdumpitem (](customdumpitem-structure.md) .  
  
 [EHostApplicationPolicy (Enumeración)](ehostapplicationpolicy-enumeration.md)  
 Indica cómo modificar un objeto de interfaz de [interfaz IHostAssemblyManager](ihostassemblymanager-interface.md) . Esta enumeración está en desuso.  
  
 [EHostBindingPolicyModifyFlags (Enumeración)](ehostbindingpolicymodifyflags-enumeration.md)  
 Permite al host especificar el tipo de redirección que debe realizar CLR al aplicar modificaciones de directiva de un ensamblado de origen a un ensamblado de destino.  
  
 [EInitializeNewDomainFlags (Enumeración)](einitializenewdomainflags-enumeration.md)  
 Permite al host proporcionar información sobre la inicialización de un dominio de aplicación en el tiempo de ejecución.  
  
 [EMemoryAvailable (Enumeración)](ememoryavailable-enumeration.md)  
 Contiene valores que indican la cantidad de memoria física disponible en el equipo.  
  
 [EMemoryCriticalLevel (Enumeración)](ememorycriticallevel-enumeration.md)  
 Contiene valores que indican el impacto de un error cuando se ha solicitado una determinada asignación de memoria, pero no se puede satisfacer.  
  
 [EPolicyAction (Enumeración)](epolicyaction-enumeration.md)  
 Describe las acciones de directiva que el host puede establecer para las operaciones descritas por la [enumeración de EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) y los errores descritos por la [enumeración eclrfailure (](eclrfailure-enumeration.md).  
  
 [ESymbolReadingPolicy (Enumeración)](esymbolreadingpolicy-enumeration.md)  
 Contiene valores que establecen la Directiva para leer archivos de base de datos de programa (PDB).  
  
 [ETaskType (Enumeración)](etasktype-enumeration.md)  
 Contiene valores que indican el tipo de tarea representada por una [interfaz ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) o una interfaz de [interfaz IHostTask](ihosttask-interface.md) .  
  
 [HOST_TYPE (Enumeración)](host-type-enumeration.md)  
 Contiene valores que especifican el tipo de host que está iniciando una aplicación.  
  
 [MALLOC_TYPE (enumeración)](malloc-type-enumeration.md)  
 Contiene valores que especifican las características de la memoria que se va a asignar.  
  
 [METAHOST_CONFIG_FLAGS (Enumeración)](metahost-config-flags-enumeration.md)  
 Describe las posibles marcas devueltas en el `pdwConfigFlags` parámetro del método [ICLRMetaHostPolicy:: GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) .  
  
 [METAHOST_POLICY_FLAGS (Enumeración)](metahost-policy-flags-enumeration.md)  
 Proporciona directivas de enlace que son comunes a la mayoría de los hosts en tiempo de ejecución.  
  
 [RUNTIME_INFO_FLAGS (Enumeración)](runtime-info-flags-enumeration.md)  
 Contiene valores que indican qué información sobre el CLR se debe devolver.  
  
 [StackOverflowType (Enumeración)](stackoverflowtype-enumeration.md)  
 Contiene valores que indican la causa subyacente de un evento de desbordamiento de pila.  
  
 [STARTUP_FLAGS (Enumeración)](startup-flags-enumeration.md)  
 Contiene valores que indican el comportamiento de inicio de CLR.  
  
 [ValidatorFlags (Enumeración)](validatorflags-enumeration.md)  
 Contiene valores que indican el tipo de validación que se debe realizar en una llamada al [método Validate](iclrvalidator-validate-method.md).  
  
 [WAIT_OPTION (Enumeración)](wait-option-enumeration.md)  
 Indica la acción que debe realizar un host si se bloquea una operación solicitada por CLR.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Coclases para el hospedaje](hosting-coclasses.md)  
  
 [Interfaces de hospedaje](hosting-interfaces.md)  
  
 [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)  
  
 [Estructuras de hospedaje](hosting-structures.md)
