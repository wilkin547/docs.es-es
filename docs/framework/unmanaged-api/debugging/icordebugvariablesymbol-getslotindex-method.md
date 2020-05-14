---
title: ICorDebugVariableSymbol::GetSlotIndex (método)
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: 251a978e96ff396d0d9d9282ded7f8a25ae0ba0b
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397092"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a>ICorDebugVariableSymbol::GetSlotIndex (método)
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
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaz ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
