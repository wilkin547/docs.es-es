---
title: Interfaz ICorDebugBreakpoint
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
ms.openlocfilehash: b92c3d3328c657762ed002155ef4947a9292b19e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894725"
---
# <a name="icordebugbreakpoint-interface"></a>Interfaz ICorDebugBreakpoint

Representa un punto de interrupción en una función o un punto de inspección en un valor.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método Activate](icordebugbreakpoint-activate-method.md)|Establece el estado activo de este `ICorDebugBreakpoint`.|  
|[IsActive (Método)](icordebugbreakpoint-isactive-method.md)|Obtiene un valor que indica si este `ICorDebugBreakpoint` está activo.|  
  
## <a name="remarks"></a>Observaciones  
 Los puntos de interrupción no admiten directamente las expresiones condicionales. Si se desea esta funcionalidad, un depurador debe implementarla en la `ICorDebugBreakpoint`parte superior de.  
  
 La interfaz ICorDebugFunctionBreakpoint se `ICorDebugBreakpoint` extiende para admitir puntos de interrupción dentro de las funciones.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [Interfaces para depuración](debugging-interfaces.md)
