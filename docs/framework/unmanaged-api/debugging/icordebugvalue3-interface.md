---
title: ICorDebugValue3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3
helpviewer_keywords:
- ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type:
- apiref
ms.openlocfilehash: 1f46866a1b975455acd294221e38ef3b4c358660
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140210"
---
# <a name="icordebugvalue3-interface"></a>ICorDebugValue3 (Interfaz)
Extiende las interfaces "ICorDebugValue" y "ICorDebugValue2" para proporcionar compatibilidad con matrices mayores de 2 GB.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetSize64 (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|Obtiene el tamaño, en bytes, de este objeto `ICorDebugValue3`.|  
  
## <a name="remarks"></a>Comentarios  
 El método [ICorDebugValue::FUL](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) devuelve un tamaño de objeto comprendido entre 0 y 2.147.483.647 bytes. En el .NET Framework 4,5, el tamaño de las matrices puede superar los 2 GB. La interfaz de `ICorDebugValue3` permite determinar el tamaño de estas matrices.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
