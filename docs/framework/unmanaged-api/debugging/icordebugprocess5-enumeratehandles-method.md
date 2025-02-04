---
description: 'Más información sobre: ICorDebugProcess5:: Enumeratehandles ((método)'
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
ms.openlocfilehash: 62ca1390ceec634e6651dc013345688fe5892bcd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649915"
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
 de Combinación bit a bit de valores de [corgcreferencetype (](corgcreferencetype-enumeration.md) que especifica el tipo de identificadores que se van a incluir en la colección.  
  
 `ppENum`  
 enuncia Puntero a la dirección de un [icordebuggcreferenceenum (](icordebuggcreferenceenum-interface.md) que es un enumerador para los objetos que se van a recolectar como elemento no utilizado.  
  
## <a name="remarks"></a>Observaciones  

 `EnumerateHandles` es una función auxiliar que admite la inspección de la tabla de identificadores. Es similar al método [ICorDebugProcess5:: enumerategcreferences (](icordebugprocess5-enumerategcreferences-method.md) , salvo que, en lugar de rellenar una colección [icordebuggcreferenceenum (](icordebuggcreferenceenum-interface.md) con todos los objetos que se van a recopilar de elementos no utilizados, solo incluye los objetos que tienen identificadores de la tabla de identificadores.  
  
 El `types` parámetro especifica los tipos de identificadores que se van a incluir en la colección. `types` puede ser cualquiera de los siguientes tres miembros de la enumeración [corgcreferencetype (](corgcreferencetype-enumeration.md) :  
  
- `CorHandleStrongOnly` (solo controla las referencias fuertes).  
  
- `CorHandleWeakOnly` (solo controla las referencias débiles).  
  
- `CorHandleAll` (todos los identificadores).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)
