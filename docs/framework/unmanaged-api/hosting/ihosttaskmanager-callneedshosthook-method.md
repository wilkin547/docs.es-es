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
ms.openlocfilehash: 7c7af1bbf3d13c3f66d525dfce69d8b49fbe045c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675144"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a>IHostTaskManager::CallNeedsHostHook (Método)

Permite al host especificar si el Common Language Runtime (CLR) puede alinear la llamada especificada a una función no administrada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `target`  
 de Dirección dentro del archivo portable ejecutable (PE) asignado de la función no administrada a la que se va a llamar.  
  
 `pbCallNeedsHostHook`  
 enuncia Un puntero a un valor booleano que indica si el host requiere que se enlace la llamada.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`CallNeedsHostHook` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se ha producido un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  

 Para ayudar a optimizar la ejecución del código, CLR realiza un análisis de cada llamada de invocación de plataforma durante la compilación para determinar si la llamada se puede insertar. `CallNeedsHostHook` permite que el host invalide esa decisión solicitando que se enlace una llamada a una función no administrada. Si el host requiere un enlace, el runtime no insertará la llamada.  
  
 Normalmente, el host requeriría un enlace donde debe ajustar un estado de punto flotante o al recibir la notificación de que una llamada está entrando en un estado en el que el host no puede realizar el seguimiento de las solicitudes de memoria en tiempo de ejecución o de los bloqueos tomados. Cuando el host requiere que se enlace la llamada, el tiempo de ejecución notifica al host de las transiciones hacia y desde el código administrado mediante llamadas a [EnterRuntime (](ihosttaskmanager-enterruntime-method.md), [LeaveRuntime (](ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md)y [ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRTask (Interfaz)](iclrtask-interface.md)
- [ICLRTaskManager (Interfaz)](iclrtaskmanager-interface.md)
- [IHostTask (Interfaz)](ihosttask-interface.md)
- [IHostTaskManager (Interfaz)](ihosttaskmanager-interface.md)
