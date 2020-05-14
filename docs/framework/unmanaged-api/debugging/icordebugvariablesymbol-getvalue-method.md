---
title: ICorDebugVariableSymbol::GetValue (método)
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
ms.openlocfilehash: f217f7226d53a27363f66eb90a340fd3604a0217
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396518"
---
# <a name="icordebugvariablesymbolgetvalue-method"></a>ICorDebugVariableSymbol::GetValue (método)
Obtiene el valor de una variable como una matriz de bytes.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetValue(  
   [in] ULONG32 offset,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [out] ULONG32 *pcbValue,  
   [out, size_is(cbValue), length_is(*pcbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `offset`  
 [in] Desplazamiento inicial de la variable de la que se va a leer el valor. Este parámetro se utiliza cuando se leen campos de miembro de un objeto.  
  
 `cbContext`  
 [in] Tamaño del argumento `context` en bytes.  
  
 `context`  
 [in] Contexto del subproceso utilizado para leer el valor.  
  
 `cbValue`  
 [in] Tamaño del búfer `pValue` en bytes.  
  
 `pcbValue`  
 [out] Número de bytes escritos realmente en el búfer `pValue`.  
  
 `pValue`  
 [out] Matriz de bytes que contiene el valor de la variable.  
  
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
