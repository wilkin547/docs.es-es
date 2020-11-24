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
ms.openlocfilehash: 0f9cb8db35a1669cead6f9f26c9a89e063628dd8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687676"
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
|`MDNotifyDefault`|Notificar cuándo se `mdTypeRef` `mdMethodDef` `mdMemberRef` `mdFieldDef` mueven los tokens,, o.|  
|`MDNotifyAll`|Notificar cuando se mueva cualquier token.|  
|`MDNotifyNone`|No notifique cuando se muevan los tokens.|  
|`MDNotifyMethodDef`|Notificar cuando `mdMethodDef` se mueva un token.|  
|`MDNotifyMemberRef`|Notificar cuando `mdMemberRef` se mueva un token.|  
|`MDNotifyFieldDef`|Notificar cuando `mdFieldDef` se mueva un token.|  
|`MDNotifyTypeRef`|Notificar cuando `mdTypeRef` se mueva un token.|  
|`MDNotifyTypeDef`|Notificar cuando `mdTypeDef` se mueva un token.|  
|`MDNotifyParamDef`|Notificar cuando `mdParamDef` se mueva un token.|  
|`MDNotifyInterfaceImpl`|Notificar cuando `mdInterfaceImpl` se mueva un token.|  
|`MDNotifyProperty`|Notificar cuando `mdProperty` se mueva un token.|  
|`MDNotifyEvent`|Notificar cuando `mdEvent` se mueva un token.|  
|`MDNotifySignature`|Notificar cuando `mdSignature` se mueva un token.|  
|`MDNotifyTypeSpec`|Notificar cuando `mdTypeSpec` se mueva un token.|  
|`MDNotifyCustomAttribute`|Notificar cuando `mdCustomAttribute` se mueva un token.|  
|`MDNotifySecurityValue`|Notificar cuando `mdSecurityValue` se mueva un token.|  
|`MDNotifyPermission`|Notificar cuando `mdPermission` se mueva un token.|  
|`MDNotifyModuleRef`|Notificar cuando `mdModuleRef` se mueva un token.|  
|`MDNotifyNameSpace`|Notificar cuando `mdNameSpace` se mueva un token.|  
|`MDNotifyAssemblyRef`|Notificar cuando `mdAssemblyRef` se mueva un token.|  
|`MDNotifyFile`|Notificar cuando `mdFile` se mueva un token.|  
|`MDNotifyExportedType`|Notificar cuando `mdExportedType` se mueva un token.|  
|`MDNotifyResource`|Notificar cuando `mdManifestResource` se mueva un token.|  
  
## <a name="remarks"></a>Comentarios  

 Un token puede volver a asignarse (es decir, moverse) durante una fusión mediante combinación de metadatos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para metadatos](metadata-enumerations.md)
