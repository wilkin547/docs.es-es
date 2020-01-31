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
ms.openlocfilehash: 23ad8882ad97e5ceaeb690dfae08a6be55b85f64
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791859"
---
# <a name="icordebugstackwalksetcontext-method"></a>ICorDebugStackWalk::SetContext (Método)
Establece el contexto actual del objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) en un contexto válido para el subproceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a>Parameters  
 `flag`  
 de Marca [CorDebugSetContextFlag (](cordebugsetcontextflag-enumeration.md) que indica si el contexto procede del marco activo de la pila o un contexto obtenido al desenredar la pila.  
  
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
|E_INVALIDARG|El contexto es una null.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|El búfer de contexto es demasiado pequeño.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Notas  
 Este método no modifica el contexto actual del subproceso.  
  
 Establecer el contexto actual en un contexto no válido puede producir resultados imprevisibles del rastreador de pila.  
  
 Puede recuperar una copia bit a bit exacta de este contexto llamando inmediatamente al método [ICorDebugStackWalk:: getContext](icordebugstackwalk-getcontext-method.md) .  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
- [Depuración](index.md)
