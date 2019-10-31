---
title: IHostIoCompletionManager::CreateIoCompletionPort (Método)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CreateIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort method [.NET Framework hosting]
- CreateIoCompletionPort method [.NET Framework hosting]
ms.assetid: 907a2b43-68db-44a7-acac-89e792e7bb3c
topic_type:
- apiref
ms.openlocfilehash: c3fa8aeebe529564c0ecc4a970f586fffc97ee05
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133877"
---
# <a name="ihostiocompletionmanagercreateiocompletionport-method"></a>IHostIoCompletionManager::CreateIoCompletionPort (Método)
Solicita que el host cree un nuevo puerto de finalización de e/s.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateIoCompletionPort (  
    [out] HANDLE *phPort  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `phPort`  
 enuncia Un puntero a un identificador del puerto de finalización de e/s recién creado o 0 (cero) si no se pudo crear el puerto.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`CreateIoCompletionPort` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No hay suficiente memoria disponible para asignar el recurso solicitado.|  
  
## <a name="remarks"></a>Comentarios  
 CLR llama al método `CreateIoCompletionPort` para solicitar que el host cree un nuevo puerto de finalización de e/s. Enlaza las operaciones de e/s a este puerto a través de una llamada al método [IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) . El host devuelve el estado a CLR llamando a [ICLRIoCompletionManager:: Alcompletate](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRIoCompletionManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [IHostIoCompletionManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
