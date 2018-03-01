---
title: "ICLRDebugging::OpenVirtualProcess (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRDebugging.OpenVirtualProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::OpenVirtualProcess
helpviewer_keywords:
- OpenVirtualProcess method [.NET Framework debugging]
- ICLRDebugging::OpenVirtualProcess method [.NET Framework debugging]
ms.assetid: e8ab7c41-d508-4ed9-8a31-ead072b5a314
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f1f71f42f10c3d25714998d1697b20a5ee13e055
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a>ICLRDebugging::OpenVirtualProcess (Método)
Obtiene el ICorDebugProcess (interfaz) que corresponde a un módulo de runtime (CLR) de lenguaje común cargado en el proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT OpenVirtualProcess(  
    [in] ULONG64 moduleBaseAddress,  
    [in] IUnknown * pDataTarget,  
    [in] ICLRDebuggingLibraryProvider * pLibraryProvider,  
    [in] CLR_DEBUGGING_VERSION * pMaxDebuggerSupportedVersion,  
    [in] REFIID riidProcess,  
    [out, iid_is(riidProcess)] IUnknown ** ppProcess,  
    [in, out] CLR_DEBUGGING_VERSION * pVersion,  
    [out] CLR_DEBUGGING_PROCESS_FLAGS * pdwFlags);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `moduleBaseAddress`  
 [in] La dirección base de un módulo en el proceso de destino. Se devolverá COR_E_NOT_CLR si el módulo especificado no es un módulo CLR.  
  
 `pDataTarget`  
 [in] Una abstracción de destino de datos que permite al depurador administrado inspeccionar el estado del proceso. El depurador debe implementar la [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaz. Debe implementar la [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interfaz para admitir escenarios donde el CLR que se está depurando no está instalado localmente en el equipo.  
  
 `pLibraryProvider`  
 [in] Una interfaz de devolución de llamada de proveedor de biblioteca que permite bibliotecas de depuración específicas de la versión buscar y cargar a petición. Este parámetro es necesario únicamente si `ppProcess` o `pFlags` no es `null`.  
  
 `pMaxDebuggerSupportedVersion`  
 [in] La versión más alta del CLR que este depurador puede depurar. Debe especificar al principal, secundario y compilar versiones de la última versión CLR que este depurador admite y establecer el número de revisión y 65535 para dar cabida a futuras CLR in situ versiones de servicio.  
  
 `riidProcess`  
 [in] Identificador de ICorDebugProcess (interfaz) que se va a recuperar. Actualmente, los únicos valores aceptados son IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2 y IID_CORDEBUGPROCESS.  
  
 `ppProcess`  
 [out] Un puntero a la interfaz COM que se identifica mediante `riidProcess`.  
  
 `pVersion`  
 [entrada, salida] La versión de CLR. En la entrada, este valor puede ser `null`. También puede señalar a un [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) estructura, en cuyo caso la estructura `wStructVersion` campo debe inicializarse en 0 (cero).  
  
 En la salida, el valor devuelto `CLR_DEBUGGING_VERSION` estructura se rellenará con la información de versión de CLR.  
  
 `pdwFlags`  
 [out] Marcas de información sobre el tiempo de ejecución especificado. Consulte la [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) tema para obtener una descripción de las marcas.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_POINTER|El valor de `pDataTarget` es `null`.|  
|CORDBG_E_LIBRARY_PROVIDER_ERROR|El [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) devolución de llamada devuelve un error o no proporciona un identificador válido.|  
|CORDBG_E_MISSING_DATA_TARGET_INTERFACE|`pDataTarget`no implementa las interfaces de destino de datos necesarios para esta versión del runtime.|  
|CORDBG_E_NOT_CLR|El módulo indicado no es un módulo CLR. Este valor de HRESULT también se devuelve cuando un módulo CLR no se puede detectar porque se ha dañado la memoria, el módulo no está disponible o la versión CLR es posterior a la versión de la corrección de compatibilidad.|  
|CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL|Esta versión del runtime no admite este modelo de depuración. Actualmente, el modelo de depuración no es compatible con versiones CLR antes de la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. El `pwszVersion` parámetro de salida sigue establecido el valor correcto después de este error.|  
|CORDBG_E_UNSUPPORTED_FORWARD_COMPAT|La versión de CLR es mayor que la versión de notificaciones para admitir este depurador. El `pwszVersion` parámetro de salida sigue establecido el valor correcto después de este error.|  
|E_NO_INTERFACE|El `riidProcess` interfaz no está disponible.|  
|CORDBG_E_UNSUPPORTED_VERSION_STRUCT|El `CLR_DEBUGGING_VERSION` estructura no tiene un valor reconocido para `wStructVersion`. El único valor aceptado en este momento es 0.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
