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
ms.openlocfilehash: e2fa5d5a998f51e0e90cfde22b40ec12f278307b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178356"
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
  
## <a name="members"></a>Members  
  
|Member|Descripción|  
|------------|-----------------|  
|`VLT_REGISTER`|La variable está en un registro.|  
|`VLT_REGISTER_RELATIVE`|La variable se encuentra en una ubicación de memoria relativa al registro.|  
|`VLT_INVALID`|La variable no se almacena en un registro o en una ubicación de memoria relativa al registro.|  
  
## <a name="remarks"></a>Observaciones  
 Un miembro `VariableLocationType` de la enumeración es devuelto por el [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones de depuración](debugging-enumerations.md)
