---
description: 'Más información sobre: ICorDebugStackWalk:: GetFrame (método)'
title: ICorDebugStackWalk::GetFrame (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetFrame
helpviewer_keywords:
- GetFrame method [.NET Framework debugging]
- ICorDebugStackWalk::GetFrame method [.NET Framework debugging]
ms.assetid: 4083b505-5b59-44fb-8c5d-129db6a96c10
topic_type:
- apiref
ms.openlocfilehash: b00ddb6a475aff4263a922f5a20b866cd0e1b2ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794746"
---
# <a name="icordebugstackwalkgetframe-method"></a>ICorDebugStackWalk::GetFrame (Método)

Obtiene el marco actual del objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pFrame`  
 de Puntero a la dirección del objeto de marco creado que representa el marco actual en la pila.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El tiempo de ejecución devolvió correctamente el marco actual.|  
|E_FAIL|No se devolvió el marco actual.|  
|S_FALSE|El marco actual es un marco de pila nativo.|  
|E_INVALIDARG|`pFrame` es null.|  
|CORDBG_E_PAST_END_OF_STACK|El puntero de marco ya está al final de la pila; por lo tanto, no se puede tener acceso a ningún fotograma adicional.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Notas  

 `ICorDebugStackWalk` Devuelve solo los marcos de pila reales. Use el método [ICorDebugThread3:: GetActiveInternalFrames (](icordebugthread3-getactiveinternalframes-method.md) para devolver Marcos internos. (Los marcos internos son estructuras de datos insertadas en la pila por el motor en tiempo de ejecución para almacenar datos temporales).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugStackWalk (Interfaz)](icordebugstackwalk-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
