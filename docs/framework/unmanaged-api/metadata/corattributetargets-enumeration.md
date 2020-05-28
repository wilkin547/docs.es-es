---
title: CorAttributeTargets (Enumeración)
ms.date: 03/30/2017
api_name:
- CorAttributeTargets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAttributeTargets
helpviewer_keywords:
- CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type:
- apiref
ms.openlocfilehash: f1836f26af99f91ab1765107573f6b067edd5e95
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007928"
---
# <a name="corattributetargets-enumeration"></a>CorAttributeTargets (Enumeración)
Especifica los elementos de aplicación en los que se permite aplicar un atributo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorAttributeTargets  
{  
    catAssembly            = 0x0001,  
    catModule              = 0x0002,  
    catClass               = 0x0004,  
    catStruct              = 0x0008,  
    catEnum                = 0x0010,  
    catConstructor         = 0x0020,  
    catMethod              = 0x0040,  
    catProperty            = 0x0080,  
    catField               = 0x0100,  
    catEvent               = 0x0200,  
    catInterface           = 0x0400,  
    catParameter           = 0x0800,  
    catDelegate            = 0x1000,  
    catGenericParameter    = 0x4000,  
  
    catAll                 =
        catAssembly | catModule | catClass | catStruct |
        catEnum | catConstructor | catMethod | catProperty |
        catField | catEvent | catInterface | catParameter |
        catDelegate | catGenericParameter,  
  
    catClassMembers        =
        catClass | catStruct | catEnum | catConstructor |
        catMethod | catProperty | catField | catEvent |
        catDelegate | catInterface  
  
} CorAttributeTargets;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`catAssembly`|El atributo puede aplicarse a un ensamblado.|  
|`catModule`|El atributo se puede aplicar a un módulo ejecutable portable (. dll o. exe).|  
|`catClass`|El atributo puede aplicarse a una clase.|  
|`catStruct`|El atributo puede aplicarse a una estructura, es decir, a un tipo de valor.|  
|`catEnum`|El atributo puede aplicarse a una enumeración.|  
|`catConstructor`|El atributo puede aplicarse a un constructor.|  
|`catMethod`|El atributo puede aplicarse a un método.|  
|`catProperty`|El atributo puede aplicarse a una propiedad.|  
|`catField`|El atributo puede aplicarse a un campo.|  
|`catEvent`|El atributo puede aplicarse a un evento.|  
|`catInterface`|El atributo puede aplicarse a una interfaz.|  
|`catParameter`|El atributo puede aplicarse a un parámetro.|  
|`catDelegate`|El atributo puede aplicarse a un delegado.|  
|`catGenericParameter`|El atributo puede aplicarse a un parámetro genérico.|  
|`catAll`|El atributo puede aplicarse a cualquier elemento de la aplicación.|  
|`catClassMembers`|El atributo se puede aplicar a un miembro de una clase.|  
  
## <a name="remarks"></a>Comentarios  
 Los `CorAttributeTargets` valores de enumeración se pueden combinar con una operación OR bit a bit para obtener la combinación preferida.  
  
 La `CorAttributeTargets` enumeración administrada es paralela <xref:System.AttributeTargets?displayProperty=nameWithType> .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para metadatos](metadata-enumerations.md)
