---
title: CorDebugInternalFrameType (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugInternalFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInternalFrameType
helpviewer_keywords:
- CorDebugInternalFrameType enumeration [.NET Framework debugging]
ms.assetid: e4412dc2-c338-4cfb-94d8-f682095dd2b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1dcbd8bb566331a6a2d4217eeec0441fbd3e6ff6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739857"
---
# <a name="cordebuginternalframetype-enumeration"></a>CorDebugInternalFrameType (Enumeración)
Identifica el tipo de marco de pila. Esta enumeración se utiliza en el [ICorDebugInternalFrame:: GetFrameType](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md) método.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorDebugInternalFrameType {  
  
    STUBFRAME_NONE                 = 0x00000000,  
    STUBFRAME_M2U                  = 0x00000001,  
    STUBFRAME_U2M                  = 0x00000002,  
    STUBFRAME_APPDOMAIN_TRANSITION = 0x00000003,  
    STUBFRAME_LIGHTWEIGHT_FUNCTION = 0x00000004,  
    STUBFRAME_FUNC_EVAL            = 0x00000005,  
    STUBFRAME_INTERNALCALL         = 0x00000006,  
    STUBFRAME_CLASS_INIT           = 0x00000007,  
    STUBFRAME_EXCEPTION            = 0x00000008,  
    STUBFRAME_SECURITY             = 0x00000009,  
    STUBFRAME_JIT_COMPILATION     = 0x0000000a,  
} CorDebugInternalFrameType;  
```  
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`STUBFRAME_NONE`|Un valor cero. El `ICorDebugInternalFrame::GetFrameType` método nunca devuelve este valor.|  
|`STUBFRAME_M2U`|Un marco de código auxiliar a administrado.|  
|`STUBFRAME_U2M`|Un marco de código auxiliar no administrado a administrado.|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|Una transición entre los dominios de aplicación.|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|Una llamada de método ligero.|  
|`STUBFRAME_FUNC_EVAL`|Inicio de la evaluación de función.|  
|`STUBFRAME_INTERNALCALL`|Una llamada interna en common language runtime.|  
|`STUBFRAME_CLASS_INIT`|Inicio de la inicialización de una clase.|  
|`STUBFRAME_EXCEPTION`|Una excepción que se produce.|  
|`STUBFRAME_SECURITY`|Un marco que se usa para la seguridad de acceso del código.|  
|`STUBFRAME_JIT_COMPILATION`|El tiempo de ejecución es un método de compilación JIT.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
