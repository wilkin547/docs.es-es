---
title: EHostBindingPolicyModifyFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- EHostBindingPolicyModifyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EHostBindingPolicyModifyFlags
helpviewer_keywords:
- EHostBindingPolicyModifyFlags enumeration [.NET Framework hosting]
ms.assetid: 0339af16-ee1d-48ec-837d-a79d9a9c89f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fa8cc15f77ff59e3d3c570341d9bba70cf1e953
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a>EHostBindingPolicyModifyFlags (Enumeración)
Permite al host especificar el tipo de redireccionamiento que debe realizar common language runtime (CLR) al aplicar las modificaciones de directiva de un ensamblado de origen a un ensamblado de destino.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|Especifica que CLR encadenará los valores de directiva del ensamblado de origen a los del ensamblado de destino.|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|Especifica que el CLR llevará a cabo la acción predeterminada.|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|Especifica que el CLR establecerá los valores de directiva del ensamblado de destino para los valores máximos.|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|Especifica que CLR reemplazará los valores de directiva del ensamblado de destino con los del ensamblado de origen.|  
  
## <a name="remarks"></a>Comentarios  
 El [ICLRHostBindingPolicyManager:: ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) método toma un parámetro de tipo `EHostBindingPolicyModifyFlags`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRHostBindingPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
