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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb58040394d99ae0c5a10672946fa5a6ead5e751
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54533421"
---
# <a name="icordebugstackwalk-interface"></a>ICorDebugStackWalk (Interfaz)
Proporciona métodos para obtener los métodos administrados, o marcos, de la pila de un subproceso.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetContext (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|Devuelve el contexto para el fotograma actual en el `ICorDebugStackWalk` objeto.|  
|[SetContext (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|Establece el `ICorDebugStackWalk` contexto actual del objeto en un contexto válido para el subproceso.|  
|[Next (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|Mueve el `ICorDebugStackWalk` objeto al marco siguiente.|  
|[GetFrame (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|Obtiene el marco actual el `ICorDebugStackWalk` objeto.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
