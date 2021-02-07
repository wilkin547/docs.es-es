---
description: 'Más información acerca de: estructura MDAInfo ('
title: MDAInfo (Estructura)
ms.date: 03/30/2017
api_name:
- MDAInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MDAInfo
helpviewer_keywords:
- MDAInfo structure [.NET Framework hosting]
ms.assetid: fb8c14f7-d461-43d1-8b47-adb6723b9b93
topic_type:
- apiref
ms.openlocfilehash: 5c42537a68d38e6cff3d70dcb796cd733ce64a1e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679763"
---
# <a name="mdainfo-structure"></a>MDAInfo (Estructura)

Proporciona detalles sobre el `Event_MDAFired` evento, que desencadena la creación de un asistente para la depuración administrada (MDA).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`lpMDACaption`|Título del MDA actual. El título describe el tipo de error que desencadenó el `Event_MDAFired` evento.|  
|`lpMDAMessage`|Mensaje de salida proporcionado por el MDA actual.|  
  
## <a name="remarks"></a>Observaciones  

 Los asistentes para la depuración administrada (MDA) son ayudas para la depuración que funcionan junto con el Common Language Runtime (CLR) para realizar tareas como la identificación de condiciones no válidas en el motor de ejecución en tiempo de ejecución o el volcado de información adicional sobre el estado del motor. Los MDA generan mensajes XML sobre eventos que, de otro modo, son difíciles de interceptar. Son especialmente útiles para depurar las transiciones entre el código administrado y no administrado.  
  
 El tiempo de ejecución sigue los pasos siguientes cuando se activa un evento que desencadena la creación de un MDA:  
  
- Si el host no ha registrado una instancia de [IActionOnCLREvent](iactiononclrevent-interface.md) llamando a [ICLROnEventManager:: RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) para recibir una notificación de un `Event_MDAFired` evento, el tiempo de ejecución continúa con su comportamiento predeterminado no hospedado.  
  
- Si el host ha registrado un controlador para este evento, el tiempo de ejecución comprueba si hay un depurador asociado al proceso. Si es así, el Runtime se interrumpe en el depurador. Cuando el depurador continúa, llama al host. Si no hay ningún depurador asociado, el Runtime llama a `IActionOnCLREvent::OnEvent` y pasa un puntero a una `MDAInfo` instancia de como `data` parámetro.  
  
 El host puede optar por activar los MDA y recibir una notificación cuando se activa un MDA. Esto proporciona al host una oportunidad para invalidar el comportamiento predeterminado y anular el subproceso administrado que provocó el evento, para evitar que dañe el estado del proceso. Para obtener más información sobre el uso de MDA, vea [diagnosticar errores con asistentes para la depuración administrada](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. idl  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de hospedaje](hosting-structures.md)
- [Diagnóstico de errores con asistentes de depuraciones administradas](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
