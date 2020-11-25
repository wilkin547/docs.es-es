---
title: ICorDebugCode3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugCode3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3
helpviewer_keywords:
- ICorDebugCode3 interface [.NET Framework debugging]
ms.assetid: 70f07c9e-0614-4bee-ac34-09fe6c51c5a9
topic_type:
- apiref
ms.openlocfilehash: 609cd557db71fac53aadf613534a23e988b14bde
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720764"
---
# <a name="icordebugcode3-interface"></a>ICorDebugCode3 (Interfaz)

Proporciona un método que extiende "ICorDebugCode" y "ICorDebugCode2" para proporcionar información sobre un valor devuelto administrado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md)|Para un desplazamiento de IL especificado, obtiene los desplazamientos nativos donde se debe colocar un punto de interrupción de modo que el depurador pueda obtener el valor devuelto de una función.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugILFrame3 (Interfaz)](icordebugilframe3-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
