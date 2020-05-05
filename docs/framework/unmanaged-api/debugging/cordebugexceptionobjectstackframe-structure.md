---
title: CorDebugExceptionObjectStackFrame (Estructura)
ms.date: 03/30/2017
api_name:
- CorDebugExceptionObjectStackFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionObjectStackFrame
helpviewer_keywords:
- CorDebugExceptionObjectStackFrame structure [.NET Framework debugging]
ms.assetid: 542cdd81-5ae7-4361-b0ef-1ae4775df258
topic_type:
- apiref
ms.openlocfilehash: 7eccaf984b187e463195bb3804f87bbb2c7ad47b
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795929"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a>CorDebugExceptionObjectStackFrame (Estructura)
Representa información del marco de pila de un objeto de excepción.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descripción|  
|------------|-----------------|  
|`pModule`|Puntero al objeto ICorDebugModule para el marco actual.|  
|`ip`|El valor del puntero de instrucción (EIP/RIP) para el marco actual.|  
|`methodDef`|El token del método para el marco actual.|  
|`isLastForeignExceptionFrame`|Valor que indica si el marco es el último fotograma en una excepción externa.|  
  
## <a name="remarks"></a>Comentarios  
 El llamador debe liberar el puntero al objeto ICorDebugModule una vez que ya no esté en uso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)
