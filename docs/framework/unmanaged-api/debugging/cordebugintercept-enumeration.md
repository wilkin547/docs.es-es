---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 148bc423a9497962ebfbc73faefcc799c6db6499
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739900"
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
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`INTERCEPT_NONE`|No se puede interceptar ningún código.|  
|`INTERCEPT_CLASS_INIT`|Se puede interceptar un constructor.|  
|`INTERCEPT_EXCEPTION_FILTER`|Se puede interceptar un filtro de excepción.|  
|`INTERCEPT_SECURITY`|Se puede interceptar código que exija seguridad.|  
|`INTERCEPT_CONTEXT_POLICY`|Se puede interceptar una directiva de contexto.|  
|`INTERCEPT_INTERCEPTION`|No se utiliza.|  
|`INTERCEPT_ALL`|Se puede interceptar todo el código.|  
  
## <a name="remarks"></a>Comentarios  
 Use la [SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) método para establecer los tipos de código que se pueden interceptar.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
