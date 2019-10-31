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
ms.openlocfilehash: b9185600d9d8b2a33830d86642727ac54b87a9cf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099656"
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
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|El evento administrado que está pendiente es una solicitud de <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType>.|  
  
## <a name="remarks"></a>Comentarios  
 Los eventos de puesta al día incluyen notificaciones de creación de procesos, dominios de aplicación, ensamblados, módulos y subprocesos que ponen el depurador al estado actual una vez que se ha adjuntado a un proceso. Los eventos que no son de puesta al día, que se indican mediante la marca `CLR_DEBUGGING_MANAGED_EVENT_PENDING`, incluyen todos los demás eventos del depurador, como las excepciones y las notificaciones del Asistente para la depuración administrada (MDA).  
  
 La marca de `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` permite al motor en tiempo de ejecución diferenciar entre una excepción de terminación y una solicitud para asociar un depurador administrado que se puede cancelar.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. idl, Metahost. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](debugging-enumerations.md)
- [Depuración](index.md)
