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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 972c650e0fb3b42e943838b72faf2658f65543ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugdatatarget-interface"></a>ICorDebugDataTarget (Interfaz)
Proporciona una interfaz de devolución de llamada que brinda acceso a un proceso de destino determinado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetPlatform (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|Proporciona información acerca de la plataforma, incluida la arquitectura de procesador y el sistema operativo en el que se ejecuta el proceso de destino.|  
|[ReadVirtual (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|Obtiene un bloque de memoria contigua empezando en la dirección especificada y lo devuelve en el búfer proporcionado.|  
|[GetThreadContext (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|Solicita el contexto del subproceso actual para el subproceso especificado.|  
  
## <a name="remarks"></a>Comentarios  
 `ICorDebugDataTarget` y sus métodos tienen las siguientes características:  
  
-   Los servicios de depuración, llamar a métodos en esta interfaz para tener acceso a la memoria y otros datos en el proceso de destino.  
  
-   El cliente del depurador debe implementar esta interfaz según corresponda para el destino determinado (por ejemplo, un proceso activo o un volcado de memoria).  
  
-   El `ICorDebugDataTarget` métodos pueden invocarse únicamente desde dentro de los métodos implementados en otra `ICorDebug*` interfaces. Esto garantiza que el cliente del depurador tiene control sobre qué subproceso se invoca y cuándo.  
  
-   El `ICorDebugDataTarget` implementación siempre debe devolver información actualizada sobre el destino.  
  
 Debe detener el proceso de destino y no cambia de forma alguna al `ICorDebug*` interfaces (y, por tanto, `ICorDebugDataTarget` métodos) se llama. Si el destino es un proceso activo y cambios en su estado, el [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) método debe llamarse para proporcionar una instancia de ICorDebugProcess de reemplazo.  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
