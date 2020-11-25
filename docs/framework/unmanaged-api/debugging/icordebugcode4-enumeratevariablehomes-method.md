---
title: 'Interfaces icordebugcode4:: EnumerateVariableHomes (método)'
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
ms.openlocfilehash: 6d58efa5629bb02158a275dec61c0313bca821a1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720767"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a>Interfaces icordebugcode4:: EnumerateVariableHomes (método)

Obtiene un enumerador para las variables locales y los argumentos de una función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppEnum`  
 Puntero a la dirección de un objeto de interfaz [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) que es un enumerador para las variables locales y los argumentos de una función.  
  
## <a name="remarks"></a>Comentarios  

 El objeto de interfaz [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) es un enumerador estándar derivado de la interfaz "ICorDebugEnum" que le permite enumerar objetos [ICorDebugVariableHome](icordebugvariablehome-interface.md) . La colección puede incluir varios objetos [ICorDebugVariableHome](icordebugvariablehome-interface.md) para la misma ranura o índice de argumento si tienen casas diferentes en distintos puntos de la función.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugCode4](icordebugcode4-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
