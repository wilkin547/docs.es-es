---
title: 'ICorDebugVariableSymbol:: SetValue (método)'
ms.date: 03/30/2017
ms.assetid: 4609418d-71fa-44bc-9618-4d529d25cabb
ms.openlocfilehash: fbd3d617e3448730241ccfda7bd26b65d17b694d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121889"
---
# <a name="icordebugvariablesymbolsetvalue-method"></a>ICorDebugVariableSymbol:: SetValue (método)
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
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugVariableSymbol (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
