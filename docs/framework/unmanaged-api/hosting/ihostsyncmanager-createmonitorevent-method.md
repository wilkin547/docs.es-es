---
title: IHostSyncManager::CreateMonitorEvent (Método)
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateMonitorEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateMonitorEvent
helpviewer_keywords:
- CreateMonitorEvent method [.NET Framework hosting]
- IHostSyncManager::CreateMonitorEvent method [.NET Framework hosting]
ms.assetid: 524c7fd3-9b5c-46e7-99ba-555fd2fe33f0
topic_type:
- apiref
ms.openlocfilehash: c0f7e1fd6bf4c9386300b11477df85e87899fc67
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803319"
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a>IHostSyncManager::CreateMonitorEvent (Método)
Crea un objeto de evento de restablecimiento automático supervisado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `cookie`  
 de Cookie que se va a asociar al objeto de evento.  
  
 `ppEvent`  
 enuncia Puntero a la dirección de una instancia de [IHostAutoEvent](ihostautoevent-interface.md) o null si no se pudo crear el objeto de evento.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`CreateMonitorEvent`se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No había suficiente memoria disponible para crear el objeto de evento solicitado.|  
  
## <a name="remarks"></a>Observaciones  
 `CreateMonitorEvent`Devuelve un `IHostAutoEvent` que CLR usa en su implementación del <xref:System.Threading.Monitor?displayProperty=nameWithType> tipo administrado. Este método refleja la `CreateEvent` función de Win32, con un valor de `false` especificado para el `bManualReset` parámetro.  
  
 El host puede usar la cookie para determinar qué tarea está esperando en el monitor llamando al método [ICLRSyncManager:: GetMonitorOwner (](iclrsyncmanager-getmonitorowner-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRSyncManager (Interfaz)](iclrsyncmanager-interface.md)
- [IHostAutoEvent (Interfaz)](ihostautoevent-interface.md)
- [IHostSyncManager (Interfaz)](ihostsyncmanager-interface.md)
- <xref:System.Threading.Monitor>
