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
ms.openlocfilehash: 5fa042223e47961dad0a6799ab8ca999ef76e285
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791091"
---
# <a name="icordebugvalue3-interface"></a>ICorDebugValue3 (Interfaz)
Extiende las interfaces "ICorDebugValue" y "ICorDebugValue2" para proporcionar compatibilidad con matrices mayores de 2 GB.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetSize64 (método)](icordebugvalue3-getsize64-method.md)|Obtiene el tamaño, en bytes, de este objeto `ICorDebugValue3`.|  
  
## <a name="remarks"></a>Notas  
 El método [ICorDebugValue::FUL](icordebugvalue3-getsize64-method.md) devuelve un tamaño de objeto comprendido entre 0 y 2.147.483.647 bytes. En el .NET Framework 4,5, el tamaño de las matrices puede superar los 2 GB. La interfaz de `ICorDebugValue3` permite determinar el tamaño de estas matrices.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
- [Depuración](index.md)
