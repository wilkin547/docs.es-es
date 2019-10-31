---
title: CorDebugExceptionFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugExceptionFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionFlags
helpviewer_keywords:
- CorDebugExceptionFlags enumeration [.NET Framework debugging]
ms.assetid: b22687a8-e9cf-4e65-a1b0-f92a81bc524e
topic_type:
- apiref
ms.openlocfilehash: 198de0aed4e229d7ed8bb1679afc3a0102bd5368
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098460"
---
# <a name="cordebugexceptionflags-enumeration"></a>CorDebugExceptionFlags (Enumeración)
Proporciona información adicional sobre una excepción.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|No hay ninguna excepción.|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|La excepción se puede interceptar.<br /><br /> Sin embargo, la temporización de la excepción podría hacer que el depurador no la intercepte. Por ejemplo, si no hay ningún código administrado debajo de la devolución de llamada actual o el evento de excepción se produjo por una asociación Just-In-Time (JIT), la excepción no se puede interceptar.|  
  
## <a name="remarks"></a>Comentarios  
 Se pueden agregar nuevos valores a esta enumeración en versiones posteriores, por lo que debe preparar el código que usa `CorDebugExceptionFlags` para valores no esperados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
