---
title: COR_TYPE_LAYOUT (Estructura)
ms.date: 03/30/2017
api_name:
- COR_TYPE_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPE_LAYOUT
helpviewer_keywords:
- COR_TYPE_LAYOUT structure [.NET Framework debugging]
ms.assetid: 43a7addd-f25a-4049-9907-abec3eb17af2
topic_type:
- apiref
ms.openlocfilehash: f33c8f5cf218979404063342d9b1cc5123839f83
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726332"
---
# <a name="cor_type_layout-structure"></a>COR_TYPE_LAYOUT (Estructura)

Proporciona información sobre la distribución de un objeto en la memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`parentID`|Identificador del tipo primario de este tipo. Será el identificador de tipo NULL (token1 = 0, token2 = 0) si el identificador de tipo corresponde a <xref:System.Object?displayProperty=nameWithType> .|  
|`objectSize`|Tamaño base de un objeto de este tipo. Es el tamaño total de los objetos de tamaño no variable.|  
|`numFields`|El número de campos incluidos en los objetos de este tipo.|  
|`boxOffset`|Si se aplica la conversión boxing a este tipo, el desplazamiento inicial de los campos de un objeto. Este campo solo es válido para tipos de valor como primitivas y estructuras.|  
|`type`|El CorElementType al que pertenece este tipo.|  
  
## <a name="remarks"></a>Comentarios  

 Si `numFields` es mayor que cero, puede llamar al método [ICorDebugProcess5:: gettypefields (](icordebugprocess5-gettypefields-method.md) para obtener información sobre los campos de este tipo. Si `type` es `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY` o `ELEMENT_TYPE_SZARRAY`, el tamaño de los objetos de este tipo es variable y se puede pasar la estructura [COR_TYPEID](cor-typeid-structure.md) al método [ICorDebugProcess5::GetArrayLayout](icordebugprocess5-getarraylayout-method.md).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)
