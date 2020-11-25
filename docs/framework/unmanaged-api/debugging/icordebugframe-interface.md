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
ms.openlocfilehash: bdc17e2c6c63deae1420fe738eac51153f6b368e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726345"
---
# <a name="icordebugframe-interface"></a>Interfaz ICorDebugFrame

Representa un marco en la pila actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateStepper (Método)](icordebugframe-createstepper-method.md)|Obtiene un ICorDebugStepper para realizar operaciones de ejecución paso a paso con respecto a este `ICorDebugFrame` .|  
|[Método GetCallee](icordebugframe-getcallee-method.md)|Obtiene un puntero al `ICorDebugFrame` en la cadena actual a la que este marco llamó, o devuelve NULL si se trata del marco más interno de la cadena.|  
|[Método GetCaller](icordebugframe-getcaller-method.md)|Obtiene un puntero al `ICorDebugFrame` en la cadena actual que llamó a este marco, o devuelve NULL si se trata del marco más externo de la cadena.|  
|[Método GetChain](icordebugframe-getchain-method.md)|Obtiene un puntero al `ICorDebugFrame` elemento ICorDebugChain del que forma parte.|  
|[Método GetCode](icordebugframe-getcode-method.md)|Obtiene un puntero a la clase ICorDebugCode asociada a este marco de pila.|  
|[Método GetFunction](icordebugframe-getfunction-method.md)|Obtiene un puntero a la clase ICorDebugFunction que contiene el código asociado a este marco de pila.|  
|[Método GetFunctionToken](icordebugframe-getfunctiontoken-method.md)|Obtiene el símbolo (token) de metadatos para la función que contiene el código asociado a este marco de pila.|  
|[GetStackRange (Método)](icordebugframe-getstackrange-method.md)|Obtiene el intervalo de direcciones absolutas del marco de pila representado por este `ICorDebugFrame` .|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
