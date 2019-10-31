---
title: ICorDebugChain (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain
helpviewer_keywords:
- ICorDebugChain interface [.NET Framework debugging]
ms.assetid: f671f519-1cb3-4ae5-b9f1-abc5e783459f
topic_type:
- apiref
ms.openlocfilehash: 8baf3567e4ae188f88ad3a2df157cffab3f597ac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125796"
---
# <a name="icordebugchain-interface"></a>ICorDebugChain (Interfaz)

Representa un segmento de una pila de llamadas física o lógica.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[EnumerateFrames (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|Obtiene un enumerador que contiene todos los marcos de pila administrados de la cadena, empezando por el fotograma más reciente.|  
|[GetActiveFrame (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|Obtiene el marco activo (es decir, el más reciente) de la cadena.|  
|[GetCallee (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|Obtiene la cadena a la que llamó esta cadena.|  
|[GetCaller (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|Obtiene la cadena que llamó a esta cadena.|  
|[GetContext (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|Sin implementar.|  
|[GetNext (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|Obtiene la cadena de fotogramas siguiente para el subproceso.|  
|[GetPrevious (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|Obtiene la cadena de fotogramas anterior para el subproceso.|  
|[GetReason (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|Obtiene el motivo del Genesis de esta cadena de llamada.|  
|[GetRegisterSet (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|Obtiene el conjunto de registros para la parte activa de esta cadena.|  
|[GetStackRange (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|Obtiene el intervalo de direcciones del segmento de pila para esta cadena.|  
|[GetThread (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|Obtiene el subproceso físico del que forma parte esta cadena de llamadas.|  
|[IsManaged (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|Obtiene un valor que indica si esta cadena ejecuta código administrado.|  
  
## <a name="remarks"></a>Comentarios  
 Los marcos de pila de una cadena ocupan el espacio de pila contiguo y comparten el mismo subproceso y contexto. Una cadena puede representar cadenas de código administradas o no administradas. Una instancia de `ICorDebugChain` vacía representa una cadena de código no administrada.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
