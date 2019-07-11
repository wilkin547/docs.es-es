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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d9dc94689083d79858319387747eb9dafe8b2f6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739566"
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
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`STEP_NORMAL`|Ejecución paso a paso ha finalizado normalmente, dentro de la misma función.|  
|`STEP_RETURN`|Ejecución paso a paso ha continuado normalmente, después de la función devuelto.|  
|`STEP_CALL`|Ejecución paso a paso ha continuado normalmente, al principio de una función llamada recientemente.|  
|`STEP_EXCEPTION_FILTER`|Se generó una excepción y el control se ha pasado a un filtro de excepciones.|  
|`STEP_EXCEPTION_HANDLER`|Se generó una excepción y el control se ha pasado a un controlador de excepciones.|  
|`STEP_INTERCEPT`|Control se ha pasado a un interceptor.|  
|`STEP_EXIT`|El subproceso se cerró antes de que se ha completado el paso.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StepComplete (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)
- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
