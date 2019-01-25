---
title: Enumeración CorDebugStateChange
ms.date: 03/30/2017
api_name:
- CorDebugStateChange
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f0f692b692628d50755ce813c66823f940dccb8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513794"
---
# <a name="cordebugstatechange-enumeration"></a>Enumeración CorDebugStateChange
Describe la cantidad de datos almacenados en caché que se debe descartar según los cambios en el proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CorDebugStateChange  
{  
    PROCESS_RUNNING = 0x0000001,   
    FLUSH_ALL       = 0x0000002,   
} CorDebugStateChange;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`PROCESS_RUNNING`|El proceso alcanzó un nuevo estado de memoria por ejecución directa.|  
|`SET_CONTEXT_FLAG_UNWIND_FRAME`|La memoria del proceso puede ser diferente de forma arbitraria de lo que era anteriormente.|  
  
## <a name="remarks"></a>Comentarios  
 Un miembro de la `CorDebugStateChange` enumeración se proporciona como un argumento cuando el depurador llama a la [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) (método)  
  
> [!NOTE]
>  Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
