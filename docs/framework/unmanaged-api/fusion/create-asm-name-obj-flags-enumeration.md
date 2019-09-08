---
title: CREATE_ASM_NAME_OBJ_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- CREATE_ASM_NAME_OBJ_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS
helpviewer_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS enumeration [.NET Framework fusion]
ms.assetid: a5ed2fd0-c7d2-4603-aaca-5d0caad92675
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9897e396424b9076da8f30c61b5a14cfa9539690
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795422"
---
# <a name="create_asm_name_obj_flags-enumeration"></a>CREATE_ASM_NAME_OBJ_FLAGS (Enumeración)
Especifica los atributos de un objeto de [interfaz de IAssemblyName](iassemblyname-interface.md) cuando se construye mediante la función [createassemblynameobject (](createassemblynameobject-function.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|Indica que el parámetro pasado es una identidad textual.|  
|`CANOF_SET_DEFAULT_VALUES`|Establece algunos valores predeterminados.|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|Comprueba la regla de ensamblado de confianza (solo el nombre y la clave pública). Este miembro es solo para uso interno.|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|Combinación de las `CANOF_PARSE_DISPLAY_NAME` marcas y `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` . Este miembro es solo para uso interno.|  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: Fusion. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IAssemblyName (interfaz)](iassemblyname-interface.md)
- [CreateAssemblyNameObject (Función)](createassemblynameobject-function.md)
- [Enumeraciones de fusión](fusion-enumerations.md)
