---
title: ICorDebugRuntimeUnwindableFrame (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugUnwindableFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnwindableFrame
helpviewer_keywords:
- ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type:
- apiref
ms.openlocfilehash: 6619b8888588341f23a93b83865cd2e75cc9b3db
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712019"
---
# <a name="icordebugruntimeunwindableframe-interface"></a>ICorDebugRuntimeUnwindableFrame (Interfaz)

Proporciona compatibilidad para métodos no administrados que necesitan que Common Language Runtime (CLR) desenrede un marco.  
  
## <a name="remarks"></a>Comentarios  

 `ICorDebugRuntimeUnwindableFrame` es una versión especializada de la interfaz ICorDebugFrame. Lo usan los métodos no administrados que requieren que el Runtime desenrede un marco en la pila actual. Las convenciones de desenredado existentes no funcionan, ya que no utilizan código compilado JIT. Cuando el depurador ve un marco que no se pueda desenredar, debe utilizar el método [ICorDebugStackWalk:: Next](icordebugstackwalk-next-method.md) para desenredarlo, pero debe realizar la inspección. Cuando el depurador recibe un `ICorDebugRuntimeUnwindableFrame` , puede llamar al método [ICorDebugStackWalk:: getContext](icordebugstackwalk-getcontext-method.md) para recuperar el contexto del marco.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
