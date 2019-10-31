---
title: IHostMemoryManager::GetMemoryLoad (Método)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.GetMemoryLoad
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::GetMemoryLoad
helpviewer_keywords:
- IHostMemoryManager::GetMemoryLoad method [.NET Framework hosting]
- GetMemoryLoad method [.NET Framework hosting]
ms.assetid: e8138f6e-a0a4-48d4-8dae-9466b4dc6180
topic_type:
- apiref
ms.openlocfilehash: 2210dcd9e8a8af92b7905ec680c53c1119e6a3cf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136707"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a>IHostMemoryManager::GetMemoryLoad (Método)
Obtiene la cantidad de memoria física que está actualmente en uso y, por lo tanto, no está disponible, tal y como lo ha indicado el host.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,   
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pMemoryLoad`  
 enuncia Un puntero al porcentaje aproximado de la memoria física total que se está usando actualmente.  
  
 `pAvailableBytes`  
 enuncia Puntero al número de bytes disponibles para el Common Language Runtime (CLR).  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`GetMemoryLoad` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 `GetMemoryLoad` incluye la función de `GlobalMemoryStatus` de Win32. El valor de `pMemoryLoad` es el equivalente del campo `dwMemoryLoad` de la estructura `MEMORYSTATUS` devuelta de `GlobalMemoryStatus`.  
  
 El motor en tiempo de ejecución utiliza el valor devuelto como una heurística para el recolector de elementos no utilizados. Por ejemplo, si el host informa de que la mayoría de la memoria está en uso, el recolector de elementos no utilizados puede optar por recopilar de varias generaciones para aumentar la cantidad de memoria que podría estar disponible.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.GC?displayProperty=nameWithType>
- [IHostMemoryManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
