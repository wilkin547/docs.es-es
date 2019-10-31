---
title: StackTrace_SimpleContext (Estructura)
ms.date: 03/30/2017
api_name:
- StackTrace_SimpleContext
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SimpleContext
helpviewer_keywords:
- SimpleContext structure [.NET Framework debugging]
- StackTrace_SimpleContext structure [.NET Framework debugging]
ms.assetid: d4cef11f-a8ca-49bc-a1b8-6631f9e28f3e
topic_type:
- apiref
ms.openlocfilehash: 1cd3c34fc292e4a050fa8a75078283e34425fc8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139130"
---
# <a name="stacktrace_simplecontext-structure"></a>StackTrace_SimpleContext (Estructura)
Proporciona un contexto simple que se puede usar en lugar de una estructura `CONTEXT` completa.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`StackOffset`|El puntero de pila o el puntero de pila Enter (ESP) en las plataformas x86.|  
|`FrameOffset`|El desplazamiento del marco o el registro EBP en las plataformas x86.|  
|`InstructionOffset`|El puntero de instrucción o el puntero de instrucción Enter (EIP) en las plataformas x86.|  
  
## <a name="remarks"></a>Comentarios  
 Dado que las funciones de seguimiento de pila normalmente solo necesitan devolver la dirección, el desplazamiento del marco y la dirección de la pila, opcionalmente puede utilizar la estructura de `SimpleContext` en lugar de una estructura de `CONTEXT` grande.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** SOS_Stacktrace. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
