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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 49784a0eba0458a7b9ddbcd58cbe1a187c3c779a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905832"
---
# <a name="corattributetargets-enumeration"></a>CorAttributeTargets (Enumeración)
Especifica los elementos de aplicación en los que se permite aplicar un atributo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
|`catAssembly`|Atributo puede aplicarse a un ensamblado.|  
|`catModule`|Atributo puede aplicarse a un módulo ejecutable portable (.dll o .exe).|  
|`catClass`|Atributo puede aplicarse a una clase.|  
|`catStruct`|Atributo puede aplicarse a una estructura; es decir, un valor de tipo.|  
|`catEnum`|Atributo puede aplicarse a una enumeración.|  
|`catConstructor`|Atributo puede aplicarse a un constructor.|  
|`catMethod`|Atributo puede aplicarse a un método.|  
|`catProperty`|Atributo puede aplicarse a una propiedad.|  
|`catField`|Atributo puede aplicarse a un campo.|  
|`catEvent`|Atributo puede aplicarse a un evento.|  
|`catInterface`|Atributo puede aplicarse a una interfaz.|  
|`catParameter`|Atributo puede aplicarse a un parámetro.|  
|`catDelegate`|Atributo puede aplicarse a un delegado.|  
|`catGenericParameter`|Atributo puede aplicarse a un parámetro genérico.|  
|`catAll`|Atributo puede aplicarse a cualquier elemento de la aplicación.|  
|`catClassMembers`|Atributo puede aplicarse a un miembro de una clase.|  
  
## <a name="remarks"></a>Comentarios  
 El `CorAttributeTargets` valores de enumeración se pueden combinar con una operación OR bit a bit para obtener la combinación preferida.  
  
 El `CorAttributeTargets` es semejante a los recursos administrados <xref:System.AttributeTargets?displayProperty=nameWithType> enumeración.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorHdr.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
