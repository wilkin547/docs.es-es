---
description: 'Más información acerca de: interfaz ICorDebugThread2'
title: Interfaz ICorDebugThread2
ms.date: 03/30/2017
api_name:
- ICorDebugThread2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2
helpviewer_keywords:
- ICorDebugThread2 interface [.NET Framework debugging]
ms.assetid: 678f89f9-cce7-46d1-af87-5e989abaa93c
topic_type:
- apiref
ms.openlocfilehash: 81f687f6daff9ffa7298ec6d818a214b8934bcc3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658508"
---
# <a name="icordebugthread2-interface"></a>Interfaz ICorDebugThread2

Actúa como una extensión lógica de la interfaz ICorDebugThread.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetActiveFunctions](icordebugthread2-getactivefunctions-method.md)|Obtiene una matriz de instancias de COR_ACTIVE_FUNCTION que contienen datos sobre las funciones activas de los marcos de un subproceso.|  
|[Método GetConnectionID](icordebugthread2-getconnectionid-method.md)|Obtiene un identificador de conexión para este `ICorDebugThread2` .|  
|[Método GetTaskID](icordebugthread2-gettaskid-method.md)|Obtiene un identificador de tarea para este `ICorDebugThread2` .|  
|[Método GetVolatileOSThreadID](icordebugthread2-getvolatileosthreadid-method.md)|Obtiene el identificador del subproceso del sistema operativo para este `ICorDebugThread2` .|  
|[Método InterceptCurrentException](icordebugthread2-interceptcurrentexception-method.md)|Permite a un depurador interceptar la excepción actual en un subproceso.|  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](debugging-interfaces.md)
