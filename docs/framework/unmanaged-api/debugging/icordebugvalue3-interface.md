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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 300d2263c076c9028340863e2f7a3fa27a36ef9d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993738"
---
# <a name="icordebugvalue3-interface"></a>ICorDebugValue3 (Interfaz)
Extiende las interfaces "ICorDebugValue" y "ICorDebugValue2" para proporcionar compatibilidad para matrices que son superiores a 2 GB.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetSize64 (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|Obtiene el tamaño, en bytes, de este `ICorDebugValue3` objeto.|  
  
## <a name="remarks"></a>Comentarios  
 El [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) método devuelve un tamaño de objeto que va de 0 a 2.147.483.647 bytes. En el [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], el tamaño de matrices puede superar los 2 GB. El `ICorDebugValue3` interfaz le permite determinar el tamaño de estas matrices.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
