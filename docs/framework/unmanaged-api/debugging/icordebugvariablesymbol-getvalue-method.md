---
title: ICorDebugVariableSymbol::GetValue (método)
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c626d21f391899a15e5ea35c47d00f1f539fea4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488869"
---
# <a name="icordebugvariablesymbolgetvalue-method"></a>ICorDebugVariableSymbol::GetValue (método)
Obtiene el valor de una variable como una matriz de bytes.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
>  Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorDebugVariableSymbol (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
