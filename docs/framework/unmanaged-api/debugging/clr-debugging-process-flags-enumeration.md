---
title: CLR_DEBUGGING_PROCESS_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_PROCESS_FLAGS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_PROCESS_FLAG
helpviewer_keywords:
- CLR_DEBUGGING_PROCESS_FLAGS enumeration [.NET Framework debugging]
ms.assetid: 85b85fde-1f87-490b-ba8d-d604670959c3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8321e5aeba435ca5f1398a9cb827a93ae821d686
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996364"
---
# <a name="clrdebuggingprocessflags-enumeration"></a>CLR_DEBUGGING_PROCESS_FLAGS (Enumeración)
Proporciona valores que se usan por el [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) método.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|Este tiempo de ejecución tiene que enviar un evento de depurador administrado-catch-up. Consulte la sección Comentarios para la distinción entre los eventos de puesta al día y -catch-up.|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|Es el evento administrado que está pendiente un <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> solicitud.|  
  
## <a name="remarks"></a>Comentarios  
 Poner eventos incluyen el proceso, dominio de aplicación, ensamblado, módulo y las notificaciones de creación del subproceso que llevan al depurador hasta el estado actual después de que ha adjuntado a un proceso. Eventos Non-catch-up, que se indican mediante el `CLR_DEBUGGING_MANAGED_EVENT_PENDING` marca, incluir todos los demás eventos de depurador, como las excepciones y administra la depuración de las notificaciones de asistente (MDA).  
  
 El `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` marca permite diferenciar entre una excepción de terminación y una solicitud para asociar un depurador administrado que se puede cancelar el tiempo de ejecución.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Metahost.idl, Metahost.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
