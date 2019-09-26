---
title: COR_DEBUG_STEP_RANGE (Estructura)
ms.date: 03/30/2017
api_name:
- COR_DEBUG_STEP_RANGE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_STEP_RANGE
helpviewer_keywords:
- COR_DEBUG_STEP_RANGE structure [.NET Framework debugging]
ms.assetid: 8809d00e-beaa-4dcf-b4e8-e89d0a5406b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11d5e2eb5e2743fca4876ed09add79be3eba514f
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274203"
---
# <a name="cor_debug_step_range-structure"></a>COR_DEBUG_STEP_RANGE (Estructura)
Contiene información de desplazamiento para un intervalo de código.  
  
 Esta estructura la usa el método [ICorDebugStepper:: steprange (](icordebugstepper-steprange-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`startOffset`|Desplazamiento del principio del intervalo.|  
|`endOffset`|Desplazamiento del final del intervalo.|  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl  
  
 **Biblioteca** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StepRange (método)](icordebugstepper-steprange-method.md)
- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)
