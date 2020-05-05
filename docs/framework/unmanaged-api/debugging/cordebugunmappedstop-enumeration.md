---
title: CorDebugUnmappedStop (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugUnmappedStop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUnmappedStop
helpviewer_keywords:
- CorDebugUnmappedStop enumeration [.NET Framework debugging]
ms.assetid: a684f7d7-d0c2-4690-b721-639e613f11f8
topic_type:
- apiref
ms.openlocfilehash: 772f1f0dee260ad3752b2f89e5fbe0d6bc27b87b
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795656"
---
# <a name="cordebugunmappedstop-enumeration"></a>CorDebugUnmappedStop (Enumeración)
Especifica el tipo de código no asignado que puede hacer que la ejecución paso a paso desencadene una detención de la ejecución del código.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorDebugUnmappedStop {  
    STOP_NONE               = 0x0,  
    STOP_PROLOG             = 0x01,  
    STOP_EPILOG             = 0x02,  
    STOP_NO_MAPPING_INFO    = 0x04,  
    STOP_OTHER_UNMAPPED     = 0x08,  
    STOP_UNMANAGED          = 0x10,  
    STOP_ALL                = 0xffff,  
} CorDebugUnmappedStop;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descripción|  
|------------|-----------------|  
|`STOP_NONE`|No se detenga en ningún tipo de código sin asignar.|  
|`STOP_PROLOG`|Detenga el código de prólogo.|  
|`STOP_EPILOG`|Detenga el código de epílogo.|  
|`STOP_NO_MAPPING_INFO`|Detenga el código que no tenga información de asignación.|  
|`STOP_OTHER_UNMAPPED`|Detenga en el código no asignado que no se ajuste a la categoría prólogo, epílogo, sin asignación-información o no administrada.|  
|`STOP_UNMANAGED`|Detenga el código no administrado. Este valor solo es válido con la depuración de interoperabilidad.|  
|`STOP_ALL`|Detenga en todos los tipos de código sin asignar.|  
  
## <a name="remarks"></a>Comentarios  
 Use el método [ICorDebugStepper:: setunmappedstopmask (](icordebugstepper-setunmappedstopmask-method.md) para establecer las marcas que especifican el código no asignado en el que se detendrá el stepper.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](debugging-enumerations.md)
