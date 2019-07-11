---
title: COR_FIELD (Estructura)
ms.date: 03/30/2017
api_name:
- COR_FIELD
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_FIELD
helpviewer_keywords:
- COR_FIELD structure [.NET Framework debugging]
ms.assetid: c0822423-a9df-4961-950d-50dcc152f863
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2efe159eaa8b49d4d3825e9737593d0a12fc4d4c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740737"
---
# <a name="corfield-structure"></a>COR_FIELD (Estructura)
Proporciona información sobre un campo en un objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`token`|Un `mdFieldDef` símbolo (token) que puede usarse para obtener información de campo.|  
|`offset`|El desplazamiento, en bytes, para los datos del campo en el objeto.|  
|`id`|Un [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) valor que identifica el tipo de este campo.|  
|`fieldType`|Un valor de enumeración CorElementType que indica el tipo del campo.|  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
