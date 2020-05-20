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
ms.openlocfilehash: 39c9752912e88b04455516c0e9bed43610ba8aa0
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703817"
---
# <a name="iclriocompletionmanageroncomplete-method"></a>ICLRIoCompletionManager::OnComplete (Método)
Notifica al Common Language Runtime (CLR) el estado de una solicitud de e/s realizada mediante una llamada al método [IHostIoCompletionManager:: Bind](ihostiocompletionmanager-bind-method.md) .  
  
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
  
- HOST_E_INTERRUPTED indica que la llamada finalizó antes de la finalización.  
  
- E_FAIL indica que se ha producido un error grave desconocido irrecuperable.  
  
 `NumberOfBytesTransferred`  
 de Número de bytes transferidos durante el procesamiento de la solicitud de e/s.  
  
 `pvOverlapped`  
 de Puntero a la `OVERLAPPED` estructura que se pasó a la llamada al `IHostIoCompletionManager::Bind` método.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`OnComplete`se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Observaciones  
 Si el host implementa una abstracción de finalización de e/s, el CLR realiza solicitudes de e/s a través del host mediante el uso de métodos de [IHostIoCompletionManager](ihostiocompletionmanager-interface.md). Después, el host llama al `OnComplete` método para notificar al tiempo de ejecución el resultado de dichas solicitudes.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [ICLRIoCompletionManager (Interfaz)](iclriocompletionmanager-interface.md)
- [IHostIoCompletionManager (Interfaz)](ihostiocompletionmanager-interface.md)
- [IHostThreadPoolManager (Interfaz)](ihostthreadpoolmanager-interface.md)
