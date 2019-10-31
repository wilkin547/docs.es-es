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
ms.openlocfilehash: 3ab4da3fcf43731587dae6f3a8e82ea48c5ee1ec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129645"
---
# <a name="icordebugprocess5enumerateheapregions-method"></a>ICorDebugProcess5::EnumerateHeapRegions (Método)
Obtiene un enumerador para los intervalos de memoria del montón administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppRegions`  
 enuncia Puntero a la dirección de un objeto de interfaz [icordebugheapsegmentenum (](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) que es un enumerador para los intervalos de memoria en los que residen los objetos en el montón administrado.  
  
## <a name="remarks"></a>Comentarios  
 Antes de llamar al método `ICorDebugProcess5::EnumerateHeapRegions`, debe llamar al método [ICorDebugProcess5:: getgcheapinformation (](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) y examinar el valor del campo `areGCStructuresValid` del objeto [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) devuelto para asegurarse de que el montón de recolección de elementos no utilizados en su el estado actual es Enumerable. Además, el método `ICorDebugProcess5::EnumerateHeapRegions` devuelve `E_FAIL` si se adjunta demasiado pronto en la duración del proceso, antes de que se creen regiones de memoria.  
  
 Se garantiza que este método enumera todas las regiones de memoria que pueden contener objetos administrados, pero no garantiza que los objetos administrados residen realmente en esas regiones. El objeto de colección [icordebugheapsegmentenum (](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) puede incluir regiones de memoria vacías o reservadas.  
  
 El objeto de interfaz [icordebugheapsegmentenum (](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) es un enumerador estándar derivado de la interfaz ICorDebugEnum que le permite enumerar objetos [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) . Cada objeto [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) proporciona información sobre el intervalo de memoria de un segmento determinado, junto con la generación de los objetos en ese segmento.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugProcess5 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
