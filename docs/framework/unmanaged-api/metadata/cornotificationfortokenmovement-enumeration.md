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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 745ba18fd1a36789f06bcd3dd4d183c9b28b9875
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650111"
---
# <a name="cornotificationfortokenmovement-enumeration"></a>CorNotificationForTokenMovement (Enumeración)
Especifica las notificaciones que se enviarán al cliente de API de metadatos cuando se produce una reasignación del token.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
|`MDNotifyDefault`|Notificar cuando `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, o `mdFieldDef` movimiento de tokens.|  
|`MDNotifyAll`|Notificar cuando se mueve ningún token.|  
|`MDNotifyNone`|No informan de los tokens de mover.|  
|`MDNotifyMethodDef`|Notificar cuando una `mdMethodDef` movimientos del token.|  
|`MDNotifyMemberRef`|Notificar cuando una `mdMemberRef` movimientos del token.|  
|`MDNotifyFieldDef`|Notificar cuando una `mdFieldDef` movimientos del token.|  
|`MDNotifyTypeRef`|Notificar cuando una `mdTypeRef` movimientos del token.|  
|`MDNotifyTypeDef`|Notificar cuando una `mdTypeDef` movimientos del token.|  
|`MDNotifyParamDef`|Notificar cuando una `mdParamDef` movimientos del token.|  
|`MDNotifyInterfaceImpl`|Notificar cuando una `mdInterfaceImpl` movimientos del token.|  
|`MDNotifyProperty`|Notificar cuando una `mdProperty` movimientos del token.|  
|`MDNotifyEvent`|Notificar cuando una `mdEvent` movimientos del token.|  
|`MDNotifySignature`|Notificar cuando una `mdSignature` movimientos del token.|  
|`MDNotifyTypeSpec`|Notificar cuando una `mdTypeSpec` movimientos del token.|  
|`MDNotifyCustomAttribute`|Notificar cuando una `mdCustomAttribute` movimientos del token.|  
|`MDNotifySecurityValue`|Notificar cuando una `mdSecurityValue` movimientos del token.|  
|`MDNotifyPermission`|Notificar cuando una `mdPermission` movimientos del token.|  
|`MDNotifyModuleRef`|Notificar cuando una `mdModuleRef` movimientos del token.|  
|`MDNotifyNameSpace`|Notificar cuando una `mdNameSpace` movimientos del token.|  
|`MDNotifyAssemblyRef`|Notificar cuando una `mdAssemblyRef` movimientos del token.|  
|`MDNotifyFile`|Notificar cuando una `mdFile` movimientos del token.|  
|`MDNotifyExportedType`|Notificar cuando una `mdExportedType` movimientos del token.|  
|`MDNotifyResource`|Notificar cuando una `mdManifestResource` movimientos del token.|  
  
## <a name="remarks"></a>Comentarios  
 Un token se puede volver a asignar (es decir, mover) durante una combinación de metadatos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorHdr.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
