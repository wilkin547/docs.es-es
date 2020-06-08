---
title: COR_FIELD_OFFSET (Estructura)
ms.date: 03/30/2017
api_name:
- COR_FIELD_OFFSET
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_FIELD_OFFSET
helpviewer_keywords:
- COR_FIELD_OFFSET structure [.NET Framework metadata]
ms.assetid: cced5298-277f-4a5a-8ecf-a0050c1096ea
topic_type:
- apiref
ms.openlocfilehash: 8cc803e3cf1442d324bf2eed0a37d0d236acd86d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493090"
---
# <a name="cor_field_offset-structure"></a>COR_FIELD_OFFSET (Estructura)
Almacena el desplazamiento, dentro de una clase, del campo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`ridOfField`|`mdFieldDef`Token de metadatos que representa el campo.|  
|`ulOffset`|Desplazamiento del campo dentro de su clase.|  
  
## <a name="remarks"></a>Comentarios  
 Los métodos [IMetaDataImport:: GetClassLayout](imetadataimport-getclasslayout-method.md) y [IMetaDataEmit:: setclasslayout (](imetadataemit-setclasslayout-method.md) toman un parámetro de tipo `COR_FIELD_OFFSET` .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h, Corprof. idl  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Estructuras de metadatos](metadata-structures.md)
- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
