---
description: 'Más información sobre: enumeración CorPropertyAttr ('
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
ms.openlocfilehash: 1f3e2fccb11a067c6c46350a2c36d47007875755
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784241"
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
  
## <a name="members"></a>Members  
  
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
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](metadata-enumerations.md)
