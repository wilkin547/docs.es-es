---
description: 'Más información sobre: enumeración CorDebugSetContextFlag ('
title: CorDebugSetContextFlag (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugSetContextFlag
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugSetContextFlag
helpviewer_keywords:
- CorDebugSetContextFlag enumeration [.NET Framework debugging]
ms.assetid: b30280bb-fe75-44ed-8589-bcff081fae44
topic_type:
- apiref
ms.openlocfilehash: 625f24e516ff462cf3d0e628dfff6c08793807ce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801558"
---
# <a name="cordebugsetcontextflag-enumeration"></a>CorDebugSetContextFlag (Enumeración)

Indica si el contexto procede del marco activo (u hoja) en la pila o si se ha calculado mediante desenredo de otro marco.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|SET_CONTEXT_FLAG_ACTIVE_FRAME|El contexto es el contexto activo del subproceso.|  
|SET_CONTEXT_FLAG_UNWIND_FRAME|El contexto se ha calculado desenredando de otro marco.|  
  
## <a name="remarks"></a>Observaciones  

 `CorDebugSetContextFlag` proporciona valores que usa el método [ICorDebugStackWalk:: SetContext](icordebugstackwalk-setcontext-method.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](debugging-enumerations.md)
- [Depuración](index.md)
