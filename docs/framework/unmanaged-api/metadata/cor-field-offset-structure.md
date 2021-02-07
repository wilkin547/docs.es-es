---
description: 'Más información acerca de: estructura de COR_FIELD_OFFSET'
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
ms.openlocfilehash: 7976e79a5484fa467d7ac887a4e1a7fa324abf69
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678645"
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
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`ridOfField`|`mdFieldDef`Token de metadatos que representa el campo.|  
|`ulOffset`|Desplazamiento del campo dentro de su clase.|  
  
## <a name="remarks"></a>Observaciones  

 Los métodos [IMetaDataImport:: GetClassLayout](imetadataimport-getclasslayout-method.md) y [IMetaDataEmit:: setclasslayout (](imetadataemit-setclasslayout-method.md) toman un parámetro de tipo `COR_FIELD_OFFSET` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h, Corprof. idl  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de metadatos](metadata-structures.md)
- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
