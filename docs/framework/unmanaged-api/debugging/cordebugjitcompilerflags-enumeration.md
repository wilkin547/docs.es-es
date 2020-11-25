---
title: CorDebugJITCompilerFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlags
helpviewer_keywords:
- CorDebugJITCompilerFlags enumeration [.NET Framework debugging]
ms.assetid: c0774f70-5bed-45e8-9922-fdad778c4c33
topic_type:
- apiref
ms.openlocfilehash: 0c8398b9e423414f32a391edcd5ea1c709af37f5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696575"
---
# <a name="cordebugjitcompilerflags-enumeration"></a>CorDebugJITCompilerFlags (Enumeración)

Contiene valores que influyen en el comportamiento del compilador Just-In-Time (JIT) administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|Especifica que el compilador debe realizar el seguimiento de los datos de compilación y permite las optimizaciones.|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|Especifica que el compilador debe realizar el seguimiento de los datos de compilación, pero deshabilita las optimizaciones.|  
|`CORDEBUG_JIT_ENABLE_ENC`|Especifica que el compilador debe realizar el seguimiento de los datos de compilación, deshabilita las optimizaciones y habilita las tecnologías editar y continuar.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones de depuración](debugging-enumerations.md)
