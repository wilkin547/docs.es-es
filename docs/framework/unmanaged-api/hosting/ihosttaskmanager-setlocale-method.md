---
title: IHostTaskManager::SetLocale (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: 747ee407-ee8c-484d-9583-25089236d2d1
topic_type:
- apiref
ms.openlocfilehash: e560d08d3e10db1b5978d1bd7be53dfed9ca3268
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132985"
---
# <a name="ihosttaskmanagersetlocale-method"></a>IHostTaskManager::SetLocale (Método)
Notifica al host que el Common Language Runtime (CLR) ha cambiado la configuración regional o la referencia cultural de la tarea que se está ejecutando actualmente.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `lcid`  
 de Valor del identificador de configuración regional que se asigna a la referencia cultural geográfica y al idioma recién asignados.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`SetLocale` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_NOTIMPL|El host no permite que el código de usuario administrado modifique la configuración regional.|  
  
## <a name="remarks"></a>Comentarios  
 El Runtime llama a `SetLocale` cuando el valor de la propiedad <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> cambia por código administrado. Este método proporciona una oportunidad para que el host ejecute cualquier mecanismo que pueda tener para la sincronización de configuraciones regionales. Si un host no permite cambiar la configuración regional del código administrado o no implementa un mecanismo para sincronizar configuraciones regionales, debe devolver E_NOTIMPL desde este método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [SetUILocale (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)
