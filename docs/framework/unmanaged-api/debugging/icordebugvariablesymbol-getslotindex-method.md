---
title: ICorDebugVariableSymbol::GetSlotIndex (método)
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: fc42517cb95dfc14c472b5bb9111ebd70639cee7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725994"
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
  
## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
