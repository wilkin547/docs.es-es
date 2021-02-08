---
description: 'Más información sobre: enumeración ESymbolReadingPolicy ('
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
ms.openlocfilehash: e84c31343b589cb6019d88fafc9b94207c5f5892
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785424"
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
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`eSymbolReadingAlways`|Especifica que el depurador siempre debe leer los archivos PDB.|  
|`eSymbolReadingFullTrustOnly`|Especifica que el depurador debe leer solo los archivos PDB asociados a los ensamblados de plena confianza.|  
|`eSymbolReadingNever`|Especifica que el depurador nunca debe leer archivos PDB.|  
  
## <a name="remarks"></a>Observaciones  

 La `ESymbolReadingPolicy` enumeración se usa con el método [ICLRDebugManager:: SetSymbolReadingPolicy (](iclrdebugmanager-setsymbolreadingpolicy-method.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para hosts](hosting-enumerations.md)
