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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2042d0936359a85d203375c42be0d8a096f004e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739763"
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
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`MAPPING_PROLOG`|El código nativo está en el prólogo, por lo que el valor de la dirección IP es 0.|  
|`MAPPING_EPILOG`|El código nativo está en un epílogo, por lo que el valor de la dirección IP es la dirección de la última instrucción del método.|  
|`MAPPING_NO_INFO`|No hay información de asignación está disponible para el método, por lo que el valor de la dirección IP es 0.|  
|`MAPPING_UNMAPPED_ADDRESS`|Aunque no hay información de asignación para el método, no se puede asignar la dirección actual al código de lenguaje intermedio (MSIL) de Microsoft. El valor de la dirección IP es 0.|  
|`MAPPING_EXACT`|El método se asigna exactamente a código MSIL o interpreta el marco, por lo que el valor de la dirección IP es preciso.|  
|`MAPPING_APPROXIMATE`|El método se ha asignado correctamente, pero el valor de la dirección IP puede ser aproximado.|  
  
## <a name="remarks"></a>Comentarios  
 Puede usar el [ICorDebugILFrame:: GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) método para obtener el valor del puntero de instrucción.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
