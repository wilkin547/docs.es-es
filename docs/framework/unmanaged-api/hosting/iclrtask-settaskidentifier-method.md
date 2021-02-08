---
description: 'Más información acerca de: ICLRTask:: Settaskidentifier ((método)'
title: ICLRTask::SetTaskIdentifier (Método)
ms.date: 03/30/2017
api_name:
- ICLRTask.SetTaskIdentifier
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SetTaskIdentifier
helpviewer_keywords:
- SetTaskIdentifier method [.NET Framework hosting]
- ICLRTask::SetTaskIdentifier method [.NET Framework hosting]
ms.assetid: bdb7f047-1e90-40fc-9e3b-d44a16509073
topic_type:
- apiref
ms.openlocfilehash: e746d8ec96d16f7761dd49ac814ddbed073c2686
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784956"
---
# <a name="iclrtasksettaskidentifier-method"></a>ICLRTask::SetTaskIdentifier (Método)

Indica al Common Language Runtime (CLR) que asocie el valor de identificador especificado a la tarea representada por la instancia de [ICLRTask](iclrtask-interface.md) actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `Asked`  
 de Identificador único del Common Language Runtime que se va a asociar a la tarea representada por la `ICLRTask` instancia actual.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`SetTaskIdentifier` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Observaciones  

 El host puede asociar un identificador a una tarea para facilitar la integración de CLR y el host en un entorno de depuración. El identificador no tiene ningún significado para CLR. El CLR lo pasa a una aplicación del depurador. El depurador puede usar este identificador para asociar una pila de llamadas de CLR a una pila de llamadas de host y permitir que la información de seguimiento respectiva sea unificada cuando se ve en la interfaz de usuario del depurador.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRTask (Interfaz)](iclrtask-interface.md)
- [ICLRTaskManager (Interfaz)](iclrtaskmanager-interface.md)
- [IHostTask (Interfaz)](ihosttask-interface.md)
- [IHostTaskManager (Interfaz)](ihosttaskmanager-interface.md)
