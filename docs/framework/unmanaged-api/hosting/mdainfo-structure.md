---
title: MDAInfo (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: MDAInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: MDAInfo
helpviewer_keywords: MDAInfo structure [.NET Framework hosting]
ms.assetid: fb8c14f7-d461-43d1-8b47-adb6723b9b93
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 53a999028f2677599598caf55e62f10721f61fe3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="mdainfo-structure"></a>MDAInfo (Estructura)
Proporciona detalles sobre la `Event_MDAFired` eventos, lo que desencadena la creación de un Asistente para depuración administrada (MDA).  
  
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
 Asistentes para la depuración administradas (MDA) son ayudas que funcionan en conjunción con common language runtime (CLR) para realizar tareas, como la identificación de las condiciones no válidas para la depuración en el motor de ejecución en tiempo de ejecución o para volcar información adicional sobre el estado de la motor de búsqueda. MDA generan mensajes XML sobre eventos que son difíciles de interceptar. Son especialmente útiles para depurar las transiciones entre código administrado y no administrado.  
  
 El tiempo de ejecución realiza los pasos siguientes cuando se desencadena un evento que desencadena la creación de un MDA:  
  
-   Si el host no ha registrado un [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) instancia mediante una llamada a [ICLROnEventManager:: RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) recibir una notificación de un `Event_MDAFired` eventos, el tiempo de ejecución continúa con su valor predeterminado, comportamiento no hospedado.  
  
-   Si el host ha registrado un controlador para este evento, el tiempo de ejecución comprueba si hay un depurador asociado al proceso. Si es así, el tiempo de ejecución se interrumpe el depurador. Cuando el depurador continúa, llama al host. Si se ha asociado ningún depurador, el runtime llama a `IActionOnCLREvent::OnEvent` y pasa un puntero a un `MDAInfo` instancia como el `data` parámetro.  
  
 El host puede elegir que se va a activar el MDA como recibir una notificación cuando se active un MDA. Esto impide al host una oportunidad para invalidar el comportamiento predeterminado y anular el subproceso administrado que desencadena el evento para evitar que se dañe el estado del proceso. Para obtener más información acerca del uso de MDA, consulte [diagnóstico de errores con asistentes de depuraciones administradas](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.idl  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Estructuras de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
