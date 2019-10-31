---
title: ICorDebugThread (Interfaz)
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
ms.openlocfilehash: c7333f4210d0a2ec4ff71a0fac0ea00068fecc57
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133497"
---
# <a name="icordebugthread-interface"></a>ICorDebugThread (Interfaz)
Representa un subproceso de un proceso. El período de duración de una instancia de `ICorDebugThread` es el mismo que el del subproceso que representa.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ClearCurrentException (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|Este método no se implementa. No lo utilice.|  
|[CreateEval (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|Crea un objeto ICorDebugEval que funciona en este `ICorDebugThread`.|  
|[CreateStepper (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|Crea un objeto ICorDebugStepper que permite recorrer en iteración el marco activo en este `ICorDebugThread`.|  
|[EnumerateChains (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|Obtiene un puntero de interfaz a un enumerador ICorDebugChainEnum (que contiene todas las cadenas de pila de este `ICorDebugThread`.|  
|[GetActiveChain (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|Obtiene un puntero de interfaz a la ICorDebugChain activa en este `ICorDebugThread`.|  
|[GetActiveFrame (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|Obtiene un puntero de interfaz al ICorDebugFrame activo en este `ICorDebugThread`.|  
|[GetAppDomain (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|Obtiene un puntero de interfaz al dominio de aplicación en el que se está ejecutando actualmente este `ICorDebugThread`.|  
|[GetCurrentException (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|Obtiene un puntero de interfaz a un objeto ICorDebugValue que representa una excepción que el código administrado está iniciando.|  
|[GetDebugState (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|Obtiene un valor CorDebugThreadState (que describe el estado de depuración actual de este `ICorDebugThread`.|  
|[GetHandle (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|Obtiene el identificador actual para la parte activa de este `ICorDebugThread`.|  
|[GetID (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|Obtiene el identificador del sistema operativo actual de la parte activa de este `ICorDebugThread`.|  
|[GetObject (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|Obtiene un puntero de interfaz al subproceso de Common Language Runtime (CLR).|  
|[GetProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|Obtiene un puntero de interfaz al proceso del que esta `ICorDebugThread` forma una parte.|  
|[GetRegisterSet (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|Obtiene un puntero de interfaz al conjunto de registros asociado a esta `ICorDebugThread`.|  
|[GetUserState (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|Obtiene una combinación bit a bit de los valores de CorDebugUserState (que describen el estado actual de este `ICorDebugThread`.|  
|[SetDebugState (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|Establece una combinación bit a bit de los valores de `CorDebugThreadState` que describen el estado de depuración de este `ICorDebugThread`.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
