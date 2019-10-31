---
title: IActionOnCLREvent::OnEvent (Método)
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent.OnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent::OnEvent
helpviewer_keywords:
- OnEvent method [.NET Framework hosting]
- IActionOnCLREvent::OnEvent method [.NET Framework hosting]
ms.assetid: 0970f10c-4304-4c12-91c0-83e51455afb4
topic_type:
- apiref
ms.openlocfilehash: 98807717fc913052dae15f9f3cbd462d4f537ad4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126927"
---
# <a name="iactiononclreventonevent-method"></a>IActionOnCLREvent::OnEvent (Método)
Realiza devoluciones de llamada en eventos que se han registrado mediante una llamada al método [ICLROnEventManager:: RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `event`  
 de Uno de los valores de [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) , que indica el tipo de evento.  
  
 `data`  
 de Un puntero a un objeto que contiene detalles sobre `event`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`OnEvent` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a cualquier método de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 El parámetro `data` es un puntero a un objeto de tipo no especificado. Si el parámetro `event` es `Event_DomainUnload`, `data` es el identificador numérico del <xref:System.AppDomain> que se ha descargado. El host puede tomar las medidas adecuadas con este identificador como clave.  
  
 Si `event` es `Event_MDAFired`, `data` es un puntero a una instancia de [MDAInfo (](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) que contiene la salida del mensaje de un asistente para la depuración administrada (MDA). Los MDA son una característica de CLR que ayuda a los desarrolladores a depurar mediante la generación de mensajes XML sobre eventos que, de otro modo, son difíciles de interceptar. Estos mensajes pueden ser especialmente útiles para depurar las transiciones entre el código administrado y no administrado. Para obtener más información, vea [diagnosticar errores con asistentes para la depuración administrada](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [EClrEvent (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [IActionOnCLREvent (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [ICLRControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICLROnEventManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [MDAInfo (estructura)](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)
