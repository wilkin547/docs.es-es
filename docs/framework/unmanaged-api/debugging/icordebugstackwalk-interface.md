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
ms.openlocfilehash: 48f1b485b6dfa8fd898f6ea00eee2d7b397deba6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131868"
---
# <a name="icordebugstackwalk-interface"></a>ICorDebugStackWalk (Interfaz)
Proporciona métodos para obtener los métodos administrados, o marcos, de la pila de un subproceso.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetContext (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|Devuelve el contexto del marco actual en el objeto `ICorDebugStackWalk`.|  
|[SetContext (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|Establece el contexto actual del objeto `ICorDebugStackWalk` en un contexto válido para el subproceso.|  
|[Next (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|Mueve el objeto de `ICorDebugStackWalk` al fotograma siguiente.|  
|[GetFrame (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|Obtiene el marco actual del objeto `ICorDebugStackWalk`.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
