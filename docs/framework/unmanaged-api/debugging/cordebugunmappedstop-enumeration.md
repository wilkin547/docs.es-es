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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d812a452910913f169d4377bafa82e823c533d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="cordebugunmappedstop-enumeration"></a>CorDebugUnmappedStop (Enumeración)
Especifica el tipo de código no asignado que puede hacer que la ejecución paso a paso desencadene una detención de la ejecución del código.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`STOP_NONE`|No se detenga en cualquier tipo de código no asignado.|  
|`STOP_PROLOG`|Detenga en código de prólogo.|  
|`STOP_EPILOG`|Detener en el código de epílogo.|  
|`STOP_NO_MAPPING_INFO`|Detenga en código que no tiene ninguna información de asignación.|  
|`STOP_OTHER_UNMAPPED`|Detenga en código no asignado que no encaja en el prólogo, el epílogo, la información de asignación no o la categoría no administrado.|  
|`STOP_UNMANAGED`|Detenga en código no administrado. Este valor solo es válido con depuración de interoperabilidad.|  
|`STOP_ALL`|Detener en todos los tipos de código no asignado.|  
  
## <a name="remarks"></a>Comentarios  
 Use la [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) método para establecer las marcas que especifican el código no asignado en el que se detendrá el paso a paso desencadene.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
