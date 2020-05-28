---
title: CorPropertyAttr (Enumeración)
ms.date: 03/30/2017
api_name:
- CorPropertyAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPropertyAttr
helpviewer_keywords:
- CorPropertyAttr enumeration [.NET Framework metadata]
ms.assetid: 58ac8202-854d-4efd-acfb-d2da8b446e12
topic_type:
- apiref
ms.openlocfilehash: b6651f30e0df3a5ffc29d310b9067e76761dcf01
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007538"
---
# <a name="corpropertyattr-enumeration"></a>CorPropertyAttr (Enumeración)
Contiene valores que describen los metadatos de una propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`prSpecialName`|Especifica que la propiedad es especial y que su nombre describe cómo.|  
|`prReservedMask`|Reservado para uso interno por el Common Language Runtime.|  
|`prRTSpecialName`|Especifica que las API internas de metadatos de Common Language Runtime deben comprobar la codificación del nombre de la propiedad.|  
|`prHasDefault`|Especifica que la propiedad tiene un valor predeterminado.|  
|`prUnused`|Sin usar.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para metadatos](metadata-enumerations.md)
