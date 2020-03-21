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
ms.openlocfilehash: f5af8e559b4fbfeb60530372185ca10104ade987
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178852"
---
# <a name="icordebugheapenumnext-method"></a>ICorDebugHeapEnum::Next (Método)
Obtiene el número especificado de [instancias de COR_HEAPOBJECT](cor-heapobject-structure.md) que contienen información sobre los objetos del montón administrado.  
  
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
 [fuera] Matriz de punteros, cada uno de los cuales apunta a un [objeto COR_HEAPOBJECT](cor-heapobject-structure.md) que proporciona información sobre un objeto en el montón administrado.  
  
 pceltFetched  
 [fuera] Puntero al número de [objetos](cor-heapobject-structure.md) `objects`COR_HEAPOBJECT realmente devueltos en . Este valor puede ser `null` si `celt` es 1.  
  
## <a name="remarks"></a>Observaciones  
 El campo `COR_HEAPOBJECT.type` es el identificador de una interfaz COM contada como referencia anidada. Esta referencia debe liberarla el llamador de `ICorDebugHeapEnum::Next`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugHeapEnum (interfaz)](icordebugheapenum-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
