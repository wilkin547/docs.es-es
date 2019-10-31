---
title: IHostMAlloc::Alloc (Método)
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Alloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Alloc
helpviewer_keywords:
- Alloc method, IHostMAlloc interface [.NET Framework hosting]
- IHostMAlloc::Alloc method [.NET Framework hosting]
ms.assetid: a3007f5e-d75d-4b37-842b-704e9edced5e
topic_type:
- apiref
ms.openlocfilehash: 9837e4e3428a0293c8e689b3f3e081aa07f055b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192070"
---
# <a name="ihostmallocalloc-method"></a>IHostMAlloc::Alloc (Método)
Solicita que el host asigne la cantidad de memoria especificada del montón.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,   
    [in] EMemoryCriticalLevel dwCriticalLevel,   
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `cbSize`  
 de Tamaño, en bytes, de la solicitud de asignación de memoria actual.  
  
 `dwCriticalLevel`  
 de Uno de los valores de [ememorycriticallevel (](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) , que indica el impacto de un error de asignación.  
  
 `ppMem`  
 enuncia Puntero a la memoria asignada o null si no se pudo completar la solicitud.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`Alloc` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No había suficiente memoria disponible para completar la solicitud de asignación.|  
  
## <a name="remarks"></a>Comentarios  
 CLR obtiene un puntero de interfaz a una instancia de `IHostMalloc` llamando al método [IHostMemoryManager:: CreateMAlloc (](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IHostMemoryManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [IHostMalloc (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
