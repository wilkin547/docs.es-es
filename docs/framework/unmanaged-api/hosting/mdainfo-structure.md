---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: faa6af54714f7f0b7ac91c7836673c163195d5f6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64656456"
---
# <a name="mdainfo-structure"></a>MDAInfo (Estructura)
Proporciona detalles sobre el `Event_MDAFired` evento que desencadena la creación de un Asistente para depuración administrada (MDA).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`lpMDACaption`|El título del MDA actual. El título describe el tipo de error que ha desencadenado la `Event_MDAFired` eventos.|  
|`lpMDAMessage`|El mensaje de salida proporcionado por el MDA actual.|  
  
## <a name="remarks"></a>Comentarios  
 Asistentes para la depuración administradas (MDA) son ayudas que funcionan en conjunción con common language runtime (CLR) para realizar tareas como la identificación de las condiciones no válidas para la depuración en el motor de ejecución o el volcado de información adicional sobre el estado de la motor. MDA generan mensajes XML sobre eventos que son difíciles de interceptar. Son especialmente útiles para depurar las transiciones entre código administrado y no administrado.  
  
 El tiempo de ejecución realiza los pasos siguientes cuando se desencadena un evento que desencadena la creación de un MDA:  
  
- Si el host no ha registrado un [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) instancia mediante una llamada a [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) para recibir una notificación de un `Event_MDAFired` eventos, el tiempo de ejecución continúa con su predeterminada, el comportamiento no hospedado.  
  
- Si el host ha registrado un controlador para este evento, el tiempo de ejecución comprueba si se adjunta un depurador al proceso. Si es así, el tiempo de ejecución se interrumpe el depurador. Cuando el depurador continúa, llama al host. Si no hay ningún depurador está conectado, el runtime llama a `IActionOnCLREvent::OnEvent` y pasa un puntero a un `MDAInfo` la instancia como el `data` parámetro.  
  
 El host puede elegir para activar el MDA y recibir una notificación cuando se activa un MDA. Esto proporciona al host una oportunidad para invalidar el comportamiento predeterminado y anular el subproceso administrado que provocó el evento, para impedir que se dañe el estado del proceso. Para obtener más información sobre el uso de los MDA, consulte [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.idl  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
