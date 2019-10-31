---
title: 'ICorDebugVariableSymbol:: Getslotindex ((método)'
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: a7a7ecf7d3e3d0d2125b03d3604c44138a2be0cc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120973"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a>ICorDebugVariableSymbol:: Getslotindex ((método)
Obtiene el índice de ranura administrado de una variable local.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pSlotIndex`  
 [out] Puntero al índice de ranura de la variable local.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` si se realiza correctamente. `E_FAIL` si la variable es un argumento de función.  
  
## <a name="remarks"></a>Comentarios  
 El índice de ranura administrado de una variable local puede utilizarse para recuperar información de metadatos de la variable  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugVariableSymbol (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
