---
title: Interfaz ICorDebugCode
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
ms.openlocfilehash: 4b24b3dfe6a931866acd7eba966811071ff39ea5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788924"
---
# <a name="icordebugcode-interface"></a>Interfaz ICorDebugCode

Representa un segmento de código de lenguaje intermedio de Microsoft (MSIL) o código nativo.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateBreakpoint (método)](icordebugcode-createbreakpoint-method.md)|Crea un punto de interrupción en el desplazamiento especificado.|  
|[GetAddress (método)](icordebugcode-getaddress-method.md)|Obtiene la dirección virtual relativa (RVA) del segmento de código que representa `ICorDebugCode`.|  
|[GetCode (método)](icordebugcode-getcode-method.md)|Obtiene todo el código para la función especificada, con formato de desensamblado. Este método está en desuso; Use [ICorDebugCode2:: getcodechunks (](icordebugcode2-getcodechunks-method.md) en su lugar.|  
|[GetEnCRemapSequencePoints (método)](icordebugcode-getencremapsequencepoints-method.md)|Sin implementar.|  
|[GetFunction (método)](icordebugcode-getfunction-method.md)|Obtiene la "ICorDebugFunction" asociada a este `ICorDebugCode`.|  
|[GetILToNativeMapping (método)](icordebugcode-getiltonativemapping-method.md)|Obtiene una matriz de instancias "COR_DEBUG_IL_TO_NATIVE_MAP" que representan asignaciones de desplazamientos MSIL a desplazamientos nativos.|  
|[GetSize (método)](icordebugcode-getsize-method.md)|Obtiene el tamaño, en bytes, del código binario representado por esta instancia de `ICorDebugCode`.|  
|[GetVersionNumber (método)](icordebugcode-getversionnumber-method.md)|Obtiene el número basado en uno que identifica la versión del código que representa esta instancia de `ICorDebugCode`.|  
|[IsIL (método)](icordebugcode-isil-method.md)|Obtiene un valor que indica si esta instancia de `ICorDebugCode` está compilada en MSIL.|  
  
## <a name="remarks"></a>Notas  
 `ICorDebugCode` puede representar MSIL o código nativo. Un objeto "ICorDebugFunction" que representa el código MSIL puede tener cero o uno `ICorDebugCode` objetos asociados a él. Un objeto "ICorDebugFunction" que representa el código nativo puede tener cualquier número de objetos `ICorDebugCode` asociados a él.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugCode3 (interfaz)](icordebugcode3-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
