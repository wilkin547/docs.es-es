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
ms.openlocfilehash: 5f83cb96e39b257a1d35786130cd5ed31d071de7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443870"
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
|`catAssembly`|El atributo se puede aplicar a un ensamblado.|  
|`catModule`|El atributo se puede aplicar a un módulo ejecutable portable (. dll o. exe).|  
|`catClass`|El atributo se puede aplicar a una clase.|  
|`catStruct`|El atributo se puede aplicar a una estructura; es decir, un tipo de valor.|  
|`catEnum`|El atributo se puede aplicar a una enumeración.|  
|`catConstructor`|El atributo se puede aplicar a un constructor.|  
|`catMethod`|El atributo se puede aplicar a un método.|  
|`catProperty`|El atributo se puede aplicar a una propiedad.|  
|`catField`|El atributo se puede aplicar a un campo.|  
|`catEvent`|El atributo se puede aplicar a un evento.|  
|`catInterface`|El atributo se puede aplicar a una interfaz.|  
|`catParameter`|El atributo se puede aplicar a un parámetro.|  
|`catDelegate`|El atributo se puede aplicar a un delegado.|  
|`catGenericParameter`|El atributo se puede aplicar a un parámetro genérico.|  
|`catAll`|El atributo se puede aplicar a cualquier elemento de la aplicación.|  
|`catClassMembers`|El atributo se puede aplicar a un miembro de una clase.|  
  
## <a name="remarks"></a>Comentarios  
 Los valores de enumeración de `CorAttributeTargets` se pueden combinar con una operación OR bit a bit para obtener la combinación preferida.  
  
 El `CorAttributeTargets` en paralelo a la enumeración de <xref:System.AttributeTargets?displayProperty=nameWithType> administrados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
