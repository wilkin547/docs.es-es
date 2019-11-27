---
title: CorNotificationForTokenMovement (Enumeración)
ms.date: 03/30/2017
api_name:
- CorNotificationForTokenMovement
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNotificationForTokenMovement
helpviewer_keywords:
- CorNotificationForTokenMovement enumeration [.NET Framework metadata]
ms.assetid: 1edd1670-976a-4fc8-bef7-7c41e60ad989
topic_type:
- apiref
ms.openlocfilehash: 411fad0accb59431f776c5bd66e8bd3027ddd907
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450149"
---
# <a name="cornotificationfortokenmovement-enumeration"></a>CorNotificationForTokenMovement (Enumeración)
Especifica las notificaciones que se enviarán al cliente de la API de metadatos cuando se produzca una reasignación de token.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorNotificationForTokenMovement {  
  
    MDNotifyDefault             = 0x0000000f,  
    MDNotifyAll                 = 0xffffffff,  
    MDNotifyNone                = 0x00000000,  
    MDNotifyMethodDef           = 0x00000001,  
    MDNotifyMemberRef           = 0x00000002,  
    MDNotifyFieldDef            = 0x00000004,  
    MDNotifyTypeRef             = 0x00000008,  
  
    MDNotifyTypeDef             = 0x00000010,  
    MDNotifyParamDef            = 0x00000020,  
    MDNotifyInterfaceImpl       = 0x00000040,  
    MDNotifyProperty            = 0x00000080,  
    MDNotifyEvent               = 0x00000100,  
    MDNotifySignature           = 0x00000200,  
    MDNotifyTypeSpec            = 0x00000400,  
    MDNotifyCustomAttribute     = 0x00000800,  
    MDNotifySecurityValue       = 0x00001000,  
    MDNotifyPermission          = 0x00002000,  
    MDNotifyModuleRef           = 0x00004000,  
  
    MDNotifyNameSpace           = 0x00008000,  
  
    MDNotifyAssemblyRef         = 0x01000000,  
    MDNotifyFile                = 0x02000000,  
    MDNotifyExportedType        = 0x04000000,  
    MDNotifyResource            = 0x08000000  
  
} CorNotificationForTokenMovement;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`MDNotifyDefault`|Notificar cuando se muevan los tokens `mdTypeRef`, `mdMethodDef`, `mdMemberRef`o `mdFieldDef`.|  
|`MDNotifyAll`|Notificar cuando se mueva cualquier token.|  
|`MDNotifyNone`|No notifique cuando se muevan los tokens.|  
|`MDNotifyMethodDef`|Notificar cuando se mueve un token de `mdMethodDef`.|  
|`MDNotifyMemberRef`|Notificar cuando se mueve un token de `mdMemberRef`.|  
|`MDNotifyFieldDef`|Notificar cuando se mueve un token de `mdFieldDef`.|  
|`MDNotifyTypeRef`|Notificar cuando se mueve un token de `mdTypeRef`.|  
|`MDNotifyTypeDef`|Notificar cuando se mueve un token de `mdTypeDef`.|  
|`MDNotifyParamDef`|Notificar cuando se mueve un token de `mdParamDef`.|  
|`MDNotifyInterfaceImpl`|Notificar cuando se mueve un token de `mdInterfaceImpl`.|  
|`MDNotifyProperty`|Notificar cuando se mueve un token de `mdProperty`.|  
|`MDNotifyEvent`|Notificar cuando se mueve un token de `mdEvent`.|  
|`MDNotifySignature`|Notificar cuando se mueve un token de `mdSignature`.|  
|`MDNotifyTypeSpec`|Notificar cuando se mueve un token de `mdTypeSpec`.|  
|`MDNotifyCustomAttribute`|Notificar cuando se mueve un token de `mdCustomAttribute`.|  
|`MDNotifySecurityValue`|Notificar cuando se mueve un token de `mdSecurityValue`.|  
|`MDNotifyPermission`|Notificar cuando se mueve un token de `mdPermission`.|  
|`MDNotifyModuleRef`|Notificar cuando se mueve un token de `mdModuleRef`.|  
|`MDNotifyNameSpace`|Notificar cuando se mueve un token de `mdNameSpace`.|  
|`MDNotifyAssemblyRef`|Notificar cuando se mueve un token de `mdAssemblyRef`.|  
|`MDNotifyFile`|Notificar cuando se mueve un token de `mdFile`.|  
|`MDNotifyExportedType`|Notificar cuando se mueve un token de `mdExportedType`.|  
|`MDNotifyResource`|Notificar cuando se mueve un token de `mdManifestResource`.|  
  
## <a name="remarks"></a>Comentarios  
 Un token puede volver a asignarse (es decir, moverse) durante una fusión mediante combinación de metadatos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
