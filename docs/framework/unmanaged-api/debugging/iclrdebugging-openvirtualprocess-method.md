---
title: ICLRDebugging::OpenVirtualProcess (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a313ea62455067fb36b94d942b0ce21589677e3b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698166"
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
  
## <a name="parameters"></a>Parámetros  
 `moduleBaseAddress`  
 [in] La dirección base de un módulo en el proceso de destino. COR_E_NOT_CLR se devolverá si el módulo especificado no es un módulo CLR.  
  
 `pDataTarget`  
 [in] Una abstracción de destino de datos que permite al depurador administrado inspeccionar el estado del proceso. El depurador debe implementar la [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaz. Debe implementar la [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interfaz para admitir escenarios donde el CLR que se está depurando no está instalado localmente en el equipo.  
  
 `pLibraryProvider`  
 [in] Una interfaz de devolución de llamada de proveedor de biblioteca que permite a las bibliotecas de depuración de versión específicas a buscar y cargar a petición. Este parámetro solo es necesario si `ppProcess` o `pFlags` no `null`.  
  
 `pMaxDebuggerSupportedVersion`  
 [in] La versión más alta de CLR que puede depurar este depurador. Debe especificar a principal, secundario y generar versiones de la última versión CLR que este depurador admite y establecer el número de revisión y 65535 para dar cabida a futuras CLR in situ las solicitudes de servicio.  
  
 `riidProcess`  
 [in] El identificador de la interfaz ICorDebugProcess debe recuperar. Actualmente, los únicos valores aceptados son IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2 y IID_CORDEBUGPROCESS.  
  
 `ppProcess`  
 [out] Un puntero a la interfaz COM que se identifica mediante `riidProcess`.  
  
 `pVersion`  
 [in, out] La versión de CLR. En la entrada, este valor puede ser `null`. También puede señalar a un [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) estructura, en cuyo caso la estructura `wStructVersion` campo debe inicializarse en 0 (cero).  
  
 En la salida, el valor devuelto `CLR_DEBUGGING_VERSION` estructura se rellenará con la información de versión de CLR.  
  
 `pdwFlags`  
 [out] Marcas informativas sobre el tiempo de ejecución especificado. Consulte la [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) tema para obtener una descripción de las marcas.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_POINTER|El valor de `pDataTarget` es `null`.|  
|CORDBG_E_LIBRARY_PROVIDER_ERROR|El [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) devolución de llamada devuelve un error o no proporciona un identificador válido.|  
|CORDBG_E_MISSING_DATA_TARGET_INTERFACE|`pDataTarget` no implementa las interfaces de destino de datos necesarios para esta versión del tiempo de ejecución.|  
|CORDBG_E_NOT_CLR|El módulo indicado no es un módulo CLR. Este resultado HRESULT también se devuelve cuando un módulo CLR no se puede detectar porque se ha dañado la memoria, el módulo no está disponible o la versión de CLR es posterior a la versión de correcciones de compatibilidad.|  
|CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL|Esta versión en tiempo de ejecución no es compatible con este modelo de depuración. Actualmente, el modelo de depuración no es compatible con versiones de CLR antes de la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. El `pwszVersion` parámetro de salida sigue establecido en el valor correcto después de este error.|  
|CORDBG_E_UNSUPPORTED_FORWARD_COMPAT|La versión de CLR es mayor que la versión de notificaciones para admitir este depurador. El `pwszVersion` parámetro de salida sigue establecido en el valor correcto después de este error.|  
|E_NO_INTERFACE|El `riidProcess` interfaz no está disponible.|  
|CORDBG_E_UNSUPPORTED_VERSION_STRUCT|El `CLR_DEBUGGING_VERSION` estructura no tiene un valor reconocido para `wStructVersion`. El único valor aceptado en este momento es 0.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
