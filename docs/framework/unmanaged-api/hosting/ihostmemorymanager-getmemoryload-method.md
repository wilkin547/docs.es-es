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
ms.openlocfilehash: 88acd50c83eb1ff4d59aa50d677db2383912659a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176284"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a>IHostMemoryManager::GetMemoryLoad (Método)
Obtiene la cantidad de memoria física que está actualmente en uso y, por lo tanto, no está disponible, según lo informado por el host.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pMemoryLoad`  
 [fuera] Puntero al porcentaje aproximado de memoria física total que está actualmente en uso.  
  
 `pAvailableBytes`  
 [fuera] Puntero al número de bytes disponibles para Common Language Runtime (CLR).  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`GetMemoryLoad`regresó con éxito.|  
|HOST_E_CLRNOTAVAILABLE|El CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se adelantó la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no es el propietario de la cerradura.|  
|HOST_E_ABANDONED|Un evento se canceló mientras un hilo bloqueado o fibra lo esperaba.|  
|E_FAIL|Se ha producido un fallo catastrófico desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Observaciones  
 `GetMemoryLoad`envuelve la función Win32. `GlobalMemoryStatus` El valor `pMemoryLoad` de es `dwMemoryLoad` el equivalente `MEMORYSTATUS` del `GlobalMemoryStatus`campo en la estructura devuelta desde .  
  
 El tiempo de ejecución utiliza el valor devuelto como heurístico para el recolector de elementos no utilizados. Por ejemplo, si el host informa de que la mayoría de la memoria está en uso, el recolector de elementos no utilizados puede optar por recopilar de varias generaciones para aumentar la cantidad de memoria que puede estar disponible.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MScorEE.h  
  
 **Biblioteca:** Incluido como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.GC?displayProperty=nameWithType>
- [IHostMemoryManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
