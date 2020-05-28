---
title: CorValidatorModuleType (Enumeración)
ms.date: 03/30/2017
api_name:
- CorValidatorModuleType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorValidatorModuleType
helpviewer_keywords:
- CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type:
- apiref
ms.openlocfilehash: 038e2ec20e5fd01edf9835080e0f7a15ec862fd9
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008942"
---
# <a name="corvalidatormoduletype-enumeration"></a>CorValidatorModuleType (Enumeración)
Especifica el tipo de un módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum  
{  
    ValidatorModuleTypeInvalid  = 0x0,  
    ValidatorModuleTypeMin      = 0x00000001,  
    ValidatorModuleTypePE       = 0x00000001,  
    ValidatorModuleTypeObj      = 0x00000002,  
    ValidatorModuleTypeEnc      = 0x00000003,  
    ValidatorModuleTypeIncr     = 0x00000004,  
    ValidatorModuleTypeMax      = 0x00000004  
} CorValidatorModuleType;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|El módulo es un tipo no válido.|  
|`ValidatorModuleTypeMin`|Valor mínimo de la `CorValidatorModuleType` enumeración.|  
|`ValidatorModuleTypePE`|El módulo es un archivo ejecutable portable (PE).|  
|`ValidatorModuleTypeObj`|El módulo es un archivo. obj.|  
|`ValidatorModuleTypeEnc`|El módulo es una sesión de depurador de edición y continuación.|  
|`ValidatorModuleTypeIncr`|El módulo es uno que se ha compilado incrementalmente.|  
|`ValidatorModuleTypeMax`|Valor máximo de la `CorValidatorModuleType` enumeración.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para metadatos](metadata-enumerations.md)
