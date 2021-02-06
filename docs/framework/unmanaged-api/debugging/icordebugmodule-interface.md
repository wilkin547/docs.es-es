---
description: 'Más información acerca de: ICorDebugModule (interfaz)'
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
ms.openlocfilehash: f78023fe9975b609309c1c511380a3a394426283
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660120"
---
# <a name="icordebugmodule-interface"></a>Interfaz ICorDebugModule

Representa un módulo de Common Language Runtime (CLR), que es un archivo ejecutable o una biblioteca de vínculos dinámicos (DLL).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método CreateBreakpoint](icordebugmodule-createbreakpoint-method.md)|Sin implementar.|  
|[Método EnableClassLoadCallbacks](icordebugmodule-enableclassloadcallbacks-method.md)|Determina si se llama a las devoluciones de llamada [ICorDebugManagedCallback:: loadClass](icordebugmanagedcallback-loadclass-method.md) y [ICorDebugManagedCallback:: UnloadClass (](icordebugmanagedcallback-unloadclass-method.md) para este módulo.|  
|[Método EnableJITDebugging](icordebugmodule-enablejitdebugging-method.md)|Determina si el compilador Just-in-Time (JIT) conserva la información de depuración de los métodos de este módulo.|  
|[Método GetAssembly](icordebugmodule-getassembly-method.md)|Obtiene el ensamblado contenedor de este módulo.|  
|[GetBaseAddress (Método)](icordebugmodule-getbaseaddress-method.md)|Obtiene la dirección base del módulo.|  
|[Método GetClassFromToken](icordebugmodule-getclassfromtoken-method.md)|Obtiene el ICorDebugClass de los metadatos.|  
|[Método GetEditAndContinueSnapshot](icordebugmodule-geteditandcontinuesnapshot-method.md)|En desuso.|  
|[Método GetFunctionFromRVA](icordebugmodule-getfunctionfromrva-method.md)|Sin implementar.|  
|[Método GetFunctionFromToken](icordebugmodule-getfunctionfromtoken-method.md)|Obtiene la función especificada por el token de metadatos.|  
|[Método GetGlobalVariableValue](icordebugmodule-getglobalvariablevalue-method.md)|Obtiene un objeto de valor para la variable global especificada.|  
|[Método GetMetaDataInterface](icordebugmodule-getmetadatainterface-method.md)|Obtiene un puntero de interfaz de metadatos que se puede utilizar para examinar los metadatos del módulo.|  
|[Método GetName](icordebugmodule-getname-method.md)|Obtiene el nombre de archivo del módulo.|  
|[Método GetProcess](icordebugmodule-getprocess-method.md)|Obtiene el proceso contenedor de este módulo.|  
|[Método GetSize](icordebugmodule-getsize-method.md)|Obtiene el tamaño del módulo en bytes.|  
|[GetToken (Método)](icordebugmodule-gettoken-method.md)|Obtiene el token para la entrada de la tabla para este módulo.|  
|[Método IsDynamic](icordebugmodule-isdynamic-method.md)|Indica si el módulo es dinámico.|  
|[Método IsInMemory](icordebugmodule-isinmemory-method.md)|Indica si este módulo solo existe en la memoria.|  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebug (Interfaz)](icordebug-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
