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
ms.openlocfilehash: 3bfcb01e30b4cb33ec9276f1d3c6ac2f3bde4b58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721769"
---
# <a name="iactiononclreventonevent-method"></a>IActionOnCLREvent::OnEvent (Método)

Realiza devoluciones de llamada en eventos que se han registrado mediante una llamada al método [ICLROnEventManager:: RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `event`  
 de Uno de los valores de [EClrEvent](eclrevent-enumeration.md) , que indica el tipo de evento.  
  
 `data`  
 de Un puntero a un objeto que contiene detalles acerca de `event` .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`OnEvent` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a cualquier método de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  

 El `data` parámetro es un puntero a un objeto de tipo no especificado. Si el `event` parámetro es `Event_DomainUnload` , `data` es el identificador numérico del <xref:System.AppDomain> que se ha descargado. El host puede tomar las medidas adecuadas con este identificador como clave.  
  
 Si `event` es `Event_MDAFired` , `data` es un puntero a una instancia de [MDAInfo (](mdainfo-structure.md) que contiene la salida del mensaje de un asistente para la depuración administrada (MDA). Los MDA son una característica de CLR que ayuda a los desarrolladores a depurar mediante la generación de mensajes XML sobre eventos que, de otro modo, son difíciles de interceptar. Estos mensajes pueden ser especialmente útiles para depurar las transiciones entre el código administrado y no administrado. Para obtener más información, vea [diagnosticar errores con asistentes para la depuración administrada](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Diagnóstico de errores con asistentes de depuraciones administradas](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [EClrEvent (Enumeración)](eclrevent-enumeration.md)
- [IActionOnCLREvent (Interfaz)](iactiononclrevent-interface.md)
- [ICLRControl (Interfaz)](iclrcontrol-interface.md)
- [ICLROnEventManager (Interfaz)](iclroneventmanager-interface.md)
- [MDAInfo (Estructura)](mdainfo-structure.md)
