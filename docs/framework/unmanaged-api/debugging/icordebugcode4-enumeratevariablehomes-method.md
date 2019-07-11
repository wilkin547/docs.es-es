---
title: Método ICorDebugCode4::EnumerateVariableHomes
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0e6acdf6996f437c85b629b0af886287b1aef03
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748560"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a>Método ICorDebugCode4::EnumerateVariableHomes
Obtiene un enumerador para los argumentos y variables locales en una función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppEnum`  
 Un puntero a la dirección de un [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) objeto de interfaz que es un enumerador para los argumentos en una función y las variables locales.  
  
## <a name="remarks"></a>Comentarios  
 El [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) objeto de interfaz es un enumerador estándar que se deriva de la interfaz "ICorDebugEnum" que permite enumerar [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objetos. La colección puede incluir varios [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) de objetos para el mismo índice de ranura o argumento si tienen las casas diferentes en distintos puntos de la función.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugCode4 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
