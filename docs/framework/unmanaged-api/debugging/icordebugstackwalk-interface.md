---
description: 'Más información sobre: ICorDebugStackWalk (interfaz)'
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
ms.openlocfilehash: 27dcdfc90829a3a28d81ad28dce0cd4d1d674948
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738096"
---
# <a name="icordebugstackwalk-interface"></a>ICorDebugStackWalk (Interfaz)

Proporciona métodos para obtener los métodos administrados, o marcos, de la pila de un subproceso.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetContext](icordebugstackwalk-getcontext-method.md)|Devuelve el contexto del marco actual del `ICorDebugStackWalk` objeto.|  
|[Método SetContext](icordebugstackwalk-setcontext-method.md)|Establece el `ICorDebugStackWalk` contexto actual del objeto en un contexto válido para el subproceso.|  
|[Next (método)](icordebugstackwalk-next-method.md)|Mueve el `ICorDebugStackWalk` objeto al siguiente fotograma.|  
|[Método GetFrame](icordebugstackwalk-getframe-method.md)|Obtiene el marco actual del `ICorDebugStackWalk` objeto.|  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
