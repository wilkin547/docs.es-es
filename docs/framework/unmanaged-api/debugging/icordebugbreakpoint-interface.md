---
description: 'Más información acerca de: ICorDebugBreakpoint (interfaz)'
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
ms.openlocfilehash: 63917512cceeccedea37acdf2ba7ab3b849d9fad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711809"
---
# <a name="icordebugbreakpoint-interface"></a>Interfaz ICorDebugBreakpoint

Representa un punto de interrupción en una función o un punto de inspección en un valor.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método Activate](icordebugbreakpoint-activate-method.md)|Establece el estado activo de este `ICorDebugBreakpoint` .|  
|[IsActive (Método)](icordebugbreakpoint-isactive-method.md)|Obtiene un valor que indica si este `ICorDebugBreakpoint` está activo.|  
  
## <a name="remarks"></a>Observaciones  

 Los puntos de interrupción no admiten directamente las expresiones condicionales. Si se desea esta funcionalidad, un depurador debe implementarla en la parte superior de `ICorDebugBreakpoint` .  
  
 La interfaz ICorDebugFunctionBreakpoint `ICorDebugBreakpoint` se extiende para admitir puntos de interrupción dentro de las funciones.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](debugging-interfaces.md)
