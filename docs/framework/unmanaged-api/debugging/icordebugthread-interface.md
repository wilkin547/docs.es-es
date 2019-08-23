---
title: Interfaz ICorDebugThread
ms.date: 03/30/2017
api_name:
- ICorDebugThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread
helpviewer_keywords:
- ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1517d686c50923f5599e33436e0ad6126e8be140
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923140"
---
# <a name="icordebugthread-interface"></a>Interfaz ICorDebugThread
Representa un subproceso de un proceso. El período de duración de una instancia de `ICorDebugThread` es el mismo que el del subproceso que representa.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIPCIÓN|  
|------------|-----------------|  
|[ClearCurrentException (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|Este método no se implementa. No lo utilice.|  
|[CreateEval (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|Crea un objeto ICorDebugEval que funciona en este `ICorDebugThread`.|  
|[CreateStepper (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|Crea un objeto ICorDebugStepper que permite recorrer el marco activo en este `ICorDebugThread`.|  
|[EnumerateChains (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|Obtiene un puntero de interfaz a un enumerador ICorDebugChainEnum (que contiene todas las cadenas de `ICorDebugThread`pila de este.|  
|[GetActiveChain (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|Obtiene un puntero de interfaz a la ICorDebugChain activa en `ICorDebugThread`este.|  
|[GetActiveFrame (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|Obtiene un puntero de interfaz al ICorDebugFrame activo en este `ICorDebugThread`.|  
|[GetAppDomain (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|Obtiene un puntero de interfaz al dominio de aplicación en el `ICorDebugThread` que se está ejecutando actualmente.|  
|[GetCurrentException (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|Obtiene un puntero de interfaz a un objeto ICorDebugValue que representa una excepción que el código administrado está iniciando.|  
|[GetDebugState (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|Obtiene un valor CorDebugThreadState (que describe el estado de depuración `ICorDebugThread`actual de este.|  
|[GetHandle (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|Obtiene el identificador actual para la parte activa de este `ICorDebugThread`.|  
|[GetID (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|Obtiene el identificador del sistema operativo actual de la parte activa de este `ICorDebugThread`.|  
|[GetObject (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|Obtiene un puntero de interfaz al subproceso de Common Language Runtime (CLR).|  
|[GetProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|Obtiene un puntero de interfaz al proceso del que `ICorDebugThread` forma parte.|  
|[GetRegisterSet (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|Obtiene un puntero de interfaz al conjunto de registros asociado a `ICorDebugThread`este.|  
|[GetUserState (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|Obtiene una combinación bit a bit de los valores de CorDebugUserState (que describen el `ICorDebugThread`estado actual de este.|  
|[SetDebugState (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|Establece una combinación bit a `CorDebugThreadState` bit de valores que describen el estado de depuración de este. `ICorDebugThread`|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cordebug. idl, Cordebug. h  
  
 **Biblioteca** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
