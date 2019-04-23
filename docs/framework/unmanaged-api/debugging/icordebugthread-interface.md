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
ms.openlocfilehash: db322bbdc7293410968542d0d22c572edb87795a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184709"
---
# <a name="icordebugthread-interface"></a>Interfaz ICorDebugThread
Representa un subproceso de un proceso. El período de duración de una instancia de `ICorDebugThread` es el mismo que el del subproceso que representa.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ClearCurrentException (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|Este método no se implementa. No lo utilice.|  
|[CreateEval (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|Crea un objeto ICorDebugEval que funciona en este `ICorDebugThread`.|  
|[CreateStepper (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|Crea un objeto ICorDebugStepper que permite recorrer el fotograma activo en este `ICorDebugThread`.|  
|[EnumerateChains (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|Obtiene un puntero de interfaz a un enumerador ICorDebugChainEnum que contiene todas las cadenas de pila en este `ICorDebugThread`.|  
|[GetActiveChain (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|Obtiene un puntero de interfaz a la ICorDebugChain activo en este `ICorDebugThread`.|  
|[GetActiveFrame (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|Obtiene un puntero de interfaz al marco ICorDebugFrame activo en este `ICorDebugThread`.|  
|[GetAppDomain (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|Obtiene un puntero de interfaz al dominio de aplicación en el que `ICorDebugThread` se está ejecutando actualmente.|  
|[GetCurrentException (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|Obtiene un puntero de interfaz a un objeto ICorDebugValue que representa una excepción iniciada actualmente mediante código administrado.|  
|[GetDebugState (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|Obtiene un valor de CorDebugThreadState que describe el estado de depuración actual de este `ICorDebugThread`.|  
|[GetHandle (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|Obtiene el identificador actual para la parte activa de este `ICorDebugThread`.|  
|[GetID (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|Obtiene el identificador de sistema operativo actual de la parte activa de este `ICorDebugThread`.|  
|[GetObject (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|Obtiene un puntero de interfaz para el subproceso de common language runtime (CLR).|  
|[GetProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|Obtiene un puntero de interfaz al proceso del que `ICorDebugThread` constituye una parte.|  
|[GetRegisterSet (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|Obtiene un puntero de interfaz al conjunto de registros asociado a este `ICorDebugThread`.|  
|[GetUserState (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|Obtiene una combinación bit a bit de valores de CorDebugUserState que describen el estado actual de este `ICorDebugThread`.|  
|[SetDebugState (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|Establece una combinación bit a bit de `CorDebugThreadState` valores que describen el estado de depuración de este `ICorDebugThread`.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
