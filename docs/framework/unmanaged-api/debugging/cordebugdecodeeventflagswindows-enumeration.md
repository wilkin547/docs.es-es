---
title: Enumeración CorDebugDecodeEventFlagsWindows
ms.date: 03/30/2017
api_name:
- CorDebugDecodeEventFlagsWindows
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aa6cf962-30ae-4cfd-8895-826deeb46a54
topic_type:
- apiref
ms.openlocfilehash: a90ddd27834e7614c1827d606a9955b4d6c53127
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795981"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a>Enumeración CorDebugDecodeEventFlagsWindows
Proporciona información extra sobre los eventos de depuración en la plataforma Windows.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descripción|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|Indica que el evento de depuración es una primera excepción.|  
  
## <a name="remarks"></a>Comentarios  
 El método [método icordebugprocess6::D ecodeevent](icordebugprocess6-decodeevent-method.md) incluye un `dwFlags` parámetro que proporciona información adicional sobre un evento de depuración y cuyo valor depende de la arquitectura de destino. La enumeración `CorDebugDecodeEventFlagsWindows` se puede usar con eventos de depuración en la plataforma Windows.  
  
> [!NOTE]
> Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](debugging-enumerations.md)
