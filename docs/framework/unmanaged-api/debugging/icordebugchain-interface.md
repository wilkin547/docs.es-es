---
title: Interfaz ICorDebugChain
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01dded47fca26df11781153eb45693057a25ad01
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220713"
---
# <a name="icordebugchain-interface"></a>Interfaz ICorDebugChain

Representa un segmento de una pila de llamadas física o lógica.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[EnumerateFrames (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|Obtiene un enumerador que contiene todos los marcos de pila administrados de la cadena, empezando por el marco más reciente.|  
|[GetActiveFrame (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|Obtiene el activo (es decir, más reciente) marco en la cadena.|  
|[GetCallee (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|Obtiene la cadena que se llamó por esta cadena.|  
|[GetCaller (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|Obtiene la cadena que llamó esta cadena.|  
|[GetContext (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|Sin implementar.|  
|[GetNext (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|Obtiene la siguiente cadena de marcos del subproceso.|  
|[GetPrevious (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|Obtiene la cadena anterior de marcos del subproceso.|  
|[GetReason (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|Obtiene la razón para la génesis de esta cadena de llamada.|  
|[GetRegisterSet (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|Obtiene el conjunto de registros para la parte activa de esta cadena.|  
|[GetStackRange (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|Obtiene el intervalo de direcciones del segmento de pila para esta cadena.|  
|[GetThread (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|Obtiene el subproceso físico que esta cadena de llamada es parte de.|  
|[IsManaged (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|Obtiene un valor que indica si esta cadena ejecuta código administrado.|  
  
## <a name="remarks"></a>Comentarios  
 Los marcos de pila en una cadena ocupan espacio de pila contiguo y comparten el mismo subproceso y contexto. Una cadena puede representar cualquier cadenas de código administrado o no administrado. Un valor vacío `ICorDebugChain` instancia representa una cadena de código no administrado.  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
