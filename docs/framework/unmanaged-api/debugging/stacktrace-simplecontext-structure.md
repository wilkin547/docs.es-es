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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0625dc72d44485dbb69b42cba5387085d1862bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986536"
---
# <a name="stacktracesimplecontext-structure"></a>StackTrace_SimpleContext (Estructura)
Proporciona un contexto simple que se puede usar en lugar de una estructura `CONTEXT` completa.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
|`StackOffset`|El puntero de pila o el puntero de pila (ESP) en x86 plataformas.|  
|`FrameOffset`|Desplazamiento del marco o registro EBP en x86 plataformas.|  
|`InstructionOffset`|El puntero de instrucción o el puntero de instrucción (EIP) en x86 plataformas.|  
  
## <a name="remarks"></a>Comentarios  
 Dado que las funciones de seguimiento de pila normalmente necesitan devolver la dirección, desplazamiento de trama y dirección de la pila, también puede usar el `SimpleContext` estructura en lugar de un gran `CONTEXT` estructura.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: SOS_Stacktrace.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
