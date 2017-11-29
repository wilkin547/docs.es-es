---
title: ICorDebugFrame Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame
helpviewer_keywords: ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2acc825f6592eae80f67e7614ca45f175b6756d8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframe-interface1"></a>ICorDebugFrame Interfaz1
Representa un marco en la pila actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateStepper (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|Obtiene un ICorDebugStepper para realizar operaciones de ejecución paso a paso en relación con este `ICorDebugFrame`.|  
|[GetCallee (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|Obtiene un puntero a la `ICorDebugFrame` en la cadena actual que llama a este marco, o devuelve null si este es el marco más interno de la cadena.|  
|[GetCaller (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|Obtiene un puntero a la `ICorDebugFrame` en la cadena actual que llama a este marco, o devuelve null si este es el marco más externo de la cadena.|  
|[GetChain (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|Obtiene un puntero a la instancia de ICorDebugChain este `ICorDebugFrame` forma parte de.|  
|[GetCode (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|Obtiene un puntero a la ICorDebugCode asociada a este marco de pila.|  
|[GetFunction (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|Obtiene un puntero a la instancia de ICorDebugFunction que contiene el código asociado con este marco de pila.|  
|[GetFunctionToken (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|Obtiene el token de metadatos para la función que contiene el código asociado con este marco de pila.|  
|[GetStackRange (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|Obtiene el intervalo de direcciones absolutas del marco de pila representado por este `ICorDebugFrame`.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
