---
title: ICorDebugBreakpoint (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint
helpviewer_keywords:
- ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type:
- apiref
ms.openlocfilehash: 29bb84341c2cb4177c43f798d25a1a6d50099aa5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122798"
---
# <a name="icordebugbreakpoint-interface"></a>ICorDebugBreakpoint (Interfaz)

Representa un punto de interrupción en una función o un punto de inspección en un valor.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Activate (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|Establece el estado activo de este `ICorDebugBreakpoint`.|  
|[IsActive (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|Obtiene un valor que indica si este `ICorDebugBreakpoint` está activo.|  
  
## <a name="remarks"></a>Comentarios  
 Los puntos de interrupción no admiten directamente las expresiones condicionales. Si se desea esta funcionalidad, un depurador debe implementarla encima de `ICorDebugBreakpoint`.  
  
 La interfaz ICorDebugFunctionBreakpoint extiende `ICorDebugBreakpoint` para admitir puntos de interrupción dentro de las funciones.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
