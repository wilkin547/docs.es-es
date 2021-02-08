---
description: 'Más información acerca de: IHostTaskManager:: EndDelayAbort (método)'
title: IHostTaskManager::EndDelayAbort (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndDelayAbort
helpviewer_keywords:
- EndDelayAbort method [.NET Framework hosting]
- IHostTaskManager::EndDelayAbort method [.NET Framework hosting]
ms.assetid: 6e02facb-2504-4356-9af5-0cee1f8436a7
topic_type:
- apiref
ms.openlocfilehash: e0d1c4231d381baf2ff92d187d33714f1c6f3003
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784566"
---
# <a name="ihosttaskmanagerenddelayabort-method"></a>IHostTaskManager::EndDelayAbort (Método)

Notifica al host que el código administrado está saliendo del período en el que la tarea actual no se debe anular, siguiendo una llamada anterior a [IHostTaskManager:: BeginDelayAbort](ihosttaskmanager-begindelayabort-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EndDelayAbort ();  
```  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`EndDelayAbort` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_UNEXPECTED|`EndDelayAbort` se llamó a sin una llamada correspondiente a `BeginDelayAbort` .|  
  
## <a name="remarks"></a>Observaciones  

 CLR realiza una llamada correspondiente a `BeginDelayAbort` en la tarea actual antes de llamar a `EndDelayAbort` . En ausencia de esta llamada correspondiente, la implementación del host de [IHostTaskManager](ihosttaskmanager-interface.md) debe devolver E_UNEXPECTED de `EndDelayAbort` y no debe realizar ninguna acción.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading>
- [ICLRTask (Interfaz)](iclrtask-interface.md)
- [ICLRTaskManager (Interfaz)](iclrtaskmanager-interface.md)
- [IHostTask (Interfaz)](ihosttask-interface.md)
- [IHostTaskManager (Interfaz)](ihosttaskmanager-interface.md)
