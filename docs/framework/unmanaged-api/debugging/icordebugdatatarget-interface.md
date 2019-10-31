---
title: ICorDebugDataTarget (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget
helpviewer_keywords:
- ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: df5f05be-bed7-4f3c-bc89-dbb435d79a0b
topic_type:
- apiref
ms.openlocfilehash: f8b216d370f7278f6d2a4beed5bab88afa666200
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122213"
---
# <a name="icordebugdatatarget-interface"></a>ICorDebugDataTarget (Interfaz)
Proporciona una interfaz de devolución de llamada que brinda acceso a un proceso de destino determinado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetPlatform (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|Proporciona información sobre la plataforma, incluida la arquitectura del procesador y el sistema operativo, en la que se ejecuta el proceso de destino.|  
|[ReadVirtual (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|Obtiene un bloque de memoria contigua que comienza en la dirección especificada y lo devuelve en el búfer proporcionado.|  
|[GetThreadContext (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|Solicita el contexto del subproceso actual para el subproceso especificado.|  
  
## <a name="remarks"></a>Comentarios  
 `ICorDebugDataTarget` y sus métodos tienen las siguientes características:  
  
- Los servicios de depuración llaman a métodos en esta interfaz para tener acceso a la memoria y a otros datos en el proceso de destino.  
  
- El cliente del depurador debe implementar esta interfaz según corresponda para el destino determinado (por ejemplo, un proceso activo o un volcado de memoria).  
  
- Los métodos de `ICorDebugDataTarget` solo se pueden invocar desde los métodos implementados en otras interfaces de `ICorDebug*`. Esto garantiza que el cliente del depurador tenga control sobre el subproceso en el que se invoca y cuándo.  
  
- La implementación de `ICorDebugDataTarget` siempre debe devolver información actualizada sobre el destino.  
  
 El proceso de destino debe detenerse y no cambiarse de ninguna manera mientras se llama a `ICorDebug*` interfaces (y, por lo tanto, `ICorDebugDataTarget` métodos). Si el destino es un proceso activo y su estado cambia, se debe llamar de nuevo al método [ICLRDebugging:: openvirtualprocess (](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) para proporcionar una instancia de ICorDebugProcess de reemplazo.  
  
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
