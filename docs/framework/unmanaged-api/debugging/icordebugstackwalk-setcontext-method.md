---
title: ICorDebugStackWalk::SetContext (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.SetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::SetContext
helpviewer_keywords:
- SetContext method [.NET Framework debugging]
- ICorDebugStackWalk::SetContext method [.NET Framework debugging]
ms.assetid: bac0b156-31a3-4e7f-be4d-ab21789c81f1
topic_type:
- apiref
ms.openlocfilehash: 90156152a2c133446dedbe22426785ab63f8dfb9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131809"
---
# <a name="icordebugstackwalksetcontext-method"></a>ICorDebugStackWalk::SetContext (Método)
Establece el contexto actual del objeto [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) en un contexto válido para el subproceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a>Parámetros  
 `flag`  
 de Marca [CorDebugSetContextFlag (](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) que indica si el contexto procede del marco activo de la pila o un contexto obtenido al desenredar la pila.  
  
 `contextSize`  
 de Tamaño asignado del búfer de `CONTEXT`.  
  
 `context`  
 de Búfer de `CONTEXT`.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El contexto del objeto `ICorDebugStackWalk` se estableció correctamente.|  
|E_FAIL|No se ha establecido el contexto del objeto `ICorDebugStackWalk`.|  
|E_INVALIDARG|El contexto es NULL.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|El búfer de contexto es demasiado pequeño.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Comentarios  
 Este método no modifica el contexto actual del subproceso.  
  
 Establecer el contexto actual en un contexto no válido puede producir resultados imprevisibles del rastreador de pila.  
  
 Puede recuperar una copia bit a bit exacta de este contexto llamando inmediatamente al método [ICorDebugStackWalk:: getContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
