---
title: ICLRPolicyManager::SetDefaultAction (Método)
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetDefaultAction
helpviewer_keywords:
- SetDefaultAction method [.NET Framework hosting]
- ICLRPolicyManager::SetDefaultAction method [.NET Framework hosting]
ms.assetid: f9411e7a-27df-451f-9f6c-d643d6a7a7ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d339fbadc3260d20fac848ad7f1a9031c3443aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154666"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a>ICLRPolicyManager::SetDefaultAction (Método)
Especifica la acción de directiva que common language runtime (CLR) debe realizar cuando se produce la operación especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `operation`  
 [in] Uno de los [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valores, que indica la acción de CLR que se debe personalizar el comportamiento.  
  
 `action`  
 [in] Uno de los [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valores, que indica la acción de directiva, el CLR debe tomar cuando `operation` se produce.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`SetDefaultAction` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada ha agotado el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.|  
|E_FAIL|Se ha producido un error irrecuperable desconocido. Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|No es válido `action` se especificó para el `operation`, o se ha proporcionado un valor no válido para `operation`.|  
  
## <a name="remarks"></a>Comentarios  
 No todos los valores de acción de la directiva pueden especificarse como el comportamiento predeterminado para las operaciones de CLR. `SetDefaultAction` Normalmente se usa solo para escalar el comportamiento. Por ejemplo, un host puede especificar que las anulaciones de subprocesos se conviertan en anulaciones anulaciones de subprocesos, pero no se especifique lo contrario. La siguiente tabla describe los válido `action` valores para cada posible `operation` valor.  
  
|Valor de `operation`|Valores válidos para `action`|  
|---------------------------|-------------------------------|  
|OPR_ThreadAbort|-   eAbortThread<br />-   eRudeAbortThread<br />-   eUnloadAppDomain<br />-   eRudeUnloadAppDomain<br />-   eExitProcess<br />-   eFastExitProcess<br />-   eRudeExitProcess<br />-   eDisableRuntime|  
|OPR_ThreadRudeAbortInNonCriticalRegion<br /><br /> OPR_ThreadRudeAbortInCriticalRegion|-   eRudeAbortThread<br />-   eUnloadAppDomain<br />-   eRudeUnloadAppDomain<br />-   eExitProcess<br />-   eFastExitProcess<br />-   eRudeExitProcess<br />-   eDisableRuntime|  
|OPR_AppDomainUnload|-   eUnloadAppDomain<br />-   eRudeUnloadAppDomain<br />-   eExitProcess<br />-   eFastExitProcess<br />-   eRudeExitProcess<br />-   eDisableRuntime|  
|OPR_AppDomainRudeUnload|-   eRudeUnloadAppDomain<br />-   eExitProcess<br />-   eFastExitProcess<br />-   eRudeExitProcess<br />-   eDisableRuntime|  
|OPR_ProcessExit|-   eExitProcess<br />-   eFastExitProcess<br />-   eRudeExitProcess<br />-   eDisableRuntime|  
|OPR_FinalizerRun|-   eNoAction<br />-   eAbortThread<br />-   eRudeAbortThread<br />-   eUnloadAppDomain<br />-   eRudeUnloadAppDomain<br />-   eExitProcess<br />-   eFastExitProcess<br />-   eRudeExitProcess<br />-   eDisableRuntime|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [EClrOperation (Enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [EPolicyAction (Enumeración)](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [ICLRPolicyManager (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
