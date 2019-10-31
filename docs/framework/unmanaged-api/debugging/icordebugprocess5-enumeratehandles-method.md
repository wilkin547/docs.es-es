---
title: ICorDebugProcess5::EnumerateHandles (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHandles
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type:
- apiref
ms.openlocfilehash: e0e68dba1f4d9ac5fa618aa842b823dcc046e70e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129674"
---
# <a name="icordebugprocess5enumeratehandles-method"></a>ICorDebugProcess5::EnumerateHandles (Método)
Obtiene un enumerador para los identificadores de objetos de un proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a>Parámetros  
 `types`  
 de Combinación bit a bit de valores de [corgcreferencetype (](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) que especifica el tipo de identificadores que se van a incluir en la colección.  
  
 `ppENum`  
 enuncia Puntero a la dirección de un [icordebuggcreferenceenum (](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) que es un enumerador para los objetos que se van a recolectar como elemento no utilizado.  
  
## <a name="remarks"></a>Comentarios  
 `EnumerateHandles` es una función auxiliar que admite la inspección de la tabla de identificadores. Es similar al método [ICorDebugProcess5:: enumerategcreferences (](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) , salvo que, en lugar de rellenar una colección [icordebuggcreferenceenum (](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) con todos los objetos que se van a recopilar de elementos no utilizados, solo incluye los objetos que tienen identificadores de tabla de identificadores.  
  
 El parámetro `types` especifica los tipos de identificadores que se van a incluir en la colección. `types` puede ser cualquiera de los siguientes tres miembros de la enumeración [corgcreferencetype (](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) :  
  
- `CorHandleStrongOnly` (solo controla las referencias fuertes).  
  
- `CorHandleWeakOnly` (solo identificadores de referencias débiles).  
  
- `CorHandleAll` (todos los identificadores).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
