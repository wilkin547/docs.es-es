---
title: IHostTask::SetPriority (Método)
ms.date: 03/30/2017
api_name:
- IHostTask.SetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetPriority
helpviewer_keywords:
- IHostTask::SetPriority method [.NET Framework hosting]
- SetPriority method [.NET Framework hosting]
ms.assetid: cd8c379b-c7a0-434f-8e23-899bd26be75d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 533e3d715b46b4ef6d473795a010fa3ad297ded2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913749"
---
# <a name="ihosttasksetpriority-method"></a>IHostTask::SetPriority (Método)
Solicita que el host ajuste el nivel de prioridad del subproceso para la tarea representada por la instancia de [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `newPriority`  
 de Entero que representa el valor de prioridad de subproceso solicitado para la tarea representada `IHostTask` por la instancia actual.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|DESCRIPCIÓN|  
|-------------|-----------------|  
|S_OK|`SetPriority`se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 A los subprocesos se les concede el tiempo de procesamiento mediante un sistema Round Robin que se basa parcialmente en el nivel de prioridad de un subproceso. `SetPriority`permite que CLR establezca el nivel de prioridad de subproceso para la tarea actual. Se admiten los valores siguientes `newPriority` .  
  
- THREAD_PRIORITY_ABOVE_NORMAL  
  
- THREAD_PRIORITY_BELOW_NORMAL  
  
- THREAD_PRIORITY_HIGHEST  
  
- THREAD_PRIORITY_IDLE  
  
- THREAD_PRIORITY_LOWEST  
  
- THREAD_PRIORITY_NORMAL  
  
- THREAD_PRIORITY_TIME_CRITICAL  
  
 CLR llama a `SetPriority` cuando el valor <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> de se modifica mediante código de usuario. Un host puede definir sus propios algoritmos para la asignación de prioridad de subprocesos y es libre de omitir esta solicitud.  
  
> [!NOTE]
> `SetPriority`no informa de si se cambió el nivel de prioridad del subproceso. Llame a [IHostTask:: GetPriority (](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) para determinar el valor del nivel de prioridad del subproceso de la tarea.  
  
 La función de Win32 `SetThreadPriority` define los valores de nivel de prioridad del subproceso. Para obtener más información sobre la prioridad de los subprocesos, vea la documentación de la plataforma Windows.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.Thread>
- [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [GetPriority (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)
- [IHostTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
