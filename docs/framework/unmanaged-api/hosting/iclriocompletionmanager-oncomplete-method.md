---
title: ICLRIoCompletionManager::OnComplete (Método)
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager.OnComplete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager::OnComplete
helpviewer_keywords:
- OnComplete method [.NET Framework hosting]
- ICLRIoCompletionManager::OnComplete method [.NET Framework hosting]
ms.assetid: 003f6974-9727-4322-bed5-e330d1224d0b
topic_type:
- apiref
ms.openlocfilehash: b44a71137e39130bb0fe4c303fdff62c76d38cbd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141011"
---
# <a name="iclriocompletionmanageroncomplete-method"></a>ICLRIoCompletionManager::OnComplete (Método)
Notifica al Common Language Runtime (CLR) el estado de una solicitud de e/s realizada mediante una llamada al método [IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwErrorCode`  
 de Un valor HRESULT que indica el estado de la operación de enlace.  
  
- S_OK indica que la operación se completó correctamente.  
  
- HOST_E_INTERRUPTED indica que la llamada finalizó antes de que se completara.  
  
- E_FAIL indica que se ha producido un error grave desconocido irrecuperable.  
  
 `NumberOfBytesTransferred`  
 de Número de bytes transferidos durante el procesamiento de la solicitud de e/s.  
  
 `pvOverlapped`  
 de Puntero a la estructura `OVERLAPPED` que se pasó a la llamada al método `IHostIoCompletionManager::Bind`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`OnComplete` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 Si el host implementa una abstracción de finalización de e/s, el CLR realiza solicitudes de e/s a través del host mediante el uso de métodos de [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md). Después, el host llama al método `OnComplete` para notificar al tiempo de ejecución el resultado de dichas solicitudes.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRIoCompletionManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [IHostIoCompletionManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [IHostThreadPoolManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
