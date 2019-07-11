---
title: ICorDebugStepper::StepOut (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepOut
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36a33b74a692761d772a888ce918aa28a2d92678
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760554"
---
# <a name="icordebugstepperstepout-method"></a>ICorDebugStepper::StepOut (Método)
Hace que este ICorDebugStepper paso a paso a través del subproceso que la contiene y que finalice cuando el marco actual devuelve el control al marco que realiza la llamada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a>Comentarios  
 Un `StepOut` operación se completará después de devolverse con normalidad desde el fotograma actual en el marco que realiza la llamada.  
  
 Si `StepOut` se llama cuando en código no administrado, el paso finalizará cuando el marco actual se devuelve al código administrado que lo llamó.  
  
 En la versión 2.0 de .NET Framework, no utilice `StepOut` con el STOP_UNMANAGED marca conjunto porque se producirá un error. (Use [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) establecer marcas para la ejecución paso a paso.) Los depuradores de interoperabilidad deben salir del código nativo a sí mismos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
