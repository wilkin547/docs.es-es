---
title: ICorDebugProcess5::GetGCHeapInformation (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetGCHeapInformation
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetGCHeapInformation
helpviewer_keywords:
- ICorDebugProcess5::GetGCHeapInformation method [.NET Framework debugging]
- GetGCHeapInformation method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: b9538ceb-230a-4079-9cb2-903dbf5c1848
topic_type:
- apiref
ms.openlocfilehash: 3aa9fe884b16a239f5105dd262edeb8fc3e4abaa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084408"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a>ICorDebugProcess5::GetGCHeapInformation (Método)
Proporciona información general sobre el montón de recolección de elementos no utilizados, incluido si es Enumerable en este momento.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pHeapInfo`  
 enuncia Un puntero a un valor de [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) que proporciona información general sobre el montón de recolección de elementos no utilizados.  
  
## <a name="remarks"></a>Comentarios  
 Se debe llamar al método `ICorDebugProcess5::GetGCHeapInformation` antes de enumerar las regiones del montón o del montón individual para asegurarse de que las estructuras de recolección de elementos no utilizados del proceso son válidas actualmente. No se puede recorrer el montón de recolección de elementos no utilizados mientras una colección está en curso. De lo contrario, la enumeración puede capturar estructuras de recolección de elementos no utilizados que no son válidas.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugProcess5 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
