---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4d21c221bba3ac668924003f96580bb660229ad7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963001"
---
# <a name="icordebugthread2-interface"></a>Interfaz ICorDebugThread2
Actúa como una extensión lógica de la interfaz ICorDebugThread.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIPCIÓN|  
|------------|-----------------|  
|[GetActiveFunctions (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|Obtiene una matriz de instancias de COR_ACTIVE_FUNCTION que contienen datos sobre las funciones activas de los marcos de un subproceso.|  
|[GetConnectionID (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|Obtiene un identificador de conexión para este `ICorDebugThread2`.|  
|[GetTaskID (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|Obtiene un identificador de tarea para este `ICorDebugThread2`.|  
|[GetVolatileOSThreadID (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|Obtiene el identificador del subproceso del sistema operativo `ICorDebugThread2`para este.|  
|[InterceptCurrentException (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|Permite a un depurador interceptar la excepción actual en un subproceso.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cordebug. idl, Cordebug. h  
  
 **Biblioteca** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
