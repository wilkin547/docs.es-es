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
ms.openlocfilehash: 5165ef081aad849c11747807d8cc76b2df0a6c74
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729322"
---
# <a name="icordebugthread-interface"></a>Interfaz ICorDebugThread

Representa un subproceso de un proceso. El período de duración de una instancia de `ICorDebugThread` es el mismo que el del subproceso que representa.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método ClearCurrentException](icordebugthread-clearcurrentexception-method.md)|Este método no se implementa. No lo utilice.|  
|[Método CreateEval](icordebugthread-createeval-method.md)|Crea un objeto ICorDebugEval que funciona en este `ICorDebugThread` .|  
|[CreateStepper (Método)](icordebugthread-createstepper-method.md)|Crea un objeto ICorDebugStepper que permite recorrer el marco activo en este `ICorDebugThread` .|  
|[Método EnumerateChains](icordebugthread-enumeratechains-method.md)|Obtiene un puntero de interfaz a un enumerador ICorDebugChainEnum (que contiene todas las cadenas de pila de este `ICorDebugThread` .|  
|[Método GetActiveChain](icordebugthread-getactivechain-method.md)|Obtiene un puntero de interfaz a la ICorDebugChain activa en este `ICorDebugThread` .|  
|[GetActiveFrame (Método)](icordebugthread-getactiveframe-method.md)|Obtiene un puntero de interfaz al ICorDebugFrame activo en este `ICorDebugThread` .|  
|[Método GetAppDomain](icordebugthread-getappdomain-method.md)|Obtiene un puntero de interfaz al dominio de aplicación en el que `ICorDebugThread` se está ejecutando actualmente.|  
|[Método GetCurrentException](icordebugthread-getcurrentexception-method.md)|Obtiene un puntero de interfaz a un objeto ICorDebugValue que representa una excepción que el código administrado está iniciando.|  
|[Método GetDebugState](icordebugthread-getdebugstate-method.md)|Obtiene un valor CorDebugThreadState (que describe el estado de depuración actual de este `ICorDebugThread` .|  
|[Método GetHandle](icordebugthread-gethandle-method.md)|Obtiene el identificador actual para la parte activa de este `ICorDebugThread` .|  
|[Método GetID](icordebugthread-getid-method.md)|Obtiene el identificador del sistema operativo actual de la parte activa de este `ICorDebugThread` .|  
|[GetObject (Método)](icordebugthread-getobject-method.md)|Obtiene un puntero de interfaz al subproceso de Common Language Runtime (CLR).|  
|[Método GetProcess](icordebugthread-getprocess-method.md)|Obtiene un puntero de interfaz al proceso del que `ICorDebugThread` forma parte.|  
|[GetRegisterSet (Método)](icordebugthread-getregisterset-method.md)|Obtiene un puntero de interfaz al conjunto de registros asociado a este `ICorDebugThread` .|  
|[Método GetUserState](icordebugthread-getuserstate-method.md)|Obtiene una combinación bit a bit de los valores de CorDebugUserState (que describen el estado actual de este `ICorDebugThread` .|  
|[Método SetDebugState](icordebugthread-setdebugstate-method.md)|Establece una combinación bit a bit de `CorDebugThreadState` valores que describen el estado de depuración de este `ICorDebugThread` .|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
