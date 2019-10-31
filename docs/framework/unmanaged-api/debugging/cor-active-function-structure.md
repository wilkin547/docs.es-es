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
ms.openlocfilehash: cbc272070e9eb6810b34ec1f3fdc9e944c624cd3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132379"
---
# <a name="cor_active_function-structure"></a>COR_ACTIVE_FUNCTION (Estructura)
Contiene información sobre las funciones que están actualmente activas en los marcos de un subproceso. El método [ICorDebugThread2:: GetActiveFunctions (](icordebugthread2-getactivefunctions-method.md) usa esta estructura.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
|`pAppDomain`|Puntero al propietario del dominio de aplicación del campo `ilOffset`.|  
|`pModule`|Puntero al propietario del módulo del campo `ilOffset`.|  
|`pFunction`|Puntero al propietario de la función del campo de `ilOffset`.|  
|`ilOffset`|Desplazamiento del lenguaje intermedio de Microsoft (MSIL) del marco.|  
|`flags`|Reservado para extensibilidad futura.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cordebug. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)
