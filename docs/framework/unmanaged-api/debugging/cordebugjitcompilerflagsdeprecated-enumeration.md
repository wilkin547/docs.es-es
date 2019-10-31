---
title: CorDebugJITCompilerFlagsDeprecated (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugJITCompilerFlagsDeprecated
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlagsDeprecated
helpviewer_keywords:
- CorDebugJITCompilerFlagsDeprecated enumeration [.NET Framework debugging]
ms.assetid: af15e2ca-6be1-472b-bd36-03644a1e3ddd
topic_type:
- apiref
ms.openlocfilehash: d731b12ddf195137ff38d32ab0ca52aa90f48d4e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132782"
---
# <a name="cordebugjitcompilerflagsdeprecated-enumeration"></a>CorDebugJITCompilerFlagsDeprecated (Enumeración)
Esta enumeración está obsoleta. En su lugar, use el miembro `CORDEBUG_JIT_DEFAULT` de la enumeración [cordebugjitcompilerflags (](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorDebugJITCompilerFlagsDeprecated {  
    CORDEBUG_JIT_TRACK_DEBUG_INFO  = 0x1  
} CorDebugJITCompilerFlagsDeprecated;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`CORDEBUG_JIT_TRACK_DEBUG_INFO`|Utilice `CORDEBUG_JIT_DEFAULT` en su lugar.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** 1,0, 1,1  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
