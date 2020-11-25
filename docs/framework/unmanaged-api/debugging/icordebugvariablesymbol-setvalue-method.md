---
title: ICorDebugVariableSymbol::SetValue (método)
ms.date: 03/30/2017
ms.assetid: 4609418d-71fa-44bc-9618-4d529d25cabb
ms.openlocfilehash: 3ef9b9b9a095d6d6026ffc38873661355d660488
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707846"
---
# <a name="icordebugvariablesymbolsetvalue-method"></a>ICorDebugVariableSymbol::SetValue (método)

Asigna el valor de una matriz de bytes a una variable.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetValue(  
   [in] ULONG32 offset,  
   [in] DWORD threadID,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [in, size_is(cbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `offset`  
 [in] Desplazamiento inicial de la variable en la que se va a establecer el valor. Este parámetro se utiliza cuando se escribe en campos de miembro de un objeto.  
  
 `threadID`  
 [in] Identificador de subproceso del subproceso cuyo contexto debe actualizarse para reflejar el nuevo valor.  
  
 `cbContext`  
 [in] Tamaño en bytes del contexto del subproceso.  
  
 `context`  
 [in] Contexto del subproceso utilizado para escribir el valor.  
  
 `cbValue`  
 [in] Tamaño del búfer `pValue` en bytes.  
  
 `pValue`  
 [in] Búfer que contiene el valor que se va a establecer.  
  
## <a name="remarks"></a>Comentarios  
  
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
