---
title: "CorDebugStepReason (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugStepReason
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugStepReason
helpviewer_keywords: CorDebugStepReason enumeration [.NET Framework debugging]
ms.assetid: fe248069-b33c-48e1-a777-06ac9b239c54
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 32892a14de820e8add38654cef92aa44930aec62
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugstepreason-enumeration"></a>CorDebugStepReason (Enumeración)
Indica el resultado de un paso individual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CorDebugStepReason {  
    STEP_NORMAL,  
    STEP_RETURN,  
    STEP_CALL,  
    STEP_EXCEPTION_FILTER,  
    STEP_EXCEPTION_HANDLER,  
    STEP_INTERCEPT,  
    STEP_EXIT  
} CorDebugStepReason;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`STEP_NORMAL`|Ejecución paso a paso ha finalizado normalmente, dentro de la misma función.|  
|`STEP_RETURN`|Ejecución paso a paso ha continuado normalmente, después de que devuelva la función.|  
|`STEP_CALL`|Ejecución paso a paso ha continuado normalmente, al principio de una función llamada recientemente.|  
|`STEP_EXCEPTION_FILTER`|Se generó una excepción y el control se ha pasado a un filtro de excepción.|  
|`STEP_EXCEPTION_HANDLER`|Se generó una excepción y el control se ha pasado a un controlador de excepciones.|  
|`STEP_INTERCEPT`|Control se ha pasado a un interceptor.|  
|`STEP_EXIT`|El subproceso se cerró antes de que se complete el paso.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [StepComplete (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)  
 [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
