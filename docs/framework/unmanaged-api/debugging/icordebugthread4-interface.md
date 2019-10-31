---
title: ICorDebugThread4 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugThread4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4
helpviewer_keywords:
- ICorDebugThread4 interface [.NET Framework debugging]
ms.assetid: a8c7719a-322b-4133-8566-4c27218dc104
topic_type:
- apiref
ms.openlocfilehash: 8779dbc95a8bef13d45605295bd68b1d3f16851d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122426"
---
# <a name="icordebugthread4-interface"></a>ICorDebugThread4 (Interfaz)
Proporciona información de bloqueo de subprocesos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetBlockingObjects (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getblockingobjects-method.md)|Proporciona una enumeración ordenada de las estructuras [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) que proporcionan información de bloqueo de subprocesos.|  
|[HadUnhandledException (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-hadunhandledexception-method.md)|Indica si el subproceso ha tenido alguna vez una excepción no controlada.|  
|[GetCurrentCustomDebuggerNotification (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md)|Obtiene el objeto [ICorDebugManagedCallback3 (:: customnotification (](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) actual en el subproceso actual.|  
  
## <a name="remarks"></a>Comentarios  
 Esta interfaz es una extensión lógica de las interfaces ICorDebugThread, ICorDebugThread2 y [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) .  
  
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
