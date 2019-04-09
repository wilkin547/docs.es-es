---
title: IHostMemoryManager::CreateMAlloc (Método)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.CreateMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::CreateMAlloc
helpviewer_keywords:
- CreateAlloc method [.NET Framework hosting]
- IHostMemoryManager::CreateMAlloc method [.NET Framework hosting]
ms.assetid: 9ee6e052-bef7-4350-9e4f-edfffd99ad6f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 194e9b73610ccb7282babf266eea2968a4f035ac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179132"
---
# <a name="ihostmemorymanagercreatemalloc-method"></a>IHostMemoryManager::CreateMAlloc (Método)
Obtiene un puntero de interfaz a un [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instancia que se usa para realizar solicitudes de asignación de un montón creado por el host.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwMallocType`  
 [in] Una combinación de [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) marcas que especifica las características de la memoria que se está asignando.  
  
 `ppMAlloc`  
 [out] Un puntero a la dirección de un `IHostMAlloc` instancia proporcionada por el host.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`CreateMAlloc` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada ha agotado el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.|  
|E_FAIL|Se ha producido un error irrecuperable desconocido. Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No hay suficiente memoria física no estaba disponible para completar la solicitud de asignación.|  
  
## <a name="remarks"></a>Comentarios  
 `CreateMAlloc` Devuelve un objeto que permite que el CLR realizar solicitudes de asignación a través del host en lugar de usar las funciones estándar de Win32.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IHostMalloc (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [IHostMemoryManager (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
