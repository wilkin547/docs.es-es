---
title: ICorDebugStackWalk (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStackWalk
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStackWalk
helpviewer_keywords: ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 018ed69e52efd21ca25029284c70f1c8493d877f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstackwalk-interface"></a>ICorDebugStackWalk (Interfaz)
Proporciona métodos para obtener los métodos administrados, o marcos, de la pila de un subproceso.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetContext (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|Devuelve el contexto para el marco actual en el `ICorDebugStackWalk` objeto.|  
|[SetContext (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|Establece el `ICorDebugStackWalk` contexto actual del objeto en un contexto válido para el subproceso.|  
|[Next (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|Mueve el `ICorDebugStackWalk` objeto al marco siguiente.|  
|[GetFrame (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|Obtiene el marco actual el `ICorDebugStackWalk` objeto.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
