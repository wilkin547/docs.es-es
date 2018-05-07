---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de467c98dfa7ad3eac69502f2afe311b301e1ec5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="cormethodsemanticsattr-enumeration"></a>CorMethodSemanticsAttr (Enumeración)
Contiene valores que describen la relación entre un método y una propiedad o evento asociados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`msSetter`|Especifica que el método es un `set` descriptor de acceso para una propiedad.|  
|`msGetter`|Especifica que el método es un `get` descriptor de acceso para una propiedad.|  
|`msOther`|Especifica que el método tiene una relación con una propiedad o un evento distintos de los definidos aquí.|  
|`msAddOn`|Especifica que el método agrega métodos de controlador de un evento.|  
|`msRemoveOn`|Especifica que el método quita los métodos de control para un evento.|  
|`msFire`|Especifica que el método genera un evento.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr.h  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
