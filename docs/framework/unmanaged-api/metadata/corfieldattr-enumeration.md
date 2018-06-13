---
title: CorFieldAttr (Enumeración)
ms.date: 03/30/2017
api_name:
- CorFieldAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFieldAttr
helpviewer_keywords:
- CorFieldAttr enumeration [.NET Framework metadata]
ms.assetid: 6ae2c4be-212c-4e74-9288-40a11dc26522
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a57318103fd875d6f2f2fe4ca54c776da86c0e53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446625"
---
# <a name="corfieldattr-enumeration"></a>CorFieldAttr (Enumeración)
Contiene valores que describen los metadatos de un campo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CorFieldAttr {  
  
    fdFieldAccessMask           =   0x0007,  
    fdPrivateScope              =   0x0000,  
    fdPrivate                   =   0x0001,  
    fdFamANDAssem               =   0x0002,  
    fdAssembly                  =   0x0003,  
    fdFamily                    =   0x0004,  
    fdFamORAssem                =   0x0005,  
    fdPublic                    =   0x0006,  
  
    fdStatic                    =   0x0010,  
    fdInitOnly                  =   0x0020,  
    fdLiteral                   =   0x0040,  
    fdNotSerialized             =   0x0080,  
  
    fdSpecialName               =   0x0200,  
  
    fdPinvokeImpl               =   0x2000,  
  
    fdReservedMask              =   0x9500,  
    fdRTSpecialName             =   0x0400,  
    fdHasFieldMarshal           =   0x1000,  
    fdHasDefault                =   0x8000,  
    fdHasFieldRVA               =   0x0100  
  
} CorFieldAttr;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`fdFieldAccessMask`|Especifica información de accesibilidad.|  
|`fdPrivateScope`|Especifica que el campo no puede hacer referencia.|  
|`fdPrivate`|Especifica que el campo solo es accesible para su tipo primario.|  
|`fdFamANDAssem`|Especifica que el campo está accesible para las clases derivadas de su ensamblado.|  
|`fdAssembly`|Especifica que el campo está accesible para todos los tipos de su ensamblado.|  
|`fdFamily`|Especifica que el campo solo es accesible para su tipo y sus clases derivadas.|  
|`fdFamORAssem`|Especifica que el campo es accesible para las clases derivadas y para todos los tipos de su ensamblado.|  
|`fdPublic`|Especifica que el campo está accesible para todos los tipos con visibilidad de este ámbito.|  
|`fdStatic`|Especifica que el campo es un miembro de su tipo en lugar de un miembro de instancia.|  
|`fdInitOnly`|Especifica que el campo no se puede cambiar una vez que se inicializa.|  
|`fdLiteral`|Especifica que el valor del campo es una constante de tiempo de compilación.|  
|`fdNotSerialized`|Especifica que no se serializa el campo cuando su tipo es remoto.|  
|`fdSpecialName`|Especifica que el campo es especial y que su nombre describe cómo.|  
|`fdPinvokeImpl`|Especifica que la implementación del campo se reenvía a través de PInvoke.|  
|`fdReservedMask`|Reservado para uso interno por common language runtime.|  
|`fdRTSpecialName`|Especifica que los metadatos de common language runtime API internas deben comprobar la codificación del nombre.|  
|`fdHasFieldMarshal`|Especifica que el campo contiene información de serialización.|  
|`fdHasDefault`|Especifica que el campo tiene un valor predeterminado.|  
|`fdHasFieldRVA`|Especifica que el campo tiene una dirección virtual relativa.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr.h  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
