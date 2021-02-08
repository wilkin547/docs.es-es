---
description: 'Más información acerca de: IHostTask:: SetPriority (método)'
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
ms.openlocfilehash: c3e8fee954e5cbea2d084141a4b2d22d2fa5e95b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784644"
---
# <a name="ihosttasksetpriority-method"></a>IHostTask::SetPriority (Método)

Solicita que el host ajuste el nivel de prioridad del subproceso para la tarea representada por la instancia de [IHostTask](ihosttask-interface.md) actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `newPriority`  
 de Entero que representa el valor de prioridad de subproceso solicitado para la tarea representada por la `IHostTask` instancia actual.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`SetPriority` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Observaciones  

 A los subprocesos se les concede el tiempo de procesamiento mediante un sistema Round Robin que se basa parcialmente en el nivel de prioridad de un subproceso. `SetPriority` permite que CLR establezca el nivel de prioridad de subproceso para la tarea actual. `newPriority`Se admiten los valores siguientes.  
  
- THREAD_PRIORITY_ABOVE_NORMAL  
  
- THREAD_PRIORITY_BELOW_NORMAL  
  
- THREAD_PRIORITY_HIGHEST  
  
- THREAD_PRIORITY_IDLE  
  
- THREAD_PRIORITY_LOWEST  
  
- THREAD_PRIORITY_NORMAL  
  
- THREAD_PRIORITY_TIME_CRITICAL  
  
 CLR llama a `SetPriority` cuando el valor de <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> se modifica mediante código de usuario. Un host puede definir sus propios algoritmos para la asignación de prioridad de subprocesos y es libre de omitir esta solicitud.  
  
> [!NOTE]
> `SetPriority` no informa de si se cambió el nivel de prioridad del subproceso. Llame a [IHostTask:: GetPriority (](ihosttask-getpriority-method.md) para determinar el valor del nivel de prioridad del subproceso de la tarea.  
  
 La función de Win32 define los valores de nivel de prioridad del subproceso `SetThreadPriority` . Para obtener más información sobre la prioridad de los subprocesos, vea la documentación de la plataforma Windows.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.Thread>
- [ICLRTask (Interfaz)](iclrtask-interface.md)
- [ICLRTaskManager (Interfaz)](iclrtaskmanager-interface.md)
- [IHostTask (Interfaz)](ihosttask-interface.md)
- [Método GetPriority](ihosttask-getpriority-method.md)
- [IHostTaskManager (Interfaz)](ihosttaskmanager-interface.md)
