---
title: Enumeraciones para hosts
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged enumerations [.NET Framework], hosting
- enumerations [.NET Framework hosting]
- hosting enumerations [.NET Framework]
ms.assetid: e09131eb-1f7d-4f52-ae42-7393e9b62ef6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05fc295d394dca7a4f0edead64d326032958b070
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775186"
---
# <a name="hosting-enumerations"></a>Enumeraciones para hosts
Esta sección describen las enumeraciones no administradas que utiliza la API de hospedaje.  
  
## <a name="in-this-section"></a>En esta sección  
 [CLSID_RESOLUTION_FLAGS (enumeración)](../../../../docs/framework/unmanaged-api/hosting/clsid-resolution-flags-enumeration.md)  
 Contiene valores que indican el modo en que common language runtime (CLR) debe resolver un `CLSID`.  
  
 [COR_GC_STAT_TYPES (enumeración)](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)  
 Especifica las estadísticas que se registren para la recolección.  
  
 [COR_GC_THREAD_STATS_TYPES (enumeración)](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-types-enumeration.md)  
 Indica las estadísticas de la colección de elementos no utilizados para un subproceso.  
  
 [EApiCategories (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 Describe las categorías de funciones que puede bloquear el host que se ejecutan en el código de confianza parcial.  
  
 [EBindPolicyLevels (enumeración)](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md)  
 Proporciona marcas que especifican el nivel al que se va a aplicar o modificar la directiva de ensamblado.  
  
 [ECLRAssemblyIdentityFlags (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md)  
 Indica el tipo de identidad de un ensamblado.  
  
 [EClrEvent (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 Describe los eventos CLR para el que el host puede registrar devoluciones de llamada.  
  
 [EClrFailure (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 Describe el conjunto de errores para el que un host puede establecer acciones de directiva.  
  
 [EClrOperation (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 Describe el conjunto de operaciones para que un host puede aplicar acciones de directiva.  
  
 [EClrUnhandledException (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)  
 Describe las opciones disponibles para administrar las excepciones que no se controlan en código de usuario.  
  
 [EContextType (enumeración)](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)  
 Describe el contexto de seguridad del subproceso en ejecución actualmente.  
  
 [ECustomDumpFlavor (enumeración)](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)  
 Contiene valores que indican qué elementos desea incluir en un subconjunto de un montón personalizado de volcado de memoria al informar de errores.  
  
 [ECustomDumpItemKind (enumeración)](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 Reservado para la futura extensión de la [CustomDumpItem (estructura)](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) estructura.  
  
 [EHostApplicationPolicy (enumeración)](../../../../docs/framework/unmanaged-api/hosting/ehostapplicationpolicy-enumeration.md)  
 Indica cómo modificar un [IHostAssemblyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md) objeto de interfaz. Esta enumeración está desusada.  
  
 [EHostBindingPolicyModifyFlags (enumeración)](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md)  
 Permite al host especificar el tipo de redirección de que CLR debe realizar al aplicar las modificaciones de directiva de un ensamblado de origen a un ensamblado de destino.  
  
 [EInitializeNewDomainFlags (enumeración)](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)  
 Permite que el host proporcionar el tiempo de ejecución con información sobre la inicialización de un dominio de aplicación.  
  
 [EMemoryAvailable (enumeración)](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md)  
 Contiene valores que indican la cantidad de memoria física disponible en el equipo.  
  
 [EMemoryCriticalLevel (enumeración)](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md)  
 Contiene valores que indican el impacto de un error cuando se ha solicitado una asignación de memoria, pero no se puede satisfacer.  
  
 [EPolicyAction (enumeración)](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 Describe las acciones de directiva, el host puede establecer para las operaciones descritas por [EClrOperation (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) y los errores descritos por [EClrFailure (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).  
  
 [ESymbolReadingPolicy (enumeración)](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md)  
 Contiene valores que establecen la directiva para leer los archivos de programa (PDB) de la base de datos.  
  
 [ETaskType (enumeración)](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md)  
 Contiene valores que indican el tipo de tarea representada por un [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) o un [IHostTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) interfaz.  
  
 [HOST_TYPE (enumeración)](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md)  
 Contiene valores que especifican el tipo de host que está iniciando una aplicación.  
  
 [MALLOC_TYPE (enumeración)](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md)  
 Contiene valores que especifican las características de la memoria que se está asignando.  
  
 [METAHOST_CONFIG_FLAGS (enumeración)](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md)  
 Describe las posibles marcas devueltas en el `pdwConfigFlags` parámetro de la [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) método.  
  
 [METAHOST_POLICY_FLAGS (enumeración)](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)  
 Proporciona directivas de enlace que son comunes a la mayoría de los hosts en tiempo de ejecución.  
  
 [RUNTIME_INFO_FLAGS (enumeración)](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md)  
 Contiene valores que indican qué información acerca del entorno CLR se debe devolver.  
  
 [StackOverflowType (enumeración)](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md)  
 Contiene valores que indican la causa subyacente de un evento de desbordamiento de pila.  
  
 [STARTUP_FLAGS (enumeración)](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)  
 Contiene valores que indican el comportamiento de inicio de CLR.  
  
 [ValidatorFlags (enumeración)](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md)  
 Contiene valores que indican el tipo de validación que se debe realizar en una llamada a [método Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md).  
  
 [WAIT_OPTION (enumeración)](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)  
 Indica la acción que debe tomar un host si una operación solicitada por los bloques de CLR.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Coclases para el hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
  
 [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [Estructuras de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
