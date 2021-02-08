---
description: 'Más información sobre: enumeración Correftodefcheck ('
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
ms.openlocfilehash: ca9d1c7ceb3d9f82ef8d5f1f54d869db64053e69
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784254"
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
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`MDRefToDefDefault`|Especifica que las referencias de tipo y las referencias de miembro deben convertirse en definiciones. Este es el valor predeterminado ( `MDTypeRefToDef` &#124; `MDMemberRefToDef` ).|  
|`MDRefToDefAll`|Especifica que todos los elementos a los que se hace referencia deben convertirse en definiciones.|  
|`MDRefToDefNone`|Especifica que no se deben convertir los elementos a los que se hace referencia en definiciones.|  
|`MDTypeRefToDef`|Especifica que solo se deben convertir las referencias de tipo en definiciones de tipo.|  
|`MDMemberRefToDef`|Especifica que solo se deben convertir las referencias de miembro en definiciones. Es decir, las referencias de miembro se deben convertir en definiciones de método o definiciones de campo.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](metadata-enumerations.md)
