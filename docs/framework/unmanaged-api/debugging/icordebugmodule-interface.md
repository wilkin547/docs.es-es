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
ms.openlocfilehash: c573e6b768aee1e8b681dcf2e828dc24d409025b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793011"
---
# <a name="icordebugmodule-interface"></a>Interfaz ICorDebugModule

Representa un módulo de Common Language Runtime (CLR), que es un archivo ejecutable o una biblioteca de vínculos dinámicos (DLL).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateBreakpoint (método)](icordebugmodule-createbreakpoint-method.md)|Sin implementar.|  
|[EnableClassLoadCallbacks (método)](icordebugmodule-enableclassloadcallbacks-method.md)|Determina si se llama a las devoluciones de llamada [ICorDebugManagedCallback:: loadClass](icordebugmanagedcallback-loadclass-method.md) y [ICorDebugManagedCallback:: UnloadClass (](icordebugmanagedcallback-unloadclass-method.md) para este módulo.|  
|[EnableJITDebugging (método)](icordebugmodule-enablejitdebugging-method.md)|Determina si el compilador Just-in-Time (JIT) conserva la información de depuración de los métodos de este módulo.|  
|[GetAssembly (método)](icordebugmodule-getassembly-method.md)|Obtiene el ensamblado contenedor de este módulo.|  
|[GetBaseAddress (método)](icordebugmodule-getbaseaddress-method.md)|Obtiene la dirección base del módulo.|  
|[GetClassFromToken (método)](icordebugmodule-getclassfromtoken-method.md)|Obtiene el ICorDebugClass de los metadatos.|  
|[GetEditAndContinueSnapshot (método)](icordebugmodule-geteditandcontinuesnapshot-method.md)|Opción obsoleta.|  
|[GetFunctionFromRVA (método)](icordebugmodule-getfunctionfromrva-method.md)|Sin implementar.|  
|[GetFunctionFromToken (método)](icordebugmodule-getfunctionfromtoken-method.md)|Obtiene la función especificada por el token de metadatos.|  
|[GetGlobalVariableValue (método)](icordebugmodule-getglobalvariablevalue-method.md)|Obtiene un objeto de valor para la variable global especificada.|  
|[GetMetaDataInterface (método)](icordebugmodule-getmetadatainterface-method.md)|Obtiene un puntero de interfaz de metadatos que se puede utilizar para examinar los metadatos del módulo.|  
|[GetName (método)](icordebugmodule-getname-method.md)|Obtiene el nombre de archivo del módulo.|  
|[GetProcess (método)](icordebugmodule-getprocess-method.md)|Obtiene el proceso contenedor de este módulo.|  
|[GetSize (método)](icordebugmodule-getsize-method.md)|Obtiene el tamaño del módulo en bytes.|  
|[GetToken (método)](icordebugmodule-gettoken-method.md)|Obtiene el token para la entrada de la tabla para este módulo.|  
|[IsDynamic (método)](icordebugmodule-isdynamic-method.md)|Indica si el módulo es dinámico.|  
|[IsInMemory (método)](icordebugmodule-isinmemory-method.md)|Indica si este módulo solo existe en la memoria.|  
  
## <a name="remarks"></a>Notas  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebug (interfaz)](icordebug-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
