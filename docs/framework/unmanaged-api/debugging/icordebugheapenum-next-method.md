---
title: ICorDebugHeapEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum::Next
helpviewer_keywords:
- ICorDebugHeapEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 2221fd06-9e27-4113-972e-2530db8c3594
topic_type:
- apiref
ms.openlocfilehash: 1beb69bfaad9acb9c269ad8becb81bea64edb6a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138467"
---
# <a name="icordebugheapenumnext-method"></a>ICorDebugHeapEnum::Next (Método)
Obtiene el número especificado de instancias de [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) que contienen información sobre los objetos del montón administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 celt  
 [in] Número de objetos que se van a recuperar.  
  
 objetos  
 enuncia Una matriz de punteros, cada uno de los cuales apunta a un objeto [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) que proporciona información sobre un objeto en el montón administrado.  
  
 pceltFetched  
 enuncia Puntero al número de objetos [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) realmente devueltos en `objects`. Este valor puede ser `null` si `celt` es 1.  
  
## <a name="remarks"></a>Comentarios  
 El campo `COR_HEAPOBJECT.type` es el identificador de una interfaz COM contada como referencia anidada. Esta referencia debe liberarla el llamador de `ICorDebugHeapEnum::Next`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugHeapEnum (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
