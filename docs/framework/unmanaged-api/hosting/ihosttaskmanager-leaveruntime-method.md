---
description: 'Más información acerca de: IHostTaskManager:: LeaveRuntime ((método)'
title: IHostTaskManager::LeaveRuntime (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.LeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type:
- apiref
ms.openlocfilehash: 7b18bdc17b9cfd52b68309a07c6714fd1efa66cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707452"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a>IHostTaskManager::LeaveRuntime (Método)

Notifica al host que la tarea que se está ejecutando actualmente está a punto de abandonar el Common Language Runtime (CLR) y especificar código no administrado.  
  
> [!IMPORTANT]
> Una llamada correspondiente a [IHostTaskManager:: EnterRuntime (](ihosttaskmanager-enterruntime-method.md) notifica al host que la tarea que se está ejecutando actualmente está reentrando el código administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `target`  
 de Dirección dentro del archivo ejecutable portable asignado de la función no administrada a la que se va a llamar.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`LeaveRuntime` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No hay suficiente memoria disponible para completar la asignación solicitada.|  
  
## <a name="remarks"></a>Observaciones  

 Las secuencias de llamadas a y desde código no administrado se pueden anidar. Por ejemplo, en la lista siguiente se describe una situación hipotética en la que la secuencia de llamadas a `LeaveRuntime` , [IHostTaskManager:: ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md), y `IHostTaskManager::EnterRuntime` permite al host identificar las capas anidadas.  
  
|Acción|Llamada al método correspondiente|  
|------------|-------------------------------|  
|Un ejecutable de Visual Basic administrado llama a una función no administrada escrita en C mediante la invocación de plataforma.|`IHostTaskManager::LeaveRuntime`|  
|La función de C no administrada llama a un método en un archivo DLL administrado escrito en C#.|`IHostTaskManager::ReverseEnterRuntime`|  
|La función administrada de C# llama a otra función no administrada escrita en C, también mediante la invocación de plataforma.|`IHostTaskManager::LeaveRuntime`|  
|La segunda función no administrada devuelve la ejecución a la función de C#.|`IHostTaskManager::EnterRuntime`|  
|La función de C# devuelve la ejecución a la primera función no administrada.|`IHostTaskManager::ReverseLeaveRuntime`|  
|La primera función no administrada devuelve la ejecución al programa Visual Basic.|`IHostTaskManager::EnterRuntime`|  
  
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
