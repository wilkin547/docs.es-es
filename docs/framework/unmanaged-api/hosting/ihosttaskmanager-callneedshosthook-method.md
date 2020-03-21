---
title: IHostTaskManager::CallNeedsHostHook (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CallNeedsHostHook
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CallNeedsHostHook
helpviewer_keywords:
- CallNeedsHostHook method [.NET Framework hosting]
- IHostTaskManager::CallNeedsHostHook method [.NET Framework hosting]
ms.assetid: b60f1f59-9825-4b57-961f-d2979518e6a7
topic_type:
- apiref
ms.openlocfilehash: 8b8b8521a09fa54a105e8263a471ab0467fb6ccc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176297"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a>IHostTaskManager::CallNeedsHostHook (Método)
Permite al host especificar si Common Language Runtime (CLR) puede inlinear la llamada especificada a una función no administrada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `target`  
 [en] La dirección dentro del archivo ejecutable portátil (PE) asignado de la función no administrada que se va a llamar.  
  
 `pbCallNeedsHostHook`  
 [fuera] Puntero a un valor booleano que indica si el host requiere que se enganche la llamada.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`CallNeedsHostHook`regresó con éxito.|  
|HOST_E_CLRNOTAVAILABLE|El CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se adelantó la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no es el propietario de la cerradura.|  
|HOST_E_ABANDONED|Un evento se canceló mientras un hilo bloqueado o fibra lo esperaba.|  
|E_FAIL|Se ha producido un fallo catastrófico desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Observaciones  
 Para ayudar a optimizar la ejecución de código, CLR realiza un análisis de cada llamada de invocación de plataforma durante la compilación para determinar si la llamada se puede insertar. `CallNeedsHostHook`permite al host invalidar esa decisión exigiendo que se enganche una llamada a una función no administrada. Si el host requiere un enlace, el tiempo de ejecución no inline la llamada.  
  
 Normalmente, el host requeriría un enlace donde debe ajustar un estado de punto flotante, o al recibir una notificación de que una llamada está entrando en un estado donde el host no puede realizar un seguimiento de las solicitudes de memoria del tiempo de ejecución o de los bloqueos tomados. Cuando el host requiere que se enlace la llamada, el tiempo de ejecución notifica al host de transiciones hacia y desde código administrado mediante llamadas a [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)y [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MScorEE.h  
  
 **Biblioteca:** Incluido como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRTask (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
