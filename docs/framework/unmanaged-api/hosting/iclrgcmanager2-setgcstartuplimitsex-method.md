---
title: ICLRGCManager2::SetGCStartupLimitsEx (Método)
ms.date: 03/30/2017
api_name:
- ICLRGCManager2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2::SetCLRGCStartupLimitsEx
helpviewer_keywords:
- ICLRGCManager2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 6c3a08a9-5d65-48d4-8bbf-2a86ed7d356a
topic_type:
- apiref
ms.openlocfilehash: 77de550cd3fb614e03f8028707c3cbf914734910
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141090"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a>ICLRGCManager2::SetGCStartupLimitsEx (Método)
Establece el tamaño de un segmento de recolección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recolección de elementos no utilizados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,   
    [in] SIZE_T MaxGen0Size  
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
|S_OK|`SetGCStartupLimitsEx` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 Los valores que `SetGCStartupLimitsEx` establece solo se pueden especificar antes de que se inicie el host. Las llamadas posteriores a `SetGCStartupLimitsEx` se omiten.  
  
 Para establecer cualquiera de los parámetros sin afectar al otro, especifique 0 (cero) para el parámetro que no quiere cambiar.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Administración automática de la memoria](../../../standard/automatic-memory-management.md)
- [Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md)
- [ICLRControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICLRGCManager2 (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
