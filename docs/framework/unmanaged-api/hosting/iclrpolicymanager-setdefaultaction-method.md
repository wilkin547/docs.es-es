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
ms.openlocfilehash: 8dc3a3c04a619ace566e173fb8d8945a9d921bce
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140768"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a>ICLRPolicyManager::SetDefaultAction (Método)
Especifica la acción de la Directiva que debe realizar el Common Language Runtime (CLR) cuando se produce la operación especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `operation`  
 de Uno de los valores de [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) , que indica la acción para la que se debe personalizar el comportamiento de CLR.  
  
 `action`  
 de Uno de los valores de [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) , que indica la acción de la Directiva que el CLR debe realizar cuando se produce `operation`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`SetDefaultAction` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|Se especificó una `action` no válida para el `operation`o se proporcionó un valor no válido para `operation`.|  
  
## <a name="remarks"></a>Comentarios  
 No todos los valores de acción de Directiva se pueden especificar como el comportamiento predeterminado para las operaciones CLR. Normalmente, `SetDefaultAction` se puede usar solo para escalar el comportamiento. Por ejemplo, un host puede especificar que las anulaciones de subprocesos se conviertan en anulaciones de subproceso forzada, pero no puede especificar lo contrario. En la tabla siguiente se describen los valores de `action` válidos para cada valor de `operation` posible.  
  
|Valor para `operation`|Valores válidos para `action`|  
|---------------------------|-------------------------------|  
|OPR_ThreadAbort|- eAbortThread<br />- eRudeAbortThread<br />- eUnloadAppDomain<br />- eRudeUnloadAppDomain<br />- eExitProcess<br />- eFastExitProcess<br />- eRudeExitProcess<br />- eDisableRuntime|  
|OPR_ThreadRudeAbortInNonCriticalRegion<br /><br /> OPR_ThreadRudeAbortInCriticalRegion|- eRudeAbortThread<br />- eUnloadAppDomain<br />- eRudeUnloadAppDomain<br />- eExitProcess<br />- eFastExitProcess<br />- eRudeExitProcess<br />- eDisableRuntime|  
|OPR_AppDomainUnload|- eUnloadAppDomain<br />- eRudeUnloadAppDomain<br />- eExitProcess<br />- eFastExitProcess<br />- eRudeExitProcess<br />- eDisableRuntime|  
|OPR_AppDomainRudeUnload|- eRudeUnloadAppDomain<br />- eExitProcess<br />- eFastExitProcess<br />- eRudeExitProcess<br />- eDisableRuntime|  
|OPR_ProcessExit|- eExitProcess<br />- eFastExitProcess<br />- eRudeExitProcess<br />- eDisableRuntime|  
|OPR_FinalizerRun|- eNoAction<br />- eAbortThread<br />- eRudeAbortThread<br />- eUnloadAppDomain<br />- eRudeUnloadAppDomain<br />- eExitProcess<br />- eFastExitProcess<br />- eRudeExitProcess<br />- eDisableRuntime|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [EClrOperation (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [EPolicyAction (enumeración)](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [ICLRPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
