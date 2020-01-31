---
title: ICorDebugProcess5::EnumerateHeapRegions (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeapRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeapRegions
helpviewer_keywords:
- EnumerateHeapRegions method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeapRegions method [.NET Framework debugging]
ms.assetid: b1edba68-9c36-4f69-be9f-678ce0b33480
topic_type:
- apiref
ms.openlocfilehash: 8070b0693b5718ad8b4cbeb9bf5792cb7f4a0a85
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792405"
---
# <a name="icordebugprocess5enumerateheapregions-method"></a>ICorDebugProcess5::EnumerateHeapRegions (Método)
Obtiene un enumerador para los intervalos de memoria del montón administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `ppRegions`  
 enuncia Puntero a la dirección de un objeto de interfaz [icordebugheapsegmentenum (](icordebugheapsegmentenum-interface.md) que es un enumerador para los intervalos de memoria en los que residen los objetos en el montón administrado.  
  
## <a name="remarks"></a>Notas  
 Antes de llamar al método `ICorDebugProcess5::EnumerateHeapRegions`, debe llamar al método [ICorDebugProcess5:: getgcheapinformation (](icordebugprocess5-getgcheapinformation-method.md) y examinar el valor del campo `areGCStructuresValid` del objeto [COR_HEAPINFO](cor-heapinfo-structure.md) devuelto para asegurarse de que el montón de recolección de elementos no utilizados en su estado actual es Enumerable. Además, el método `ICorDebugProcess5::EnumerateHeapRegions` devuelve `E_FAIL` si se adjunta demasiado pronto en la duración del proceso, antes de que se creen regiones de memoria.  
  
 Se garantiza que este método enumera todas las regiones de memoria que pueden contener objetos administrados, pero no garantiza que los objetos administrados residen realmente en esas regiones. El objeto de colección [icordebugheapsegmentenum (](icordebugheapsegmentenum-interface.md) puede incluir regiones de memoria vacías o reservadas.  
  
 El objeto de interfaz [icordebugheapsegmentenum (](icordebugheapsegmentenum-interface.md) es un enumerador estándar derivado de la interfaz ICorDebugEnum que le permite enumerar objetos [COR_SEGMENT](cor-segment-structure.md) . Cada objeto de [COR_SEGMENT](cor-segment-structure.md) proporciona información sobre el intervalo de memoria de un segmento determinado, junto con la generación de los objetos en ese segmento.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugProcess5 (interfaz)](icordebugprocess5-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
