---
title: ESymbolReadingPolicy (Enumeración)
ms.date: 03/30/2017
api_name:
- ESymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ESymbolReadingPolicy
helpviewer_keywords:
- ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type:
- apiref
ms.openlocfilehash: 786ff6895383fc18dcfedb26fab344f80f04c1df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138207"
---
# <a name="esymbolreadingpolicy-enumeration"></a>ESymbolReadingPolicy (Enumeración)
Contiene valores que establecen la Directiva para leer archivos de base de datos de programa (PDB).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`eSymbolReadingAlways`|Especifica que el depurador siempre debe leer los archivos PDB.|  
|`eSymbolReadingFullTrustOnly`|Especifica que el depurador debe leer solo los archivos PDB asociados a los ensamblados de plena confianza.|  
|`eSymbolReadingNever`|Especifica que el depurador nunca debe leer archivos PDB.|  
  
## <a name="remarks"></a>Comentarios  
 La enumeración `ESymbolReadingPolicy` se usa con el método [ICLRDebugManager:: SetSymbolReadingPolicy (](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
