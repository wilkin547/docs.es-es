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
ms.openlocfilehash: e6c3c9b842bd823e8975661964480fd801779b2d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450121"
---
# <a name="correftodefcheck-enumeration"></a>CorRefToDefCheck (Enumeración)
Especifica marcas para controlar qué elementos referenciados se convierten en sus definiciones para optimizar el código.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
|`MDRefToDefDefault`|Especifica que las referencias de tipo y las referencias de miembro deben convertirse en definiciones. Este es el valor predeterminado (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).|  
|`MDRefToDefAll`|Especifica que todos los elementos a los que se hace referencia deben convertirse en definiciones.|  
|`MDRefToDefNone`|Especifica que no se deben convertir los elementos a los que se hace referencia en definiciones.|  
|`MDTypeRefToDef`|Especifica que solo se deben convertir las referencias de tipo en definiciones de tipo.|  
|`MDMemberRefToDef`|Especifica que solo se deben convertir las referencias de miembro en definiciones. Es decir, las referencias de miembro se deben convertir en definiciones de método o definiciones de campo.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
