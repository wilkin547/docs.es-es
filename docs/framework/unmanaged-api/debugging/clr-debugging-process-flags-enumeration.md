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
ms.openlocfilehash: 292f6953fad0d65b368642543af107c73ec42ab5
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274110"
---
# <a name="clr_debugging_process_flags-enumeration"></a>CLR_DEBUGGING_PROCESS_FLAGS (Enumeración)
Proporciona valores que usa el método [ICLRDebugging:: openvirtualprocess (](iclrdebugging-openvirtualprocess-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|Este Runtime tiene un evento de depurador administrado que no es de puesta en marcha para enviar. Vea la sección Comentarios para ver la distinción entre eventos de puesta al día y de no puesta al día.|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|El evento administrado que está pendiente es una <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> solicitud.|  
  
## <a name="remarks"></a>Comentarios  
 Los eventos de puesta al día incluyen notificaciones de creación de procesos, dominios de aplicación, ensamblados, módulos y subprocesos que ponen el depurador al estado actual una vez que se ha adjuntado a un proceso. Los eventos que no son de puesta al día, que se `CLR_DEBUGGING_MANAGED_EVENT_PENDING` indican mediante la marca, incluyen todos los demás eventos del depurador, como las excepciones y las notificaciones del Asistente para la depuración administrada (MDA).  
  
 La `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` marca permite al motor en tiempo de ejecución diferenciar entre una excepción de terminación y una solicitud para asociar un depurador administrado que se puede cancelar.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: Metahost. idl, Metahost. h  
  
 **Biblioteca** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](debugging-enumerations.md)
- [Depuración](index.md)
