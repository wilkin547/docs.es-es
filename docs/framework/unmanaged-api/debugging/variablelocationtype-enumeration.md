---
title: Enumeración VariableLocationType
ms.date: 03/30/2017
api_name:
- VariableLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- VariableLocationType
helpviewer_keywords:
- VariableLocationType enumeration [.NET Framework debugging]
ms.assetid: 8635ee3a-c84b-4626-876c-416bee54f787
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2093466c78b039a06a01e2d850b88ff4543d0ab3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752461"
---
# <a name="variablelocationtype-enumeration"></a>Enumeración VariableLocationType
Indica el tipo de ubicación nativa de una variable.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`VLT_REGISTER`|La variable está en un registro.|  
|`VLT_REGISTER_RELATIVE`|La variable está en una ubicación de memoria relativa del registro.|  
|`VLT_INVALID`|La variable no se almacena en un registro o una ubicación de memoria relativa del registro.|  
  
## <a name="remarks"></a>Comentarios  
 Un miembro de la `VariableLocationType` enumeración devuelta por la [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
