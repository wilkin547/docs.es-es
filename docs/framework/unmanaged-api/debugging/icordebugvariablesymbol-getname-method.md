---
title: ICorDebugVariableSymbol::GetName (método)
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
ms.openlocfilehash: ea414a39e140c74df736764dbbb1bb3934bda78f
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397129"
---
# <a name="icordebugvariablesymbolgetname-method"></a>ICorDebugVariableSymbol::GetName (método)
Obtiene el nombre de una variable.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `cchName`  
 [in] Número de caracteres del búfer `szName`.  
  
 `pcchName`  
 [out] Puntero al número de caracteres escritos realmente en el búfer `szName`.  
  
 `szName`  
 Puntero a una matriz de caracteres que contiene el nombre de la variable.  
  
## <a name="remarks"></a>Comentarios  
  
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
