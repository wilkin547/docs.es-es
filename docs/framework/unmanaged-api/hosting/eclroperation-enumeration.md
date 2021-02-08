---
description: 'Más información sobre: EClrOperation (enumeración)'
title: EClrOperation (Enumeración)
ms.date: 03/30/2017
api_name:
- EClrOperation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrOperation
helpviewer_keywords:
- EClrOperation enumeration [.NET Framework hosting]
ms.assetid: 5aef6808-5aac-4b2f-a2c7-fee1575c55ed
topic_type:
- apiref
ms.openlocfilehash: 9f75762a400955b5f36fb2a337f283e36a32658c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785567"
---
# <a name="eclroperation-enumeration"></a>EClrOperation (Enumeración)

Describe el conjunto de operaciones para las que un host puede aplicar acciones de directiva.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|El host puede especificar acciones de directiva que deben realizarse cuando un <xref:System.AppDomain> se descarga de forma no estable (forzada).|  
|`OPR_AppDomainUnload`|El host puede especificar acciones de directiva que se deben realizar cuando <xref:System.AppDomain> se descarga un.|  
|`OPR_FinalizerRun`|El host puede especificar acciones de directiva que se realizarán cuando se ejecuten los finalizadores.|  
|`OPR_ProcessExit`|El host puede especificar acciones de directiva que se realizarán cuando se cierre el proceso.|  
|`OPR_ThreadAbort`|El host puede especificar acciones de directiva que se deben realizar cuando se anula un subproceso.|  
|`OPR_ThreadRudeAbortInCriticalRegion`|El host puede especificar acciones de directiva que se deben realizar cuando se produce una anulación de subproceso forzada en una región de código crítica.|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|El host puede especificar acciones de directiva que se deben realizar cuando se produce una anulación de subproceso forzada en una región de código no crítica.|  
  
## <a name="remarks"></a>Observaciones  

 La infraestructura de confiabilidad de Common Language Runtime (CLR) distingue entre anulaciones y errores de asignación de recursos que se producen en regiones críticas de código y las que se producen en regiones no críticas de código. Esta distinción está diseñada para permitir que los hosts establezcan diferentes directivas en función de dónde se produzca un error en el código.  
  
 Una *región crítica de código* es cualquier espacio en el que CLR no pueda garantizar que la anulación de una tarea o que no se pueda completar una solicitud de recursos afectará solo a la tarea actual. Por ejemplo, si una tarea está manteniendo un bloqueo y recibe un valor HRESULT que indica un error al realizar una solicitud de asignación de memoria, no basta con anular la tarea para garantizar la estabilidad de <xref:System.AppDomain> , ya que <xref:System.AppDomain> puede contener otras tareas que esperan el mismo bloqueo. Para abandonar la tarea actual, puede que esas otras tareas dejen de responder. En tal caso, el host necesita la capacidad de descargar todo <xref:System.AppDomain> en lugar de riesgo potencial de inestabilidad.  
  
 Una *región de código no crítica*, por otro lado, es una región en la que CLR puede garantizar que una anulación o un error solo afectará a la tarea en la que se produce el error.  
  
 CLR también distingue entre anulaciones correctas y no correctas (forzada). En general, una anulación normal o correcta realiza cada esfuerzo para ejecutar rutinas de control de excepciones y finalizadores antes de anular una tarea, mientras que una anulación forzada no realiza ninguna garantía.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [EClrFailure (Enumeración)](eclrfailure-enumeration.md)
- [EPolicyAction (Enumeración)](epolicyaction-enumeration.md)
- [ICLRPolicyManager (Interfaz)](iclrpolicymanager-interface.md)
- [IHostPolicyManager (Interfaz)](ihostpolicymanager-interface.md)
- [Enumeraciones para hosts](hosting-enumerations.md)
