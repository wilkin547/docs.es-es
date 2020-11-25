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
ms.openlocfilehash: 1c94e03aa088d8f48eb7f7a418cebd0492319513
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696601"
---
# <a name="cordebuginternalframetype-enumeration"></a>CorDebugInternalFrameType (Enumeración)

Identifica el tipo de marco de pila. Esta enumeración la usa el método [ICorDebugInternalFrame (:: GetFrameType (](icordebuginternalframe-getframetype-method.md) .  
  
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
  
|Miembro|Descripción|  
|------------|-----------------|  
|`STUBFRAME_NONE`|Un valor cero. El `ICorDebugInternalFrame::GetFrameType` método nunca devuelve este valor.|  
|`STUBFRAME_M2U`|Marco de código auxiliar administrado a no administrado.|  
|`STUBFRAME_U2M`|Marco de código auxiliar no administrado que se administra.|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|Una transición entre dominios de aplicación.|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|Llamada al método ligero.|  
|`STUBFRAME_FUNC_EVAL`|Inicio de la evaluación de la función.|  
|`STUBFRAME_INTERNALCALL`|Una llamada interna en el Common Language Runtime.|  
|`STUBFRAME_CLASS_INIT`|Inicio de una inicialización de clase.|  
|`STUBFRAME_EXCEPTION`|Excepción que se produce.|  
|`STUBFRAME_SECURITY`|Marco que se usa para la seguridad de acceso del código.|  
|`STUBFRAME_JIT_COMPILATION`|El tiempo de ejecución es una compilación JIT de un método.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones de depuración](debugging-enumerations.md)
