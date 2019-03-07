---
title: ICorDebugVariableSymbol::SetValue (método)
ms.date: 03/30/2017
ms.assetid: 4609418d-71fa-44bc-9618-4d529d25cabb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b83efca5a8b175d5dc83c03de473262ca033354c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491313"
---
# <a name="icordebugvariablesymbolsetvalue-method"></a>ICorDebugVariableSymbol::SetValue (método)
Asigna el valor de una matriz de bytes a una variable.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
>  Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorDebugVariableSymbol (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
