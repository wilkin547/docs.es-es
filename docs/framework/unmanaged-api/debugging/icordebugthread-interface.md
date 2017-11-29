---
title: ICorDebugThread Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread
helpviewer_keywords: ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 25b5c8f0720402cce56c69394c6fbe2fb70a6177
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthread-interface1"></a>ICorDebugThread Interfaz1
Representa un subproceso de un proceso. El período de duración de una instancia de `ICorDebugThread` es el mismo que el del subproceso que representa.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ClearCurrentException (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|Este método no se implementa. No lo utilice.|  
|[CreateEval (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|Crea un objeto ICorDebugEval que opera en el objeto `ICorDebugThread`.|  
|[CreateStepper (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|Crea un objeto ICorDebugStepper que permite recorrer el fotograma activo en este `ICorDebugThread`.|  
|[EnumerateChains (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|Obtiene un puntero de interfaz a un enumerador ICorDebugChainEnum que contiene todas las cadenas de pila en este `ICorDebugThread`.|  
|[GetActiveChain (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|Obtiene un puntero de interfaz a la ICorDebugChain activa en el objeto `ICorDebugThread`.|  
|[GetActiveFrame (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|Obtiene un puntero de interfaz a la ICorDebugFrame activo en el objeto `ICorDebugThread`.|  
|[GetAppDomain (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|Obtiene un puntero de interfaz al dominio de aplicación en la que `ICorDebugThread` se está ejecutando actualmente.|  
|[GetCurrentException (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|Obtiene un puntero de interfaz a un objeto ICorDebugValue que representa una excepción producida por el código administrado.|  
|[GetDebugState (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|Obtiene un valor de CorDebugThreadState que describe el estado de depuración actual de este `ICorDebugThread`.|  
|[GetHandle (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|Obtiene el identificador actual para la parte activa de este `ICorDebugThread`.|  
|[GetID (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|Obtiene el identificador de sistema operativo actual de la parte activa de este `ICorDebugThread`.|  
|[GetObject (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|Obtiene un puntero de interfaz para el subproceso de common language runtime (CLR).|  
|[GetProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|Obtiene un puntero de interfaz al proceso de que este `ICorDebugThread` constituye una parte.|  
|[GetRegisterSet (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|Obtiene un puntero de interfaz al conjunto de registros asociado a este `ICorDebugThread`.|  
|[GetUserState (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|Obtiene una combinación bit a bit de valores de CorDebugUserState que describen el estado actual de este `ICorDebugThread`.|  
|[SetDebugState (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|Establece una combinación bit a bit de `CorDebugThreadState` valores que describen el estado de depuración de este `ICorDebugThread`.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
