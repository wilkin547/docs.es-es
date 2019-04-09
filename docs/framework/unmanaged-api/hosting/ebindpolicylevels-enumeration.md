---
title: EBindPolicyLevels (Enumeración)
ms.date: 03/30/2017
api_name:
- EBindPolicyLevels
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EBindPolicyLevels
helpviewer_keywords:
- EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8f2b08662e719a3308a62ab5b60f5dc490f2a6a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142212"
---
# <a name="ebindpolicylevels-enumeration"></a>EBindPolicyLevels (Enumeración)
Proporciona marcas para especificar el nivel en el que se va a aplicar o modificar la directiva de ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum {  
    ePolicyLevelNone         = 0x0,  
    ePolicyLevelRetargetable = 0x1,  
    ePolicyUnifiedToCLR      = 0x2,  
    ePolicyLevelApp          = 0x4,  
    ePolicyLevelPublisher    = 0x8,  
    ePolicyLevelHost         = 0x10,  
    ePolicyLevelAdmin        = 0x20  
    ePolicyPortability       = 0x40  
} EBindPolicyLevels;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|Especifica que debe aplicarse la directiva en el nivel de administrador.|  
|`ePolicyLevelApp`|Especifica que debe aplicarse la directiva en el nivel de aplicación.|  
|`ePolicyLevelHost`|Especifica que debe aplicarse la directiva a nivel de host.|  
|`ePolicyLevelNone`|No especifica ningún indicador de nivel de directiva.|  
|`ePolicyLevelPublisher`|Especifica que debe aplicarse la directiva en el nivel de publicador.|  
|`ePolicyLevelRetargetable`|Especifica que Directiva debe aplicarse en niveles variables.|  
|`ePolicyPortability`|Especifica que Directiva debe admitir la portabilidad entre las implementaciones de un ensamblado de .NET Framework. Consulte la [ \<supportPortability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) elemento del archivo de configuración.|  
|`ePolicyUnifiedToCLR`|Especifica que la directiva debe unificarse para que el de common language runtime (CLR).|  
  
## <a name="remarks"></a>Comentarios  
 Esta enumeración se pasa a los métodos de la [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interfaz para especificar los cambios en la directiva de aplicación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRAssemblyIdentityManager (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
