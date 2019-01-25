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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 512122d264e0817b89e8a371f57f11d31f7c4380
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54639652"
---
# <a name="cordebugjitcompilerflags-enumeration"></a>CorDebugJITCompilerFlags (Enumeración)
Contiene valores que influyen en el comportamiento del compilador Just-In-Time (JIT) administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|Especifica que el compilador debe realizar un seguimiento de los datos de compilación y permite las optimizaciones.|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|Especifica que el compilador debe realizar el seguimiento de los datos de compilación, pero deshabilita las optimizaciones.|  
|`CORDEBUG_JIT_ENABLE_ENC`|Especifica que el compilador debe realizar un seguimiento de datos de compilación, deshabilita las optimizaciones, y permite editar y continuar de tecnologías.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
