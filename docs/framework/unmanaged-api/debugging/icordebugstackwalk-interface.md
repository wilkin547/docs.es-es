---
title: ICorDebugStackWalk (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
ms.openlocfilehash: b37a89c0a86df49c894dc43676f8feafb80f5c95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687520"
---
# <a name="icordebugstackwalk-interface"></a>ICorDebugStackWalk (Interfaz)

Proporciona métodos para obtener los métodos administrados, o marcos, de la pila de un subproceso.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetContext](icordebugstackwalk-getcontext-method.md)|Devuelve el contexto del marco actual del `ICorDebugStackWalk` objeto.|  
|[Método SetContext](icordebugstackwalk-setcontext-method.md)|Establece el `ICorDebugStackWalk` contexto actual del objeto en un contexto válido para el subproceso.|  
|[Next (Método)](icordebugstackwalk-next-method.md)|Mueve el `ICorDebugStackWalk` objeto al siguiente fotograma.|  
|[Método GetFrame](icordebugstackwalk-getframe-method.md)|Obtiene el marco actual del `ICorDebugStackWalk` objeto.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
