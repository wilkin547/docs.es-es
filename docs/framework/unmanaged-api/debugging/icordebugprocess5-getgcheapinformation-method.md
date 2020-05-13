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
ms.openlocfilehash: 62d45da44a95eae399fbbd287aa997a5f913d0b0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209661"
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
 enuncia Puntero a un valor de [COR_HEAPINFO](cor-heapinfo-structure.md) que proporciona información general sobre el montón de recolección de elementos no utilizados.  
  
## <a name="remarks"></a>Observaciones  
 Se `ICorDebugProcess5::GetGCHeapInformation` debe llamar al método antes de enumerar las regiones del montón o del montón individual para asegurarse de que las estructuras de recolección de elementos no utilizados del proceso son válidas actualmente. No se puede recorrer el montón de recolección de elementos no utilizados mientras una colección está en curso. De lo contrario, la enumeración puede capturar estructuras de recolección de elementos no utilizados que no son válidas.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugProcess5 (Interfaz)](icordebugprocess5-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
