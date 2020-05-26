---
title: IHostIoCompletionManager::GetAvailableThreads (Método)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: bab363d1-b859-47a4-9884-5661c611cce7
topic_type:
- apiref
ms.openlocfilehash: 7ea7395bb1f185ba59940d76def562ab5440e560
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804762"
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a>IHostIoCompletionManager::GetAvailableThreads (Método)
Obtiene el número de subprocesos de finalización de e/s, del número total de subprocesos administrados por el host, que no están atendiendo actualmente solicitudes.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pdwAvailableIoCompletionThreads`  
 enuncia Puntero al número de subprocesos de finalización de e/s administrados por el host que están actualmente disponibles para las solicitudes de servicio.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`GetAvailableThreads`se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_NOTIMPL|El host no proporciona una implementación de `GetAvailableThreads` .|  
  
## <a name="remarks"></a>Observaciones  
 Un host podría querer tener un control exclusivo sobre el tamaño del grupo de subprocesos de finalización de e/s, por motivos como la implementación, el rendimiento o la escalabilidad. Por lo tanto, no es necesario que el host implemente `GetAvailableThreads` . En este caso, el host debe devolver E_NOTIMPL desde este método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRIoCompletionManager (Interfaz)](iclriocompletionmanager-interface.md)
- [IHostIoCompletionManager (Interfaz)](ihostiocompletionmanager-interface.md)
