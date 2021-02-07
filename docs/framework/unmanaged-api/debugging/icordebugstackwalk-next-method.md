---
description: 'Más información acerca de: ICorDebugStackWalk:: Next (método)'
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
ms.openlocfilehash: 27a48ca40f6b43cae32511b71b73e68d88eb60c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717763"
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
  
## <a name="remarks"></a>Notas  

 El `Next` método hace avanzar el `ICorDebugStackWalk` objeto hasta el marco que realiza la llamada solo si el tiempo de ejecución puede desenredar el fotograma actual. De lo contrario, el objeto avanza hasta el siguiente fotograma que el runtime puede desenredar.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugStackWalk (Interfaz)](icordebugstackwalk-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
