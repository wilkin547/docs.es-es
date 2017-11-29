---
title: "CorNotificationForTokenMovement (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorNotificationForTokenMovement
api_location: mscoree.dll
api_type: COM
f1_keywords: CorNotificationForTokenMovement
helpviewer_keywords: CorNotificationForTokenMovement enumeration [.NET Framework metadata]
ms.assetid: 1edd1670-976a-4fc8-bef7-7c41e60ad989
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 60d6c56394952fca84b45ba042f7d45a1dec6b1c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="cornotificationfortokenmovement-enumeration"></a>CorNotificationForTokenMovement (Enumeración)
Especifica las notificaciones que se enviará al cliente de API de metadatos cuando se produce una reasignación de símbolo (token).  
  
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
|`MDNotifyDefault`|Notificar cuando `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, o `mdFieldDef` movimiento de símbolos (tokens).|  
|`MDNotifyAll`|Notificar cuando se mueve ningún símbolo (token).|  
|`MDNotifyNone`|No notificar cuando se mueva de símbolos (tokens).|  
|`MDNotifyMethodDef`|Notificar cuando un `mdMethodDef` símbolo (token) se mueve.|  
|`MDNotifyMemberRef`|Notificar cuando un `mdMemberRef` símbolo (token) se mueve.|  
|`MDNotifyFieldDef`|Notificar cuando un `mdFieldDef` símbolo (token) se mueve.|  
|`MDNotifyTypeRef`|Notificar cuando un `mdTypeRef` símbolo (token) se mueve.|  
|`MDNotifyTypeDef`|Notificar cuando un `mdTypeDef` símbolo (token) se mueve.|  
|`MDNotifyParamDef`|Notificar cuando un `mdParamDef` símbolo (token) se mueve.|  
|`MDNotifyInterfaceImpl`|Notificar cuando un `mdInterfaceImpl` símbolo (token) se mueve.|  
|`MDNotifyProperty`|Notificar cuando un `mdProperty` símbolo (token) se mueve.|  
|`MDNotifyEvent`|Notificar cuando un `mdEvent` símbolo (token) se mueve.|  
|`MDNotifySignature`|Notificar cuando un `mdSignature` símbolo (token) se mueve.|  
|`MDNotifyTypeSpec`|Notificar cuando un `mdTypeSpec` símbolo (token) se mueve.|  
|`MDNotifyCustomAttribute`|Notificar cuando un `mdCustomAttribute` símbolo (token) se mueve.|  
|`MDNotifySecurityValue`|Notificar cuando un `mdSecurityValue` símbolo (token) se mueve.|  
|`MDNotifyPermission`|Notificar cuando un `mdPermission` símbolo (token) se mueve.|  
|`MDNotifyModuleRef`|Notificar cuando un `mdModuleRef` símbolo (token) se mueve.|  
|`MDNotifyNameSpace`|Notificar cuando un `mdNameSpace` símbolo (token) se mueve.|  
|`MDNotifyAssemblyRef`|Notificar cuando un `mdAssemblyRef` símbolo (token) se mueve.|  
|`MDNotifyFile`|Notificar cuando un `mdFile` símbolo (token) se mueve.|  
|`MDNotifyExportedType`|Notificar cuando un `mdExportedType` símbolo (token) se mueve.|  
|`MDNotifyResource`|Notificar cuando un `mdManifestResource` símbolo (token) se mueve.|  
  
## <a name="remarks"></a>Comentarios  
 Un símbolo (token) se puede volver a asignar (es decir, mover) durante una combinación de metadatos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr.h  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
