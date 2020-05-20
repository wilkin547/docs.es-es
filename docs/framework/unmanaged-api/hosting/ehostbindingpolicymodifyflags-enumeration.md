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
ms.openlocfilehash: 256c362ae0aea51fea16ce799db243b105dee81a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616247"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a>EHostBindingPolicyModifyFlags (Enumeración)
Permite al host especificar el tipo de redirección que debe realizar el Common Language Runtime (CLR) al aplicar las modificaciones de directiva de un ensamblado de origen a un ensamblado de destino.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|Especifica que CLR encadenará los valores de la Directiva del ensamblado de origen en los del ensamblado de destino.|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|Especifica que CLR llevará a cabo la acción predeterminada.|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|Especifica que CLR establecerá los valores de directiva del ensamblado de destino en los valores máximos.|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|Especifica que CLR reemplazará los valores de directiva del ensamblado de destino por los del ensamblado de origen.|  
  
## <a name="remarks"></a>Observaciones  
 El método [ICLRHostBindingPolicyManager:: ModifyApplicationPolicy (](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) toma un parámetro de tipo `EHostBindingPolicyModifyFlags` .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [ICLRHostBindingPolicyManager (Interfaz)](iclrhostbindingpolicymanager-interface.md)
- [Enumeraciones para hosts](hosting-enumerations.md)
