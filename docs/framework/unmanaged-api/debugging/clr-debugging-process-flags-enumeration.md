---
title: "CLR_DEBUGGING_PROCESS_FLAGS (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLR_DEBUGGING_PROCESS_FLAGS
api_location: mscordbi.dll
api_type: COM
f1_keywords: CLR_DEBUGGING_PROCESS_FLAG
helpviewer_keywords: CLR_DEBUGGING_PROCESS_FLAGS enumeration [.NET Framework debugging]
ms.assetid: 85b85fde-1f87-490b-ba8d-d604670959c3
topic_type: apiref
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5040b1e1eb7ec4bd814329de156fcdfeb9c383c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
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
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|Este tiempo de ejecución tiene un evento de depurador administrado-catch-up para enviar. Vea la sección Comentarios para la distinción entre eventos de puesta al día y -catch-up.|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|Es el evento administrado que está pendiente un <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> solicitud.|  
  
## <a name="remarks"></a>Comentarios  
 Eventos de puesta al día incluyen proceso, dominio de aplicación, ensamblado, módulo y las notificaciones de creación de subproceso que poner al depurador hasta el estado actual después de que ha adjuntado a un proceso. Eventos de no-catch-up, que se indican mediante el `CLR_DEBUGGING_MANAGED_EVENT_PENDING` marca, incluir todos los otros eventos del depurador, como las excepciones y administra depuración notificaciones Ayudante (MDA).  
  
 El `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` marca permite que el tiempo de ejecución diferenciar entre una excepción de terminación y una solicitud para adjuntar un depurador administrado que se puede cancelar.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Metahost.idl, Metahost.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
