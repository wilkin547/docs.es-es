---
title: IHostIoCompletionManager::InitializeHostOverlapped (Método)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.InitializeHostOverlapped
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type:
- apiref
ms.openlocfilehash: 9fd299ad25166bcbcf0202da13a5b4cbdd20d7d7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133802"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a>IHostIoCompletionManager::InitializeHostOverlapped (Método)
Proporciona al host la oportunidad de inicializar los datos personalizados que se van a anexar a una estructura de `OVERLAPPED` de Win32 que se usa para las solicitudes de e/s asincrónicas.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pvOverlapped`  
 de Puntero a la estructura de `OVERLAPPED` de Win32 que se va a incluir con la solicitud de e/s.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`InitializeHostOverlapped` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No hay suficiente memoria disponible para asignar el recurso solicitado.|  
  
## <a name="remarks"></a>Comentarios  
 Las funciones de la plataforma Windows usan la estructura `OVERLAPPED` para almacenar el estado de las solicitudes de e/s asincrónicas. CLR llama al método `InitializeHostOverlapped` para ofrecer al host la oportunidad de anexar datos personalizados a una instancia de `OVERLAPPED`.  
  
> [!IMPORTANT]
> Para ir al principio de su bloque de datos personalizado, los hosts deben establecer el desplazamiento en el tamaño de la estructura de `OVERLAPPED` (`sizeof(OVERLAPPED)`).  
  
 Un valor devuelto de E_OUTOFMEMORY indica que el host no pudo inicializar sus datos personalizados. En este caso, CLR informa de un error y produce un error en la llamada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRIoCompletionManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [GetHostOverlappedSize (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [IHostIoCompletionManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
