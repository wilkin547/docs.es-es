---
description: 'Más información sobre: enumeración Cordebugintercept ('
title: CorDebugIntercept (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugIntercept
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIntercept
helpviewer_keywords:
- CorDebugIntercept enumeration [.NET Framework debugging]
ms.assetid: 3d5b642e-7ef2-428b-a5ae-509c35ed461a
topic_type:
- apiref
ms.openlocfilehash: ddd17aff309396fdcda37c731ff907224ee17db2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661979"
---
# <a name="cordebugintercept-enumeration"></a>CorDebugIntercept (Enumeración)

Indica los tipos de código que se pueden interceptar, es decir, ejecutar paso a paso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorDebugIntercept {  
    INTERCEPT_NONE                = 0x0,  
    INTERCEPT_CLASS_INIT          = 0x01,  
    INTERCEPT_EXCEPTION_FILTER    = 0x02,  
    INTERCEPT_SECURITY            = 0x04,  
    INTERCEPT_CONTEXT_POLICY      = 0x08,  
    INTERCEPT_INTERCEPTION        = 0x10,  
    INTERCEPT_ALL                 = 0xffff  
} CorDebugIntercept;  
```  
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`INTERCEPT_NONE`|No se puede interceptar ningún código.|  
|`INTERCEPT_CLASS_INIT`|Se puede interceptar un constructor.|  
|`INTERCEPT_EXCEPTION_FILTER`|Se puede interceptar un filtro de excepción.|  
|`INTERCEPT_SECURITY`|Se puede interceptar código que exija seguridad.|  
|`INTERCEPT_CONTEXT_POLICY`|Se puede interceptar una directiva de contexto.|  
|`INTERCEPT_INTERCEPTION`|No se usa.|  
|`INTERCEPT_ALL`|Se puede interceptar todo el código.|  
  
## <a name="remarks"></a>Observaciones  

 Use el método [ICorDebugStepper:: setinterceptmask (](icordebugstepper-setinterceptmask-method.md) para establecer los tipos de código que se pueden interceptar.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](debugging-enumerations.md)
