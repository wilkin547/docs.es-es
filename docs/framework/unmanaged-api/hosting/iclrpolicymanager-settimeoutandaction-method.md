---
description: 'Más información sobre: ICLRPolicyManager:: SetTimeoutAndAction ((método)'
title: ICLRPolicyManager::SetTimeoutAndAction (Método)
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeoutAndAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeoutAndAction
helpviewer_keywords:
- ICLRPolicyManager::SetTimeoutAndAction method [.NET Framework hosting]
- SetTimeoutAndAction method [.NET Framework hosting]
ms.assetid: 60454f91-d855-4ddf-bb6d-60a02f5eabab
topic_type:
- apiref
ms.openlocfilehash: c91d43cce381bef804b30e9e1dcb50574ddcd1b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716580"
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a>ICLRPolicyManager::SetTimeoutAndAction (Método)

Establece un valor de tiempo de espera para la operación especificada y especifica la acción de la Directiva que debe realizar el Common Language Runtime (CLR) cuando se produce la operación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `operation`  
 de Uno de los valores de [EClrOperation](eclroperation-enumeration.md) , que indica la operación para la que se va a establecer el tiempo de espera y la directiva `action` . Se admiten los valores siguientes:  
  
- OPR_AppDomainUnload  
  
- OPR_ProcessExit  
  
- OPR_ThreadRudeAbortInCriticalRegion  
  
- OPR_ThreadRudeAbortInNonCriticalRegion  
  
 `dwMilliseconds`  
 de Nuevo valor de tiempo de espera, en milisegundos. Un valor de infinito hace que `operation` nunca agote el tiempo de espera.  
  
 `action`  
 de Uno de los valores de [EPolicyAction](epolicyaction-enumeration.md) , que indica la acción de la Directiva que el CLR debe realizar cuando `operation` se produce.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`SetTimeoutAndAction` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|No se puede establecer un tiempo de espera para el especificado `operation` o se proporcionó un valor no válido para `action` .|  
  
## <a name="remarks"></a>Observaciones  

 `SetTimeoutAndAction` encapsula las capacidades de los métodos [ICLRPolicyManager:: setTimeout](iclrpolicymanager-settimeout-method.md) y [ICLRPolicyManager:: SetActionOnTimeout (](iclrpolicymanager-setactionontimeout-method.md) , y se puede llamar en lugar de llamadas secuenciales a estos dos métodos.  
  
> [!IMPORTANT]
> No todos los valores de acción de Directiva se pueden especificar como el comportamiento de tiempo de espera para las operaciones CLR. Vea las secciones comentarios de los temas de estos dos métodos para ver los valores válidos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [EClrOperation (Enumeración)](eclroperation-enumeration.md)
- [EPolicyAction (Enumeración)](epolicyaction-enumeration.md)
- [ICLRPolicyManager (Interfaz)](iclrpolicymanager-interface.md)
- [Método SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md)
- [ICLRPolicyManager:: SetTimeoutAndAction (](iclrpolicymanager-settimeoutandaction-method.md)
