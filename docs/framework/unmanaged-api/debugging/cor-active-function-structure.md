---
title: COR_ACTIVE_FUNCTION (Estructura)
ms.date: 03/30/2017
api_name:
- COR_ACTIVE_FUNCTION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ACTIVE_FUNCTION
helpviewer_keywords:
- COR_ACTIVE_FUNCTION structure [.NET Framework debugging]
ms.assetid: ed86185f-2152-459c-961f-10c06d62e83f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5adf43bd68db449e465ffe3517c9eb9d41a5c18a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54502057"
---
# <a name="coractivefunction-structure"></a>COR_ACTIVE_FUNCTION (Estructura)
Contiene información sobre las funciones que están actualmente activas en los marcos de un subproceso. Esta estructura se usa por la [Icordebugthread2](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md) método.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`pAppDomain`|Puntero en el propietario del dominio de aplicación de la `ilOffset` campo.|  
|`pModule`|Puntero al propietario del módulo de la `ilOffset` campo.|  
|`pFunction`|Puntero al propietario de la función de la `ilOffset` campo.|  
|`ilOffset`|El desplazamiento de lenguaje intermedio (MSIL) de Microsoft del marco.|  
|`flags`|Reservado para extensibilidad futura.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
