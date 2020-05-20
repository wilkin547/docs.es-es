---
title: ICLRGCManager::SetGCStartupLimits (Método)
ms.date: 03/30/2017
api_name:
- ICLRGCManager.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: 1c8d9959-95b5-4131-be4a-556d97774014
topic_type:
- apiref
ms.openlocfilehash: 0dce86a12ed3e93983ee62620fa0ddf7dfbc48f5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616949"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a>ICLRGCManager::SetGCStartupLimits (Método)
Establece el tamaño de un segmento de recolección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recolección de elementos no utilizados.  
  
> [!IMPORTANT]
> A partir del .NET Framework 4,5, puede establecer el tamaño del segmento y el tamaño máximo de la generación 0 en valores mayores que mediante `DWORD` el método [iclrgcmanager2 (:: setgcstartuplimitsex (](iclrgcmanager2-setgcstartuplimitsex-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `SegmentSize`  
 de Tamaño especificado de un segmento de recolección de elementos no utilizados.  
  
 El tamaño mínimo del segmento es 4 MB. Los segmentos se pueden aumentar en incrementos de 1 MB o más.  
  
 `MaxGen0Size`  
 de Tamaño máximo especificado para la generación 0.  
  
 El tamaño mínimo de la generación 0 es 64 KB.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`SetGCStartupLimits`se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Observaciones  
 Los valores que `SetGCStartupLimits` establece solo se pueden especificar una vez. Las llamadas posteriores a `SetGCStartupLimits` se omiten.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [Administración de memoria automática](../../../standard/automatic-memory-management.md)
- [Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md)
- [ICLRControl (Interfaz)](iclrcontrol-interface.md)
- [ICLRGCManager (Interfaz)](iclrgcmanager-interface.md)
