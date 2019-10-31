---
title: CorDebugStepReason (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugStepReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugStepReason
helpviewer_keywords:
- CorDebugStepReason enumeration [.NET Framework debugging]
ms.assetid: fe248069-b33c-48e1-a777-06ac9b239c54
topic_type:
- apiref
ms.openlocfilehash: 6c73afb00cbd104cff3d310d1369097b459c131e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133687"
---
# <a name="cordebugstepreason-enumeration"></a>CorDebugStepReason (Enumeración)
Indica el resultado de un paso individual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
|`STEP_NORMAL`|La ejecución paso a paso se completó normalmente, dentro de la misma función.|  
|`STEP_RETURN`|La ejecución continuará normalmente, después de que se devuelva la función.|  
|`STEP_CALL`|El paso continuó normalmente, al principio de una función recién llamada.|  
|`STEP_EXCEPTION_FILTER`|Se generó una excepción y se pasó el control a un filtro de excepciones.|  
|`STEP_EXCEPTION_HANDLER`|Se generó una excepción y se pasó el control a un controlador de excepciones.|  
|`STEP_INTERCEPT`|El control se pasó a un interceptor.|  
|`STEP_EXIT`|El subproceso se cerró antes de que se completara el paso.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StepComplete (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)
- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
