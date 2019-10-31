---
title: ICorDebugEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum
helpviewer_keywords:
- ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 80be7efe-2c32-4b9f-8c52-40c6f6268219
topic_type:
- apiref
ms.openlocfilehash: 59dcb7ae6f27f8d049cd4dc2d313f7f1130fc503
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085257"
---
# <a name="icordebugenum-interface"></a>ICorDebugEnum (Interfaz)

Actúa como la interfaz base abstracta para los enumeradores que se usan en una aplicación de depuración.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Clone (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|Crea una copia de este objeto `ICorDebugEnum`.|  
|[GetCount (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|Obtiene el número de elementos de la enumeración.|  
|[Reset (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|Mueve el cursor al principio de la enumeración.|  
|[Skip (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|Mueve el cursor hacia delante en la enumeración el número de elementos especificado.|  
  
## <a name="remarks"></a>Comentarios  
 Los enumeradores siguientes derivan de `ICorDebugEnum`:  
  
- ICorDebugAppDomainEnum (  
  
- ICorDebugAssemblyEnum  
  
- [ICorDebugBlockingObjectEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
- ICorDebugBreakpointEnum (  
  
- ICorDebugChainEnum (  
  
- ICorDebugCodeEnum (  
  
- Icordebugerrorinfoenum (  
  
- [Icordebugexceptionobjectcallstackenum (](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
- ICorDebugFrameEnum (  
  
- [Icordebuggcreferenceenum (](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
- [Icordebugguidtotypeenum (](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
- [Icordebugheapenum (](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
- [Icordebugheapsegmentenum (](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
- ICorDebugModuleEnum (  
  
- ICorDebugObjectEnum (  
  
- Icordebugprocessenum (  
  
- ICorDebugStepperEnum (  
  
- ICorDebugThreadEnum (  
  
- ICorDebugTypeEnum  
  
- ICorDebugValueEnum  
  
- [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
