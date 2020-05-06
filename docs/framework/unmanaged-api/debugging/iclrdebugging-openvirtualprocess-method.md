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
ms.openlocfilehash: 1598130eb097655d3e83689956eb3614103eb573
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860369"
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a>ICLRDebugging::OpenVirtualProcess (Método)
Obtiene la interfaz ICorDebugProcess que corresponde a un módulo de Common Language Runtime (CLR) cargado en el proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
 de La dirección base de un módulo en el proceso de destino. Se devolverá COR_E_NOT_CLR si el módulo especificado no es un módulo CLR.  
  
 `pDataTarget`  
 de Una abstracción de destino de datos que permite al depurador administrado inspeccionar el estado del proceso. El depurador debe implementar la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md) . Debe implementar la interfaz [ICLRDebuggingLibraryProvider (](iclrdebugginglibraryprovider-interface.md) para admitir escenarios en los que el CLR que se está depurando no se instala localmente en el equipo.  
  
 `pLibraryProvider`  
 de Una interfaz de devolución de llamada del proveedor de bibliotecas que permite buscar y cargar a petición bibliotecas de depuración específicas de la versión. Este parámetro es necesario solo si `ppProcess` o `pFlags` no `null`lo es.  
  
 `pMaxDebuggerSupportedVersion`  
 de Versión más alta de CLR que este depurador puede depurar. Debe especificar las versiones principal, secundaria y de compilación de la versión de CLR más reciente que admite este depurador y establecer el número de revisión en 65535 para acomodar futuras versiones de servicio de CLR en contexto.  
  
 `riidProcess`  
 de IDENTIFICADOR de la interfaz ICorDebugProcess que se va a recuperar. Actualmente, los únicos valores aceptados son IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2 y IID_CORDEBUGPROCESS.  
  
 `ppProcess`  
 enuncia Puntero a la interfaz COM identificada por `riidProcess`.  
  
 `pVersion`  
 [in, out] Versión de CLR. En la entrada, este valor puede `null`ser. También puede apuntar a una estructura de [CLR_DEBUGGING_VERSION](clr-debugging-version-structure.md) , en cuyo caso el campo `wStructVersion` de la estructura se debe inicializar en 0 (cero).  
  
 En la salida, la `CLR_DEBUGGING_VERSION` estructura devuelta se rellenará con la información de versión de CLR.  
  
 `pdwFlags`  
 enuncia Marcas informativas sobre el tiempo de ejecución especificado. Vea el tema [CLR_DEBUGGING_PROCESS_FLAGS](clr-debugging-process-flags-enumeration.md) para obtener una descripción de las marcas.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_POINTER|`pDataTarget` es `null`.|  
|CORDBG_E_LIBRARY_PROVIDER_ERROR|La devolución de llamada [ICLRDebuggingLibraryProvider (](iclrdebugginglibraryprovider-interface.md) devuelve un error o no proporciona un identificador válido.|  
|CORDBG_E_MISSING_DATA_TARGET_INTERFACE|`pDataTarget`no implementa las interfaces de destino de datos necesarias para esta versión del Runtime.|  
|CORDBG_E_NOT_CLR|El módulo indicado no es un módulo CLR. Este valor HRESULT también se devuelve cuando no se puede detectar un módulo CLR porque la memoria está dañada, el módulo no está disponible o la versión de CLR es posterior a la versión de la corrección de compatibilidad.|  
|CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL|Esta versión en tiempo de ejecución no admite este modelo de depuración. Actualmente, las versiones de CLR no admiten el modelo de depuración antes de la .NET Framework 4. El `pwszVersion` parámetro de salida sigue establecido en el valor correcto después de este error.|  
|CORDBG_E_UNSUPPORTED_FORWARD_COMPAT|La versión de CLR es mayor que la versión que este depurador notifica para admitir. El `pwszVersion` parámetro de salida sigue establecido en el valor correcto después de este error.|  
|E_NO_INTERFACE|La `riidProcess` interfaz no está disponible.|  
|CORDBG_E_UNSUPPORTED_VERSION_STRUCT|La `CLR_DEBUGGING_VERSION` estructura no tiene un valor reconocido para `wStructVersion`. El único valor aceptado en este momento es 0.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Observaciones  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
