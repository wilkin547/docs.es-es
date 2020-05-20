---
title: ICLRRuntimeHost::SetHostControl (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.SetHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::SetHostControl
helpviewer_keywords:
- SetHostControl method [.NET Framework hosting]
- ICLRRuntimeHost::SetHostControl method [.NET Framework hosting]
ms.assetid: 6136be87-e631-4756-81ed-74b66581bad4
topic_type:
- apiref
ms.openlocfilehash: 8d6a4e1ca934c748352b0c4f5120536a4dd24e0b
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703956"
---
# <a name="iclrruntimehostsethostcontrol-method"></a>ICLRRuntimeHost::SetHostControl (Método)
Establece el puntero de interfaz que puede usar el Common Language Runtime (CLR) para obtener la implementación del host de la [interfaz IHostControl](ihostcontrol-interface.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pHostControl`  
 de Puntero de interfaz a la implementación del host de la [interfaz IHostControl](ihostcontrol-interface.md).  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`SetHostControl`se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_CLR_ALREADY_STARTED|CLR ya se ha inicializado.|  
  
## <a name="remarks"></a>Observaciones  
 Debe llamar a `SetHostControl` antes de que se inicialice el CLR, es decir, antes de llamar al [método de inicio](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) o usar cualquiera de las [interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md). Se recomienda llamar a `SetHostControl` inmediatamente después de llamar a la función [CorBindToCurrentRuntime (](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) o a la [función CorBindToRuntimeEx](corbindtoruntimeex-function.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [ICLRRuntimeHost (Interfaz)](iclrruntimehost-interface.md)
- [IHostControl (Interfaz)](ihostcontrol-interface.md)
