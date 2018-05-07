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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 023e112aa8273d99efce2e0f2116f95569ac0c3b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a>IHostIoCompletionManager::InitializeHostOverlapped (Método)
Ofrece al host la oportunidad de inicializar los datos personalizados para anexar a Win32 `OVERLAPPED` estructura que se utiliza para solicitudes de E/S asincrónicas.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pvOverlapped`  
 [in] Un puntero a la de Win32 `OVERLAPPED` estructura que se incluya con la solicitud de E/S.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`InitializeHostOverlapped` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada agotó el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.|  
|E_FAIL|Se ha producido un error catastrófico desconocido. Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No había memoria suficiente disponible para asignar el recurso solicitado.|  
  
## <a name="remarks"></a>Comentarios  
 Funciones de la plataforma de Windows utilizan el `OVERLAPPED` estructura para almacenar el estado de solicitudes de E/S asincrónicas. CLR llama el `InitializeHostOverlapped` método para dar al host la oportunidad de anexar datos personalizados a un `OVERLAPPED` instancia.  
  
> [!IMPORTANT]
>  Para ir al principio del bloque de datos personalizado, los hosts deben establecer el desplazamiento al tamaño de la `OVERLAPPED` estructura (`sizeof(OVERLAPPED)`).  
  
 Un valor devuelto de E_OUTOFMEMORY indica que el host ha podido inicializar sus datos personalizados. En este caso, CLR notifica un error y produce un error en la llamada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRIoCompletionManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [GetHostOverlappedSize (método)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)  
 [IHostIoCompletionManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
