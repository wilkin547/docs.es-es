---
description: 'Más información sobre: enumeración Cormethodsemanticsattr ('
title: CorMethodSemanticsAttr (Enumeración)
ms.date: 03/30/2017
api_name:
- CorMethodSemanticsAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodSemanticsAttr
helpviewer_keywords:
- CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type:
- apiref
ms.openlocfilehash: 4079e81ae2389ff0684fd11d0751b191a7289932
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784371"
---
# <a name="cormethodsemanticsattr-enumeration"></a>CorMethodSemanticsAttr (Enumeración)

Contiene valores que describen la relación entre un método y una propiedad o evento asociados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`msSetter`|Especifica que el método es un `set` descriptor de acceso para una propiedad.|  
|`msGetter`|Especifica que el método es un `get` descriptor de acceso para una propiedad.|  
|`msOther`|Especifica que el método tiene una relación con una propiedad o un evento distintos de los que se definen aquí.|  
|`msAddOn`|Especifica que el método agrega métodos de controlador para un evento.|  
|`msRemoveOn`|Especifica que el método quita los métodos de controlador de un evento.|  
|`msFire`|Especifica que el método genera un evento.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](metadata-enumerations.md)
