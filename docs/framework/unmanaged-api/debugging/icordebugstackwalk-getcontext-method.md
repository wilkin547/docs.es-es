---
title: ICorDebugStackWalk::GetContext (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bba1e6c113fb4caa0db8963e238d3eceba0cc8ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224863"
---
# <a name="icordebugstackwalkgetcontext-method"></a>ICorDebugStackWalk::GetContext (Método)
Devuelve el contexto para el fotograma actual en el [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
## <a name="parameters"></a>Parámetros  
 `contextFlags`  
 [in] Marcas que indican el contenido solicitado del búfer de contexto (se definen en WinNT.h).  
  
 `contextBufSize`  
 [in] El tamaño asignado del búfer de contexto.  
  
 `contextSize`  
 [out] El tamaño real del contexto. Este valor debe ser menor o igual que el tamaño del búfer de contexto.  
  
 `contextBuf`  
 [out] El búfer de contexto.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El contexto del marco actual se devolvió correctamente.|  
|E_FAIL|No se pudo devolver el contexto.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)|El búfer de contexto es demasiado pequeño.|  
|CORDBG_E_PAST_END_OF_STACK|El puntero de marco ya está al final de la pila; por lo tanto, no puede tener acceso a ningún marco adicional.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Comentarios  
 Porque desenredo restaura solo un subconjunto de los registros, como los registros no volátiles, el contexto puede no coincidir exactamente con el estado del registro en el momento de la llamada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
