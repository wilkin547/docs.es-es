---
title: Interfaz ICorDebugModule
ms.date: 03/30/2017
api_name:
- ICorDebugModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule
helpviewer_keywords:
- ICorDebugModule interface [.NET Framework debugging]
ms.assetid: 32e4d6fa-e5a3-413e-9166-d5e2871d3114
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 257011562a9ea687ef70b842c6d47219283e158e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225643"
---
# <a name="icordebugmodule-interface"></a>Interfaz ICorDebugModule

Representa un módulo de common language runtime (CLR), que es un archivo ejecutable o una biblioteca de vínculos dinámicos (DLL).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método CreateBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|Sin implementar.|  
|[Método EnableClassLoadCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|Determina si el [loadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) y [UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) devoluciones de llamada se llaman para este módulo.|  
|[Método EnableJITDebugging](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|Determina si el compilador de just-in-time (JIT) conserva la información de depuración para los métodos de este módulo.|  
|[Método GetAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|Obtiene el ensamblado que contiene este módulo.|  
|[Método GetBaseAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|Obtiene la dirección base del módulo.|  
|[Método GetClassFromToken](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|Obtiene el ICorDebugClass desde los metadatos.|  
|[Método GetEditAndContinueSnapshot](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|Desusado.|  
|[Método GetFunctionFromRVA](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|Sin implementar.|  
|[Método GetFunctionFromToken](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|Obtiene la función especificada por el token de metadatos.|  
|[Método GetGlobalVariableValue](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|Obtiene un objeto de valor para la variable global especificada.|  
|[Método GetMetaDataInterface](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|Obtiene un puntero de interfaz de metadatos que puede usarse para examinar los metadatos para el módulo.|  
|[Método GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|Obtiene el nombre de archivo del módulo.|  
|[Método GetProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|Obtiene el proceso que contiene este módulo.|  
|[Método GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|Obtiene el tamaño del módulo en bytes.|  
|[Método GetToken](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|Obtiene el token para la entrada de tabla para este módulo.|  
|[Método IsDynamic](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|Indica si el módulo es dinámico.|  
|[Método IsInMemory](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|Indica si este módulo solo existe en memoria.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebug (Interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [Interfaces para depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
