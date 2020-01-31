---
title: ICorDebugProcess5::EnumerateGCReferences (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateGCReferences
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type:
- apiref
ms.openlocfilehash: 81993f108ae9b59300b5d29402d7a423c3657757
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792444"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a>ICorDebugProcess5::EnumerateGCReferences (Método)
Obtiene un enumerador para todos los objetos que se van a recopilar de elementos no utilizados en un proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `enumerateWeakReferences`  
 de Valor booleano que indica si también se deben enumerar las referencias débiles. Si `enumerateWeakReferences` es `true`, el enumerador de `ppEnum` incluye referencias fuertes y referencias débiles. Si `enumerateWeakReferences` es `false`, el enumerador incluye solo referencias seguras.  
  
 `ppEnum`  
 enuncia Puntero a la dirección de un [icordebuggcreferenceenum (](icordebuggcreferenceenum-interface.md) que es un enumerador para los objetos que se van a recolectar como elemento no utilizado.  
  
## <a name="remarks"></a>Notas  
 Este método proporciona una manera de determinar la cadena de raíz completa de cualquier objeto administrado en un proceso y se puede usar para determinar por qué un objeto sigue estando activo.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugProcess5 (interfaz)](icordebugprocess5-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
