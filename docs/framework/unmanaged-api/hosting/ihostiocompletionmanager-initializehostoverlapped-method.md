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
ms.openlocfilehash: 397dbbeb0b85cb549a8b5917f977ecb13b3d6539
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720222"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a>IHostIoCompletionManager::InitializeHostOverlapped (Método)

Proporciona al host la oportunidad de inicializar los datos personalizados que se van a anexar a una `OVERLAPPED` estructura de Win32 que se usa para las solicitudes de e/s asincrónicas.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pvOverlapped`  
 de Puntero a la estructura de Win32 `OVERLAPPED` que se va a incluir con la solicitud de e/s.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`InitializeHostOverlapped` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No hay suficiente memoria disponible para asignar el recurso solicitado.|  
  
## <a name="remarks"></a>Comentarios  

 Las funciones de la plataforma Windows usan la `OVERLAPPED` estructura para almacenar el estado de las solicitudes de e/s asincrónicas. CLR llama al `InitializeHostOverlapped` método para proporcionar al host la oportunidad de anexar datos personalizados a una `OVERLAPPED` instancia de.  
  
> [!IMPORTANT]
> Para llegar al principio de su bloque de datos personalizado, los hosts deben establecer el desplazamiento en el tamaño de la `OVERLAPPED` estructura ( `sizeof(OVERLAPPED)` ).  
  
 Un valor devuelto de E_OUTOFMEMORY indica que el host no pudo inicializar sus datos personalizados. En este caso, CLR informa de un error y produce un error en la llamada.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRIoCompletionManager (Interfaz)](iclriocompletionmanager-interface.md)
- [Método GetHostOverlappedSize](ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [IHostIoCompletionManager (Interfaz)](ihostiocompletionmanager-interface.md)
