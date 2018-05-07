---
title: ICorDebugCode Interfaz1
ms.date: 03/30/2017
api_name:
- ICorDebugCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode
helpviewer_keywords:
- ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37917577c802514fcebc3ea0792cbce9bb8a7345
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugcode-interface1"></a>ICorDebugCode Interfaz1
Representa un segmento de código de lenguaje intermedio de Microsoft (MSIL) o código nativo.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateBreakpoint (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|Crea un punto de interrupción en el desplazamiento especificado.|  
|[GetAddress (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|Obtiene la dirección virtual relativa (RVA) del segmento de código que representa `ICorDebugCode`.|  
|[GetCode (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|Obtiene todo el código para la función especificada, con formato de desensamblado. Este método está desusado; usar [ICorDebugCode2:: GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) en su lugar.|  
|[GetEnCRemapSequencePoints (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|Sin implementar.|  
|[GetFunction (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|Obtiene la "ICorDebugFunction" asociada a esta `ICorDebugCode`.|  
|[GetILToNativeMapping (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|Obtiene una matriz de instancias de "COR_DEBUG_IL_TO_NATIVE_MAP" que representan asignaciones de desplazamientos de MSIL a desplazamientos nativos.|  
|[GetSize (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|Obtiene el tamaño, en bytes, del código binario representado por esta instancia de `ICorDebugCode`.|  
|[GetVersionNumber (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|Obtiene el número basado en uno que identifica la versión del código que representa esta instancia de `ICorDebugCode`.|  
|[IsIL (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|Obtiene un valor que indica si esta instancia de `ICorDebugCode` está compilada en MSIL.|  
  
## <a name="remarks"></a>Comentarios  
 `ICorDebugCode` puede representar MSIL o código nativo. Un objeto de "ICorDebugFunction" que representa código MSIL puede tener cero o uno `ICorDebugCode` objetos asociados con él. Un objeto de "ICorDebugFunction" que representa código nativo puede tener cualquier número de `ICorDebugCode` objetos asociados con él.  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
    
 [ICorDebugCode3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
