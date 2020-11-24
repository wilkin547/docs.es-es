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
ms.openlocfilehash: 30775b4a6f904d06b9c77e6b2b64aec693c446d7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671803"
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

 Dado que las funciones de seguimiento de pila normalmente solo necesitan devolver la dirección, el desplazamiento del marco y la dirección de la pila, también puede usar la `SimpleContext` estructura en lugar de una `CONTEXT` estructura grande.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** SOS_Stacktrace. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)
