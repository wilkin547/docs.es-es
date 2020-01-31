---
title: Interfaz ICorDebugFrame
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
ms.openlocfilehash: ba138e79e0d6fb6f9c5e9c3efe3466f3c88cccae
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782618"
---
# <a name="icordebugframe-interface"></a>Interfaz ICorDebugFrame

Representa un marco en la pila actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateStepper (método)](icordebugframe-createstepper-method.md)|Obtiene un ICorDebugStepper para realizar operaciones de ejecución paso a paso con respecto a este `ICorDebugFrame`.|  
|[GetCallee (método)](icordebugframe-getcallee-method.md)|Obtiene un puntero al `ICorDebugFrame` en la cadena actual a la que este marco llamó, o devuelve NULL si se trata del marco más interno de la cadena.|  
|[GetCaller (método)](icordebugframe-getcaller-method.md)|Obtiene un puntero al `ICorDebugFrame` en la cadena actual que llamó a este marco, o devuelve NULL si se trata del marco más externo de la cadena.|  
|[GetChain (método)](icordebugframe-getchain-method.md)|Obtiene un puntero al elemento ICorDebugChain del que forma parte este `ICorDebugFrame`.|  
|[GetCode (método)](icordebugframe-getcode-method.md)|Obtiene un puntero a la clase ICorDebugCode asociada a este marco de pila.|  
|[GetFunction (método)](icordebugframe-getfunction-method.md)|Obtiene un puntero a la clase ICorDebugFunction que contiene el código asociado a este marco de pila.|  
|[GetFunctionToken (método)](icordebugframe-getfunctiontoken-method.md)|Obtiene el símbolo (token) de metadatos para la función que contiene el código asociado a este marco de pila.|  
|[GetStackRange (método)](icordebugframe-getstackrange-method.md)|Obtiene el intervalo de direcciones absolutas del marco de pila representado por este `ICorDebugFrame`.|  
  
## <a name="remarks"></a>Notas  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
