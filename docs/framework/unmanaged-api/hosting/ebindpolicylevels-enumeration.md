---
title: "EBindPolicyLevels (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EBindPolicyLevels
api_location: mscoree.dll
api_type: COM
f1_keywords: EBindPolicyLevels
helpviewer_keywords: EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 52e4d4522c7401aba198deed7853ccca71752d83
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ebindpolicylevels-enumeration"></a>EBindPolicyLevels (Enumeración)
Proporciona las marcas que especifican el nivel en el que se va a aplicar o modificar la directiva de ensamblado.  
  
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
|`ePolicyLevelAdmin`|Especifica que la directiva debe aplicarse en el nivel de administrador.|  
|`ePolicyLevelApp`|Especifica que la directiva debe aplicarse en el nivel de aplicación.|  
|`ePolicyLevelHost`|Especifica que la directiva debe aplicarse en el nivel de host.|  
|`ePolicyLevelNone`|No especifica ningún indicador de nivel de directiva.|  
|`ePolicyLevelPublisher`|Especifica que la directiva debe aplicarse en el nivel del Editor.|  
|`ePolicyLevelRetargetable`|Especifica que Directiva debe aplicarse en niveles variables.|  
|`ePolicyPortability`|Especifica que la directiva debe admitir portabilidad entre las implementaciones de un ensamblado de .NET Framework. Consulte la [ \<supportPortability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) elemento de archivo de configuración.|  
|`ePolicyUnifiedToCLR`|Especifica que la directiva debe unificarse a la de common language runtime (CLR).|  
  
## <a name="remarks"></a>Comentarios  
 Esta enumeración se pasa a métodos de la [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interfaz para especificar los cambios en la directiva de aplicación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRAssemblyIdentityManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
