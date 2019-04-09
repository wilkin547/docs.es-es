---
title: CorRefToDefCheck (Enumeración)
ms.date: 03/30/2017
api_name:
- CorRefToDefCheck
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRefToDefCheck
helpviewer_keywords:
- CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82abeb0ce3db075d794787bb1fcd5bc18321bef2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093896"
---
# <a name="correftodefcheck-enumeration"></a>CorRefToDefCheck (Enumeración)
Especifica marcas para controlar qué elementos referenciados se convierten en sus definiciones para optimizar el código.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`MDRefToDefDefault`|Especifica que se debe convertir a las definiciones de las referencias de tipo y miembro. Este es el valor predeterminado (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).|  
|`MDRefToDefAll`|Especifica que se deben convertir todos los elementos que se hace referencia a las definiciones.|  
|`MDRefToDefNone`|Especifica que no hay elementos que se hace referencia deben convertirse a las definiciones.|  
|`MDTypeRefToDef`|Especifica que solo las referencias de tipos se deben convertir las definiciones de tipo.|  
|`MDMemberRefToDef`|Especifica que solo las referencias de miembro deben convertirse a las definiciones. Es decir, las referencias de miembro deben convertirse en definiciones de método o definiciones de campo.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorHdr.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
