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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b3cc158c48e8bb9f833429bbddaa74ed459f1b6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108839"
---
# <a name="icordebugprocess5enumeratehandles-method"></a>ICorDebugProcess5::EnumerateHandles (Método)
Obtiene un enumerador para los identificadores de objeto en un proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a>Parámetros  
 `types`  
 [in] Una combinación bit a bit de [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) valores que especifica el tipo de identificadores para incluir en la colección.  
  
 `ppENum`  
 [out] Un puntero a la dirección de un [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) que es un enumerador para los objetos de recopilar los elementos no utilizados.  
  
## <a name="remarks"></a>Comentarios  
 `EnumerateHandles` es una función auxiliar que admita la inspección de la tabla de identificadores. Es similar a la [Icordebugprocess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) método, salvo que en lugar de rellenar un [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) colección con todos los objetos para recopilar los elementos no utilizados, lo incluye solo los objetos que tienen identificadores de la tabla de identificadores.  
  
 El `types` parámetro especifica los tipos de identificador que desea incluir en la colección. `types` puede ser cualquiera de los siguientes tres miembros de la [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeración:  
  
-   `CorHandleStrongOnly` (controladores para las referencias fuertes solo).  
  
-   `CorHandleWeakOnly` (controladores para solo referencias débiles).  
  
-   `CorHandleAll` (todos los identificadores).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
