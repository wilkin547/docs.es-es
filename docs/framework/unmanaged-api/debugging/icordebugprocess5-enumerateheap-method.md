---
title: ICorDebugProcess5::EnumerateHeap (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeap
helpviewer_keywords:
- EnumerateHeap method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeap method [.NET Framework debugging]
ms.assetid: b0192104-6073-4089-a4df-dc29ee033074
topic_type:
- apiref
ms.openlocfilehash: 9386c77cc98df17d797d5886e1603ffc4824b6dc
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205236"
---
# <a name="icordebugprocess5enumerateheap-method"></a>ICorDebugProcess5::EnumerateHeap (Método)
Obtiene un enumerador para los objetos en el montón administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppObject`  
 enuncia Puntero a la dirección de un objeto de interfaz [icordebugheapenum (](icordebugheapenum-interface.md) que es un enumerador para los objetos que residen en el montón administrado.  
  
## <a name="remarks"></a>Observaciones  
 Antes de llamar al `ICorDebugProcess5::EnumerateHeap` método, debe llamar al método [ICorDebugProcess5:: getgcheapinformation (](icordebugprocess5-getgcheapinformation-method.md) y examinar el valor del `areGCStructuresValid` campo del objeto devuelto [COR_HEAPINFO](cor-heapinfo-structure.md) para asegurarse de que el montón de recolección de elementos no utilizados en su estado actual es Enumerable. Además, `ICorDebugProcess5::EnumerateHeap` devuelve `E_FAIL` si se adjunta demasiado pronto en la duración del proceso, antes de que se asigne la memoria para el montón administrado.  
  
 El objeto de interfaz [icordebugheapenum (](icordebugheapenum-interface.md) es un enumerador estándar derivado de la interfaz ICorDebugEnum que le permite enumerar objetos [COR_HEAPOBJECT](cor-heapobject-structure.md) . Este método rellena el objeto de colección [icordebugheapenum (](icordebugheapenum-interface.md) con instancias [COR_HEAPOBJECT](cor-heapobject-structure.md) que proporcionan información acerca de todos los objetos. La colección también puede incluir instancias de [COR_HEAPOBJECT](cor-heapobject-structure.md) que proporcionan información sobre los objetos que no están raíz de ningún objeto pero que el recolector de elementos no utilizados aún no ha recopilado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugProcess5 (Interfaz)](icordebugprocess5-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
