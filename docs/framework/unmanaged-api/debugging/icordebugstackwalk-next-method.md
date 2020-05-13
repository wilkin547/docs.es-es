---
title: ICorDebugStackWalk::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::Next
helpviewer_keywords:
- ICorDebugStackWalk::Next method [.NET Framework debugging]
- Next method, ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 189c36be-028c-4fba-a002-5edfb8fcd07f
topic_type:
- apiref
ms.openlocfilehash: b89e968e9b12943c8192af3b280f8bd321a02110
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378793"
---
# <a name="icordebugstackwalknext-method"></a>ICorDebugStackWalk::Next (Método)
Mueve el objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) al siguiente fotograma.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El tiempo de ejecución se desenrollará correctamente en el siguiente fotograma (vea la sección comentarios).|  
|E_FAIL|El `ICorDebugStackWalk` objeto no pudo ser avanzado.|  
|CORDBG_S_AT_END_OF_STACK|Se alcanzó el final de la pila como resultado de este desenredado.|  
|CORDBG_E_PAST_END_OF_STACK|El puntero de marco ya está al final de la pila; por lo tanto, no se puede tener acceso a ningún fotograma adicional.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Observaciones  
 El `Next` método hace avanzar el `ICorDebugStackWalk` objeto hasta el marco que realiza la llamada solo si el tiempo de ejecución puede desenredar el fotograma actual. De lo contrario, el objeto avanza hasta el siguiente fotograma que el runtime puede desenredar.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugStackWalk (Interfaz)](icordebugstackwalk-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
