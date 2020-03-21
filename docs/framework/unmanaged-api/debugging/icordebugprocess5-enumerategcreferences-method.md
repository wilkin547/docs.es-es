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
ms.openlocfilehash: a97c14d83f99c847bb8569a33e175ab6eb5bccd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178621"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a>ICorDebugProcess5::EnumerateGCReferences (Método)
Obtiene un enumerador para todos los objetos que se van a recopilar como elementos no utilizados en un proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `enumerateWeakReferences`  
 [en] Un valor booleano que indica si también se van a enumerar las referencias débiles. Si `enumerateWeakReferences` `true`es `ppEnum` , el enumerador incluye referencias seguras y referencias débiles. Si `enumerateWeakReferences` `false`es , el enumerador solo incluye referencias seguras.  
  
 `ppEnum`  
 [fuera] Puntero a la dirección de un [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) que es un enumerador para los objetos que se van a recopilar como elementos no utilizados.  
  
## <a name="remarks"></a>Observaciones  
 Este método proporciona una manera de determinar la cadena de enraizamiento completa para cualquier objeto administrado en un proceso y se puede usar para determinar por qué un objeto sigue vivo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugProcess5 (Interfaz)](icordebugprocess5-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
