---
title: CorDebugMappingResult (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugMappingResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMappingResult
helpviewer_keywords:
- CorDebugMappingResult enumeration [.NET Framework debugging]
ms.assetid: 701281dd-2936-45c8-a1f0-3bf7332b093b
topic_type:
- apiref
ms.openlocfilehash: fc3f77adf33502bfbc3d65ff5131420093fbbec8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097930"
---
# <a name="cordebugmappingresult-enumeration"></a>CorDebugMappingResult (Enumeración)
Proporciona información detallada sobre cómo se obtuvo el valor del puntero de instrucción (IP).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorDebugMappingResult {  
    MAPPING_PROLOG              = 0x1,  
    MAPPING_EPILOG              = 0x2,  
    MAPPING_NO_INFO             = 0x4,  
    MAPPING_UNMAPPED_ADDRESS    = 0x8,  
    MAPPING_EXACT               = 0x10,  
    MAPPING_APPROXIMATE         = 0x20,  
} CorDebugMappingResult;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`MAPPING_PROLOG`|El código nativo está en el prólogo, por lo que el valor de la dirección IP es 0.|  
|`MAPPING_EPILOG`|El código nativo está en un epílogo, por lo que el valor de la dirección IP es la dirección de la última instrucción del método.|  
|`MAPPING_NO_INFO`|No hay información de asignación disponible para el método, por lo que el valor de la dirección IP es 0.|  
|`MAPPING_UNMAPPED_ADDRESS`|Aunque hay información de asignación para el método, la dirección actual no se puede asignar al código del lenguaje intermedio de Microsoft (MSIL). El valor de la dirección IP es 0.|  
|`MAPPING_EXACT`|El método se asigna exactamente al código MSIL o el marco se ha interpretado, por lo que el valor de la dirección IP es preciso.|  
|`MAPPING_APPROXIMATE`|El método se ha asignado correctamente, pero el valor de la dirección IP puede ser aproximado.|  
  
## <a name="remarks"></a>Comentarios  
 Puede usar el método [ICorDebugILFrame:: GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) para obtener el valor del puntero de instrucción.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
