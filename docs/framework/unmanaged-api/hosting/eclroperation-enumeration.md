---
title: "EClrOperation (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EClrOperation
api_location: mscoree.dll
api_type: COM
f1_keywords: EClrOperation
helpviewer_keywords: EClrOperation enumeration [.NET Framework hosting]
ms.assetid: 5aef6808-5aac-4b2f-a2c7-fee1575c55ed
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 343ff04dba1a02660734beb726f9b895370a10af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="eclroperation-enumeration"></a>EClrOperation (Enumeración)
Describe el conjunto de operaciones para el que un host puede aplicar acciones de directiva.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum {  
    OPR_ThreadAbort,  
    OPR_ThreadRudeAbortInNonCriticalRegion,  
    OPR_ThreadRudeAbortInCriticalRegion,  
    OPR_AppDomainUnload,  
    OPR_AppDomainRudeUnload,  
    OPR_ProcessExit,  
    OPR_FinalizerRun  
} EClrOperation;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|El host puede especificar las acciones de la directiva para tener cuidado cuando un <xref:System.AppDomain> se descargan de forma no adecuada (forzada).|  
|`OPR_AppDomainUnload`|El host puede especificar las acciones de la directiva para tener cuidado cuando un <xref:System.AppDomain> se descarga.|  
|`OPR_FinalizerRun`|El host puede especificar acciones de directiva que se realizarán al ejecutar los finalizadores.|  
|`OPR_ProcessExit`|El host puede especificar acciones de directiva que se realizarán cuando termina el proceso.|  
|`OPR_ThreadAbort`|El host puede especificar acciones de directiva que se realizarán cuando se anula un subproceso.|  
|`OPR_ThreadRudeAbortInCriticalRegion`|El host puede especificar acciones de directiva que se realizarán cuando se produce una anulación de subproceso forzada en una región crítica del código.|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|El host puede especificar las acciones de directiva que se deben realizar cuando se produce una anulación de subproceso forzada en una región no crítica del código.|  
  
## <a name="remarks"></a>Comentarios  
 La infraestructura de confiabilidad de common language runtime (CLR) distingue entre las anulaciones y recursos errores de asignación que se producen en regiones críticas del código y las que se producen en regiones no críticas del código. Esta distinción está diseñada para permitir que los hosts establecer directivas distintas dependiendo de dónde se produce un error en el código.  
  
 A *región crítica del código* cualquier espacio donde el CLR no puede garantizar que si no se puede completar una solicitud de recursos afectará solo a la tarea actual o anulación de una tarea. Por ejemplo, si una tarea mantiene un bloqueo y recibe un valor HRESULT que indica un error al realizar una solicitud de asignación de memoria, es suficiente con anular la tarea para garantizar la estabilidad de la <xref:System.AppDomain>, porque el <xref:System.AppDomain> podría contener otros tareas que esperan el mismo bloqueo. Abandonar actual tarea es posible que las otras tareas deje de responder (o se bloquee) indefinidamente. En tal caso, el host necesita la capacidad de descargar todo el <xref:System.AppDomain> en lugar de riesgo potencial de inestabilidad.  
  
 A *región no crítica del código*, por otro lado, es una región donde CLR puede garantizar que una anulación o un error afectará solo a la tarea en la que se produce el error.  
  
 CLR también distingue entre anulaciones (forzadas) estable y no es correcta. En general, una anulación normal o correcta hace todo lo posible por ejecutar rutinas de control de excepciones y los finalizadores antes de anular una tarea, mientras que una anulación forzada no ofrece esas garantías.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [EClrFailure (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [EPolicyAction (enumeración)](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [ICLRPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [IHostPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
