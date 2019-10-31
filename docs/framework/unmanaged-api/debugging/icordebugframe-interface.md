---
title: ICorDebugFrame (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame
helpviewer_keywords:
- ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type:
- apiref
ms.openlocfilehash: 5aeea11b7e61869968aafe3425e27d6004f495ea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124074"
---
# <a name="icordebugframe-interface"></a>ICorDebugFrame (Interfaz)

Representa un marco en la pila actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateStepper (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|Obtiene un ICorDebugStepper para realizar operaciones de ejecución paso a paso con respecto a este `ICorDebugFrame`.|  
|[GetCallee (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|Obtiene un puntero al `ICorDebugFrame` en la cadena actual a la que este marco llamó, o devuelve NULL si se trata del marco más interno de la cadena.|  
|[GetCaller (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|Obtiene un puntero al `ICorDebugFrame` en la cadena actual que llamó a este marco, o devuelve NULL si se trata del marco más externo de la cadena.|  
|[GetChain (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|Obtiene un puntero al elemento ICorDebugChain del que forma parte este `ICorDebugFrame`.|  
|[GetCode (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|Obtiene un puntero a la clase ICorDebugCode asociada a este marco de pila.|  
|[GetFunction (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|Obtiene un puntero a la clase ICorDebugFunction que contiene el código asociado a este marco de pila.|  
|[GetFunctionToken (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|Obtiene el símbolo (token) de metadatos para la función que contiene el código asociado a este marco de pila.|  
|[GetStackRange (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|Obtiene el intervalo de direcciones absolutas del marco de pila representado por este `ICorDebugFrame`.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
