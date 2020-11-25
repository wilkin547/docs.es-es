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
ms.openlocfilehash: a0992ca8ac4bfffef681c74de455a0eeb627a042
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726852"
---
# <a name="ebindpolicylevels-enumeration"></a>EBindPolicyLevels (Enumeración)

Proporciona marcas para especificar el nivel en el que se va a aplicar o modificar la Directiva de ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
|`ePolicyLevelAdmin`|Especifica que debe aplicarse la Directiva en el nivel de administrador.|  
|`ePolicyLevelApp`|Especifica que la Directiva debe aplicarse en el nivel de aplicación.|  
|`ePolicyLevelHost`|Especifica que debe aplicarse la Directiva en el nivel de host.|  
|`ePolicyLevelNone`|No especifica ninguna marca de nivel de directiva.|  
|`ePolicyLevelPublisher`|Especifica que debe aplicarse la Directiva en el nivel de publicador.|  
|`ePolicyLevelRetargetable`|Especifica que la Directiva debe ser aplicable en los niveles variables.|  
|`ePolicyPortability`|Especifica que la Directiva debe admitir la portabilidad entre las implementaciones de un ensamblado de .NET Framework. Vea el [\<supportPortability>](../../configure-apps/file-schema/runtime/supportportability-element.md) elemento de archivo de configuración.|  
|`ePolicyUnifiedToCLR`|Especifica que la Directiva se debe unificar con la del Common Language Runtime (CLR).|  
  
## <a name="remarks"></a>Comentarios  

 Esta enumeración se pasa a los métodos de la interfaz [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) para especificar cambios en la Directiva de aplicación.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRAssemblyIdentityManager (Interfaz)](iclrassemblyidentitymanager-interface.md)
- [Enumeraciones para hosts](hosting-enumerations.md)
