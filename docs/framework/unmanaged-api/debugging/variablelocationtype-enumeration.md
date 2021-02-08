---
description: 'Más información sobre: enumeración VariableLocationType'
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
ms.openlocfilehash: 8561077b9f3f4d318eeb743d51538b2a9a22a217
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800531"
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
  
|Miembro|Descripción|  
|------------|-----------------|  
|`VLT_REGISTER`|La variable está en un registro.|  
|`VLT_REGISTER_RELATIVE`|La variable está en una ubicación de memoria relativa de registro.|  
|`VLT_INVALID`|La variable no se almacena en un registro o en una ubicación de memoria relativa al registro.|  
  
## <a name="remarks"></a>Observaciones  

 `VariableLocationType`El método [ICorDebugVariableHome:: GetLocationType](icordebugvariablehome-getlocationtype-method.md) devuelve un miembro de la enumeración.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](debugging-enumerations.md)
