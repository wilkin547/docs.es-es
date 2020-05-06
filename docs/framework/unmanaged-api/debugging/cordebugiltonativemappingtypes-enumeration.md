---
title: CorDebugIlToNativeMappingTypes (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugIlToNativeMappingTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIlToNativeMappingTypes
helpviewer_keywords:
- CorDebugIIToNativeMappingTypes enumeration [.NET Framework debugging]
ms.assetid: c35e2919-42c3-4ba0-ae28-443c35f66f93
topic_type:
- apiref
ms.openlocfilehash: 808fc70a308eff1b05aa49ea2bb89fe53377c973
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795851"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a>CorDebugIlToNativeMappingTypes (Enumeración)
Indica si un determinado intervalo de instrucciones nativas, representado por una instancia de la estructura COR_DEBUG_IL_TO_NATIVE_MAP, corresponde a una región de código especial.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descripción|  
|------------|-----------------|  
|`NO_MAPPING`|El intervalo de instrucciones nativas no se corresponde con ninguna región de código especial.|  
|`PROLOG`|El intervalo de instrucciones nativas corresponde al prólogo.|  
|`EPILOG`|El intervalo de instrucciones nativas corresponde al epílogo.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método GetILToNativeMapping](icordebugcode-getiltonativemapping-method.md)
- [Enumeraciones de depuración](debugging-enumerations.md)
