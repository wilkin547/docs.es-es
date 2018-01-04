---
title: "CorAttributeTargets (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorAttributeTargets
api_location: mscoree.dll
api_type: COM
f1_keywords: CorAttributeTargets
helpviewer_keywords: CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4ce701c026b4e977c376b6e6f0f342b031634e38
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
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
|`catAssembly`|Atributo se puede aplicar a un ensamblado.|  
|`catModule`|Atributo se puede aplicar a un módulo ejecutable portable (.dll o .exe).|  
|`catClass`|Atributo se puede aplicar a una clase.|  
|`catStruct`|Atributo se puede aplicar a una estructura; es decir, un tipo de valor.|  
|`catEnum`|Atributo se puede aplicar a una enumeración.|  
|`catConstructor`|Atributo se puede aplicar a un constructor.|  
|`catMethod`|Atributo se puede aplicar a un método.|  
|`catProperty`|Atributo se puede aplicar a una propiedad.|  
|`catField`|Atributo se puede aplicar a un campo.|  
|`catEvent`|Atributo se puede aplicar a un evento.|  
|`catInterface`|Atributo se puede aplicar a una interfaz.|  
|`catParameter`|Atributo se puede aplicar a un parámetro.|  
|`catDelegate`|Atributo se puede aplicar a un delegado.|  
|`catGenericParameter`|Atributo se puede aplicar a un parámetro genérico.|  
|`catAll`|Atributo se puede aplicar a cualquier elemento de la aplicación.|  
|`catClassMembers`|Atributo se puede aplicar a un miembro de una clase.|  
  
## <a name="remarks"></a>Comentarios  
 El `CorAttributeTargets` valores de enumeración se pueden combinar con una operación OR bit a bit para obtener la combinación preferida.  
  
 El `CorAttributeTargets` se asemeja a los recursos administrados <xref:System.AttributeTargets?displayProperty=nameWithType> enumeración.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr.h  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
